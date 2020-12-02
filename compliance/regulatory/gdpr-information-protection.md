---
title: 情報保護
description: EU 一般データ保護規則 (GDPR) 向けの Microsoft 365 の情報保護機能について説明します。
keywords: Microsoft 365、Microsoft 365 Education、Microsoft 365 ドキュメント、GDPR
localization_priority: Priority
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 04/13/2018
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 28b1c76cedd2f232165ac5ad3ee8eb186af554a4
ms.sourcegitcommit: 626b0076d133e588cd28598c149a7f272fc18bae
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2020
ms.locfileid: "49508496"
---
# <a name="information-protection-for-gdpr-with-microsoft-365-capabilities"></a><span data-ttu-id="fa234-104">GDPR のための情報保護と Microsoft 365 の機能</span><span class="sxs-lookup"><span data-stu-id="fa234-104">Information protection for GDPR with Microsoft 365 capabilities</span></span>

<span data-ttu-id="fa234-p101">Microsoft 365 は、一般データ保護規則 (GDPR) に準拠するための豊富な機能を提供します。この記事では、推奨する機能の要約、および詳細情報へのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="fa234-p101">Microsoft 365 provides a rich set of capabilities to help you achieve compliance with the General Data Protection Regulation (GDPR). This article summarizes recommended capabilities with links to more information.</span></span>

<span data-ttu-id="fa234-107">マイクロソフトによる GDPR サポートの詳細については、Service Trust Portal の[はじめに: GDPR 責任のサポート](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa234-107">For more information about how Microsoft can help you with the GDPR, see [Get Started: Support for GDPR Accountability](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted) in the Service Trust Portal.</span></span>

## <a name="information-protection"></a><span data-ttu-id="fa234-108">情報保護</span><span class="sxs-lookup"><span data-stu-id="fa234-108">Information protection</span></span>

<span data-ttu-id="fa234-p102">Office 365 は、豊富なデータ管理機能を提供します。個人データの検索、分類、保護、監視の詳細については、[GDPR のための Office 365 の情報保護](https://docs.microsoft.com/microsoft-365/compliance/office-365-information-protection-for-gdpr)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa234-p102">Office 365 provides a rich set of data governance capabilities. For help with finding, classifying, protecting, and monitoring personal data, see [Office 365 Information Protection for GDPR](https://docs.microsoft.com/microsoft-365/compliance/office-365-information-protection-for-gdpr).</span></span>

<span data-ttu-id="fa234-111">ファイル共有、SharePoint Server、Exchange Server、Skype for Business Server、Project Server、Office Online Server を含むオンプレミス サーバーのヘルプについては、[オンプレミス Office サーバーに関する GDPR](https://docs.microsoft.com/microsoft-365/compliance/gdpr-for-office-servers) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa234-111">For help with on-premises servers, including file shares, SharePoint Server, Exchange Server, Skype for Business Server, Project Server, and Office Online Server, see [GDPR for on-premises Office servers](https://docs.microsoft.com/microsoft-365/compliance/gdpr-for-office-servers).</span></span> 

## <a name="identity-and-access-management"></a><span data-ttu-id="fa234-112">ID およびアクセス管理</span><span class="sxs-lookup"><span data-stu-id="fa234-112">Identity and access management</span></span>

<span data-ttu-id="fa234-113">Azure Active Directory とその他の Microsoft 365 機能は、ID やデバイスのデータへのアクセスを保護するための豊富な機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="fa234-113">Azure Active Directory and other Microsoft 365 capabilities provide a rich set of capabilities to protect access to your data from identities and devices:</span></span>

- <span data-ttu-id="fa234-114">多要素認証 (MFA)</span><span class="sxs-lookup"><span data-stu-id="fa234-114">Multi-factor authentication (MFA)</span></span>
- <span data-ttu-id="fa234-115">条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="fa234-115">Conditional access</span></span>
- <span data-ttu-id="fa234-116">Privileged Identity Management</span><span class="sxs-lookup"><span data-stu-id="fa234-116">Privileged identity management</span></span>
- <span data-ttu-id="fa234-117">モバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="fa234-117">Mobile device management</span></span>
- <span data-ttu-id="fa234-118">モバイル アプリケーション管理</span><span class="sxs-lookup"><span data-stu-id="fa234-118">Mobile application management</span></span>
- <span data-ttu-id="fa234-119">資格情報のハードウェア保護</span><span class="sxs-lookup"><span data-stu-id="fa234-119">Hardware protection for credentials</span></span>

<span data-ttu-id="fa234-120">Microsoft は、開始点として使用できる推奨設定を提供しています。</span><span class="sxs-lookup"><span data-stu-id="fa234-120">Microsoft provides a recommended configuration you can use as a starting point:</span></span>

- <span data-ttu-id="fa234-p103">[ID とデバイスのアクセス構成](https://docs.microsoft.com/microsoft-365/security/office-365-security/microsoft-365-policies-configurations): 3 層保護 (ベースライン、機密、高度な規制) を実現する推奨ポリシー構成。このガイダンスでは、Exchange Online および SharePoint Online (OneDrive for Business を含む) のための推奨ポリシーを記載します。</span><span class="sxs-lookup"><span data-stu-id="fa234-p103">[Identity and device access configurations](https://docs.microsoft.com/microsoft-365/security/office-365-security/microsoft-365-policies-configurations): Recommended policy configurations to achieve three tiers of protection (baseline, sensitive, highly regulated). This guidance includes recommended policies for Exchange Online and SharePoint Online (including OneDrive for Business).</span></span>
- <span data-ttu-id="fa234-123">[政治キャンペーン、非営利団体、その他のアジャイル組織のセキュリティに関するガイダンス](https://docs.microsoft.com/microsoft-365/security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o): これには同じポリシーのセットが含まれていますが、BYOD 環境と B2B アカウントのための追加のガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="fa234-123">[Security guidance for political campaigns, nonprofits, and other agile organizations](https://docs.microsoft.com/microsoft-365/security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o): This includes the same set of policies but provides more guidance for BYOD environments and for B2B accounts.</span></span>

## <a name="threat-protection"></a><span data-ttu-id="fa234-124">脅威保護</span><span class="sxs-lookup"><span data-stu-id="fa234-124">Threat Protection</span></span>

<span data-ttu-id="fa234-p104">Microsoft 365 サービス間での脅威保護を確立します。作業を開始するための、いくつかのリソースを紹介します。</span><span class="sxs-lookup"><span data-stu-id="fa234-p104">Threat protection is built across Microsoft 365 services. Here are a few resources to get you started:</span></span>

- <span data-ttu-id="fa234-p105">[Office 365 のセキュリティ ロードマップ: 最初の 30 日間、90 日間、およびそれ以後の優先事項](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)。このロードマップには、機能を実装するための推奨事項を記載します。</span><span class="sxs-lookup"><span data-stu-id="fa234-p105">[Office 365 security roadmap: Top priorities for the first 30 days, 90 days, and beyond](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap). This roadmap includes recommendations for implementing capabilities.</span></span> 
- <span data-ttu-id="fa234-129">[Office 365 で脅威から保護します](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)。</span><span class="sxs-lookup"><span data-stu-id="fa234-129">[Protect against threats in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats).</span></span> <span data-ttu-id="fa234-130">Microsoft 365 セキュリティ センターで実行できる保護のためのアクションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="fa234-130">Learn about protection actions you can take in the Microsoft 365 security center.</span></span>
- <span data-ttu-id="fa234-p107">[Windows の脅威保護](https://docs.microsoft.com/windows/security/threat-protection/)。Windows Defender Advanced Threat Protection とその他の Windows 10 の機能の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="fa234-p107">[Windows Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/). Learn more about Windows Defender Advanced Threat Protection and other capabilities in Windows 10.</span></span>

## <a name="learn-more"></a><span data-ttu-id="fa234-133">詳細情報</span><span class="sxs-lookup"><span data-stu-id="fa234-133">Learn more</span></span>

[<span data-ttu-id="fa234-134">Microsoft Trust Center</span><span class="sxs-lookup"><span data-stu-id="fa234-134">Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
