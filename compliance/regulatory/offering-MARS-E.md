---
title: Minimum Acceptable Risk Standards for Exchanges (MARS-E) 2.0 フレームワーク
description: Microsoft は米国の Minimum Acceptable Risk Standards for Exchanges (MARS-E) に準拠しています。
keywords: Microsoft 365、コンプライアンス、サービス
localization_priority: Priority
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- M365-security-compliance
- MS-Compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 8eeeeac094911a0151c643bc6de7a3661a0e3165
ms.sourcegitcommit: 626b0076d133e588cd28598c149a7f272fc18bae
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2020
ms.locfileid: "49509419"
---
# <a name="minimum-acceptable-risk-standards-for-exchanges-mars-e-20-framework"></a><span data-ttu-id="47ce1-104">Minimum Acceptable Risk Standards for Exchanges (MARS-E) 2.0 フレームワーク</span><span class="sxs-lookup"><span data-stu-id="47ce1-104">Minimum Acceptable Risk Standards for Exchanges (MARS-E) 2.0 Framework</span></span>

## <a name="mars-e-20-framework-overview"></a><span data-ttu-id="47ce1-105">MARS-E 2.0 フレームワークの概要</span><span class="sxs-lookup"><span data-stu-id="47ce1-105">MARS-E 2.0 Framework overview</span></span>

<span data-ttu-id="47ce1-106">2012 年、Center for Medicare and Medicaid Services (CMS) は、CMS 情報セキュリティおよびプライバシー プログラムに従い、Minimum Acceptable Risk Standards for Exchanges (MARS-E) を発行しました。</span><span class="sxs-lookup"><span data-stu-id="47ce1-106">In 2012, the Center for Medicare and Medicaid Services (CMS) published the Minimum Acceptable Risk Standards for Exchanges (MARS-E) in accordance with CMS information security and privacy programs.</span></span> <span data-ttu-id="47ce1-107">これは、ガイダンス、要件、テンプレートを含むドキュメント セットで、Patient Protection and Affordable Care Act (ACA) の命令と、ACA に適用される Department of Health and Human Services の規則に対応できるよう策定されています。</span><span class="sxs-lookup"><span data-stu-id="47ce1-107">The suite of documents, including guidance, requirements, and templates, was designed to address mandates of the Patient Protection and Affordable Care Act (ACA) and regulations of the Department of Health and Human Services that apply to the ACA.</span></span> <span data-ttu-id="47ce1-108">米国標準技術研究所 (NIST) Special Publication 800-53 が、ACA が強制適用される医療保健取引所と市場間のすべてのシステム、インターフェイス、接続を対象とするセキュリティおよびコンプライアンス要件を規定する大元のフレームワークになっています。</span><span class="sxs-lookup"><span data-stu-id="47ce1-108">The National Institute of Standards and Technology (NIST) Special Publication 800-53 serves as the parent framework that establishes the security and compliance requirements for all systems, interfaces, and connections between ACA-mandated health exchanges and marketplaces.</span></span>

<span data-ttu-id="47ce1-109">MARS-E のリリースに続き、NIST は新しいパブリケーションの Special Publication 800-53r4 をリリースしました。これは、アプリケーション セキュリティ、内部からの脅威や高度で執拗な脅威、サプライ チェーンにおけるリスクのほか、モバイルおよびクラウド コンピューティングのシステムの信頼性、保証、回復性など、増え続けるオンライン セキュリティの課題に対応しています。</span><span class="sxs-lookup"><span data-stu-id="47ce1-109">Following the release of MARS-E, NIST released an update, Special Publication 800-53r4, to address growing challenges to online security, including application security; insider and advanced persistent threats; supply chain risks; and the trustworthiness, assurance, and resilience of systems of mobile and cloud computing.</span></span> <span data-ttu-id="47ce1-110">その後、CMS は、NIST 800.53r4 の更新されたコントロールとパラメーターに合わせて MARS-E フレームワークを改訂し、2015 年に MARS-E 2.0 を発行しました。</span><span class="sxs-lookup"><span data-stu-id="47ce1-110">CMS then revised the MARS-E framework to align with the updated controls and parameters in NIST 800.53r4, publishing MARS-E 2.0 in 2015.</span></span>

<span data-ttu-id="47ce1-111">上記の各更新は、健康保険取引所における保護対象データの機密性、整合性、可用性に対応しています。保護対象データには、個人を特定できる情報、保護対象の医療情報、連邦税金情報 (FTI) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="47ce1-111">These updates address the confidentiality, integrity, and availability in health exchanges of protected data, which includes personally identifiable information, protected health information, and federal tax information.</span></span> <span data-ttu-id="47ce1-112">MARS-E 2.0 フレームワークは、この保護対象データを保護することを目的としており、ACA が適用されるすべての法人に適用されます。適用対象には、取引所やマーケットプレース (連邦政府関係機関、州政府関係機関、州のメディケイド機関、児童医療保険プログラム (CHIP) 機関) と委託先会社が含まれます。</span><span class="sxs-lookup"><span data-stu-id="47ce1-112">The MARS-E 2.0 framework aims to secure this protected data and applies to all ACA administering entities, including exchanges or marketplaces, federal, state, state Medicaid, or Children's Health Insurance Program (CHIP) agencies, and supporting contractors.</span></span>

## <a name="microsoft-and-mars-e-20-framework"></a><span data-ttu-id="47ce1-113">Microsoft と MARS-E 2.0 フレームワーク</span><span class="sxs-lookup"><span data-stu-id="47ce1-113">Microsoft and MARS-E 2.0 framework</span></span>

<span data-ttu-id="47ce1-114">現時点では、MARS-E には正式な承認や認定のプロセスはありません。</span><span class="sxs-lookup"><span data-stu-id="47ce1-114">Currently, there is no formal authorization and accreditation process for MARS-E.</span></span> <span data-ttu-id="47ce1-115">ただし、Microsoft Azure Platform サービスは独立機関による FedRAMP 監査を Moderate Impact Level で、Azure Government は High Impact Level で受けており、FedRAMP 規格に準拠していることが認定されています。</span><span class="sxs-lookup"><span data-stu-id="47ce1-115">However, Microsoft Azure platform services have undergone independent FedRAMP audits at the Moderate Impact Level and Azure Government at the High Impact Level, and are authorized according to FedRAMP standards.</span></span> <span data-ttu-id="47ce1-116">これらは MARS-E のための規格ではありませんが、MARS-E の統制要件と目標は似通っていて、Azure でのデータの機密性、整合性、可用性の確保に利用できます。</span><span class="sxs-lookup"><span data-stu-id="47ce1-116">Although these standards do not specifically focus on MARS-E, the MARS-E control requirements and objectives are closely aligned and serve to protect the confidentiality, integrity, and availability of data on Azure.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="47ce1-117">対象となる Microsoft のクラウド サービス</span><span class="sxs-lookup"><span data-stu-id="47ce1-117">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="47ce1-118">Azure および Azure Government</span><span class="sxs-lookup"><span data-stu-id="47ce1-118">Azure and Azure Government</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="47ce1-119">Intune</span><span class="sxs-lookup"><span data-stu-id="47ce1-119">Intune</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="47ce1-120">監査、レポート、証明書</span><span class="sxs-lookup"><span data-stu-id="47ce1-120">Audits, reports, and certificates</span></span>

<span data-ttu-id="47ce1-121">Microsoft ビジネス クラウド サービスは、FedRAMP 認定プロセスに従い、毎年監視および評価されます。</span><span class="sxs-lookup"><span data-stu-id="47ce1-121">Microsoft business cloud services are monitored and assessed each year for the FedRAMP authorization process.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="47ce1-122">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="47ce1-122">Frequently asked questions</span></span>

<span data-ttu-id="47ce1-123">**この標準はだれに適用されますか?**</span><span class="sxs-lookup"><span data-stu-id="47ce1-123">**To whom does the standard apply?**</span></span>

<span data-ttu-id="47ce1-124">MARS-E は、Affordable Care Act が適用されるすべての法人に適用されます。適用対象には、取引所やマーケットプレース (Basic Health Program を運営する連邦政府関係機関、州政府関係機関、メディケイド機関、CHIP 機関) と、それらのすべての委託先会社および下請けの委託先会社が含まれます。</span><span class="sxs-lookup"><span data-stu-id="47ce1-124">MARS-E applies to all Affordable Care Act administering entities, including exchanges or marketplaces, federal, state, Medicaid, and CHIP agencies administering the Basic Health Program, as well as all their contractors and subcontractors.</span></span>

<span data-ttu-id="47ce1-125">**Azure および Azure Government がこの規格に準拠していることは、どのように実証されますか?**</span><span class="sxs-lookup"><span data-stu-id="47ce1-125">**How does Microsoft demonstrate Azure and Azure Government compliance with this standard?**</span></span>

<span data-ttu-id="47ce1-126">第三者による正式な FedRAMP 認定のための監査レポートを使用することで、Microsoft はこれらのレポートに記載されている関連するコントロールにより、Azure が MARS-E のセキュリティおよびプライバシー コントロール要件に準拠できることを実証できます。</span><span class="sxs-lookup"><span data-stu-id="47ce1-126">Using the formal audit reports prepared by third parties for FedRAMP authorizations, Microsoft is able to show how relevant controls noted that within these reports demonstrate Azure capabilities in meeting MARS-E security and privacy control requirements.</span></span> <span data-ttu-id="47ce1-127">Microsoft が実装している監査対象のコントロールによって、Azure Platform に格納されるデータの機密性、整合性、および可用性を確保できます。これらは、Microsoft の責任として特定されている MARS-E の規制要件に対応します。</span><span class="sxs-lookup"><span data-stu-id="47ce1-127">Audited controls implemented by Microsoft serve to protect the confidentiality, integrity, and availability of data stored on the Azure platform, and correspond to the applicable regulatory requirements defined in MARS-E that have been identified as the responsibility of Microsoft.</span></span>

<span data-ttu-id="47ce1-128">**この標準への準拠を維持するうえで Microsoft にはどのような責任がありますか?**</span><span class="sxs-lookup"><span data-stu-id="47ce1-128">**What are Microsoft's responsibilities for maintaining compliance with this standard?**</span></span>

<span data-ttu-id="47ce1-129">Microsoft は Azure Platform が[オンライン サービス条件](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=31)と該当するサービス レベル アグリーメント (SLA) で規定されている条件に適合していることを保証します。</span><span class="sxs-lookup"><span data-stu-id="47ce1-129">Microsoft ensures that the Azure platform meets the terms defined within the governing [Online Services Terms](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=31) and applicable service level agreements (SLAs).</span></span> <span data-ttu-id="47ce1-130">これらの契約は、Azure Platform の安全を確保してシステムを監視するために適切なコントロールを実装および維持する責任が Microsoft にあることが規定されています。</span><span class="sxs-lookup"><span data-stu-id="47ce1-130">These agreements define our responsibility for implementing and maintaining controls adequate to secure the Azure platform and monitor the system.</span></span>

<span data-ttu-id="47ce1-131">**Microsoft のコンプライアンスを自分の組織の MARS-E の適合認定プロセスに利用できますか?**</span><span class="sxs-lookup"><span data-stu-id="47ce1-131">**Can I use Microsoft's compliance in the MARS-E qualification efforts for my organization?**</span></span>

<span data-ttu-id="47ce1-132">はい。</span><span class="sxs-lookup"><span data-stu-id="47ce1-132">Yes.</span></span> <span data-ttu-id="47ce1-133">FedRAMP 規格に対する第三者監査レポートは、Azure Platform のセキュリティとプライバシーを維持するために Microsoft が実装しているコントロールの有効性を証明しています。</span><span class="sxs-lookup"><span data-stu-id="47ce1-133">Third-party audit reports to the FedRAMP standards attest to the effectiveness of the controls Microsoft has implemented to maintain the security and privacy of the Azure platform.</span></span> <span data-ttu-id="47ce1-134">Azure および Azure Government のお客様は、FedRAMP や MARS-E のリスク分析や適合認定の一環で、これらの関連レポートに記載されている監査済みの統制を利用できます。</span><span class="sxs-lookup"><span data-stu-id="47ce1-134">Azure and Azure Government customers may use the audited controls described in these related reports as part of their own FedRAMP and MARS-E risk analysis and qualification efforts.</span></span>

## <a name="resources"></a><span data-ttu-id="47ce1-135">リソース</span><span class="sxs-lookup"><span data-stu-id="47ce1-135">Resources</span></span>

- <span data-ttu-id="47ce1-136">MARS-E regulatory guidance, MARS-E Document Suite, Version 2.0</span><span class="sxs-lookup"><span data-stu-id="47ce1-136">MARS-E regulatory guidance, MARS-E Document Suite, Version 2.0</span></span>
    - [<span data-ttu-id="47ce1-137">第 II 版: Minimum Acceptable Risk Standards for Exchanges</span><span class="sxs-lookup"><span data-stu-id="47ce1-137">Volume II: Minimum acceptable risk standards for exchanges</span></span>](https://www.cms.gov/CCIIO/Resources/Regulations-and-Guidance/Downloads/2-MARS-E-v2-0-Minimum-Acceptable-Risk-Standards-for-Exchanges-11102015.pdf)
    - [<span data-ttu-id="47ce1-138">第 III 版: Minimum Acceptable Risk Standards for Exchanges のカタログ</span><span class="sxs-lookup"><span data-stu-id="47ce1-138">Volume III: Catalog of minimum acceptable risk security and privacy controls for exchanges</span></span>](https://www.cms.gov/CCIIO/Resources/Regulations-and-Guidance/Downloads/3-MARS-E-v2-0-Catalog-of-Security-and-Privacy-Controls-11102015.pdf)
- [<span data-ttu-id="47ce1-139">オンライン サービス用の Microsoft コンプライアンス フレームワーク ホワイト ペーパー</span><span class="sxs-lookup"><span data-stu-id="47ce1-139">Microsoft compliance framework for online services white paper</span></span>](https://aka.ms/compliance-framework)
- [<span data-ttu-id="47ce1-140">Microsoft オンライン サービス条件</span><span class="sxs-lookup"><span data-stu-id="47ce1-140">Microsoft cloud services terms</span></span>](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=31)
- [<span data-ttu-id="47ce1-141">Microsoft セキュリティ センターのコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="47ce1-141">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)
