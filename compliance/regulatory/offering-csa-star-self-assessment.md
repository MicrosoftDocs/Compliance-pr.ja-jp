---
title: コンプライアンス認証 - Cloud Security Alliance (CSA) STAR Self-Assessment
description: Microsoft の STAR Self-Assessment では、クラウド サービスにおいて Cloud Security Alliance の要件を満たす方法の詳細を説明しています。
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
ms.openlocfilehash: d9bf4c3cf6615b966b4bfb4e70293415deaeeac6
ms.sourcegitcommit: 626b0076d133e588cd28598c149a7f272fc18bae
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2020
ms.locfileid: "49508286"
---
# <a name="cloud-security-alliance-csa-star-self-assessment"></a><span data-ttu-id="2788c-104">Cloud Security Alliance (CSA) STAR Self-Assessment</span><span class="sxs-lookup"><span data-stu-id="2788c-104">Cloud Security Alliance (CSA) STAR self-assessment</span></span>

## <a name="csa-star-self-assessment-overview"></a><span data-ttu-id="2788c-105">CSA STAR Self-Assessment の概要</span><span class="sxs-lookup"><span data-stu-id="2788c-105">CSA STAR self-assessment overview</span></span>

<span data-ttu-id="2788c-106">Cloud Security Alliance (CSA) は、業界の実務者、企業、および他の重要な関係者の幅広い連合によって主導される非営利組織です。</span><span class="sxs-lookup"><span data-stu-id="2788c-106">The Cloud Security Alliance (CSA) is a nonprofit organization led by a broad coalition of industry practitioners, corporations, and other important stakeholders.</span></span> <span data-ttu-id="2788c-107">最も安全なクラウド コンピューティング環境の確保に役立ち、IT 運用をクラウドに移行する際にクラウドのお客様が詳細な情報を得た上で決断できるようにするためのベスト プラクティスを定義することに尽力しています。</span><span class="sxs-lookup"><span data-stu-id="2788c-107">It is dedicated to defining best practices to help ensure a more secure cloud computing environment, and to helping potential cloud customers make informed decisions when transitioning their IT operations to the cloud.</span></span>  
  
<span data-ttu-id="2788c-108">2010 年に CSA はクラウド IT 運用を評価するためのツールのスイートである CSA Governance, Risk Management, and Compliance (GRC) スタックを公開しました。</span><span class="sxs-lookup"><span data-stu-id="2788c-108">In 2010, the CSA published a suite of tools to assess cloud IT operations: the CSA Governance, Risk Management, and Compliance (GRC) Stack.</span></span> <span data-ttu-id="2788c-109">これは、業界のベスト プラクティスや規格の順守状態、および規制への準拠状態について、クラウドのお客様がクラウド サービス プロバイダー (CSP) を評価できるように作成されています。</span><span class="sxs-lookup"><span data-stu-id="2788c-109">It was designed to help cloud customers assess how cloud service providers (CSPs) follow industry best practices and standards and comply with regulations.</span></span>  
  
<span data-ttu-id="2788c-110">2013 年に、CSA と British Standards Institution は Security, Trust & Assurance Registry (STAR) を発表しました。これは、CSP が CSA 関連の評価を公開できる無償の公的にアクセス可能なレジストリです。</span><span class="sxs-lookup"><span data-stu-id="2788c-110">In 2013, the CSA and the British Standards Institution launched the Security, Trust & Assurance Registry (STAR), a free, publicly accessible registry in which CSPs can publish their CSA-related assessments.</span></span>  
  
<span data-ttu-id="2788c-111">CSA STAR は、CSA GRC スタックの 2 つの主要なコンポーネントを基にしています。</span><span class="sxs-lookup"><span data-stu-id="2788c-111">CSA STAR is based on two key components of the CSA GRC Stack:</span></span>

- <span data-ttu-id="2788c-112">Cloud Controls Matrix (CCM): 16 のドメインを対象とする、基本のセキュリティ原則についての管理フレームワークです。クラウドのお客様が CSP の全体的なセキュリティ リスクを評価できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2788c-112">Cloud Controls Matrix (CCM): a controls framework covering fundamental security principles across 16 domains to help cloud customers assess the overall security risk of a CSP.</span></span>
- <span data-ttu-id="2788c-113">Consensus Assessments Initiative Questionnaire (CAIQ): CCM を基に、CSA ベスト プラクティスへの準拠状態を評価するためにお客様やクラウド監査機関が CSP に対して確認するとよい 140 項目以上の質問をまとめています。</span><span class="sxs-lookup"><span data-stu-id="2788c-113">The Consensus Assessments Initiative Questionnaire (CAIQ): a set of more than 140 questions based on the CCM that a customer or cloud auditor may want to ask of CSPs to assess their compliance with CSA best practices.</span></span>

<span data-ttu-id="2788c-114">STAR は 3 つのレベルの保証を提供します。CSA STAR Self-Assessment は、導入レベルである Level 1 の保証になり、すべての CSP が無料で使用できます。</span><span class="sxs-lookup"><span data-stu-id="2788c-114">STAR provides three levels of assurance; CSA-STAR Self-Assessment is the introductory offering at Level 1, which is free and open to all CSPs.</span></span> <span data-ttu-id="2788c-115">それ以降の STAR プログラムの保証については、Level 2 では第三者による評価ベースの認定が必要になり、Level 3 では継続的な監視に基づく認定が必要になります。</span><span class="sxs-lookup"><span data-stu-id="2788c-115">Going further up the assurance stack, Level 2 of the STAR program involves third-party assessment-based certifications, and Level 3 involves certifications based on continuous monitoring.</span></span>

## <a name="microsoft-and-csa-star-self-assessment"></a><span data-ttu-id="2788c-116">Microsoft および CSA STAR Self-Assessment</span><span class="sxs-lookup"><span data-stu-id="2788c-116">Microsoft and CSA STAR self-assessment</span></span>

<span data-ttu-id="2788c-117">STAR Self-Assessment の一環として、CSP は、CSA ベスト プラクティスへの準拠を示す 2 種類の異なるドキュメントを提出できます。1 つは回答を記入した CAIQ で、もう 1 つは CCM への準拠状態を記録したレポートです。</span><span class="sxs-lookup"><span data-stu-id="2788c-117">As part of the STAR Self-Assessment, CSPs can submit two different types of documents to indicate their compliance with CSA best practices: a completed CAIQ, or a report documenting compliance with CCM.</span></span> <span data-ttu-id="2788c-118">CSA STAR Self-Assessment の場合、Microsoft では Microsoft Azure 用に CAIQ と CCM ベースのレポートの両方を、Microsoft Dynamics 365 と Microsoft Office 365 用には CCM ベースのレポートを公開しています。</span><span class="sxs-lookup"><span data-stu-id="2788c-118">For the CSA STAR Self-Assessment, Microsoft publishes both a CAIQ and a CCM-based report for Microsoft Azure, and CCM-based reports for Microsoft Dynamics 365 and Microsoft Office 365.</span></span>  

<span data-ttu-id="2788c-119">「Azure のセキュリティとコンプライアンスのブループリント」で CSA STAR Self-Assessment のデプロイメントを加速する方法についてご確認ください: [CSA STAR コンセンサス評価に対する Azure の対応をダウンロードする](https://gallery.technet.microsoft.com/Azure-Responses-to-CSA-46034a11)</span><span class="sxs-lookup"><span data-stu-id="2788c-119">Learn how to accelerate your CSA STAR Self-Assessment deployment with our Azure Security and Compliance Blueprint: [Download Azure response to the CSA Consensus Assessments](https://gallery.technet.microsoft.com/Azure-Responses-to-CSA-46034a11)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="2788c-120">対象となる Microsoft のクラウド サービス</span><span class="sxs-lookup"><span data-stu-id="2788c-120">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="2788c-121">Azure および Azure Government</span><span class="sxs-lookup"><span data-stu-id="2788c-121">Azure and Azure Government</span></span>](https://gallery.technet.microsoft.com/Overview-of-Azure-c1be3942)
- [<span data-ttu-id="2788c-122">Dynamics 365 CSA STAR Self-Assessment</span><span class="sxs-lookup"><span data-stu-id="2788c-122">Dynamics 365 CSA STAR Self-Assessment</span></span>](https://cloudsecurityalliance.org/star/registry/microsoft/)

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="2788c-123">監査、レポート、証明書</span><span class="sxs-lookup"><span data-stu-id="2788c-123">Audits, reports, and certificates</span></span>

- [<span data-ttu-id="2788c-124">情報要求に対する Azure の標準応答</span><span class="sxs-lookup"><span data-stu-id="2788c-124">Azure standard response for request for information</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=f7ca8423-1bc5-4be0-bff8-b6056f87c134&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers)
- [<span data-ttu-id="2788c-125">Azure Cloud Security Alliance CAIQ</span><span class="sxs-lookup"><span data-stu-id="2788c-125">Azure Cloud Security Alliance CAIQ</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=a966a424-ecfd-4de2-9739-b08aee2d3ca0&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides)
- [<span data-ttu-id="2788c-126">CSA CAIQ v3.0.1 への Azure の対応</span><span class="sxs-lookup"><span data-stu-id="2788c-126">Azure responses to the CSA CAIQ v3.0.1</span></span>](https://gallery.technet.microsoft.com/Azure-Responses-to-CSA-46034a11)

## <a name="frequently-asked-questions"></a><span data-ttu-id="2788c-127">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="2788c-127">Frequently asked questions</span></span>

<span data-ttu-id="2788c-128">**CSA CCM が対応しているのはどの業界標準ですか?**</span><span class="sxs-lookup"><span data-stu-id="2788c-128">**Which industry standards does the CSA CCM align with?**</span></span>

<span data-ttu-id="2788c-129">CCM は、ISO 27001、PCI DSS、HIPAA、AICPA SOC 2、NERC CIP、FedRAMP、NIST など、業界で受け入れられているさまざまなセキュリティ基準、規制、管理フレームワークに対応しています。</span><span class="sxs-lookup"><span data-stu-id="2788c-129">The CCM corresponds to industry-accepted security standards, regulations, and control frameworks such as ISO 27001, PCI DSS, HIPAA, AICPA SOC 2, NERC CIP, FedRAMP, NIST, and many more.</span></span> <span data-ttu-id="2788c-130">最新のリストについては [CSA の Web サイト](https://cloudsecurityalliance.org/)にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="2788c-130">For the most current list, visit the [CSA website](https://cloudsecurityalliance.org/).</span></span>

<span data-ttu-id="2788c-131">**CSA STAR Self-Assessment が重要であるのはなぜですか?**</span><span class="sxs-lookup"><span data-stu-id="2788c-131">**Why is the CSA STAR Self-Assessment important?**</span></span>

<span data-ttu-id="2788c-132">CSP は CSA STAR Self-Assessment を使用すると、透明性の高い方法で、CSA が発行したベスト プラクティスに準拠していることを文書化できます。</span><span class="sxs-lookup"><span data-stu-id="2788c-132">It enables CSPs to document compliance with CSA published best practices in a transparent manner.</span></span> <span data-ttu-id="2788c-133">自己評価レポートは一般に公開されるため、クラウドのお客様が CSP のセキュリティ施策について確認し、同じ基準を使用して異なる CSP を比較検討できます。</span><span class="sxs-lookup"><span data-stu-id="2788c-133">Self-assessment reports are publicly available, thereby helping cloud customers gain visibility into the security practices of CSPs, and compare various CSPs using the same baseline.</span></span>

<span data-ttu-id="2788c-134">**Microsoft のビジネス クラウド サービスは、CSA STAR のどの保証レベルを達成していますか?**</span><span class="sxs-lookup"><span data-stu-id="2788c-134">**Which CSA STAR levels of assurance have Microsoft business cloud services attained?**</span></span>

- <span data-ttu-id="2788c-135">**Level 1**: **CSA STAR Self-Assessment**: Azure、Dynamics 365、Office 365。</span><span class="sxs-lookup"><span data-stu-id="2788c-135">**Level 1**: **CSA STAR Self-Assessment**: Azure, Dynamics 365, and Office 365.</span></span> <span data-ttu-id="2788c-136">Self-Assessment は、お客様がサービスのセキュリティを評価できるように、クラウド サービス プロバイダーが自社のセキュリティ コントロールの文書化に使用でき、無料で提供されます。</span><span class="sxs-lookup"><span data-stu-id="2788c-136">The Self-Assessment is a complimentary offering from cloud service providers to document their security controls to help customers assess the security of the service.</span></span>
- <span data-ttu-id="2788c-137">**Level 2**: **CSA STAR 認定資格**: Azure、Microsoft Cloud App Security、Intune、Power BI。</span><span class="sxs-lookup"><span data-stu-id="2788c-137">**Level 2**: **CSA STAR Certification**: Azure, Microsoft Cloud App Security, Intune, and Power BI.</span></span> <span data-ttu-id="2788c-138">STAR 認証は、ISO/IEC 27001 認証の取得および CCM に規定されている基準への適合に基づきます。</span><span class="sxs-lookup"><span data-stu-id="2788c-138">STAR Certification is based on achieving ISO/IEC 27001 certification and meeting criteria specified in the CCM.</span></span> <span data-ttu-id="2788c-139">この認証は、クラウド サービス プロバイダーにおけるセキュリティの制御と取り組みについて、第三者による厳格な評価を経て付与されます。</span><span class="sxs-lookup"><span data-stu-id="2788c-139">It is awarded after a rigorous third-party assessment of the security controls and practices of a cloud service provider.</span></span>
- <span data-ttu-id="2788c-140">**レベル 2**: **CSA STAR 評価証明**: Azure および Intune。</span><span class="sxs-lookup"><span data-stu-id="2788c-140">**Level 2**: **CSA STAR Attestation**: Azure and Intune.</span></span> <span data-ttu-id="2788c-141">CSA と AICPA が協力して、CPA が SOC 2 に取り組む際に使用できるガイドラインを提供しています。このガイドラインでは、AICPA (Trust Service Principles, AT 101) および CSA CCM の基準を使用しています。</span><span class="sxs-lookup"><span data-stu-id="2788c-141">CSA and the AICPA have collaborated to provide guidelines for CPAs to use in conducting SOC 2 engagements, using criteria from the AICPA (Trust Service Principles, AT 101) and the CSA CCM.</span></span> <span data-ttu-id="2788c-142">STAR Attestation では、これらのガイドラインを基に、クラウド プロバイダーに対する独立機関による厳格な評価を経て認定されます。</span><span class="sxs-lookup"><span data-stu-id="2788c-142">STAR Attestation is based on these guidelines and is awarded after rigorous independent assessments of cloud providers.</span></span>

## <a name="resources"></a><span data-ttu-id="2788c-143">リソース</span><span class="sxs-lookup"><span data-stu-id="2788c-143">Resources</span></span>

- [<span data-ttu-id="2788c-144">Cloud Security Alliance</span><span class="sxs-lookup"><span data-stu-id="2788c-144">Cloud Security Alliance</span></span>](https://cloudsecurityalliance.org/)
- [<span data-ttu-id="2788c-145">Cloud Controls Matrix (CCM)</span><span class="sxs-lookup"><span data-stu-id="2788c-145">Cloud Controls Matrix (CCM)</span></span>](https://cloudsecurityalliance.org/group/cloud-controls-matrix/)
- [<span data-ttu-id="2788c-146">Consensus Assessments Initiative Questionnaire (CAIQ)</span><span class="sxs-lookup"><span data-stu-id="2788c-146">Consensus Assessments Initiative Questionnaire (CAIQ)</span></span>](https://cloudsecurityalliance.org/group/consensus-assessments/)
- [<span data-ttu-id="2788c-147">CSA Security, Trust & Assurance Registry (STAR)</span><span class="sxs-lookup"><span data-stu-id="2788c-147">CSA Security, Trust & Assurance Registry (STAR)</span></span>](https://cloudsecurityalliance.org/star/)
- [<span data-ttu-id="2788c-148">Microsoft Trust Center のコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="2788c-148">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="microsoft-csa-star-self-assessments"></a><span data-ttu-id="2788c-149">Microsoft の CSA STAR self-assessments</span><span class="sxs-lookup"><span data-stu-id="2788c-149">Microsoft CSA STAR self-assessments</span></span>

- [<span data-ttu-id="2788c-150">Azure</span><span class="sxs-lookup"><span data-stu-id="2788c-150">Azure</span></span>](https://aka.ms/Azure_STAR)
- [<span data-ttu-id="2788c-151">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="2788c-151">Dynamics 365</span></span>](https://aka.ms/DynamicsCRM_Online_STAR)
