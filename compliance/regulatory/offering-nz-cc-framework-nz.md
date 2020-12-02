---
title: ニュージーランド政府機関向けクラウドコンピューティングのセキュリティとプライバシーに関する考慮事項
description: Microsoft NZ は、ニュージーランドクラウドコンピューティングフレームワークで公開されている質問に対応しています。
keywords: Microsoft 365、コンプライアンス、サービス
localization_priority: None
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
ms.openlocfilehash: db1168d494fd5a8d0a31176ccccdff72dd096f1d
ms.sourcegitcommit: c697549cdc5785e163bd6147cf0d95ba61b078fe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2020
ms.locfileid: "49528893"
---
# <a name="new-zealand-government-cloud-computing-security-and-privacy-considerations"></a><span data-ttu-id="26107-104">ニュージーランド政府機関向けクラウドコンピューティングのセキュリティとプライバシーに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="26107-104">New Zealand Government Cloud Computing Security and Privacy Considerations</span></span>

## <a name="new-zealand-government-cloud-computing-security-and-privacy-overview"></a><span data-ttu-id="26107-105">ニュージーランド政府機関向けクラウドコンピューティングのセキュリティとプライバシーの概要</span><span class="sxs-lookup"><span data-stu-id="26107-105">New Zealand Government Cloud Computing Security and Privacy overview</span></span>

<span data-ttu-id="26107-106">2015年10月に、民間政府は、公的機関の情報技術を使用して、「クラウドファースト」ポリシーを再確定する、改正されたすべての ICT 戦略を裏書しました。</span><span class="sxs-lookup"><span data-stu-id="26107-106">In October 2015, the New Zealand Government endorsed a revised all-government ICT strategy that reaffirmed its 'cloud first' policy on using information technology across the public sector.</span></span> <span data-ttu-id="26107-107">改訂された戦略では、「クラウドコンピューティングのリスクと保証のフレームワーク」が、NZ 政府のチーフ情報責任者 (GCIO) の権限で開発および実装されています。</span><span class="sxs-lookup"><span data-stu-id="26107-107">The revised strategy retains the 'Cloud Computing Risk and Assurance Framework' that was developed and implemented under the authority of the NZ Government Chief Information Officer (GCIO).</span></span>

<span data-ttu-id="26107-108">政府は、クラウドサービスを評価して採用するときに、すべてのニュージーランド状態サービスエージェンシーがこのフレームワーク内で機能することを想定しています。</span><span class="sxs-lookup"><span data-stu-id="26107-108">The government expects all New Zealand State Service agencies to work within this framework when assessing and adopting cloud services.</span></span> <span data-ttu-id="26107-109">「クラウドコンピューティングの要件」では、クラウドサービスを採用する際に行う必要のある機関と、政府機関のクラウドポリシーの概要について概説します。</span><span class="sxs-lookup"><span data-stu-id="26107-109">'Requirements for Cloud Computing' outlines what agencies must do when adopting cloud services along with an overview of the history of the government's cloud policy.</span></span>

<span data-ttu-id="26107-110">「クラウドコンピューティング: 情報のセキュリティとプライバシーに関する考慮事項」 (クラウドコンピューティング ISPC) を公開している場合は、「クラウドコンピューティング: 情報セキュリティとプライバシーに関する考慮事項」に記載されているように、NZ 政府機関による一貫性のある堅牢なデューデリジェンスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="26107-110">To assist NZ government agencies in conducting consistent and robust due diligence on potential cloud solutions, the GCIO has published 'Cloud Computing: Information Security and Privacy Considerations' (the 'Cloud Computing ISPC').</span></span> <span data-ttu-id="26107-111">このドキュメントには、データ主権、プライバシー、セキュリティ、ガバナンス、機密性、データの整合性、可用性、およびインシデントの対応と管理に焦点を絞った100の質問が含まれています。</span><span class="sxs-lookup"><span data-stu-id="26107-111">This document contains more than 100 questions focused on data sovereignty, privacy, security, governance, confidentiality, data integrity, availability, and incident response and management.</span></span> <span data-ttu-id="26107-112">' Cloud Computing IPSC ' では、クラウドサービスプロバイダーが公式のコンプライアンスを示すために必要な NZ 政府標準が定義されていません。</span><span class="sxs-lookup"><span data-stu-id="26107-112">'Cloud Computing IPSC' does not define a NZ government standard against which cloud service providers must demonstrate formal compliance.</span></span> <span data-ttu-id="26107-113">ドキュメントで設定されているいくつかの質問については、クラウドサービスプロバイダーがさまざまな関連標準に準拠する方法を理解することが重要であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="26107-113">Many of the questions set out in the document do, however, point toward the importance of understanding how cloud service providers comply with a wide array of relevant standards.</span></span>

<span data-ttu-id="26107-114">Microsoft およびニュージーランド政府機関向けのクラウドコンピューティングのセキュリティとプライバシーに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="26107-114">Microsoft and New Zealand Government Cloud Computing Security and Privacy Considerations</span></span>

<span data-ttu-id="26107-115">エージェンシーが Microsoft enterprise cloud services の分析と評価を行うのに役立つように、microsoft ニュージーランドでは、microsoft cloud services が認定されている基準にリンクすることによって、企業クラウドサービスが「クラウドコンピューティング ISPC」で設定されている質問に対処する方法を示したドキュメントが作成されています。</span><span class="sxs-lookup"><span data-stu-id="26107-115">To help agencies undertake their analysis and evaluation of Microsoft enterprise cloud services, Microsoft New Zealand has produced documents showing how its enterprise cloud services address the questions set out in the 'Cloud Computing ISPC' by linking them to the standards against which Microsoft cloud services are certified.</span></span> <span data-ttu-id="26107-116">これらの認定資格は、Microsoft がクラウドサービスを設計、構築、運用することによって、プライバシーおよびセキュリティリスクを効果的に軽減し、データ主権の懸念事項を解決できるようにすることを中心としています。</span><span class="sxs-lookup"><span data-stu-id="26107-116">These certifications are central to how Microsoft assures both public and private sector customers that its cloud services are designed, built, and operated to effectively mitigate privacy and security risks and address data sovereignty concerns.</span></span>

<span data-ttu-id="26107-117">Azure セキュリティおよびコンプライアンスブループリントを使用して、NZ による [CC] フレームワークの展開を促進する方法について説明します。 [azure からの応答を nz にダウンロード](https://gallery.technet.microsoft.com/Response-to-GCIO-Cloud-e117bbb9)します。</span><span class="sxs-lookup"><span data-stu-id="26107-117">Learn how to accelerate your NZ CC Framework deployment with our Azure Security and Compliance Blueprint: [Download Azure response to the NZ CC Framework](https://gallery.technet.microsoft.com/Response-to-GCIO-Cloud-e117bbb9)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="26107-118">対象となる Microsoft のクラウド サービス</span><span class="sxs-lookup"><span data-stu-id="26107-118">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="26107-119">Azure および Azure Government</span><span class="sxs-lookup"><span data-stu-id="26107-119">Azure and Azure Government</span></span>](https://aka.ms/AzureCompliance)
- [<span data-ttu-id="26107-120">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="26107-120">Dynamics 365</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="26107-121">Intune</span><span class="sxs-lookup"><span data-stu-id="26107-121">Intune</span></span>
- <span data-ttu-id="26107-122">Power BI クラウド サービス (スタンドアロン サービス、または Office 365 ブランド プランあるいはスイートに搭載されているサービス)</span><span class="sxs-lookup"><span data-stu-id="26107-122">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- [<span data-ttu-id="26107-123">Office 365</span><span class="sxs-lookup"><span data-stu-id="26107-123">Office 365</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- <span data-ttu-id="26107-124">Exchange Online、SharePoint Online、Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="26107-124">Exchange Online, SharePoint Online, and Microsoft Teams.</span></span> <span data-ttu-id="26107-125">Microsoft NZ は、Exchange Online と SEEMail を統合するためのリファレンスアーキテクチャを開発するために、GCIO チームと協力しています。</span><span class="sxs-lookup"><span data-stu-id="26107-125">Microsoft NZ has worked with the GCIO team to develop a reference architecture for integrating Exchange Online and SEEMail.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="26107-126">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="26107-126">Frequently asked questions</span></span>

<span data-ttu-id="26107-127">**フレームワークが適用されるユーザー**</span><span class="sxs-lookup"><span data-stu-id="26107-127">**To whom does the framework apply?**</span></span>

<span data-ttu-id="26107-128">「CIO の義務」の下にある組織では、パブリックおよび非パブリックのサービス部門、20個の学区の健康ボード、7クラウンエンティティは、クラウドサービスの使用を決定する際に、フレームワークに準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="26107-128">Organizations that fall under the GCIO mandate, the public and non-public service departments, the 20 district health boards, and 7 Crown entities, must adhere to the framework when they are deciding on the use of a cloud service.</span></span>

<span data-ttu-id="26107-129">**このフレームワークに対する Microsoft の対応を ICT システムの認定プロセスに使用することはできますか?**</span><span class="sxs-lookup"><span data-stu-id="26107-129">**Can my agency use Microsoft's responses to this framework in the certification process of our ICT systems?**</span></span>

<span data-ttu-id="26107-130">事務局が [新ニュージーランド情報セキュリティマニュアル](https://go.microsoft.com/fwlink/p/?linkid=2099496)の下にある ICT システムの認定および認定を行う必要がある場合は、これらの応答を分析の一部として使用できます。</span><span class="sxs-lookup"><span data-stu-id="26107-130">If your agency is required to undertake certification and accreditation of its ICT system under the [New Zealand Information Security Manual](https://go.microsoft.com/fwlink/p/?linkid=2099496), then you can use these responses as part of your analysis.</span></span>

## <a name="resources"></a><span data-ttu-id="26107-131">リソース</span><span class="sxs-lookup"><span data-stu-id="26107-131">Resources</span></span>

- [<span data-ttu-id="26107-132">海外でホストされている Office プロダクティビティサービスのセキュリティ要件: Office 365 の準拠ガイド</span><span class="sxs-lookup"><span data-stu-id="26107-132">Security requirements for offshore hosted Office productivity services: conformance guide for Office 365</span></span>](https://aka.ms/o365-gcio-conformance-guidance)
- [<span data-ttu-id="26107-133">ニュージーランドのセキュリティおよびプライバシーに関する要件のコンテキストにおける Microsoft Azure コンプライアンス</span><span class="sxs-lookup"><span data-stu-id="26107-133">Microsoft Azure compliance in the context of New Zealand security and privacy requirements</span></span>](https://aka.ms/azurecompliancenewzealand)
- [<span data-ttu-id="26107-134">NZ 政府 ICT 戦略2015</span><span class="sxs-lookup"><span data-stu-id="26107-134">NZ Government ICT Strategy 2015</span></span>](https://www.ict.govt.nz/strategy-and-action-plan/strategy/)
- [<span data-ttu-id="26107-135">クラウドコンピューティングのための NZ 政府の要件</span><span class="sxs-lookup"><span data-stu-id="26107-135">NZ Government requirements for cloud computing</span></span>](https://aka.ms/NZ-Cloud-Requirements)
- [<span data-ttu-id="26107-136">クラウドコンピューティング: 情報のセキュリティとプライバシーに関する考慮事項 (ISPC)</span><span class="sxs-lookup"><span data-stu-id="26107-136">Cloud Computing: Information Security and Privacy Considerations (ISPC)</span></span>](https://www.digital.govt.nz/standards-and-guidance/technology-and-architecture/cloud-services/)
- [<span data-ttu-id="26107-137">Microsoft オンライン サービス条件</span><span class="sxs-lookup"><span data-stu-id="26107-137">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
- [<span data-ttu-id="26107-138">Microsoft セキュリティ センターのコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="26107-138">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="microsoft-responses-to-cloud-computing-ipsc"></a><span data-ttu-id="26107-139">' クラウドコンピューティング IPSC ' への Microsoft の応答</span><span class="sxs-lookup"><span data-stu-id="26107-139">Microsoft responses to 'Cloud Computing IPSC'</span></span>

- [<span data-ttu-id="26107-140">Azure</span><span class="sxs-lookup"><span data-stu-id="26107-140">Azure</span></span>](https://aka.ms/Azure-NZ-response)
- [<span data-ttu-id="26107-141">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="26107-141">Dynamics 365</span></span>](https://aka.ms/d365-nz-response)
- [<span data-ttu-id="26107-142">Intune</span><span class="sxs-lookup"><span data-stu-id="26107-142">Intune</span></span>](https://aka.ms/Intune-NZ-response)
- [<span data-ttu-id="26107-143">Office 365</span><span class="sxs-lookup"><span data-stu-id="26107-143">Office 365</span></span>](https://aka.ms/O365-NZ-Response)
- [<span data-ttu-id="26107-144">Power BI</span><span class="sxs-lookup"><span data-stu-id="26107-144">Power BI</span></span>](https://download.microsoft.com/download/5/1/7/51726B9B-2E76-49C4-9D4F-A36BF025CB93/Response-to-GCIO-105-questions-Power-BI.pdf)
