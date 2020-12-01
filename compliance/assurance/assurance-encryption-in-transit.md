---
title: 送信中のデータの暗号化
description: この記事では、microsoft 365 のお客様データを送信中にどのように暗号化するかについて、簡単な説明を記載しています。
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
- MS-Compliance
ms.custom: seo-marvel-apr2020
titleSuffix: Microsoft Service Assurance
ms.openlocfilehash: d1587e4bc315f99dc554158500638645606fbcec
ms.sourcegitcommit: 626b0076d133e588cd28598c149a7f272fc18bae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2020
ms.locfileid: "49507876"
---
# <a name="encryption-for-data-in-transit"></a>送信中のデータの暗号化

保存中の顧客データの保護に加え、Microsoft では暗号化技術を使用してお客様の送信中の顧客データを保護します。 データの送信中:

- クライアントコンピューターが Microsoft サーバーと通信するとき。
- Microsoft サーバーが他の Microsoft サーバーと通信する場合そして
- Microsoft サーバーが Microsoft 以外のサーバーと通信する場合 (たとえば、Exchange Online が電子メールをサードパーティの電子メールサーバーに配信する場合)。

Microsoft サーバー間のデータセンター間の通信は TLS または IPsec 経由で行われ、お客様向けのすべてのサーバーは tls を使用してクライアントマシンとのセキュリティで保護されたセッションをネゴシエートします (たとえば、Exchange Online は TLS 1.2 を256ビットの暗号強度で使用しています (FIPS 140-2 レベル 2-検証)。 (Office 365 でサポートされている TLS 暗号スイートの一覧については、 [暗号化に関する技術リファレンスの詳細](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption) を参照してください)。これは、Outlook、Skype for Business、Microsoft Teams、web 上の Outlook などのクライアントによって使用されるプロトコル (たとえば、HTTP、POP3 など) に適用されます。

公開証明書は、microsoft IT SSL によって発行された microsoft IT SSL で、送信された情報の機密性を保護するための内部 Microsoft ツールです。 Microsoft によって発行されるすべての証明書の長さは2048ビットです。また、Webtrust コンプライアンスでは、証明書が Microsoft によって所有されるパブリック IP アドレスにのみ発行されるようにするために、SSLAdmin が必要になります。 この条件を満たすことができない IP アドレスは、例外プロセスを経由してルーティングされます。

使用されている TLS のバージョン、転送機密性 (FS) が有効になっているかどうか、暗号スイートの順番など、すべての実装の詳細を公開できます。 これらの詳細を確認する1つの方法は、 [QUALYS SSL Labs](https://www.ssllabs.com)などのサードパーティの web サイトを使用することです。 次のサービスの情報を表示する Qualys からの自動テストページへのリンクを以下に示します。

- [Office 365 ポータル](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [Exchange Online](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [SharePoint Online](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [Skype for Business (SIP)](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [Skype for Business (Web)](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [Exchange Online Protection](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [Microsoft Teams](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

Exchange Online Protection の場合、Url はテナント名によって異なります。ただし、すべてのお客様は **microsoft-com.mail.protection.outlook.com** を使用して Microsoft 365 をテストできます。
