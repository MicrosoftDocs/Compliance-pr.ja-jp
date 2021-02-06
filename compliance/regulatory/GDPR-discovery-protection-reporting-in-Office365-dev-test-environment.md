---
title: Microsoft 365 開発/テスト環境における GDPR の検出、保護、および報告
description: Microsoft 365 開発/テスト環境の GDPR において、個人を特定できる情報 (PII) を構成して実証する方法について説明します。
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
- MS-Compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
titleSuffix: Microsoft GDPR
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 92c98d710c34f1304ddc0a2e8acfe09c4570e97c
ms.sourcegitcommit: 21ed42335efd37774ff5d17d9586d5546147241a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50121636"
---
# <a name="gdpr-discovery-protection-and-reporting-in-the-devtest-environment"></a><span data-ttu-id="6ba3f-103">開発/テスト環境における GDPR の検出、保護、および報告</span><span class="sxs-lookup"><span data-stu-id="6ba3f-103">GDPR discovery, protection, and reporting in the dev/test environment</span></span>

 <span data-ttu-id="6ba3f-104">**概要:** Microsoft 365 の GDPR 機能をデモします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-104">**Summary:** Demonstrate GDPR capabilities in Microsoft 365.</span></span>

<span data-ttu-id="6ba3f-105">この記事では、Microsoft 365 開発/テスト環境で一般データ保護規則 (GDPR) 用に個人を特定できる情報 (PII) の検出、保護、および報告を構成してデモする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-105">This article describes how you configure and demonstrate personally identifiable information (PII) discovery, protection, and reporting for the General Data Protection Regulation (GDPR) in a Microsoft 365 dev/test environment.</span></span>

## <a name="phase-1-create-and-configure-your-trial-microsoft-365-subscription"></a><span data-ttu-id="6ba3f-106">フェーズ 1: 試用版の Microsoft 365 サブスクリプションを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="6ba3f-106">Phase 1: Create and configure your trial Microsoft 365 subscription</span></span>

<span data-ttu-id="6ba3f-107">まず、「[Microsoft 365 開発/テスト環境のフェーズ 2](/Office365/Enterprise/office-365-dev-test-environment#phase-2-create-an-office-365-trial-subscription)」の記事内の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-107">First, follow the steps in [Phase 2 of the Microsoft 365 dev/test environment](/Office365/Enterprise/office-365-dev-test-environment#phase-2-create-an-office-365-trial-subscription) article.</span></span>

<span data-ttu-id="6ba3f-108">次に、以下の手順を使用して、電子情報開示マネージャーを構成します。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-108">Next, use these steps to configure the eDiscovery manager:</span></span>

1. <span data-ttu-id="6ba3f-109">全体管理者アカウントを使用して、Microsoft 365 試用版テナントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-109">Sign in to your Microsoft 365 trial tenant with your global administrator account.</span></span>
2. <span data-ttu-id="6ba3f-110">Microsoft 365 のホーム ページで、**[セキュリティとコンプライアンス]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-110">From the Microsoft 365 home page, click **Security & Compliance**.</span></span>
3. <span data-ttu-id="6ba3f-111">新しい [セキュリティとコンプライアンス] タブで、**[アクセス許可]** > **[電子情報開示マネージャー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-111">From the new Security & Compliance tab, click **Permissions** > **eDiscovery Manager**.</span></span>
4. <span data-ttu-id="6ba3f-112">電子情報開示マネージャーの **[編集]** をクリックしてから、**[電子情報開示マネージャーの選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-112">Click **Edit** for eDiscovery Manager, and then click **Choose eDiscovery Manager**.</span></span>
5. <span data-ttu-id="6ba3f-113">**[+ 追加]** をクリックして、自分の全体管理者アカウント名を探し、そのアカウントを電子情報開示マネージャーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-113">Click **+ Add**, search for your global administrator account name and add your global administrator account as an eDiscovery Manager.</span></span>
6. <span data-ttu-id="6ba3f-114">**[完了]** > **[保存]** > **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-114">Click **Done** > **Save** > **Close**.</span></span>

## <a name="phase-2-add-personally-identifiable-information-to-your-tenant"></a><span data-ttu-id="6ba3f-115">フェーズ 2: 個人を特定できる情報をテナントに追加する</span><span class="sxs-lookup"><span data-stu-id="6ba3f-115">Phase 2: Add personally identifiable information to your tenant</span></span>

<span data-ttu-id="6ba3f-116">このフェーズでは、国際銀行口座番号 (IBAN) の事例用として PII を含むドキュメントを作成し、Microsoft 365 開発/テスト環境内の SharePoint Online サイトに保存します。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-116">In this phase, you create a document with PII for a set of example International Banking Account Numbers (IBANs) and store it on a SharePoint Online site in your Microsoft 365 dev/test environment.</span></span>

1. <span data-ttu-id="6ba3f-117">ローカル コンピューターで、Microsoft Word を開きます。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-117">On your local computer, open Microsoft Word.</span></span>
2. <span data-ttu-id="6ba3f-118">Word ファイルに次の表を貼り付け、そのファイルを 'IBANs.docx' としてローカル コンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-118">Paste the following table in the Word file and save it as 'IBANs.docx' on your local computer.</span></span>

   |<span data-ttu-id="6ba3f-119">数値</span><span class="sxs-lookup"><span data-stu-id="6ba3f-119">Number</span></span>|<span data-ttu-id="6ba3f-120">国</span><span class="sxs-lookup"><span data-stu-id="6ba3f-120">Country</span></span>|<span data-ttu-id="6ba3f-121">コード</span><span class="sxs-lookup"><span data-stu-id="6ba3f-121">Code</span></span>|<span data-ttu-id="6ba3f-122">IBAN</span><span class="sxs-lookup"><span data-stu-id="6ba3f-122">IBAN</span></span>|
   |---|---|---|---|
   |<span data-ttu-id="6ba3f-123">1</span><span class="sxs-lookup"><span data-stu-id="6ba3f-123">1</span></span>|<span data-ttu-id="6ba3f-124">オーストリア SEPA</span><span class="sxs-lookup"><span data-stu-id="6ba3f-124">Austria SEPA</span></span>|<span data-ttu-id="6ba3f-125">AT</span><span class="sxs-lookup"><span data-stu-id="6ba3f-125">AT</span></span>|<span data-ttu-id="6ba3f-126">AT611904300234573201</span><span class="sxs-lookup"><span data-stu-id="6ba3f-126">AT611904300234573201</span></span>|
   |<span data-ttu-id="6ba3f-127">2</span><span class="sxs-lookup"><span data-stu-id="6ba3f-127">2</span></span>|<span data-ttu-id="6ba3f-128">ブルガリア SEPA</span><span class="sxs-lookup"><span data-stu-id="6ba3f-128">Bulgaria SEPA</span></span>|<span data-ttu-id="6ba3f-129">BG</span><span class="sxs-lookup"><span data-stu-id="6ba3f-129">BG</span></span>|<span data-ttu-id="6ba3f-130">BG80BNBG96611020345678</span><span class="sxs-lookup"><span data-stu-id="6ba3f-130">BG80BNBG96611020345678</span></span>|
   |<span data-ttu-id="6ba3f-131">3</span><span class="sxs-lookup"><span data-stu-id="6ba3f-131">3</span></span>|<span data-ttu-id="6ba3f-132">デンマーク SEPA</span><span class="sxs-lookup"><span data-stu-id="6ba3f-132">Denmark SEPA</span></span>|<span data-ttu-id="6ba3f-133">DK</span><span class="sxs-lookup"><span data-stu-id="6ba3f-133">DK</span></span>|<span data-ttu-id="6ba3f-134">DK5000400440116243</span><span class="sxs-lookup"><span data-stu-id="6ba3f-134">DK5000400440116243</span></span>|
   |<span data-ttu-id="6ba3f-135">4</span><span class="sxs-lookup"><span data-stu-id="6ba3f-135">4</span></span>|<span data-ttu-id="6ba3f-136">フィンランド SEPA</span><span class="sxs-lookup"><span data-stu-id="6ba3f-136">Finland SEPA</span></span>|<span data-ttu-id="6ba3f-137">FI</span><span class="sxs-lookup"><span data-stu-id="6ba3f-137">FI</span></span>|<span data-ttu-id="6ba3f-138">FI2112345600000785</span><span class="sxs-lookup"><span data-stu-id="6ba3f-138">FI2112345600000785</span></span>|
   |<span data-ttu-id="6ba3f-139">5</span><span class="sxs-lookup"><span data-stu-id="6ba3f-139">5</span></span>|<span data-ttu-id="6ba3f-140">フランス SEPA</span><span class="sxs-lookup"><span data-stu-id="6ba3f-140">France SEPA</span></span>|<span data-ttu-id="6ba3f-141">FR</span><span class="sxs-lookup"><span data-stu-id="6ba3f-141">FR</span></span>|<span data-ttu-id="6ba3f-142">FR1420041010050500013M02606</span><span class="sxs-lookup"><span data-stu-id="6ba3f-142">FR1420041010050500013M02606</span></span>|
   |<span data-ttu-id="6ba3f-143">6</span><span class="sxs-lookup"><span data-stu-id="6ba3f-143">6</span></span>|<span data-ttu-id="6ba3f-144">ドイツ SEPA</span><span class="sxs-lookup"><span data-stu-id="6ba3f-144">Germany SEPA</span></span>|<span data-ttu-id="6ba3f-145">DE</span><span class="sxs-lookup"><span data-stu-id="6ba3f-145">DE</span></span>|<span data-ttu-id="6ba3f-146">DE89370400440532013000</span><span class="sxs-lookup"><span data-stu-id="6ba3f-146">DE89370400440532013000</span></span>|
   |<span data-ttu-id="6ba3f-147">7</span><span class="sxs-lookup"><span data-stu-id="6ba3f-147">7</span></span>|<span data-ttu-id="6ba3f-148">ギリシャ SEPA</span><span class="sxs-lookup"><span data-stu-id="6ba3f-148">Greece SEPA</span></span>|<span data-ttu-id="6ba3f-149">GR</span><span class="sxs-lookup"><span data-stu-id="6ba3f-149">GR</span></span>|<span data-ttu-id="6ba3f-150">GR1601101250000000012300695</span><span class="sxs-lookup"><span data-stu-id="6ba3f-150">GR1601101250000000012300695</span></span>|
   |<span data-ttu-id="6ba3f-151">8</span><span class="sxs-lookup"><span data-stu-id="6ba3f-151">8</span></span>|<span data-ttu-id="6ba3f-152">イタリア SEPA</span><span class="sxs-lookup"><span data-stu-id="6ba3f-152">Italy SEPA</span></span>|<span data-ttu-id="6ba3f-153">IT</span><span class="sxs-lookup"><span data-stu-id="6ba3f-153">IT</span></span>|<span data-ttu-id="6ba3f-154">GR1601101250000000012300695</span><span class="sxs-lookup"><span data-stu-id="6ba3f-154">GR1601101250000000012300695</span></span>|
   |<span data-ttu-id="6ba3f-155">9</span><span class="sxs-lookup"><span data-stu-id="6ba3f-155">9</span></span>|<span data-ttu-id="6ba3f-156">オランダ SEPA</span><span class="sxs-lookup"><span data-stu-id="6ba3f-156">Netherlands SEPA</span></span>|<span data-ttu-id="6ba3f-157">NL</span><span class="sxs-lookup"><span data-stu-id="6ba3f-157">NL</span></span>|<span data-ttu-id="6ba3f-158">NL91ABNA0417164300</span><span class="sxs-lookup"><span data-stu-id="6ba3f-158">NL91ABNA0417164300</span></span>|
   |<span data-ttu-id="6ba3f-159">10</span><span class="sxs-lookup"><span data-stu-id="6ba3f-159">10</span></span>|<span data-ttu-id="6ba3f-160">ポーランド SEPA</span><span class="sxs-lookup"><span data-stu-id="6ba3f-160">Poland SEPA</span></span>|<span data-ttu-id="6ba3f-161">PL</span><span class="sxs-lookup"><span data-stu-id="6ba3f-161">PL</span></span>|<span data-ttu-id="6ba3f-162">PL27114020040000300201355387</span><span class="sxs-lookup"><span data-stu-id="6ba3f-162">PL27114020040000300201355387</span></span>|

   <span data-ttu-id="6ba3f-163">メモ:- このサンプル データ セットは、公開されている情報から得られたもので、テスト目的でのみ使用することを意図しています。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-163">Note:- This sample data set is derived from publicly available information and is intended to be used for test purposes only.</span></span>

3. <span data-ttu-id="6ba3f-164">ブラウザーの新しいタブで、「**https://**\<YourTenantName\>**.sharepoint.com**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-164">In a new tab of your browser, type:  **https://**\<YourTenantName\>**.sharepoint.com**</span></span>
4. <span data-ttu-id="6ba3f-p101">**[ドキュメント]** をクリックして、このサイトのドキュメント ライブラリを開きます。新しいリスト エクスペリエンス ツアーのプロンプトが表示されたら、終了するまで **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-p101">Click **Documents** to open the document library for this site. If you're prompted for a new list experience tour, click **Next** until it's finished.</span></span>
5. <span data-ttu-id="6ba3f-167">**[アップロード]** > **[ファイル]** をクリックして、手順 2 で作成した IBANs.docx を選択します。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-167">Click **Upload** > **Files** and select the IBANs.docx you created in step 2.</span></span>

## <a name="phase-3-demonstrate-data-discovery"></a><span data-ttu-id="6ba3f-168">フェーズ 3: データ検出をデモする</span><span class="sxs-lookup"><span data-stu-id="6ba3f-168">Phase 3: Demonstrate data discovery</span></span>

<span data-ttu-id="6ba3f-169">このフェーズでは、IBAN を含むコンテンツに基づいて、フェーズ 2 で作成して保存したドキュメントを検索するデモを示します。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-169">In this phase, you demonstrate search to find the document created and stored in Phase 2, based on its content containing IBANs.</span></span>

1. <span data-ttu-id="6ba3f-170">[セキュリティとコンプライアンス] タブで、**[ホーム]** をクリックしてから、**[検索と調査]** > **[コンテンツ検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-170">From the Security & Compliance tab, click **Home**, and then click **Search & investigation** > **Content search**.</span></span>
2. <span data-ttu-id="6ba3f-171">**+** をクリックすることで、新しい検索項目を作成します。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-171">Create a new search item by clicking on **+**.</span></span>
3. <span data-ttu-id="6ba3f-172">新しいウィンドウで、次の情報を指定します。a.</span><span class="sxs-lookup"><span data-stu-id="6ba3f-172">In a new window, provide the following information: a.</span></span> <span data-ttu-id="6ba3f-173">名前: IBAN 検索 b.</span><span class="sxs-lookup"><span data-stu-id="6ba3f-173">Name: IBAN Search b.</span></span> <span data-ttu-id="6ba3f-174">何を検索しますか?: **検索する特定のサイトを選択** (**+** をクリック) してから、サイトの URL (**https://**\<YourTenantName\>**.sharepoint.com/**) を入力します。c.</span><span class="sxs-lookup"><span data-stu-id="6ba3f-174">Where do you want us to look?: **Choose specific sites to search** (click **+**), and then enter the site's URL: **https://**\<YourTenantName\>**.sharepoint.com/** c.</span></span> <span data-ttu-id="6ba3f-175">**[追加]** をクリックし、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-175">Click **Add**, and then click **OK**.</span></span> <span data-ttu-id="6ba3f-176">警告が表示されたら、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-176">If you see a Warning, click **OK**.</span></span>
    <span data-ttu-id="6ba3f-177">d. </span><span class="sxs-lookup"><span data-stu-id="6ba3f-177">d.</span></span> <span data-ttu-id="6ba3f-178">**[新しい検索]** ウィンドウで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-178">Click **Next** on a **New search** window.</span></span>
    <span data-ttu-id="6ba3f-179">e. </span><span class="sxs-lookup"><span data-stu-id="6ba3f-179">e.</span></span> <span data-ttu-id="6ba3f-180">**何を検索しますか?**: **SensitiveType:"国際銀行口座番号 (IBAN)"** と入力して、**[検索]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-180">For **What do you want us to look for?**: **SensitiveType:"International Banking Account Number (IBAN)"**, and then click **Search**.</span></span>

4. <span data-ttu-id="6ba3f-181">**IBAN 検索** の結果に少なくとも 1 つの項目が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-181">Make sure you see at least one item listed in the **IBAN Search** results.</span></span>

## <a name="phase-4-create-a-custom-sensitive-information-type-via-powershell"></a><span data-ttu-id="6ba3f-182">フェーズ 4: PowerShell 経由でカスタムの機密情報の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="6ba3f-182">Phase 4: Create a custom sensitive information type via PowerShell</span></span>

<span data-ttu-id="6ba3f-p103">このフェーズでは、Microsoft PowerShell を使用して、架空の Contoso 社のカスタムの機密情報の種類を作成します。Contoso 社では、Contoso 顧客番号 (CCN) を使用して、顧客データベース内の各顧客を識別しています。CCN の構造は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-p103">In this phase, you create a custom sensitive information type for the fictional Contoso Corporation using Microsoft PowerShell.  Contoso uses a Contoso Customer Number (CCN) to identify each customer in their customer database. A CCN consists of the following structure:</span></span>

- <span data-ttu-id="6ba3f-186">レコードが作成された年を表す 2 桁の数字。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-186">Two digits to represent the year that the record was created.</span></span>
  - <span data-ttu-id="6ba3f-187">Contoso 社は 2002 年に設立されました。そのため、最小値は 02 です。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-187">Contoso was founded in 2002; therefore, the earliest possible value would be 02.</span></span>
- <span data-ttu-id="6ba3f-188">レコードを作成したパートナー代理店を表す 3 桁の数字。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-188">Three digits to represent the partner agency that created the record.</span></span>
  - <span data-ttu-id="6ba3f-189">使用可能な代理店の値の範囲は 000 ～ 999 です。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-189">Possible agency values range from 000 to 999.</span></span>
- <span data-ttu-id="6ba3f-190">基幹業務を表す英字。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-190">An alphabetic character to represent the line of business.</span></span>
  - <span data-ttu-id="6ba3f-191">使用可能な値は a ～ z で、大文字と小文字を区別する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-191">Possible values are a-z and should be case insensitive.</span></span>
- <span data-ttu-id="6ba3f-192">4 桁のシリアル番号。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-192">A four-digit serial number.</span></span>
  - <span data-ttu-id="6ba3f-193">使用可能なシリアル番号の値の範囲は、0000 ～ 9999 です。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-193">Possible serial number values range from 0000 to 9999.</span></span>

<span data-ttu-id="6ba3f-p104">Contoso では、必ず、内部対応、外部対応、ドキュメント、およびその他の形式で CCN を使用して顧客を参照しています。また、この形式の個人を識別できる情報の使用に対して保護が適用されるように、Microsoft 365 コンテンツ内の CCN の使用を検出するためのカスタムの機密項目の種類が必要です。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-p104">Contoso always refers to customers by using a CCN in internal correspondence, external correspondence, documents, and other forms. Contoso needs a custom sensitive item type to detect the use of CCNs in Microsoft 365 content so that they may apply protection to the use of this form of personal identifiable information.</span></span>

1. <span data-ttu-id="6ba3f-196">「[セキュリティ/コンプライアンス センターの PowerShell に接続する](/powershell/exchange/connect-to-scc-powershell)」に記載されている多要素認証 (MFA) 接続の手順を使用して、全体管理者アカウントの UPN でセキュリティ/コンプライアンス センターに接続します。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-196">Use the multi-factor authentication (MFA) connection instructions in [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and connect to the Security & Compliance Center with UPN of your global administrator account.</span></span>

2. <span data-ttu-id="6ba3f-197">次の PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-197">Run the following PowerShell commands.</span></span>

   ```powershell
   #Create & start search for sample data
   $searchName = "Sample Customer Information Search"
   $searchQuery = "15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118"
   New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery
   Start-ComplianceSearch -Identity $searchName#Create & start search for sample data
   $searchName = "Sample Customer Information Search"
   $searchQuery = "15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118"
   New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery
   Start-ComplianceSearch -Identity $searchName
   ```

3. <span data-ttu-id="6ba3f-198">次の PowerShell コマンドを実行して、生成された GUID を表示順にコンピューター上で開いているメモ帳のインスタンスにコピーします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-198">Run the following PowerShell commands and copy the generated GUIDs to an open instance of Notepad on your computer in the order in which they are listed.</span></span>

   ```powershell
   #Generate three unique GUIDs
   Write-Host "GUID1 = "([guid]::NewGuid().Guid)
   Write-Host "GUID2 = "([guid]::NewGuid().Guid)
   Write-Host "GUID3 = "([guid]::NewGuid().Guid)
   ```

4. <span data-ttu-id="6ba3f-199">ローカル コンピューターで、メモ帳の別のインスタンスを開いて、次の内容を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-199">On your local computer, open another instance of Notepad and paste in the following content:</span></span>

   ```text
   <?xml version="1.0" encoding="utf-8"?>
   <RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce">
   <RulePack id="GUID1">
   <Version major="1" minor="0" build="0" revision="0" />
   <Publisher id="GUID2" />
   <Details defaultLangCode="en">
   <LocalizedDetails langcode="en">
   <PublisherName>Contoso Ltd.</PublisherName>
   <Name>Contoso Rule Package</Name>
   <Description>Defines Contoso's custom set of classification rules</Description>
   </LocalizedDetails>
   </Details>
   </RulePack>
   <Rules>
   <!-- Contoso Customer Number (CCN) -->
   <Entity id="GUID3" patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
   <IdMatch idRef="Regex_contoso_ccn" />
   <Match idRef="Keyword_contoso_ccn" />
   <Match idRef="Regex_eu_date" />
   </Pattern>
   </Entity>
   <Regex id="Regex_contoso_ccn">[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}</Regex>
   <Keyword id="Keyword_contoso_ccn">
   <Group matchStyle="word">
   <Term caseSensitive="false">customer number</Term>
   <Term caseSensitive="false">customer no</Term>
   <Term caseSensitive="false">customer #</Term>
   <Term caseSensitive="false">customer#</Term>
   <Term caseSensitive="false">Contoso customer</Term>
   </Group>
   </Keyword>
   <Regex id="Regex_eu_date"> (0?[1-9]|[12][0-9]|3[0-1])[\/-](0?[1-9]|1[0-2]|j\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)? |feb(ruary|ruari|rero|braio|ruar|br)?|f\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\x00e4rz|maart|apr(ile|il)?|abr(il)?|avril |may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)? |nov(ember|iembre|embre|embro)?|dec(ember)?|dic(iembre|embre)?|dez(ember|embro)?|d\x00e9c(embre)?)[ \/-](19|20)?[0-9]{2}</Regex>
   <LocalizedStrings>
   <Resource idRef="GUID3">
   <Name default="true" langcode="en-us">Contoso Customer Number (CCN)</Name>
   <Description default="true" langcode="en-us">Contoso Customer Number (CCN) that looks for additional keywords and EU formatted date</Description>
   </Resource>
   </LocalizedStrings>
   </Rules>
   </RulePackage>
   ```

5. <span data-ttu-id="6ba3f-200">手順 4 の XML テキスト内の GUID1、GUID2、および GUID3 の値を手順 3 の値に置換し、その内容を ContosoCCN.xml という名前でローカル コンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-200">Replace the values of GUID1, GUID2, and GUID3 in the XML text of step 4 with their values from step 3, and then save the contents on your local computer with the name ContosoCCN.xml.</span></span>

6. <span data-ttu-id="6ba3f-201">ContosoCCN.xml ファイルへのパスを入力して、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-201">Fill in the path to your ContosoCCN.xml file and run the following commands.</span></span>

   ```powershell
   #Create new Sensitive Information Type
   $path="<path to the ContosoCCN.xml file, such as C:\Scripts\ContosoCCN.xml>"
   New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path $path -Encoding Byte -ReadCount 0)
   ```

7. <span data-ttu-id="6ba3f-p105">[セキュリティとコンプライアンス] タブで、**[分類]** > **[機密情報の種類]** をクリックします。リストに Contoso 顧客番号 (CCN) が表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-p105">From the Security & Compliance tab, click **Classifications** > **Sensitive information types**. You should see the Contoso Customer Number (CCN) in the list.</span></span>

## <a name="phase-5-demonstrate-data-protection"></a><span data-ttu-id="6ba3f-204">フェーズ 5: データ保護をデモする</span><span class="sxs-lookup"><span data-stu-id="6ba3f-204">Phase 5: Demonstrate data protection</span></span>

<span data-ttu-id="6ba3f-205">Microsoft 365 の個人情報の保護には、データ損失防止 (DLP) 機能の使用が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-205">Protection of personal information in Microsoft 365 includes using data loss prevention (DLP) capabilities.</span></span>  <span data-ttu-id="6ba3f-206">DLP ポリシーにより、Microsoft 365 全体で自動的に機密情報を保護できます。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-206">With DLP policies, you can automatically protect sensitive information across Microsoft 365.</span></span>

<span data-ttu-id="6ba3f-p107">保護を適用するための複数の方法があります。環境内の EU 居住者データの保存場所と従業員によるその処理方法の教育と認識の向上は、Office 365 DLP を使用した情報保護の 1 つのレベルを表しています。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-p107">There are multiple ways you can apply the protection. Educating and raising awareness to where EU resident data is stored in your environment and how your employees are permitted to handle it represents one level of information protection using Office 365 DLP.</span></span>

<span data-ttu-id="6ba3f-209">このフェーズでは、新しい DLP ポリシーを作成して、フェーズ 2 で SharePoint Online に保存した IBANs.docx ファイルに適用する方法と IBAN を含む電子メールを送信するタイミングをデモします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-209">In this phase, you create a new DLP policy and demonstrate how it gets applied to the IBANs.docx file you stored in SharePoint Online in Phase 2 and when you attempt to send an email containing IBANs.</span></span>

1. <span data-ttu-id="6ba3f-210">ブラウザーの [セキュリティとコンプライアンス] タブで、**[ホーム]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-210">From the Security & Compliance tab of your browser, click **Home**.</span></span>
2. <span data-ttu-id="6ba3f-211">**[データ損失防止]** > **[ポリシー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-211">Click **Data loss prevention** > **Policy**.</span></span>
3. <span data-ttu-id="6ba3f-212">**[+ ポリシーの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-212">Click **+ Create a policy**.</span></span>
4. <span data-ttu-id="6ba3f-213">**[テンプレートで開始またはカスタム ポリシーの作成]** で、**[カスタム]** > **[カスタム ポリシー]** > **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-213">In **Start with a template or create a custom policy**, click **Custom** > **Custom policy** > **Next**.</span></span>
5. <span data-ttu-id="6ba3f-p108">**[ポリシーに名前を付ける]** で、次の詳細を入力してから、**[次へ]** をクリックします。a. 名前: **EU 市民 PII ポリシー** b. 説明: **欧州市民の個人を特定できる情報を保護する**</span><span class="sxs-lookup"><span data-stu-id="6ba3f-p108">In **Name your policy**, provide the following details and then click **Next**:  a. Name: **EU Citizen PII Policy** b. Description: **Protect the personally identifiable information of European citizens**</span></span>
6. <span data-ttu-id="6ba3f-p109">**[場所の選択]** で、**[Microsoft 365 のすべての場所]** を選択します。これに、Exchange メール、OneDrive ドキュメント、および SharePoint ドキュメントの内容が追加されます。その後で、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-p109">In **Choose locations**, select **All locations in Microsoft 365**. This will include content in Exchange email and OneDrive and SharePoint documents. And then click **Next**.</span></span>
7. <span data-ttu-id="6ba3f-220">**[保護するコンテンツの種類のカスタマイズ]** で、**[含まれているコンテンツを検索する:]** をクリックしてから、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-220">In **Customize the type of content you want to protect**, click **Find content that contains:** and then click **Edit**.</span></span>
8. <span data-ttu-id="6ba3f-221">**[保護するコンテンツの種類の選択]** で、**[追加]** > **[機密情報の種類]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-221">In **Choose the types of content to protect**, click **Add** > **Sensitive info types**.</span></span>
9. <span data-ttu-id="6ba3f-222">**[機密情報の種類]** で、**[+ 追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-222">In **Sensitive info types**, click **+ Add**.</span></span>
10. <span data-ttu-id="6ba3f-223">**[機密情報の種類]** で、**IBAN** を検索して、**[国際銀行口座番号 (IBAN)]** チェック ボックスをオンにしてから、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-223">In **Sensitive info types**, search for **IBAN**, select the check box for **International Banking Account Number (IBAN)**, and then click **Add**.</span></span>
11. <span data-ttu-id="6ba3f-224">**国際銀行口座番号 (IBAN)** 機密情報の種類が追加されたことを確認してから、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-224">Confirm that the **International Banking Account Number (IBAN)** sensitive information type was added, and then click **Done**.</span></span>
12. <span data-ttu-id="6ba3f-225">**[含まれるコンテンツ]** で、機密情報の種類が追加されたことを確認してから、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-225">In **Content contains**, confirm that the sensitive information types were added and then click **Save**.</span></span>
13. <span data-ttu-id="6ba3f-226">**[保護するコンテンツの種類のカスタマイズ]** で、**[含まれているコンテンツを検索する:]** に **国際銀行口座番号 (IBAN)** が含まれていることを確認してから、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-226">In **Customize the type of content you want to protect**, confirm  **Find content that contains:** contains the **International Banking Account Number (IBAN)**, and then click **Next**.</span></span>
14. <span data-ttu-id="6ba3f-227">**[共有されているコンテンツが含まれる時期の検出:（Detect when content that's being shared contains:）]** で、値を **10** から **1** に変更してから、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-227">In **Detect when content that's being shared contains:**, change the value from **10** to **1**, and then click **Next**.</span></span>
15. <span data-ttu-id="6ba3f-228">**[ポリシーを有効にしますか、または最初にテストしますか?]** で、次の設定を選択してから、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-228">In **Do you want to turn on the policy or test things out first?**, choose the following settings, and then click **Next**.</span></span>
    <span data-ttu-id="6ba3f-229">a.</span><span class="sxs-lookup"><span data-stu-id="6ba3f-229">a.</span></span> <span data-ttu-id="6ba3f-230">**[最初にテストする]** のオプションを選択する b.</span><span class="sxs-lookup"><span data-stu-id="6ba3f-230">Select the option for **I'd like to test it out first** b.</span></span> <span data-ttu-id="6ba3f-231">**[テスト モードでポリシー ヒントを表示する]** チェック ボックスをオンにする</span><span class="sxs-lookup"><span data-stu-id="6ba3f-231">Select the check box for **Show policy tips while in test mode**</span></span>
16. <span data-ttu-id="6ba3f-p111">**[設定の確認]** で、設定の確認後に **[作成]** をクリックします。メモ: 新しい DLP ポリシーを作成したら、それが有効になるまでしばらく時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-p111">In **Review your settings**, click **Create** after reviewing the settings. NOTE: After you create a new DLP policy, it will take a while for it to take effect.</span></span>
17. <span data-ttu-id="6ba3f-234">ローカル コンピューター上で、ブラウザーのプライベート インスタンスを開きます。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-234">On your local computer, open a private instance of your browser.</span></span>
18. <span data-ttu-id="6ba3f-235">アドレス バーに、「**https://**\<YourTenantName\>**.sharepoint.com**」と入力して、全体管理者アカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-235">In the address bar, type **https://**\<YourTenantName\>**.sharepoint.com** and sign in using your global administrator account.</span></span>
19. <span data-ttu-id="6ba3f-236">**[ドキュメント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-236">Click **Documents**.</span></span>
20. <span data-ttu-id="6ba3f-p112">'IBANs.docx' という名前のファイルをクリックします。'IBANs.docx のポリシー ヒント' が表示されるはずです。IBANs.docx ファイルは、DLP ポリシーに違反している外部の受信者と共有されています。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-p112">Click the file named 'IBANs.docx'. You should see 'Policy tip for IBANs.docx'.  The IBANs.docx file was shared with external recipients, which violates the DLP policy.</span></span>
21. <span data-ttu-id="6ba3f-240">アドレス バーに、「`https://outlook.office365.com`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-240">In the address bar, type: `https://outlook.office365.com`</span></span>
22. <span data-ttu-id="6ba3f-241">**[新規]** - **[電子メール メッセージ]** をクリックして、次の項目を入力します。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-241">Click **New** - **Email message** and provide the following:</span></span>

    - <span data-ttu-id="6ba3f-242">**宛先:** \<a personal email address\></span><span class="sxs-lookup"><span data-stu-id="6ba3f-242">**To:** \<a personal email address\></span></span>
    - <span data-ttu-id="6ba3f-243">**件名:** GDPR テスト</span><span class="sxs-lookup"><span data-stu-id="6ba3f-243">**Subject:** GDPR Test</span></span>
    - <span data-ttu-id="6ba3f-244">**本文:** 下に示す値の表にコピーしてください。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-244">**Body:** Copy in the table of values shown below.</span></span>

      |<span data-ttu-id="6ba3f-245">番号</span><span class="sxs-lookup"><span data-stu-id="6ba3f-245">Number</span></span>|<span data-ttu-id="6ba3f-246">国</span><span class="sxs-lookup"><span data-stu-id="6ba3f-246">Country</span></span>|<span data-ttu-id="6ba3f-247">コード</span><span class="sxs-lookup"><span data-stu-id="6ba3f-247">Code</span></span>|<span data-ttu-id="6ba3f-248">IBAN</span><span class="sxs-lookup"><span data-stu-id="6ba3f-248">IBAN</span></span>|
      |---|---|---|---|
      |<span data-ttu-id="6ba3f-249">1</span><span class="sxs-lookup"><span data-stu-id="6ba3f-249">1</span></span>|<span data-ttu-id="6ba3f-250">オーストリア SEPA</span><span class="sxs-lookup"><span data-stu-id="6ba3f-250">Austria SEPA</span></span>|<span data-ttu-id="6ba3f-251">AT</span><span class="sxs-lookup"><span data-stu-id="6ba3f-251">AT</span></span>|<span data-ttu-id="6ba3f-252">AT611904300234573201</span><span class="sxs-lookup"><span data-stu-id="6ba3f-252">AT611904300234573201</span></span>|
      |<span data-ttu-id="6ba3f-253">2</span><span class="sxs-lookup"><span data-stu-id="6ba3f-253">2</span></span>|<span data-ttu-id="6ba3f-254">ブルガリア SEPA</span><span class="sxs-lookup"><span data-stu-id="6ba3f-254">Bulgaria SEPA</span></span>|<span data-ttu-id="6ba3f-255">BG</span><span class="sxs-lookup"><span data-stu-id="6ba3f-255">BG</span></span>|<span data-ttu-id="6ba3f-256">BG80BNBG96611020345678</span><span class="sxs-lookup"><span data-stu-id="6ba3f-256">BG80BNBG96611020345678</span></span>|
      |<span data-ttu-id="6ba3f-257">3</span><span class="sxs-lookup"><span data-stu-id="6ba3f-257">3</span></span>|<span data-ttu-id="6ba3f-258">デンマーク SEPA</span><span class="sxs-lookup"><span data-stu-id="6ba3f-258">Denmark SEPA</span></span>|<span data-ttu-id="6ba3f-259">DK</span><span class="sxs-lookup"><span data-stu-id="6ba3f-259">DK</span></span>|<span data-ttu-id="6ba3f-260">DK5000400440116243</span><span class="sxs-lookup"><span data-stu-id="6ba3f-260">DK5000400440116243</span></span>|
      |<span data-ttu-id="6ba3f-261">4</span><span class="sxs-lookup"><span data-stu-id="6ba3f-261">4</span></span>|<span data-ttu-id="6ba3f-262">フィンランド SEPA</span><span class="sxs-lookup"><span data-stu-id="6ba3f-262">Finland SEPA</span></span>|<span data-ttu-id="6ba3f-263">FI</span><span class="sxs-lookup"><span data-stu-id="6ba3f-263">FI</span></span>|<span data-ttu-id="6ba3f-264">FI2112345600000785</span><span class="sxs-lookup"><span data-stu-id="6ba3f-264">FI2112345600000785</span></span>|
      |<span data-ttu-id="6ba3f-265">5</span><span class="sxs-lookup"><span data-stu-id="6ba3f-265">5</span></span>|<span data-ttu-id="6ba3f-266">フランス SEPA</span><span class="sxs-lookup"><span data-stu-id="6ba3f-266">France SEPA</span></span>|<span data-ttu-id="6ba3f-267">FR</span><span class="sxs-lookup"><span data-stu-id="6ba3f-267">FR</span></span>|<span data-ttu-id="6ba3f-268">FR1420041010050500013M02606</span><span class="sxs-lookup"><span data-stu-id="6ba3f-268">FR1420041010050500013M02606</span></span>|
      |<span data-ttu-id="6ba3f-269">6</span><span class="sxs-lookup"><span data-stu-id="6ba3f-269">6</span></span>|<span data-ttu-id="6ba3f-270">ドイツ SEPA</span><span class="sxs-lookup"><span data-stu-id="6ba3f-270">Germany SEPA</span></span>|<span data-ttu-id="6ba3f-271">DE</span><span class="sxs-lookup"><span data-stu-id="6ba3f-271">DE</span></span>|<span data-ttu-id="6ba3f-272">DE89370400440532013000</span><span class="sxs-lookup"><span data-stu-id="6ba3f-272">DE89370400440532013000</span></span>|
      |<span data-ttu-id="6ba3f-273">7</span><span class="sxs-lookup"><span data-stu-id="6ba3f-273">7</span></span>|<span data-ttu-id="6ba3f-274">ギリシャ SEPA</span><span class="sxs-lookup"><span data-stu-id="6ba3f-274">Greece SEPA</span></span>|<span data-ttu-id="6ba3f-275">GR</span><span class="sxs-lookup"><span data-stu-id="6ba3f-275">GR</span></span>|<span data-ttu-id="6ba3f-276">GR1601101250000000012300695</span><span class="sxs-lookup"><span data-stu-id="6ba3f-276">GR1601101250000000012300695</span></span>|
      |<span data-ttu-id="6ba3f-277">8</span><span class="sxs-lookup"><span data-stu-id="6ba3f-277">8</span></span>|<span data-ttu-id="6ba3f-278">イタリア SEPA</span><span class="sxs-lookup"><span data-stu-id="6ba3f-278">Italy SEPA</span></span>|<span data-ttu-id="6ba3f-279">IT</span><span class="sxs-lookup"><span data-stu-id="6ba3f-279">IT</span></span>|<span data-ttu-id="6ba3f-280">GR1601101250000000012300695</span><span class="sxs-lookup"><span data-stu-id="6ba3f-280">GR1601101250000000012300695</span></span>|
      |<span data-ttu-id="6ba3f-281">9</span><span class="sxs-lookup"><span data-stu-id="6ba3f-281">9</span></span>|<span data-ttu-id="6ba3f-282">オランダ SEPA</span><span class="sxs-lookup"><span data-stu-id="6ba3f-282">Netherlands SEPA</span></span>|<span data-ttu-id="6ba3f-283">NL</span><span class="sxs-lookup"><span data-stu-id="6ba3f-283">NL</span></span>|<span data-ttu-id="6ba3f-284">NL91ABNA0417164300</span><span class="sxs-lookup"><span data-stu-id="6ba3f-284">NL91ABNA0417164300</span></span>|
      |<span data-ttu-id="6ba3f-285">10</span><span class="sxs-lookup"><span data-stu-id="6ba3f-285">10</span></span>|<span data-ttu-id="6ba3f-286">ポーランド SEPA</span><span class="sxs-lookup"><span data-stu-id="6ba3f-286">Poland SEPA</span></span>|<span data-ttu-id="6ba3f-287">PL</span><span class="sxs-lookup"><span data-stu-id="6ba3f-287">PL</span></span>|<span data-ttu-id="6ba3f-288">PL27114020040000300201355387</span><span class="sxs-lookup"><span data-stu-id="6ba3f-288">PL27114020040000300201355387</span></span>|
      |

    <span data-ttu-id="6ba3f-289">メモ:- このサンプル データ セットは、公開されている情報から得られたもので、テスト目的でのみ使用することを意図しています。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-289">Note:- This sample data set is derived from publicly available information and is intended to be used for test purposes only.</span></span>

23. <span data-ttu-id="6ba3f-290">電子メールの本文に IBAN が含まれ、メッセージ ウィンドウの上部にポリシー ヒントが表示されることが DLP ポリシーで認識されたことが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-290">You will see that the DLP policy recognized that body of the email contains IBANs and provides you with the policy tip at the top of the message window.</span></span>
24. <span data-ttu-id="6ba3f-291">ブラウザーのプライベート インスタンスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-291">Close the private instance of your browser.</span></span>

## <a name="phase-6-demonstrate-reporting"></a><span data-ttu-id="6ba3f-292">フェーズ 6: レポート機能をデモする</span><span class="sxs-lookup"><span data-stu-id="6ba3f-292">Phase 6: Demonstrate reporting</span></span>

<span data-ttu-id="6ba3f-293">このフェーズでは、フェーズ 5 で構成した DLP ポリシーに基づいて Microsoft 365 のレポート機能をデモします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-293">In this phase, you demonstrate Microsoft 365 reporting based on the DLP policy configured in Phase 5.</span></span>

   1. <span data-ttu-id="6ba3f-294">ブラウザーの [セキュリティとコンプライアンス] タブで、**[ホーム]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-294">From the Security & Compliance tab of your browser, click **Home**.</span></span>
   2. <span data-ttu-id="6ba3f-295">**[レポート]** > **[ダッシュボード]** > **[DLP ポリシー一致]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-295">Click **Reports** > **Dashboard** > **DLP policy matches**.</span></span>
   3. <span data-ttu-id="6ba3f-p113">DLP ポリシーは、組織の機密情報の特定と保護に役立ちます。たとえば、レポートには、SharePoint Online に保存された IBAN を含むドキュメントがポリシーで特定されたことが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6ba3f-p113">Your DLP policy helps identify and protect organization's sensitive information. For example, in the report you will see that the policy identified the document that contains IBANs stored in SharePoint Online.</span></span>
