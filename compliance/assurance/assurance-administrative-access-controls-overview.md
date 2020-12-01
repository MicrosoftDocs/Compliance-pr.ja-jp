---
title: Microsoft 365 の管理アクセス制御
description: この記事では、Microsoft 365 の管理アクセス制御とデータ分類の概要について説明します。
ms.author: robmazz
author: robmazz
manager: laurawi
ms.reviewer: sosstah
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
f1.keywords:
- NOCSH
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- MS-Compliance
ms.custom: seo-marvel-apr2020
titleSuffix: Microsoft Service Assurance
ms.openlocfilehash: 6298e027b891edb0729474ea9b6052be2bf6b056
ms.sourcegitcommit: 626b0076d133e588cd28598c149a7f272fc18bae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2020
ms.locfileid: "49508645"
---
# <a name="administrative-access-controls-in-microsoft-365"></a><span data-ttu-id="59d74-103">Microsoft 365 の管理アクセス制御</span><span class="sxs-lookup"><span data-stu-id="59d74-103">Administrative access controls in Microsoft 365</span></span> 

<span data-ttu-id="59d74-104">Microsoft は、microsoft によってお客様のコンテンツへのアクセスを意図的に制限する一方で、Microsoft の365の大部分を自動化するシステムと管理に多大な投資を行っています。</span><span class="sxs-lookup"><span data-stu-id="59d74-104">Microsoft has invested heavily in systems and controls that automate most Microsoft 365 operations while intentionally limiting access to customer content by Microsoft.</span></span> <span data-ttu-id="59d74-105">人間がサービスを制御し、ソフトウェアがサービスを運用します。</span><span class="sxs-lookup"><span data-stu-id="59d74-105">Humans govern the service, and software operates the service.</span></span> <span data-ttu-id="59d74-106">この構造では、microsoft 365 をスケールで管理し、お客様のコンテンツに対する内部の脅威のリスクを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="59d74-106">This structure enables Microsoft to manage Microsoft 365 at scale and manage the risks of internal threats to customer content.</span></span>

<span data-ttu-id="59d74-107">既定では、Microsoft のエンジニアは、Microsoft 365 ではゼロの管理者権限と、お客様のコンテンツへのアクセスがゼロになります。</span><span class="sxs-lookup"><span data-stu-id="59d74-107">By default, Microsoft engineers have zero standing administrative privileges and zero standing access to customer content in Microsoft 365.</span></span> <span data-ttu-id="59d74-108">Microsoft のエンジニアは、限られた期間、お客様のコンテンツへのアクセスを制限、監査、およびセキュリティで保護することができます。</span><span class="sxs-lookup"><span data-stu-id="59d74-108">A Microsoft engineer can have limited, audited, and secured access to a customer's content for a limited amount of time.</span></span> <span data-ttu-id="59d74-109">アクセスは、サービス操作に必要な場合と、Microsoft シニアマネージメントのメンバーによって承認された場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="59d74-109">Access is only when necessary for service operations and only when approved by a member of Microsoft senior management.</span></span> <span data-ttu-id="59d74-110">お客様にライセンスを供与されたお客様のために、お客様は Microsoft 365 でホストされているコンテンツへのアクセスを承認します。</span><span class="sxs-lookup"><span data-stu-id="59d74-110">For Customer Lockbox licensed customers, the customer provides access approval to their content hosted on Microsoft 365.</span></span>

<span data-ttu-id="59d74-111">Microsoft では、複数の形式のクラウド配信を使用したオンラインサービスを提供しています。</span><span class="sxs-lookup"><span data-stu-id="59d74-111">Microsoft provides online services using multiple forms of cloud delivery:</span></span>

- <span data-ttu-id="59d74-112">**パブリッククラウド:** Microsoft 365、Azure、および北アメリカ、南米、ヨーロッパ、アジア、オーストラリアなどでホストされているその他のサービスのマルチテナントバージョンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="59d74-112">**Public clouds:** Includes multi-tenant versions of Microsoft 365, Azure, and other services hosted in North America, South America, Europe, Asia, Australia, etc.</span></span>
- <span data-ttu-id="59d74-113">**国立雲:** 米国外にあるすべての独立およびサードパーティ製の雲 (前述したものを除く) (中国で運用されている 365)、ドイツの microsoft 365 (ドイツのデータを使用している場合はドイツの場合がありますが、ドイツのテレの場合があります) により、顧客データおよびお客様のデータを含むシステムへのアクセス</span><span class="sxs-lookup"><span data-stu-id="59d74-113">**National clouds:** Includes all sovereign and third party-operated clouds outside of the United States (except ones noted previously), such as Microsoft 365 in China (operated by 21Vianet), and Microsoft 365 in Germany (operated by Microsoft, but under a model in which a German data trustee, Deutsche Telekom, controls and monitors Microsoft's access to customer data and systems that contain customer data).</span></span>
- <span data-ttu-id="59d74-114">**行政機関向けクラウド:** 米国政府機関のお客様が利用できる Microsoft 365 および Azure サービスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="59d74-114">**Government clouds:** Includes Microsoft 365 and Azure services that are available to United States government customers.</span></span>

<span data-ttu-id="59d74-115">この記事の目的として、Microsoft 365 サービスには次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="59d74-115">For purposes of this article, Microsoft 365 services include:</span></span>

- [<span data-ttu-id="59d74-116">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="59d74-116">Exchange Online</span></span>](https://docs.microsoft.com/Exchange/exchange-online)
- [<span data-ttu-id="59d74-117">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="59d74-117">Exchange Online Protection</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview)
- [<span data-ttu-id="59d74-118">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="59d74-118">SharePoint Online</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-online)
- [<span data-ttu-id="59d74-119">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="59d74-119">OneDrive for Business</span></span>](https://docs.microsoft.com/OneDrive/onedrive)
- [<span data-ttu-id="59d74-120">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="59d74-120">Skype for Business</span></span>](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online)
- [<span data-ttu-id="59d74-121">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="59d74-121">Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
- [<span data-ttu-id="59d74-122">Yammer</span><span class="sxs-lookup"><span data-stu-id="59d74-122">Yammer</span></span>](https://docs.microsoft.com/yammer/yammer-landing-page)

## <a name="microsoft-365-access-controls"></a><span data-ttu-id="59d74-123">Microsoft 365 のアクセス制御</span><span class="sxs-lookup"><span data-stu-id="59d74-123">Microsoft 365 access controls</span></span>

<span data-ttu-id="59d74-124">アクセス制御を目的として、microsoft は Microsoft 365 データを顧客データまたはその他の種類のデータとして分類しています。</span><span class="sxs-lookup"><span data-stu-id="59d74-124">For access control purposes, Microsoft categorizes Microsoft 365 data as customer data or other types of data.</span></span>

### <a name="customer-data"></a><span data-ttu-id="59d74-125">顧客データ</span><span class="sxs-lookup"><span data-stu-id="59d74-125">Customer data</span></span>

<span data-ttu-id="59d74-126">お客様のデータは、Microsoft 365 サービスを使用している場合に、お客様によって提供されるすべてのデータです。</span><span class="sxs-lookup"><span data-stu-id="59d74-126">Customer data is all data provided by or on behalf of a customer when using Microsoft 365 services.</span></span> <span data-ttu-id="59d74-127">このデータは、Microsoft 365 ユーザーが直接作成またはアップロードした、次のようなお客様向けコンテンツです。</span><span class="sxs-lookup"><span data-stu-id="59d74-127">This data is customer content directly created or uploaded by Microsoft 365 users, including:</span></span>

- <span data-ttu-id="59d74-128">メール</span><span class="sxs-lookup"><span data-stu-id="59d74-128">Emails</span></span>
- <span data-ttu-id="59d74-129">SharePoint Online のコンテンツ</span><span class="sxs-lookup"><span data-stu-id="59d74-129">SharePoint Online content</span></span>
- <span data-ttu-id="59d74-130">インスタント メッセージ</span><span class="sxs-lookup"><span data-stu-id="59d74-130">Instant messages</span></span>
- <span data-ttu-id="59d74-131">予定表アイテム</span><span class="sxs-lookup"><span data-stu-id="59d74-131">Calendar items</span></span>
- <span data-ttu-id="59d74-132">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="59d74-132">Documents</span></span>
- <span data-ttu-id="59d74-133">連絡先</span><span class="sxs-lookup"><span data-stu-id="59d74-133">Contacts</span></span>
- <span data-ttu-id="59d74-134">エンドユーザー識別情報 (EUII) (ユーザーに固有のデータ、または個別のユーザーに linkable されていても、顧客コンテンツは含まれません)</span><span class="sxs-lookup"><span data-stu-id="59d74-134">End-user identifiable information (EUII) (data that is unique to a user or that is linkable to an individual user but does not include customer content)</span></span>

### <a name="other-types-of-data"></a><span data-ttu-id="59d74-135">その他の種類のデータ</span><span class="sxs-lookup"><span data-stu-id="59d74-135">Other types of data</span></span>

<span data-ttu-id="59d74-136">その他の種類のデータは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="59d74-136">Other types of data include:</span></span>

- <span data-ttu-id="59d74-137">**アカウントデータ:** 管理データ (管理者がサインアップまたはサービスを購入するときに提供される情報) と支払いデータ (クレジットカードの詳細などの支払い手段に関する情報) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="59d74-137">**Account data:** Includes administrative data (information provided by administrators when they sign-up or purchase services), and payment data (information about payment instruments, such as credit card details).</span></span>
- <span data-ttu-id="59d74-138">**組織的に識別できる情報:** テナントを識別するために使用されるデータ、使用状況データ、個々のユーザーに linkable していないこと、または顧客コンテンツに含まれているデータを含みます。</span><span class="sxs-lookup"><span data-stu-id="59d74-138">**Organizationally identifiable information:** Includes data used to identify a tenant, usage data, and not linkable to an individual user or included in customer content.</span></span>
- <span data-ttu-id="59d74-139">**システムのメタデータ:** 構成設定、システム状態、Microsoft IP アドレス、およびサブスクリプションとテナントに関する技術情報を含むサービスログが含まれています。</span><span class="sxs-lookup"><span data-stu-id="59d74-139">**System metadata:** Includes service logs that contain configuration settings, system status, Microsoft IP addresses, and technical information about subscriptions and tenants.</span></span>

<span data-ttu-id="59d74-140">Microsoft は、お客様のデータまたはアクセスコントロールのデータへのアクセスが許可されていないことを確認するためのアクセス制御メカニズムを確立しています。</span><span class="sxs-lookup"><span data-stu-id="59d74-140">Microsoft has established access control mechanisms to ensure that no one has unapproved access to Customer Data or access control data.</span></span> <span data-ttu-id="59d74-141">Access control データは、お客様のコンテンツや EUII、Microsoft のパスワード、セキュリティ証明書、およびその他の認証関連データへのアクセスを含む、環境内の他の種類のデータまたは機能へのアクセスを管理します。</span><span class="sxs-lookup"><span data-stu-id="59d74-141">Access control data manages access to other types of data or functions within the environment, including access to customer content or EUII, Microsoft passwords, security certificates, and other authentication-related data.</span></span> <span data-ttu-id="59d74-142">アクセス制御メカニズムは、Microsoft 365 運用環境への許可されていない物理、論理、またはリモートアクセスに対する保護も行います。</span><span class="sxs-lookup"><span data-stu-id="59d74-142">Access control mechanisms also guard against unapproved physical, logical, or remote access to the Microsoft 365 production environment.</span></span>

<span data-ttu-id="59d74-143">Microsoft が microsoft 365 を実行するために使用するアクセス制御には、次の3つのカテゴリがあります。</span><span class="sxs-lookup"><span data-stu-id="59d74-143">There are three categories of access controls used by Microsoft for operating Microsoft 365:</span></span>

- <span data-ttu-id="59d74-144">分離の制御</span><span class="sxs-lookup"><span data-stu-id="59d74-144">Isolation controls</span></span>
- <span data-ttu-id="59d74-145">担当者の制御</span><span class="sxs-lookup"><span data-stu-id="59d74-145">Personnel controls</span></span>
- <span data-ttu-id="59d74-146">テクノロジの制御</span><span class="sxs-lookup"><span data-stu-id="59d74-146">Technology controls</span></span>

<span data-ttu-id="59d74-147">これらのコントロールを組み合わせると、Microsoft 365 で悪意のあるアクションを防ぎ、検出することができます。</span><span class="sxs-lookup"><span data-stu-id="59d74-147">When combined, these controls help prevent and detect malicious actions in Microsoft 365.</span></span> <span data-ttu-id="59d74-148">Microsoft によって使用される分離、人物、およびテクノロジのコントロールに加えて、次のようなコントロールのカテゴリがあります。これらのコントロールは顧客によって実装されています。</span><span class="sxs-lookup"><span data-stu-id="59d74-148">In addition to the isolation, personnel, and technology controls used by Microsoft, there is a fourth category of controls: those controls implemented by customers.</span></span>

<span data-ttu-id="59d74-149">Microsoft 365 では、オンプレミス環境でのデータ管理と同じ方法でデータを管理できます。</span><span class="sxs-lookup"><span data-stu-id="59d74-149">Microsoft 365 allows you to manage data the same way data is managed in on-premises environments.</span></span> <span data-ttu-id="59d74-150">Microsoft 365 の組織にサインアップするユーザーは、自動的にグローバル管理者になります。</span><span class="sxs-lookup"><span data-stu-id="59d74-150">The person who signs up an organization for Microsoft 365 automatically becomes a global administrator.</span></span> <span data-ttu-id="59d74-151">グローバル管理者は、管理ポータルのすべての機能にアクセスでき、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="59d74-151">The global admin has access to all features in Management Portals and can:</span></span>

- <span data-ttu-id="59d74-152">ユーザーを作成または編集する</span><span class="sxs-lookup"><span data-stu-id="59d74-152">Create or edit users</span></span>
- <span data-ttu-id="59d74-153">他のユーザーに管理者ロールを割り当てる</span><span class="sxs-lookup"><span data-stu-id="59d74-153">Assign admin roles to others</span></span>
- <span data-ttu-id="59d74-154">ユーザーのパスワードをリセットする</span><span class="sxs-lookup"><span data-stu-id="59d74-154">Reset user passwords</span></span>
- <span data-ttu-id="59d74-155">ユーザーライセンスを管理する</span><span class="sxs-lookup"><span data-stu-id="59d74-155">Manage user licenses</span></span>
- <span data-ttu-id="59d74-156">ドメインの管理</span><span class="sxs-lookup"><span data-stu-id="59d74-156">Manage domains</span></span>
- <span data-ttu-id="59d74-157">顧客のロックボックス要求を承認する</span><span class="sxs-lookup"><span data-stu-id="59d74-157">Approve Customer Lockbox requests</span></span>

<span data-ttu-id="59d74-158">各組織で少なくとも2人の管理者アカウントを構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="59d74-158">We recommend that each organization configure at least two admin accounts.</span></span> <span data-ttu-id="59d74-159">大規模な企業組織の場合、さまざまな機能を提供する特別な管理者アカウントをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="59d74-159">For large enterprise organizations, we recommend specialized admin accounts that serve different functions.</span></span>

<span data-ttu-id="59d74-160">管理者の役割とアクセス許可の割り当ての詳細については、「 [管理者の役割の割り当て](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) 」および「 [管理者の役割につい](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)て」を参照</span><span class="sxs-lookup"><span data-stu-id="59d74-160">For information about assigning admin roles and permissions, see [Assign admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) and [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

## <a name="related-links"></a><span data-ttu-id="59d74-161">関連リンク</span><span class="sxs-lookup"><span data-stu-id="59d74-161">Related Links</span></span>

- [<span data-ttu-id="59d74-162">Microsoft 365 での分離</span><span class="sxs-lookup"><span data-stu-id="59d74-162">Isolation in Microsoft 365</span></span>](assurance-isolation-in-microsoft-365.md)
- [<span data-ttu-id="59d74-163">Microsoft 雇用前審査</span><span class="sxs-lookup"><span data-stu-id="59d74-163">Microsoft pre-employment screening</span></span>](assurance-pre-employment-screening.md)
- [<span data-ttu-id="59d74-164">Microsoft クラウドの背景チェック</span><span class="sxs-lookup"><span data-stu-id="59d74-164">Microsoft cloud background check</span></span>](assurance-cloud-background-check.md)
- [<span data-ttu-id="59d74-165">アクセス制御の監視と監査</span><span class="sxs-lookup"><span data-stu-id="59d74-165">Monitoring and Auditing Access Controls</span></span>](assurance-monitoring-and-auditing-access-controls.md)
- [<span data-ttu-id="59d74-166">Yammer Enterprise でのアクセス制御</span><span class="sxs-lookup"><span data-stu-id="59d74-166">Yammer Enterprise Access Controls</span></span>](assurance-yammer-enterprise-access-controls.md)
