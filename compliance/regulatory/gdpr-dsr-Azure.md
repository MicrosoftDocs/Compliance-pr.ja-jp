---
title: GDPR および CCPA のための Azure データ主体要求
description: Azure 製品、サービス、管理ツールを使用して、DSR に応じて個人データを検索して操作する方法について説明します。
keywords: Microsoft 365、Microsoft 365 Education、Microsoft 365 ドキュメント、GDPR、CCPA
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
- GDPR
- M365-security-compliance
- MS-Compliance
hideEdit: true
titleSuffix: Microsoft GDPR
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 8d4dc89e8733db718491fcaa7c69b51e7b6d74f2
ms.sourcegitcommit: fb379d1110a9a86c7f9bab8c484dc3f4b3dfd6f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2021
ms.locfileid: "53089851"
---
# <a name="azure-data-subject-requests-for-the-gdpr-and-ccpa"></a><span data-ttu-id="ea86c-104">GDPR および CCPA のための Azure データ主体要求</span><span class="sxs-lookup"><span data-stu-id="ea86c-104">Azure Data Subject Requests for the GDPR and CCPA</span></span>

## <a name="introduction-to-data-subject-requests-dsrs"></a><span data-ttu-id="ea86c-105">データ主体要求 (DSR) の概要</span><span class="sxs-lookup"><span data-stu-id="ea86c-105">Introduction to Data Subject Requests (DSRs)</span></span>

<span data-ttu-id="ea86c-p101">欧州連合の [一般データ保護規則 (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) は、雇用主または他の種類の機関や組織 (*データ コントローラー* または単に *コントローラー* と呼ばれます) によって収集された個人データを管理する権限を個人 (同規則にでは *データ主体* と呼ばれます) に与えます。GDPR での個人データは、特定されたまたは特定可能な自然人に関連するすべてのデータと、非常に幅広く定義されています。GDPR では、個人データに対するデータ主体固有の権限が付与されます。このような権限には、個人データのコピーの取得、個人データの修正の要求、個人データの処理の制限、個人データの削除、または別のコントローラーに移動できる電子的な形式での個人データの受け取りが含まれます。データ 主体からコントローラーに個人データへのアクション実行を求める正式な要求は、*データ主体要求* または DSR と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p101">The European Union [General Data Protection Regulation (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) gives rights to people (known in the regulation as *data subjects*) to manage the personal data that has been collected by an employer or other type of agency or organization (known as the *data controller* or just *controller*). Personal data is defined very broadly under the GDPR as any data that relates to an identified or identifiable natural person. The GDPR gives data subjects specific rights to their personal data; these rights include obtaining copies of personal data, requesting corrections to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller. A formal request by a data subject to a controller to take an action on their personal data is called a *Data Subject Request* or DSR.</span></span>

<span data-ttu-id="ea86c-110">同様に、カリフォルニア州消費者プライバシー法 (CCPA) では、個人情報の削除、アクセスおよび受信 (移植性) など、GDPR のデータ主体の権利に類似している権利を含む、カリフォルニア州の消費者のプライバシーの権利および義務を規定します。</span><span class="sxs-lookup"><span data-stu-id="ea86c-110">Similarly, the California Consumer Privacy Act (CCPA), provides privacy rights and obligations to California consumers, including rights similar to GDPR's Data Subject Rights, such as the right to delete, access and receive (portability) their personal information.</span></span> <span data-ttu-id="ea86c-111">また、CCPA では、特定の開示、権利の行使を選択する際の差別に対する保護、"売上" として分類された特定のデータ転送の "オプトアウト/オプトイン" 要件を規定します。</span><span class="sxs-lookup"><span data-stu-id="ea86c-111">The CCPA also provides for certain disclosures, protections against discrimination when electing exercise rights, and "opt-out/ opt-in" requirements for certain data transfers classified as "sales".</span></span> <span data-ttu-id="ea86c-112">「販売」は広く定義されており、有価約因に関するデータの共有を含みます。</span><span class="sxs-lookup"><span data-stu-id="ea86c-112">Sales are broadly defined to include the sharing of data for a valuable consideration.</span></span> <span data-ttu-id="ea86c-113">CCPA の詳細については、「[カリフォルニア州消費者プライバシー法](offering-ccpa.md)」と「[カリフォルニア州消費者プライバシー法に関する FAQ](ccpa-faq.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea86c-113">For more information about the CCPA, see the [California Consumer Privacy Act](offering-ccpa.md) and the [California Consumer Privacy Act FAQ](ccpa-faq.md).</span></span>

<span data-ttu-id="ea86c-p103">このガイドでは、DSR への対応として個人データを見つけて処理するコントローラーのお客様を支援する目的で、Microsoft の製品、サービス、管理ツールをどのように使用できるかを説明します。特に、Microsoft クラウドにある個人データを検出、アクセス、処理する方法を示します。このガイドで説明するプロセスの概要は次のとおりです:</span><span class="sxs-lookup"><span data-stu-id="ea86c-p103">The guide discusses how to use Microsoft products, services and administrative tools to help our controller customers find and act on personal data to respond to DSRs. Specifically, this includes how to find, access, and act on personal data that reside in the Microsoft cloud. Here's a quick overview of the processes outlined in this guide:</span></span>

- <span data-ttu-id="ea86c-117">**検出:** 検索および検出ツールを使用して、DSR の対象である可能性がある顧客データを簡単に検索します。</span><span class="sxs-lookup"><span data-stu-id="ea86c-117">**Discover:** Use search and discovery tools to more easily find customer data that may be the subject of a DSR.</span></span> <span data-ttu-id="ea86c-118">可能性のある応答ドキュメントが収集されると、以下の手順に示す 1 つ以上の DSR アクションを実行して、要求に応答できます。</span><span class="sxs-lookup"><span data-stu-id="ea86c-118">Once potentially responsive documents are collected, you can perform one or more of the DSR actions described in the following steps to respond to the request.</span></span> <span data-ttu-id="ea86c-119">または、DSR への応答に関する組織のガイドラインを要求が満たしていないと判断する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="ea86c-119">Alternatively, you may determine that the request doesn't meet your organization's guidelines for responding to DSRs.</span></span>
- <span data-ttu-id="ea86c-120">**アクセス:** Microsoft クラウドにある個人データを取り出し、要求がある場合は、データ主体が利用できるコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ea86c-120">**Access:** Retrieve personal data that resides in the Microsoft cloud and, if requested, make a copy of it that can be available to the data subject.</span></span>
- <span data-ttu-id="ea86c-121">**修正:** 必要に応じて、個人データを変更したり、要求された他の操作を個人データに対して実行したりします。</span><span class="sxs-lookup"><span data-stu-id="ea86c-121">**Rectify:** Make changes or implement other requested actions on the personal data, where applicable.</span></span>
- <span data-ttu-id="ea86c-122">**制限:** さまざまな Azure サービスのライセンスを削除するか、可能な場合は該当するサービスを無効にすることで、個人データの処理を制限します。</span><span class="sxs-lookup"><span data-stu-id="ea86c-122">**Restrict:** Restrict the processing of personal data, either by removing licenses for various Azure services or turning off the desired services where possible.</span></span> <span data-ttu-id="ea86c-123">また、データを Microsoft クラウドから削除してオンプレミスまたは別の場所で保持することもできます。</span><span class="sxs-lookup"><span data-stu-id="ea86c-123">You can also remove data from the Microsoft cloud and retain it on-premises or at another location.</span></span>
- <span data-ttu-id="ea86c-124">**削除:** Microsoft クラウドに格納されていた個人データを完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="ea86c-124">**Delete:** Permanently remove personal data that resided in the Microsoft cloud.</span></span>
- <span data-ttu-id="ea86c-125">**エクスポート/受信 (移植性):** 個人データまたは個人情報の電子コピー (コンピューターで読み取り可能な形式) をデータ主体に提供します。</span><span class="sxs-lookup"><span data-stu-id="ea86c-125">**Export/Receive (Portability):** Provide an electronic copy (in a machine-readable format) of personal data or personal information to the data subject.</span></span> <span data-ttu-id="ea86c-126">CCPA における個人情報とは、識別された人、または識別可能な人に関するあらゆる情報のことです。</span><span class="sxs-lookup"><span data-stu-id="ea86c-126">Personal information under the CCPA is any information relating to an identified or identifiable person.</span></span> <span data-ttu-id="ea86c-127">個人の私的、公的、または職業上の役割による区別はありません。</span><span class="sxs-lookup"><span data-stu-id="ea86c-127">There is no distinction between a person's private, public, or work roles.</span></span> <span data-ttu-id="ea86c-128">"個人情報" と定義された用語は、GDPR における "個人データ" とほぼ同義です。</span><span class="sxs-lookup"><span data-stu-id="ea86c-128">The defined term "personal information" roughly lines up with "personal data" under GDPR.</span></span> <span data-ttu-id="ea86c-129">ただし、CCPA では家族データおよび世帯データも含まれます。</span><span class="sxs-lookup"><span data-stu-id="ea86c-129">However, the CCPA also includes family and household data.</span></span> <span data-ttu-id="ea86c-130">CCPA の詳細については、「[カリフォルニア州消費者プライバシー法](offering-ccpa.md)」と「[カリフォルニア州消費者プライバシー法に関する FAQ](ccpa-faq.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea86c-130">For more information about the CCPA, see the [California Consumer Privacy Act](offering-ccpa.md) and the [California Consumer Privacy Act FAQ](ccpa-faq.md).</span></span>

<span data-ttu-id="ea86c-131">このガイドの各セクションでは、Microsoft クラウド内の個人データに関する DSR への対応としてデータ コントローラー組織が実行できる技術的な手順の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="ea86c-131">Each section in this guide outlines the technical procedures that a data controller organization can take to respond to a DSR for personal data in the Microsoft cloud.</span></span>

## <a name="terminology"></a><span data-ttu-id="ea86c-132">用語集</span><span class="sxs-lookup"><span data-stu-id="ea86c-132">Terminology</span></span>

<span data-ttu-id="ea86c-133">このガイドに関連する用語を以下に定義します。</span><span class="sxs-lookup"><span data-stu-id="ea86c-133">The following provides definitions of terms that are relevant to this guide.</span></span>

- <span data-ttu-id="ea86c-134">**管理者:** 単独または他者と共同で、個人データの処理に関する目的と手段を決定する自然人や法人、公的機関、団体、その他の組織。そのような処理の目的と手段が EU 法もしくは加盟国の法律によって決定される場合、コントローラーまたはその指名に関する具体的な基準が EU 法または加盟国の法律によって提供される場合があります。</span><span class="sxs-lookup"><span data-stu-id="ea86c-134">**Controller:** The natural or legal person, public authority, agency or other body which, alone or jointly with others, determines the purposes and means of the processing of personal data; where the purposes and means of such processing are determined by Union or Member State law, the controller, or the specific criteria for its nomination may be provided for by Union or Member State law.</span></span>
- <span data-ttu-id="ea86c-135">**個人データおよびデータ主体:** 特定されたまたは特定可能な自然人 ('データ主体') に関するあらゆる情報。特定可能な自然人とは、その者の名前、ID 番号、位置データ、オンライン ID、または当該自然人に固有の 1 つ以上の特に身体的、生理学的、遺伝的、心理的、経済的、文化的、社会的な識別情報などの要素を参照することにより、直接または間接的に特定することができる者のことです。</span><span class="sxs-lookup"><span data-stu-id="ea86c-135">**Personal data and data subject:** Any information relating to an identified or identifiable natural person ('data subject'); an identifiable natural person is one who can be identified, directly or indirectly, in particular by reference to an identifier such as a name, an identification number, location data, an online identifier or to one or more factors specific to the physical, physiological, genetic, mental, economic, cultural, or social identity of that natural person.</span></span>
- <span data-ttu-id="ea86c-136">**処理者:** 管理者に代わって個人データを処理する自然人または法人、公的機関、団体、その他の組織。</span><span class="sxs-lookup"><span data-stu-id="ea86c-136">**Processor:** A natural or legal person, public authority, agency, or other body, which processes personal data on behalf of the controller.</span></span>
- <span data-ttu-id="ea86c-137">**顧客データ:** これは、顧客または顧客の代理が エンタープライズ サービスの使用を通じて Microsoft に提供する、テキスト、音声、ビデオ、画像ファイル、およびソフトウェアを含むすべてのデータのことです。</span><span class="sxs-lookup"><span data-stu-id="ea86c-137">**Customer Data:** All data, including all text, sound, video, or image files, and software, that are provided to Microsoft by, or on behalf of, a customer through use of the enterprise service.</span></span> <span data-ttu-id="ea86c-138">顧客データには次の両方が含まれます: (1) 特定を可能にするエンド ユーザーの情報 (例: Azure Active Directory でのユーザー名と連絡先情報)、および (2) 特定のサービスでお客様がアップロードまたは作成する顧客コンテンツ (例: Azure Storage アカウント内の顧客コンテンツ、Azure SQL データベースの顧客コンテンツ、Azure Virtual Machines でのお客様の仮想マシン イメージ)。</span><span class="sxs-lookup"><span data-stu-id="ea86c-138">Customer Data includes both (1) identifiable information of end users (for example, user names and contact information in Azure Active Directory) and Customer Content that a customer uploads into or creates in specific services (for example, customer content in an Azure Storage account, customer content of an Azure SQL Database, or a customer's virtual machine image in Azure Virtual Machines).</span></span>
- <span data-ttu-id="ea86c-139">**システム生成ログ:** Microsoft がエンタープライズ サービスをユーザーに提供するうえで役立つ、Microsoft により生成されるログおよび関連データ。</span><span class="sxs-lookup"><span data-stu-id="ea86c-139">**System-Generated Logs:** Logs and related data generated by Microsoft that help Microsoft provide enterprise services to users.</span></span> <span data-ttu-id="ea86c-140">システム生成ログには主に固有 ID などの仮名化データが含まれています。固有 ID とは一般的に、それ自体は特定の個人を識別しないものの、エンタープライズ サービスをユーザーに提供するために使われるシステム生成番号です。</span><span class="sxs-lookup"><span data-stu-id="ea86c-140">System-generated logs contain primarily pseudonymized data, such as unique identifiers — typically a number generated by the system that cannot on its own identify an individual person but is used to deliver the enterprise services to users.</span></span> <span data-ttu-id="ea86c-141">また、ユーザー名などの、特定を可能にするエンド ユーザーの情報がシステム生成ログに含まれることもあります。</span><span class="sxs-lookup"><span data-stu-id="ea86c-141">System-generated logs may also contain identifiable information about end users, such as a user name.</span></span>

## <a name="how-to-use-this-guide"></a><span data-ttu-id="ea86c-142">このガイドの使用方法</span><span class="sxs-lookup"><span data-stu-id="ea86c-142">How to use this guide</span></span>

<span data-ttu-id="ea86c-143">このガイドは次のような 2 部構成になっています。</span><span class="sxs-lookup"><span data-stu-id="ea86c-143">This guide consists of two parts:</span></span>

- <span data-ttu-id="ea86c-144">**第 1 部: 顧客データに関するデータ サブジェクト要求に対応する:** このガイドの第 1 部では、アプリケーションで作成されたデータにアクセスし、データを修正、制限、削除、エクスポートする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ea86c-144">**Part 1: Responding to Data Subject Requests for Customer Data:** Part 1 of this guide discusses how to access, rectify, restrict, delete, and export data from applications in which you have authored data.</span></span> <span data-ttu-id="ea86c-145">このセクションでは、カスタマー コンテンツとエンド ユーザー個人情報の両方に対して DSR を実行する方法について詳しく述べます。</span><span class="sxs-lookup"><span data-stu-id="ea86c-145">This section details how to execute DSRs against both Customer Content and also identifiable information of end users.</span></span>
- <span data-ttu-id="ea86c-146">**第 2 部: システム生成ログに関するデータ主体の要求に対応する:** Microsoft のエンタープライズ サービスを利用する際、Microsoft がサービスを提供するために使われるシステム生成ログという情報が生成されます。</span><span class="sxs-lookup"><span data-stu-id="ea86c-146">**Part 2: Responding to Data Subject Requests for System-Generated Logs:** When you use Microsoft's enterprise services, Microsoft generates some information, known as System-Generated Logs, in order to provide the service.</span></span> <span data-ttu-id="ea86c-147">このガイドの第 2 部では、Azure でこのような情報にアクセスしたり、削除したり、エクスポートしたりする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ea86c-147">Part 2 of this guide discusses how to access, delete, and export such information for Azure.</span></span>

## <a name="understanding-dsrs-for-azure-active-directory-and-microsoft-service-accounts"></a><span data-ttu-id="ea86c-148">Azure Active Directory および Microsoft サービス アカウントに関する DSR について</span><span class="sxs-lookup"><span data-stu-id="ea86c-148">Understanding DSRs for Azure Active Directory and Microsoft service accounts</span></span>

<span data-ttu-id="ea86c-p111">お客様企業へのサービス提供を考慮するとき、特定の Azure Active Directory (AAD) テナント内のコンテキストで常に DSR の実行について理解する必要があります。特に、DSR は特定の AAD テナントの内部で常に実行されます。あるユーザーが複数のテナントに参加する場合、要求を受け取った特定のテナントのコンテキスト内で *のみ*、その DSR が実行されることを強調することが重要です。あるお客様企業からの DSR を実行しても、隣接するお客様企業のデータは影響を **受けない** という点を理解することは重要です。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p111">When considering services provided to enterprise customers, execution of DSRs must always be understood within the context of a specific Azure Active Directory (AAD) tenant. Notably, DSRs are always executed within a given AAD tenant. If a user is participating in multiple tenants, it is important to emphasize that a given DSR is *only* executed within the context of the specific tenant the request was received within. This is critical to understand as it means the execution of a DSR by one enterprise customer **will not** impact the data of an adjacent enterprise customer.</span></span>

<span data-ttu-id="ea86c-p112">また、Microsoft Service Accounts (MSA) に関しても、お客様企業に提供されるサービスのコンテキスト内で同じことが当てはまります。*ある AAD テナントに関連付けられた* MSA アカウントに対する DSR 実行では、そのテナント内のデータ **のみ** が対象となります。さらに、テナント内の MSA アカウントを扱う際には次の点を理解することが重要です:</span><span class="sxs-lookup"><span data-stu-id="ea86c-p112">The same also applies for Microsoft Service Accounts (MSA) within the context of services provided to an enterprise customer: execution of a DSR against an MSA account *associated with an AAD tenant* **will only** pertain to data within the tenant. In addition, it is important to understand the following when handling MSA accounts within a tenant:</span></span>

- <span data-ttu-id="ea86c-p113">MSA ユーザーが Azure サブスクリプションを作成すると、そのサブスクリプションは AAD テナントであるかのように扱われます。その結果、DSR の範囲は上記のようにテナント内となります。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p113">If an MSA user creates an Azure subscription, the subscription will be handled as if it were an AAD tenant. Consequently, DSRs are scoped within the tenant as described above.</span></span>
- <span data-ttu-id="ea86c-p114">MSA アカウントを介して作成された Azure サブスクリプションが削除された場合、実際の MSA アカウントには影響が **ありません**。ここでも、上記のように、Azure サブスクリプション内で実行される DSR はテナント自体の範囲に限定されます。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p114">If an Azure subscription created via an MSA account is deleted, **it will not affect** the actual MSA account. Again, as noted above, DSRs executing within the Azure subscription are limited to the scope of the tenant itself.</span></span>

<span data-ttu-id="ea86c-p115">**特定のテナント外部の** MSA アカウント自体に対する DSR は、カスタマー プライバシー ダッシュボードを介して実行されます。詳しくは、Windows データ サブジェクト要求ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p115">DSRs against an MSA account itself, **outside a given tenant**, are executed via the Consumer Privacy Dashboard. Please refer to the Windows Data Subject Request Guide for further details.</span></span>

## <a name="part-1-dsr-guide-for-customer-data"></a><span data-ttu-id="ea86c-161">第 1 部: 顧客データに関する DSR ガイド</span><span class="sxs-lookup"><span data-stu-id="ea86c-161">Part 1: DSR Guide for customer data</span></span>

### <a name="executing-dsrs-against-customer-data"></a><span data-ttu-id="ea86c-162">顧客データに対する DSR の実行</span><span class="sxs-lookup"><span data-stu-id="ea86c-162">Executing DSRs against customer data</span></span>

<span data-ttu-id="ea86c-p116">特定のお客様データにアクセスし、それを削除したりエクスポートしたりするには、Azure ポータルを使用するか、特定のサービス用の既存のアプリケーション プログラミング インターフェイス (API) やユーザー インターフェイス (UI) を直接使用することができます (後者は *製品内エクスペリエンス* とも呼ばれます)。このような製品内エクスペリエンスについての詳細は、各サービスのリファレンス ドキュメントに記載されています。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p116">Microsoft provides the ability to access, delete, and export certain Customer Data through the Azure Portal and also directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services (also referred to as *in-product experiences*). Details regarding such in-product experiences are described in the respective services' reference documentation.</span></span>

>[!IMPORTANT]  
> <span data-ttu-id="ea86c-p117">製品内 DSR をサポートするサービスでは、そのサービスのアプリケーション プログラミング インターフェイス (API) またはユーザー インターフェイス (UI) を直接使用し、該当する CRUD (作成、読み取り、更新、削除) 操作を記述する必要があります。したがって、特定のデータ主体の要求全体を完了するには Azure ポータル内での DSR 実行に加えて特定のサービス内での DSR の実行が必要です。詳細については、特定のサービスのリファレンス ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p117">Services supporting in-product DSRs require direct usage of the service's application programming interface (API) or user interface (UI), describing applicable CRUD (create, read, update, delete) operations. Consequently, execution of DSRs within a given service must be done in addition to execution of a DSR within the Azure Portal in order to complete a full request for a given data subject. Please refer to specific services' reference documentation for further details.</span></span>

### <a name="step-1-discover"></a><span data-ttu-id="ea86c-168">ステップ 1: 検出</span><span class="sxs-lookup"><span data-stu-id="ea86c-168">Step 1: Discover</span></span>

<span data-ttu-id="ea86c-p118">DSR への対応の第一歩は、要求の対象となる個人データを見つけることです。この第 1 ステップ (該当する個人データの検出と確認) により、DSR の承認/拒否に関する組織の要件を DSR が満たしているかどうかを判断することができます。たとえば、該当する個人データを検出して確認した後、その要求を実行すると他者の権利や自由が侵害される恐れがあるので、その要求は組織の要件に適合しないと判断する場合があります。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p118">The first step in responding to a DSR is to find the personal data that is the subject of the request. This first step — finding and reviewing the personal data at issue — will help you determine whether a DSR meets your organization's requirements for honoring or declining a DSR. For example, after finding and reviewing the personal data at issue, you may determine the request doesn't meet your organization's requirements because doing so may adversely affect the rights and freedoms of others.</span></span>

<span data-ttu-id="ea86c-172">データが見つかったら、データ主体の要求に対応するために特定の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="ea86c-172">After you find the data, you can then perform the specific action to satisfy the request by the data subject.</span></span>

<span data-ttu-id="ea86c-p119">[Azure Active Directory](https://azure.microsoft.com/services/active-directory/) は、Microsoft が提供するクラウド ベースのマルチテナント ディレクトリおよびアイデンティティ管理サービスです。[Azure Active Directory](https://azure.microsoft.com/services/active-directory/) (AAD) 環境にある個人データを含むエンド ユーザー個人情報 (顧客や従業員のユーザー プロファイルなど) およびユーザー勤務先情報を見つけるには、[Azure Portal](https://portal.azure.com/) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p119">[Azure Active Directory](https://azure.microsoft.com/services/active-directory/) is Microsoft's cloud-based, multi-tenant directory and identity management service. You can locate identifiable information of end users, such as customer and employee user profiles and user work information that contain personal data in your [Azure Active Directory](https://azure.microsoft.com/services/active-directory/) (AAD) environment by using the [Azure portal](https://portal.azure.com/).</span></span>

<span data-ttu-id="ea86c-p120">特定のユーザーの個人データを検出または変更する必要がある場合には、これが特に役立ちます。また、ユーザー プロファイルや勤務先情報を追加したり変更したりすることもできます。ディレクトリのグローバル管理者であるアカウントを使用してサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p120">This is particularly helpful if you want to find or change personal data for a specific user. You can also add or change user profile and work information. You must sign in with an account that's a global admin for the directory.</span></span>

#### <a name="how-do-i-locate-or-view-user-profile-and-work-information"></a><span data-ttu-id="ea86c-178">ユーザー プロファイルや勤務先情報を検出または表示する方法</span><span class="sxs-lookup"><span data-stu-id="ea86c-178">How do I locate or view user profile and work information?</span></span>

1. <span data-ttu-id="ea86c-179">ディレクトリのグローバル管理者であるアカウントを使用して [Azure Portal](https://portal.azure.com/) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="ea86c-179">Sign in to the [Azure portal](https://portal.azure.com/) with an account that's a global admin for the directory.</span></span>

2. <span data-ttu-id="ea86c-180">[**Azure Active Directory**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea86c-180">Select **Azure Active Directory**.</span></span>

     ![[すべてのサービス] を選択します](../media/gdpr-azure-dsr-azure-portal.png)

3. <span data-ttu-id="ea86c-182">[**ユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea86c-182">Select **Users**.</span></span>

     ![ユーザーを選択します](../media/gdpr-azure-dsr-azure-all-users.png)

4. <span data-ttu-id="ea86c-184">[**すべてのユーザー**] ブレードで、リストからユーザーを選択し、そのユーザーのブレードの [**プロファイル**] を選択すると、ユーザー プロファイル情報が表示されます。そこには個人データが含まれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ea86c-184">On the **All users** blade, select a user from the list, and then, on the blade for the selected user, select **Profile** to view user profile information that might contain personal data.</span></span>

    ![プロファイルを選択します](../media/gdpr-azure-dsr-azure-user-profile.png)

5. <span data-ttu-id="ea86c-186">ユーザー プロファイル情報を追加または変更する必要がある場合は、コマンド バーの [**編集**] を選択し、追加または変更を行った後に、[**保存**] を選択します。 </span><span class="sxs-lookup"><span data-stu-id="ea86c-186">If you need to add or change user profile information, you can do so by selecting **Edit** in the command bar, then select **Save** after making changes.</span></span>

#### <a name="service-specific-interfaces"></a><span data-ttu-id="ea86c-187">サービス固有のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="ea86c-187">Service-specific interfaces</span></span>

<span data-ttu-id="ea86c-p121">特定のサービス用の既存のアプリケーション プログラミング インターフェイス (API) またはユーザー インターフェイス (UI) を介して顧客データを直接検出できます。各サービスの参照ドキュメントに詳細が記載され、該当する CRUD (作成、読み取り、更新、削除) 操作について記述しています。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p121">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services' reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

### <a name="step-2-access"></a><span data-ttu-id="ea86c-190">ステップ 2: アクセス</span><span class="sxs-lookup"><span data-stu-id="ea86c-190">Step 2: Access</span></span>

<span data-ttu-id="ea86c-p122">DSR に応答する可能性のある個人データを含む顧客データを発見したら、担当者および組織は、データ主体に提供するデータを決定する必要があります。実際のドキュメントのコピー、適切に編集したバージョン、または共有できると判断した部分のスクリーン ショットを提供することができます。アクセス要求に対するこれらの各応答には、応答性の高いデータを含むドキュメントまたはその他のアイテムのコピーを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p122">After you've found Customer Data containing personal data that is potentially responsive to a DSR, it is up to you and your organization to decide which data to provide to the data subject. You can provide them with a copy of the actual document, an appropriately redacted version, or a screenshot of the portions you have deemed appropriate to share. For each of these responses to an access request, you will have to retrieve a copy of the document or other item that contains the responsive data.</span></span>

<span data-ttu-id="ea86c-194">データ主体にコピーを提供する際には、別のデータ主体に関する個人情報などの機密情報を削除または編集することが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ea86c-194">When providing a copy to the data subject, you may have to remove or redact personal information about other data subjects and any confidential information.</span></span>

#### <a name="azure-active-directory"></a><span data-ttu-id="ea86c-195">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ea86c-195">Azure Active Directory</span></span>

<span data-ttu-id="ea86c-p123">お客様企業のテナント管理者は、ポータルおよび製品内エクスペリエンスを介して DSR アクセス要求を管理できます。DSR アクセス要求では (a) エンド ユーザーに関する個人情報、および (b) システム生成ログを含むユーザー個人データへのアクセスが扱われます。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p123">Microsoft offers both a portal and in-product experiences providing the enterprise customer's tenant administrator the capability to manage DSR access requests. DSR Access requests allow for access of the personal data of the user, including: (a) identifiable information about an end-user and (b) system-generated logs.</span></span>

#### <a name="service-specific-interfaces"></a><span data-ttu-id="ea86c-198">サービス固有のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="ea86c-198">Service-specific interfaces</span></span>

<span data-ttu-id="ea86c-p124">特定のサービス用の既存のアプリケーション プログラミング インターフェイス (API) またはユーザー インターフェイス (UI) を介して顧客データを直接検出できます。各サービスの参照ドキュメントに詳細が記載され、該当する CRUD (作成、読み取り、更新、削除) 操作について記述しています。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p124">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services' reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

### <a name="step-3-rectify"></a><span data-ttu-id="ea86c-201">ステップ 3: 修正</span><span class="sxs-lookup"><span data-stu-id="ea86c-201">Step 3: Rectify</span></span>

<span data-ttu-id="ea86c-p125">組織のデータに含まれる個人データを修正するようデータ サブジェクトが依頼した場合、組織とその担当者は、要求を承認するのが適切かどうか判断する必要があります。データの修正には、ドキュメントまたは他の種類のアイテムの中の個人データを編集、変更、または削除するアクションが含まれます。Microsoft サポートおよび FastTrack データに対してこれを行う最も便利な方法を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p125">If a data subject has asked you to rectify the personal data that resides in your organization's data, you and your organization will have to determine whether it's appropriate to honor the request. Rectifying the data may include taking actions such as editing, redacting, or removing personal data from a document or other type or item. The most expedient way to do this for Microsoft Support and FastTrack data is provided below.</span></span>

#### <a name="azure-active-directory"></a><span data-ttu-id="ea86c-205">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ea86c-205">Azure Active Directory</span></span>

<span data-ttu-id="ea86c-p126">お客様企業は、各 Microsoft サービスの性質に応じて、限定的な編集を含む DSR 修正要求の管理機能を利用できます。Microsoft はデータ プロセッサとして、システム生成ログの修正機能を提供しません。これはシステム生成ログが実際のアクティビティを表し、Microsoft サービス内のイベントの履歴レコードを形成するためです。Azure Active Directory に関しては、下記で説明するように、エンド ユーザーの個人情報を限定的に編集できる機能があります。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p126">Enterprise customers have the ability to manage DSR rectify requests, including limited editing features per the nature of a given Microsoft service. As a data processor, Microsoft does not offer the ability to correct system-generated logs as it reflects factual activities and constitutes a historical record of events within Microsoft services. With respect to Azure Active Directory, limited editing features exist to rectify identifiable information about an end-user, as described further below.</span></span>

##### <a name="azure-active-directory-rectifycorrect-inaccurate-or-incomplete-personal-data"></a><span data-ttu-id="ea86c-209">Azure Active Directory: 不正確または不完全な個人データの修正</span><span class="sxs-lookup"><span data-stu-id="ea86c-209">Azure Active Directory: rectify/correct inaccurate or incomplete personal data</span></span>

<span data-ttu-id="ea86c-p127">[Azure Active Directory](https://azure.microsoft.com/services/active-directory/) (AAD) 環境で [Azure Portal](https://portal.azure.com/) を使用すると、ユーザーの氏名、役職、住所、電話番号などの個人データを含むエンド ユーザー個人情報 (顧客や従業員のユーザー プロファイルなど) やユーザーの勤務先情報を修正、更新、または削除することができます。ディレクトリのグローバル管理者であるアカウントを使用してサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p127">You can correct, update, or delete identifiable information about end users, such as customer and employee user profiles and user work information that contain personal data, such as a user's name, work title, address, or phone number, in your [Azure Active Directory](https://azure.microsoft.com/services/active-directory/) (AAD) environment by using the [Azure portal](https://portal.azure.com/). You must sign in with an account that's a global admin for the directory.</span></span>

###### <a name="how-do-i-correct-or-update-user-profile-and-work-information-in-azure-active-directory"></a><span data-ttu-id="ea86c-212">Azure Active Directory でユーザー プロファイルや勤務先情報を修正または更新する方法</span><span class="sxs-lookup"><span data-stu-id="ea86c-212">How do I correct or update user profile and work information in Azure Active Directory?</span></span>

1. <span data-ttu-id="ea86c-213">ディレクトリのグローバル管理者であるアカウントを使用して [Azure Portal](https://portal.azure.com/) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="ea86c-213">Sign in to the [Azure portal](https://portal.azure.com/) with an account that's a global admin for the directory.</span></span>

2. <span data-ttu-id="ea86c-214">[**Azure Active Directory**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea86c-214">Select **Azure Active Directory**.</span></span>

    ![[すべてのサービス] を選択します](../media/gdpr-azure-dsr-azure-portal.png)

3. <span data-ttu-id="ea86c-216">[**ユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea86c-216">Select **Users**.</span></span>

    ![ユーザーを選択します](../media/gdpr-azure-dsr-azure-all-users.png)

4. <span data-ttu-id="ea86c-218">[**すべてのユーザー**] ブレードで、リストからユーザーを選択し、そのユーザーのブレードの [**プロファイル**] を選択して修正または更新が必要なユーザー プロファイル情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="ea86c-218">On the **All users** blade, select a user from the list, and then, on the blade for the selected user, select **Profile** to view the user profile information that needs to be corrected or updated.</span></span>

    ![ユーザー プロファイルを選択する](../media/gdpr-azure-dsr-azure-user-profile.png)

5. <span data-ttu-id="ea86c-220">コマンド バーの [**編集**] を選択して勤務先情報を含むユーザー プロファイル情報を修正または更新し、更新が完了したら [ **保存**] を選択します。 </span><span class="sxs-lookup"><span data-stu-id="ea86c-220">Correct or update the user profile information including work information by selecting **Edit** in the command bar, then select **Save** after making changes.</span></span>

    ![[編集] を選択する](../media/gdpr-azure-dsr-azure-edit-user-profile.png)

#### <a name="service-specific-interfaces"></a><span data-ttu-id="ea86c-222">サービス固有のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="ea86c-222">Service-Specific Interfaces</span></span>

<span data-ttu-id="ea86c-p128">特定のサービス用の既存のアプリケーション プログラミング インターフェイス (API) またはユーザー インターフェイス (UI) を介して顧客データを直接検出できます。各サービスの参照ドキュメントに詳細が記載され、該当する CRUD (作成、読み取り、更新、削除) 操作について記述しています。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p128">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services' reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

### <a name="step-4-restrict"></a><span data-ttu-id="ea86c-225">ステップ 4: 制限</span><span class="sxs-lookup"><span data-stu-id="ea86c-225">Step 4: Restrict</span></span>

<span data-ttu-id="ea86c-p129">個人データの処理を制限するようデータ サブジェクトから依頼されることがあります。その場合、Azure ポータルと既存のアプリケーション プログラミング インターフェイス (API) またはユーザー インターフェイス (UI) の両方を使用できます。お客様企業のテナント管理者はこれらのエクスペリエンスを利用し、データ エクスポートとデータ削除を組み合わせて、このような DSR を管理できます。お客様は (a) アカウント、(b) システム生成ログ、(c) 関連するログを含むユーザー個人データの電子的なコピーを (1) エクスポートし、その後、Microsoft システム内に保管されているアカウントおよび関連するデータを (2) 削除できます。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p129">Data subjects may request that you restrict processing of their personal data. We provide both the Azure Portal and pre-existing application programming interfaces (APIs) or user interfaces (UIs). These experiences provide the enterprise customer's tenant administrator the capability to manage such DSRs through a combination of data export and data deletion. A customer may (1) export an electronic copy of the personal data of the user, including (a) account(s), (b) system-generated logs, and (c) associated logs, followed with (2) deletion of the account and associated data residing within Microsoft systems.</span></span>

### <a name="step-5-delete"></a><span data-ttu-id="ea86c-230">ステップ 5: 削除</span><span class="sxs-lookup"><span data-stu-id="ea86c-230">Step 5: Delete</span></span>

<span data-ttu-id="ea86c-231">組織のサポート データからの個人データの削除による「削除する権利」は GDPR における主要な保護の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="ea86c-231">The "right to erasure" by the removal of personal data from an organization's Customer Data is a key protection in the GDPR.</span></span> <span data-ttu-id="ea86c-232">個人データの削除には、監査ログ情報を除く、すべての個人データとシステム生成ログの削除が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ea86c-232">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span> <span data-ttu-id="ea86c-233">あるユーザーが **回復可能削除** (下記を参照) されると、そのアカウントが 30 日間にわたり無効になります。</span><span class="sxs-lookup"><span data-stu-id="ea86c-233">When a user is **soft deleted** (see details below), the account is disabled for 30 days.</span></span> <span data-ttu-id="ea86c-234">この 30 日間に何のアクションも行われない場合、そのユーザーは **完全削除** (これも下記を参照) されます。 </span><span class="sxs-lookup"><span data-stu-id="ea86c-234">If no further action is taken during this 30-day period, the user is **permanently deleted** (again, see details below).</span></span> <span data-ttu-id="ea86c-235">**完全削除** された場合、そのユーザーのアカウント、個人データ、システム生成ログがその後 30 日以内に抹消されます。</span><span class="sxs-lookup"><span data-stu-id="ea86c-235">Upon a **permanent delete**, the user's account, personal data, and system-generated logs are expunged within an additional 30 days.</span></span> <span data-ttu-id="ea86c-236">テナント管理者が即時に **完全削除** を発行した場合、ユーザーのアカウント、個人データ、システム生成ログがその後 30 日以内に抹消されます。</span><span class="sxs-lookup"><span data-stu-id="ea86c-236">If a tenant admin immediately issues a **permanent delete**, the user's account, personal data, and system-generated logs are expunged within 30 days of issuance.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ea86c-237">ユーザーをテナントから削除するには、テナント管理者でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="ea86c-237">You must be a tenant administrator to delete a user from the tenant.</span></span>

#### <a name="delete-a-user-and-associated-data-through-the-azure-portal"></a><span data-ttu-id="ea86c-238">Azure Portal を介してユーザーおよび関連データを削除する</span><span class="sxs-lookup"><span data-stu-id="ea86c-238">Delete a user and associated data through the Azure portal</span></span>

<span data-ttu-id="ea86c-239">データ サブジェクトから削除要求を受け取った後、Azure Portal を使用してユーザーおよび関連する個人情報、さらにシステム生成ログを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="ea86c-239">After you receive a delete request for a data subject, you can use the Azure portal to delete both a user and the associated personal information as well as system-generated logs.</span></span>

<span data-ttu-id="ea86c-p131">このデータを削除すると、それとともにテナントからユーザーが削除されます。ユーザーは最初に回復可能な方法で削除されます。つまり、回復可能削除のマークが付いてから 30 日以内にテナント管理者がアカウントを回復することができます。30 日後は、アカウントがテナントから自動的かつ完全に削除されます。この 30 日が経過する前に、回復可能削除されたユーザーをごみ箱から手動で削除できます。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p131">Deleting this data also means deleting the user from the tenant. Users are initially soft-deleted, which means the account can be recovered by a tenant admin within 30 days of being marked for soft-delete. After 30 days, the account is automatically, and permanently, deleted from the tenant. Prior to that 30 days, you can manually delete a soft-deleted user from the recycle bin.</span></span>

<span data-ttu-id="ea86c-244">テナントからユーザーを削除する大まかな手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ea86c-244">Here's the high-level process for deleting users from your tenant.</span></span>

1. <span data-ttu-id="ea86c-245">Azure Portal に移動し、ユーザーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="ea86c-245">Go to the Azure portal and locate the user.</span></span>

2. <span data-ttu-id="ea86c-p132">ユーザーを削除します。ユーザーを最初に削除すると、そのユーザーのアカウントがごみ箱に送られます。**この時点で、ユーザーは回復可能削除された状態になります。つまり、アカウントが無効になりますが、Azure Active Directory から抹消されたわけではありません。**</span><span class="sxs-lookup"><span data-stu-id="ea86c-p132">Delete the user. When you initially delete the user, the user's account is sent to the Recycle Bin. **At this point, the user is soft deleted, meaning the account is disabled, but not expunged from Azure Active Directory.**</span></span>

3. <span data-ttu-id="ea86c-p133">最近削除されたユーザーのリストに移動して、ユーザーを永続的に削除します。**この時点でユーザーが永続的に削除されます (完全削除ともいう)。つまりアカウントが Azure Active Directory から抹消済みになります**</span><span class="sxs-lookup"><span data-stu-id="ea86c-p133">Go to the Recently deleted users list and permanently delete the user. **At this point the user is permanently deleted (also known as hard deleted), meaning the account has been expunged from Azure Active Directory**</span></span>

###### <a name="to-delete-a-user-from-an-azure-tenant"></a><span data-ttu-id="ea86c-251">Azure テナントからユーザーを削除するには</span><span class="sxs-lookup"><span data-stu-id="ea86c-251">To delete a user from an Azure tenant</span></span>

1. <span data-ttu-id="ea86c-252">ディレクトリのグローバル管理者のアカウントを使用して [Azure Portal](https://portal.azure.com/) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="ea86c-252">Sign in to the [Azure portal](https://portal.azure.com/) with an account that's a global admin for the directory.</span></span>

2. <span data-ttu-id="ea86c-253">[**Azure Active Directory**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea86c-253">Select **Azure Active Directory**.</span></span>

    ![[すべてのサービス] を選択します](../media/gdpr-azure-dsr-azure-portal.png)

3. <span data-ttu-id="ea86c-255">[**ユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea86c-255">Select **Users**.</span></span>

    ![ユーザーを選択します](../media/gdpr-azure-dsr-azure-all-users.png)

4. <span data-ttu-id="ea86c-257">削除するユーザーの横にあるボックスをオンにして **[ユーザーの削除]** を選択し、ユーザー削除を確認するボックスで **[はい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea86c-257">Check the box next to the user you want to delete, select **Delete user**, and then select **Yes** in the box asking if you want to delete the user.</span></span>

    ![ユーザーの管理](../media/gdpr-azure-dsr-azure-selected-user.png)

5. <span data-ttu-id="ea86c-259">[ **すべてのユーザー**]  ブレードで、[ **削除済みユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea86c-259">On the **All users** blade, select **Deleted users**.</span></span>

    ![ユーザー プロファイルを表示します](../media/gdpr-azure-dsr-azure-deleted-user.png)

4. <span data-ttu-id="ea86c-261">同じユーザーを再び選択し、コマンド バーで　 **[完全に削除する]** を選択して、確認を求めるボックスで  **[はい]**   を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea86c-261">Select the same user again, select **Delete permanently** in the command bar, and then select **Yes** in the box asking if you're sure.</span></span>

>[!IMPORTANT]  
><span data-ttu-id="ea86c-p134">**[はい]** をクリックすると、ユーザーおよび関連するすべてのデータとシステム生成ログが完全に削除され、この操作を元に戻せないことに注意してください。間違ってこの操作を行った場合、手動でユーザーをテナントに再び追加する必要があります。関連するデータとシステム生成ログは回復不能です。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p134">Be aware that by clicking **Yes** you are permanently, and irrevocably, deleting the user and all associated data and system-generated logs. If you do this by mistake, you'll have to manually add the user back to the tenant. The associated data and system-generated logs are non-recoverable.</span></span>

   ![ユーザー勤務先情報を表示します](../media/gdpr-azure-dsr-azure-permanently-deleted-user.png)

#### <a name="service-specific-interfaces"></a><span data-ttu-id="ea86c-266">サービス固有のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="ea86c-266">Service-specific interfaces</span></span>

<span data-ttu-id="ea86c-p135">特定のサービス用の既存のアプリケーション プログラミング インターフェイス (API) またはユーザー インターフェイス (UI) を介して顧客データを直接検出できます。各サービスの参照ドキュメントに詳細が記載され、該当する CRUD (作成、読み取り、更新、削除) 操作について記述しています。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p135">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services' reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

## <a name="step-6-export"></a><span data-ttu-id="ea86c-269">ステップ 6: エクスポート</span><span class="sxs-lookup"><span data-stu-id="ea86c-269">Step 6: Export</span></span>

<span data-ttu-id="ea86c-p136">「データ移植性の権利」により、データ サブジェクトは、別のデータ コントローラーに移送できる電子的な形式 (つまり、「構造化され、一般使用される、マシン読み取り可能かつ相互運用可能な形式」) の個人データのコピーを要求できます。Azure をご利用の組織は、ネイティブ JSON 形式のデータを指定の Azure Storage コンテナーにエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p136">The "right of data portability" allows a data subject to request a copy of their personal data in an electronic format (that's a "structured, commonly used, machine read-able, and interoperable format") that may be transmitted to another data controller. Azure supports this by enabling your organization to export the data in the native JSON format, to your specified Azure Storage Container.</span></span>

>[!IMPORTANT]
><span data-ttu-id="ea86c-272">ユーザー データをテナントからエクスポートするには、テナント管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea86c-272">You must be a tenant administrator to export user data from the tenant.</span></span>

### <a name="azure-active-directory"></a><span data-ttu-id="ea86c-273">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ea86c-273">Azure Active Directory</span></span>

<span data-ttu-id="ea86c-274">顧客データに関して、お客様企業のテナント管理者はポータルと製品エクスペリエンスの両方を利用して、エンド ユーザーに関する特定可能な情報のエクスポート要求を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="ea86c-274">With respect to Customer Data, Microsoft offers both a portal and in-product experiences providing the enterprise customer's tenant administrator the capability to manage export requests for identifiable information about an end user.</span></span>

### <a name="service-specific-interfaces"></a><span data-ttu-id="ea86c-275">サービス固有のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="ea86c-275">Service-specific interfaces</span></span>

<span data-ttu-id="ea86c-p137">特定のサービス用の既存のアプリケーション プログラミング インターフェイス (API) またはユーザー インターフェイス (UI) を介して顧客データを直接検出できます。各サービスの参照ドキュメントに詳細が記載され、該当する CRUD (作成、読み取り、更新、削除) 操作について記述しています。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p137">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services' reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

## <a name="part-2-system-generated-logs"></a><span data-ttu-id="ea86c-278">第 2 部: システム生成ログ</span><span class="sxs-lookup"><span data-stu-id="ea86c-278">Part 2: System-Generated Logs</span></span>

<span data-ttu-id="ea86c-279">さらに、ユーザーによる Azure 使用状況に関連する特定のシステム生成ログにアクセスし、それを削除したりエクスポートしたりできます。</span><span class="sxs-lookup"><span data-stu-id="ea86c-279">Microsoft also provides you with the ability to access, delete, and export certain system-generated logs associated with a user's use of Azure.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="ea86c-p138">システム生成ログを制限または修正する機能はサポートされていない点に注意してください。システム生成ログは、Microsoft クラウド内で実行された実際のアクションと診断データを形成し、そのようなデータが変更されるとアクションの履歴記録が損なわれ、詐欺やセキュリティのリスクが増大します。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p138">The ability to restrict or rectify system-generated logs is not supported. System-generated logs constitute factual actions conducted within the Microsoft cloud and diagnostic data, and modifications to such data would compromise the historical record of actions, increasing fraud and security risks.</span></span>

### <a name="executing-dsrs-against-system-generated-logs"></a><span data-ttu-id="ea86c-282">システム生成ログに対する DSR の実行</span><span class="sxs-lookup"><span data-stu-id="ea86c-282">Executing DSRs against System-Generated Logs</span></span>

<span data-ttu-id="ea86c-p139">Azure ポータルを使用したり、特定のサービス用のプログラマティック インターフェイスまたはユーザー インターフェイスを直接使用したりすることで、特定のシステム生成ログにアクセスし、削除/エクスポートすることができます。詳細については、各サービスの参照ドキュメンテーションに記載されています。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p139">Microsoft provides the ability to access, delete, and export certain system-generated logs through the Azure Portal and also directly via programmatic interfaces or user interfaces for specific services. Details are described in the respective services' reference documentation.</span></span>

>[!IMPORTANT]  
> <span data-ttu-id="ea86c-p140">製品内 DSR をサポートするサービスでは、そのサービスのアプリケーション プログラミング インターフェイス (API) またはユーザー インターフェイス (UI) を直接使用する必要があります。したがって、特定のデータ サブジェクトの要求全体を完了するには Azure ポータル内での DSR 実行に加えて製品内 DSR **を実行する必要があります。詳細については、特定のサービスの参照ドキュメントをご覧ください。**</span><span class="sxs-lookup"><span data-stu-id="ea86c-p140">Services supporting in-product DSRs require direct usage of the service's application programming interface (API) or user interface (UI). Consequently, execution of an in-product DSRs **must be done in addition to execution of a DSR within the Azure Portal in order to complete a full request for a given data subject. Please refer to specific services' reference documentation for further details.**</span></span>

### <a name="step-1-access"></a><span data-ttu-id="ea86c-287">手順 1: アクセス</span><span class="sxs-lookup"><span data-stu-id="ea86c-287">Step 1: Access</span></span>

<span data-ttu-id="ea86c-p141">組織内で特定のユーザーによる Azure 使用状況に関連するシステム生成ログにアクセスできるのは、テナント管理者のみです。アクセス要求に関して取得されるデータはマシン読み取り可能形式で提供され、データの関連先のサービスがユーザーにわかるようなファイルで提供されます。上記のように、サービスのセキュリティを損なう可能性のあるデータは取得対象データに含まれません。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p141">The tenant admin is the only person within your organization who can access system-generated logs associated with a particular user's use of Azure. The data retrieved for an access request will be provided in a machine-readable format and will be provided in files that will allow the user to know which services the data is associated with. As noted above, the data retrieved will not include data that may compromise the security of the service.</span></span>

#### <a name="azure-active-directory"></a><span data-ttu-id="ea86c-291">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ea86c-291">Azure Active Directory</span></span>

<span data-ttu-id="ea86c-p142">お客様企業のテナント管理者は、ポータルおよび製品内エクスペリエンスを介してアクセス要求を管理できます。アクセス要求では (a) エンド ユーザーに関する個人情報、および (b) サービス生成ログを含むユーザー個人データへのアクセスが扱われます。このプロセスは、第 1 部「ステップ 2: アクセス」の Azure Active Directory セクションと同じです。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p142">Microsoft offers both a portal and in-product experiences providing the enterprise customer's tenant administrator the capability to manage access requests. Access requests will allow for access of the personal data of the user, including: (a) identifiable information about an end user and (b) service-generated logs. The process is identical to that described in the Azure Active Directory section of Part 1, Step 2: Access.</span></span>

#### <a name="service-specific-interfaces"></a><span data-ttu-id="ea86c-295">サービス固有のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="ea86c-295">Service-specific interfaces</span></span>

<span data-ttu-id="ea86c-p143">特定のサービス用の既存のアプリケーション プログラミング インターフェイス (API) またはユーザー インターフェイス (UI) を介して顧客データを直接検出できます。各サービスの参照ドキュメントに詳細が記載され、該当する CRUD (作成、読み取り、更新、削除) 操作について記述しています。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p143">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services' reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

### <a name="step-2-delete"></a><span data-ttu-id="ea86c-298">ステップ 2: 削除</span><span class="sxs-lookup"><span data-stu-id="ea86c-298">Step 2: Delete</span></span>

<span data-ttu-id="ea86c-299">組織内で、Azure テナントの特定のユーザーに関する DSR 削除要求を実行できるのはテナント管理者だけです。</span><span class="sxs-lookup"><span data-stu-id="ea86c-299">The tenant admin is the only person within your organization who can execute a DSR delete request for a particular user within an Azure tenant.</span></span>

#### <a name="azure-active-directory"></a><span data-ttu-id="ea86c-300">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ea86c-300">Azure Active Directory</span></span>

<span data-ttu-id="ea86c-p144">お客様企業のテナント管理者は、ポータルおよび製品内エクスペリエンスを介して DSR 削除要求を管理できます。DSR 削除要求は、第 1 部、「ステップ 5: 削除」の「Azure Portal を介してユーザーおよび関連データを削除する」のセクションと同じ方法で扱われます。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p144">Microsoft offers both a portal and in-product experiences providing the enterprise customer's tenant administrator the capability to manage DSR delete requests. DSR delete requests follow the same as described in the Delete a user and associated data through the Azure portal section of Part 1, Step 5: Delete.</span></span>

#### <a name="service-specific-interfaces"></a><span data-ttu-id="ea86c-303">サービス固有のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="ea86c-303">Service-specific interfaces</span></span>

<span data-ttu-id="ea86c-p145">特定のサービス用の既存のアプリケーション プログラミング インターフェイス (API) またはユーザー インターフェイス (UI) を介して顧客データを直接検出できます。各サービスの参照ドキュメントに詳細が記載され、該当する CRUD (作成、読み取り、更新、削除) 操作について記述しています。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p145">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services' reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

### <a name="step-3-export"></a><span data-ttu-id="ea86c-306">ステップ 3: エクスポート</span><span class="sxs-lookup"><span data-stu-id="ea86c-306">Step 3: Export</span></span>

<span data-ttu-id="ea86c-p146">組織内で特定のユーザーによる Azure 使用状況に関連するシステム生成ログにアクセスできるのは、テナント管理者のみです。エクスポート要求に関して取得されるデータはマシン読み取り可能形式で提供され、データの関連先のサービスがユーザーにわかるようなファイルで提供されます。上記のように、サービスのセキュリティや安定性を損なう可能性のあるデータは取得対象データに含まれません。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p146">The tenant admin is the only person within your organization who can access system-generated logs associated with a particular user's use of Azure. The data retrieved for an export request will be provided in a machine-readable format and will be provided in files that will allow the user to know which services the data is associated with. As noted above, the data retrieved will not include data that may compromise the security or stability of the service.</span></span>

#### <a name="export-system-generated-logs-using-the-azure-portal"></a><span data-ttu-id="ea86c-310">Azure Portal を使用してシステム生成ログをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="ea86c-310">Export system-generated logs using the Azure portal</span></span>

<span data-ttu-id="ea86c-311">データ サブジェクトのエクスポート要求を受け取った後、Azure Portal を使用して、特定のユーザーに関連するシステム生成ログをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="ea86c-311">After you receive an export request for a data subject, you can use the Azure portal to export system-generated logs associated with a given user.</span></span>

<span data-ttu-id="ea86c-312">テナントからデータをエクスポートする大まかな手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ea86c-312">Here's the high-level process for exporting data from your tenant.</span></span>

1. <span data-ttu-id="ea86c-313">Azure Portal に移動し、ユーザーに代わってエクスポート要求を作成します。</span><span class="sxs-lookup"><span data-stu-id="ea86c-313">Go to the Azure portal and create an export request on behalf of the user.</span></span>
2. <span data-ttu-id="ea86c-314">データをエクスポートして、ファイルをユーザーに送ります。</span><span class="sxs-lookup"><span data-stu-id="ea86c-314">Export the data and send file to user.</span></span>

###### <a name="to-export-a-users-info-from-an-azure-tenant"></a><span data-ttu-id="ea86c-315">Azure テナントからユーザーの情報をエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="ea86c-315">To export a user's info from an Azure tenant</span></span>

1. <span data-ttu-id="ea86c-316">Azure Portal を開き、**[すべてのサービス]** を選択し、フィルターに「*policy*」と入力して **[ポリシー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea86c-316">Open the Azure portal, select **All services**, type *policy* into the filter, and then select **Policy**.</span></span>

     ![<span data-ttu-id="ea86c-317">[すべてのサービス] フィルター</span><span class="sxs-lookup"><span data-stu-id="ea86c-317">All services filter</span></span> ](../media/gdpr-azure-dsr-azure-policy.png)

2. <span data-ttu-id="ea86c-318">**[ポリシー]** ブレードで **[ユーザー プライバシー]** を選択し、**[ユーザー要求の管理]** を選択して、**[エクスポート要求の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea86c-318">In the **Policy** blade, select **User privacy**, select **Manage User Requests**, and then select **Add export request**.</span></span>

    ![<span data-ttu-id="ea86c-319">エクスポート要求を追加します</span><span class="sxs-lookup"><span data-stu-id="ea86c-319">Add export request</span></span> ](../media/gdpr-azure-dsr-azure-add-export-request.png)

3. <span data-ttu-id="ea86c-320">**[データ エクスポート要求]** に次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ea86c-320">Complete the **Export data request**:</span></span>

    ![新しいデータ エクスポート要求](../media/gdpr-azure-dsr-azure-export-data-request.png)

- <span data-ttu-id="ea86c-p147">**ユーザー**: エクスポートを要求した Azure Active Directory ユーザーの電子メール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p147">**User.** Type the email address of the Azure Active Directory user that requested the export.</span></span>
- <span data-ttu-id="ea86c-p148">**サブスクリプション**: リソース使用状況の報告とサービス料金の請求に使用するアカウントを選択します。これは Azure ストレージ アカウントの場所でもあります。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p148">**Subscription.** Select the account you use to report resource usage and to bill for services. This is also the location of your Azure storage account.</span></span>
- <span data-ttu-id="ea86c-p149">**ストレージ アカウント**: Azure Storage (Blob) の場所を選択します。詳しくは「[Microsoft Azure Storage の概要 – Blob ストレージ](/azure/storage/common/storage-introduction#blob-storage)」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p149">**Storage account.** Select the location of your Azure Storage (Blob). For more info, see the [Introduction to Microsoft Azure Storage — Blob storage](/azure/storage/common/storage-introduction#blob-storage) article.</span></span>
- <span data-ttu-id="ea86c-p150">**コンテナー**: エクスポートされたユーザー プライバシー データの保存場所として新しいコンテナーを作成するか、既存のものを選択します。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p150">**Container.** Create a new (or select an existing) container as the storage location for the user's exported privacy data.</span></span>

4. <span data-ttu-id="ea86c-332">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea86c-332">Select **Create**.</span></span>

<span data-ttu-id="ea86c-p151">エクスポート要求が [**保留中**] 状態になります。[**ユーザー プライバシー - 概要**] ブレードでレポートの状況を確認できます。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p151">The export request goes into **Pending** status. You can view the report status on the **User privacy — Overview** blade.</span></span>

>[!IMPORTANT]  
><span data-ttu-id="ea86c-335">個人データは複数のシステムから取得される可能性があるので、エクスポート プロセスが完了するまでに 1 か月かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ea86c-335">Because personal data can come from multiple systems, it's possible that the export process might take up to one month to complete.</span></span>

#### <a name="service-specific-interfaces"></a><span data-ttu-id="ea86c-336">サービス固有のインターフェイス</span><span class="sxs-lookup"><span data-stu-id="ea86c-336">Service-Specific Interfaces</span></span>

<span data-ttu-id="ea86c-p152">特定のサービス用の既存のアプリケーション プログラミング インターフェイス (API) またはユーザー インターフェイス (UI) を介して顧客データを直接検出できます。各サービスの参照ドキュメントに詳細が記載され、該当する CRUD (作成、読み取り、更新、削除) 操作について記述しています。</span><span class="sxs-lookup"><span data-stu-id="ea86c-p152">Microsoft provides the ability to discover Customer Data directly via pre-existing application programming interfaces (APIs) or user interfaces (UIs) for specific services. Details are described in the respective services' reference documentation, describing applicable CRUD (create, read, update, delete) operations.</span></span>

### <a name="notify-about-exporting-or-deleting-issues"></a><span data-ttu-id="ea86c-339">エクスポートまたは削除に関する問題を通知する</span><span class="sxs-lookup"><span data-stu-id="ea86c-339">Notify about exporting or deleting issues</span></span>

<span data-ttu-id="ea86c-340">Azure portal でデータをエクスポートまたは削除中に問題が発生した場合は、Azure ポータルの **[ヘルプとサポート]** ブレードに移動し、**[サブスクリプションの管理] > [サブスクリプションに必要なプライバシーとコンプライアンスの要求] > [プライバシー ブレードと GDPR 要求]** で新しいチケットを送信します。</span><span class="sxs-lookup"><span data-stu-id="ea86c-340">If you run into issues while exporting or deleting data from the Azure portal, go to the Azure portal **Help + Support** blade and submit a new ticket under **Subscription Management > Privacy and compliance requests for Subscriptions > Privacy Blade and GDPR Requests**.</span></span>

## <a name="learn-more"></a><span data-ttu-id="ea86c-341">詳細情報</span><span class="sxs-lookup"><span data-stu-id="ea86c-341">Learn more</span></span>

- [<span data-ttu-id="ea86c-342">Microsoft Trust Center</span><span class="sxs-lookup"><span data-stu-id="ea86c-342">Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
