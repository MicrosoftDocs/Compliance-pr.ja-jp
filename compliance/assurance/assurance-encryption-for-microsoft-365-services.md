---
title: Skype、OneDrive、SharePoint、および Exchange の暗号化
description: '概要: Skype、OneDrive、SharePoint、Microsoft Teams、および Exchange Online の暗号化について説明します。'
ms.author: krowley
author: kccross
manager: laurawi
ms.reviewer: sosstah
f1.keywords:
- NOCSH
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
- SPO_Content
- MS-Compliance
titleSuffix: Microsoft Service Assurance
ms.openlocfilehash: 8f76a8a7c8b9d579128dffab67a8a2aedf26fc20
ms.sourcegitcommit: 626b0076d133e588cd28598c149a7f272fc18bae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2020
ms.locfileid: "49508206"
---
# <a name="encryption-for-skype-for-business-onedrive-for-business-sharepoint-online-microsoft-teams-and-exchange-online"></a>Skype for business、OneDrive for Business、SharePoint Online、Microsoft Teams、Exchange Online の暗号化

Microsoft 365 は、高度なセキュリティで保護された環境で、物理データセンターのセキュリティ、ネットワークセキュリティ、アクセスセキュリティ、アプリケーションセキュリティ、およびデータセキュリティがあります。

## <a name="skype-for-business"></a>Skype for Business

Skype for Business の顧客データは、会議の参加者によってアップロードされたファイルやプレゼンテーションの形式で保存されている場合があります。 Web 会議サーバーは、256ビットキーを使用して AES を使用して顧客データを暗号化します。 暗号化された顧客データは、ファイル共有に保存されます。 顧客データの各要素は、ランダムに生成された異なる256ビットキーを使用して暗号化されます。 会議で顧客データの一部が共有されている場合、Web 会議サーバーは、HTTPS を介して暗号化された顧客データをダウンロードするよう、会議クライアントに指示します。 対応するキーをクライアントに送信して、顧客データを復号化できるようにします。 Web 会議サーバーは、クライアントが会議の顧客データにアクセスできるようにするために、会議クライアントも認証します。 Web 会議に参加する場合、各会議クライアントは、最初に TLS を介してフロントエンドサーバーの内部で実行されている会議フォーカスコンポーネントを使用して SIP ダイアログを確立します。 会議フォーカスは、Web 会議サーバーによって生成された認証 cookie を会議クライアントに渡します。 その後、会議クライアントは Web 会議サーバーに接続して、サーバーによって認証される認証 cookie を提示します。

## <a name="sharepoint-online-and-onedrive-for-business"></a>SharePoint Online と OneDrive for Business

SharePoint Online のすべての顧客ファイルは、1つのテナントに対して常に排他的な一意のファイルごとのキーによって保護されています。 これらのキーは、SharePoint Online サービスによって作成され、管理されるか、顧客キーが使用されるときに、顧客によって作成および管理されます。 ファイルをアップロードすると、アップロード要求のコンテキスト内で SharePoint Online によって暗号化が実行されてから、Azure ストレージに送信されます。 ファイルがダウンロードされると、SharePoint Online は一意のドキュメント識別子に基づいて Azure ストレージから暗号化された顧客データを取得し、顧客データを復号化してからユーザーに送信します。 Azure ストレージには、お客様のデータを復号化したり、識別したり、理解したりする機能はありません。 すべての暗号化と復号化は、テナントの分離を強制するのと同じシステムで行われます。これは、Azure Active Directory と SharePoint Online です。

Microsoft 365 のいくつかのワークロード sharepoint online のデータを格納します。 Microsoft Teams は、sharepoint online のすべてのファイルを格納し、OneDrive for Business を使用します。これにより、sharepoint online でそのストレージを使用します。 SharePoint Online に格納されているすべての顧客データは、(1 つ以上の AES 256 ビットキーを使用して) 暗号化され、次のようにデータセンター全体に分散されます。 (この暗号化プロセスのすべての手順は、FIPS 140-2 レベル2で検証されています。 FIPS 140-2 準拠の詳細については、「 [fips 140-2 コンプライアンス](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb326611(v=sql.105))」を参照してください)。

- 各ファイルは、ファイルサイズに応じて、1つまたは複数のチャンクに分割されます。 各チャンクは、固有の AES 256 ビットキーを使用して暗号化されます。
- ファイルが更新されると、その更新は同じ方法で処理されます。変更は1つ以上のチャンクに分割され、各チャンクは個別の一意のキーを使用して暗号化されます。
- これらのチャンク–ファイル、ファイル、および更新デルタは、複数の Azure ストレージアカウント間でランダムに分散される Azure ストレージの blob として格納されます。
- このような顧客データのチャンクの暗号化キーのセットは、それ自体が暗号化されます。

    - Blob の暗号化に使用されるキーは、SharePoint Online コンテンツデータベースに格納されます。
    - コンテンツデータベースは、データベースのアクセス制御と、保存時の暗号化によって保護されています。 暗号化は、 [AZURE SQL Database](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview)で[透過的データ暗号化](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption-tde)(tde) を使用して実行されます。 (Azure SQL Database は、リレーショナルデータ、JSON、空間的、XML などの構造をサポートする Microsoft Azure の汎用リレーショナルデータベースサービスです)。これらの機密情報は、テナントレベルではなく、SharePoint Online のサービスレベルで行われます。 これらの機密情報 (マスターキーと呼ばれることもあります) は、キーストアと呼ばれる別の安全なリポジトリに格納されます。 TDE は、アクティブデータベースとデータベースのバックアップとトランザクションログの両方に対して、セキュリティで保護を提供します。
    - 顧客がオプションのキーを指定すると、顧客キーが Azure Key Vault に格納され、サービスはキーを使用してテナントキーを暗号化します。これは、サイトキーを暗号化するために使用されます。これは、ファイルレベルのキーを暗号化するために使用されます。 基本的に、顧客がキーを提供すると、新しいキー階層が導入されます。
- ファイルを再アセンブルするために使用されるマップは、暗号化されたキーと共にコンテンツデータベースに格納されます。これは、それらを復号化するために必要なマスターキーとは別に格納されます。
- 各 Azure storage アカウントには、アクセスの種類 (読み取り、書き込み、列挙、および削除) ごとに固有の資格情報があります。 各資格情報セットはセキュリティが確保されたキー ストアで保管され、定期的に更新されます。 前述したように、それぞれ異なる関数を持つ3種類のストアがあります。
    - お客様のデータは、Azure ストレージに暗号化された blob として格納されます。 顧客データの各チャンクのキーは暗号化され、コンテンツデータベースに格納されます。 お客様のデータ自体には、復号化の方法についての手掛かりはありません。
    - コンテンツデータベースは SQL Server データベースです。 Azure ストレージに格納されている顧客データ blob と、それらの blob を暗号化するために必要なキーを検索して再構築するために必要なマップを保持します。 ただし、キーのセットは (前述のように) 暗号化され、別のキーストアに保持されます。
    - キーストアは、コンテンツデータベースと Azure ストレージとは物理的に分離されています。 各 Azure storage コンテナーの資格情報と、コンテンツデータベースに保持されている暗号化キーのセットに対するマスタキーを保持します。

これら3つの各ストレージコンポーネント (Azure blob ストア、コンテンツデータベース、およびキーストア) は物理的に分離されています。 いずれかのコンポーネントに保管されている情報は、それ自体では使用できません。 3つのすべてにアクセスできない場合は、チャンクへのキーを取得し、それらを使用できるようにするためにキーを復号化し、対応するチャンクにキーを関連付け、各チャンクを復号化するか、またはドキュメントを構成するチャンクから再構築することはできません。

データセンター内のコンピューター上の物理ディスクボリュームを保護する BitLocker 証明書は、ファームキーで保護された安全なリポジトリ (SharePoint Online シークレットストア) に格納されます。

Blob キーごとのキーを保護する TDE キーは、次の2つの場所に格納されます。

- 保護されたリポジトリ。これは、BitLocker 証明書を格納し、ファームキーによって保護されています。そして
- Azure SQL データベースによって管理される、セキュリティで保護されたリポジトリ。

Azure ストレージコンテナーへのアクセスに使用される資格情報は、必要に応じて SharePoint Online シークレットストアに保持され、各 SharePoint Online ファームに委任されます。 これらの資格情報は、データの読み取りまたは書き込みに使用される個別の資格情報と、60日ごとに自動的に有効期限切れになるように、ポリシーが適用された、Azure ストレージの SAS 署名です。 データの読み取りまたは書き込みに異なる資格情報が使用されます (両方ではない)。また、SharePoint Online ファームには、列挙するためのアクセス許可が与えられていません。

> [!NOTE]
> Office 365 米国政府機関のお客様の場合、データ blob は米国政府機関のストレージに格納されます。 さらに、Office 365 での SharePoint Online キーへのアクセスについては、米国政府機関に365限定されています。 Azure の米国政府運用スタッフには、データ blob の暗号化に使用される SharePoint Online キーストアへのアクセス権がありません。

SharePoint Online と OneDrive for Business のデータ暗号化の詳細については、「 [onedrive for business および Sharepoint Online のデータ暗号化](https://technet.microsoft.com/library/dn905447.aspx)」を参照してください。

### <a name="list-items-in-sharepoint-online"></a>SharePoint Online のリストアイテム

リストアイテムは、ユーザーが作成したリスト内の行、SharePoint Online ブログ内の個々の投稿、SharePoint Online wiki ページ内のエントリなど、一時的に作成された、またはサイト内で動的に維持できる、より小さな顧客データの塊です。 リストアイテムは、コンテンツデータベース (Azure SQL Database) に格納され、TDE で保護されています。

## <a name="encryption-of-data-in-transit"></a>転送中データの暗号化

OneDrive for Business と SharePoint Online では、データを入力してデータセンターを終了する2つのシナリオがあります。

- SharePoint Online とインターネットを介した OneDrive for business との **クライアント通信は、** TLS 接続を使用します。
- **データセンター** 間でのデータの移動-データセンター間でデータを移動する主な理由は、geo レプリケーションを使用して障害復旧を可能にすることです。 たとえば、SQL Server のトランザクションログと blob ストレージのデルタは、このパイプに沿って移動します。 このデータは、プライベートネットワークを使用して既に送信されていますが、クラス最高の暗号化を使用してさらに保護されています。

## <a name="exchange-online"></a>Exchange Online

Exchange Online では、すべてのメールボックスデータに BitLocker を使用し、bitlocker 構成については [暗号化](https://docs.microsoft.com/microsoft-365/compliance/office-365-bitlocker-and-distributed-key-manager-for-encryption)について説明します。 サービスレベルの暗号化は、すべてのメールボックスのデータをメールボックスレベルで暗号化します。 

サービス暗号化に加えて、Microsoft 365 は顧客キーをサポートしています。これは、サービス暗号化の上に構築されています。 顧客キーは、Microsoft のロードマップにもある Exchange Online サービス暗号化の Microsoft が管理するキーオプションです。 この暗号化方法では、サーバー管理者とデータの復号化に必要な暗号化キーが分離されているため、また、暗号化がデータに直接適用されるため (BitLocker の場合は、論理ディスクボリュームで暗号化が適用されるため)、Exchange サーバーからコピーした顧客データは暗号化されたままとなります。

Exchange Online サービス暗号化のスコープは、Exchange Online 内の rest に格納されている顧客データです。 (Skype for Business では、ユーザーによって生成されたすべてのコンテンツがユーザーの Exchange Online メールボックス内に保存されるため、Exchange Online のサービス暗号化機能を継承します。)


## <a name="microsoft-teams"></a>Microsoft Teams

Teams は TLS と MTLS を使用してインスタントメッセージを暗号化します。 すべてのサーバー間トラフィックは、トラフィックが内部ネットワークに限定されているか、または内部ネットワーク境界を越えているかに関係なく、MTLS を必要とします。

次の表は、Teams で使用されるプロトコルの概要を示しています。

|**トラフィックの種類**|**によって暗号化**|
|:-----|:-----|
|サーバー間|MTLS|
|クライアントとサーバー (例 インスタントメッセージングとプレゼンス)|TLS|
|メディアフロー (例) メディアの音声およびビデオ共有)|TLS|
|メディアの音声およびビデオ共有|SRTP/TLS|
|通知|TLS|

#### <a name="media-encryption"></a>メディアの暗号化

メディアトラフィックは、セキュリティで保護された RTP (SRTP) を使用して暗号化されます。 Real-Time トランスポートプロトコル (RTP) のプロファイルは、機密性、認証、および再生攻撃保護を RTP トラフィックに提供します。 SRTP は、セキュリティで保護された乱数ジェネレーターを使用して生成されたセッションキーを使用し、シグナリング TLS チャネルを使用して交換されます。 クライアント間のメディアトラフィックは、クライアントとサーバー間の接続信号を通じてネゴシエートされますが、クライアントからクライアントへの直接アクセス時には SRTP を使用して暗号化されます。

Teams は、資格情報ベースのトークンを使用して、メディアリレーへの安全なアクセスを可能にします。 メディアリレーは、TLS で保護されたチャネルを介してトークンを交換します。

#### <a name="fips"></a>使う

Teams は、暗号化キー交換に FIPS (連邦情報処理規格) 準拠アルゴリズムを使用します。 FIPS の実装の詳細については、「 [連邦情報処理規格 (fips) 文書 140-2](https://docs.microsoft.com/microsoft-365/compliance/offering-fips-140-2)」を参照してください。
