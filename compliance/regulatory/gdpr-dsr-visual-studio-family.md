---
title: GDPR および CCPA に関する Visual Studio ファミリ データ主体要求
description: GDPR および CCPA 関して、Microsoft ツールを使用して Visual Studio のファミリ データ主体要求を管理する方法について説明します。
keywords: Visual Studio、Visual Studio Code、Visual Studio for Mac、Visual Studio ドキュメント、プライバシー、GDPR、CCPA
localization_priority: Priority
audience: itpro
ms.prod: visual-studio-family
ms.topic: article
author: robmazz
f1.keywords:
- NOCSH
ms.author: robmazz
manager: laurawi
ms.collection:
- GDPR
- M365-security-compliance
- MS-Compliance
ms.workload:
- multiple
titleSuffix: Microsoft GDPR
ms.custom: seo-marvel-apr2020
hideEdit: true
ms.openlocfilehash: 4a4ec723a046b65ade51b2e7aaa08fcda3a1908d
ms.sourcegitcommit: 8bf2602d56eedee4447ddb374ef95b0587f254e7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53377944"
---
# <a name="visual-studio-family-data-subject-requests-for-the-gdpr-and-ccpa"></a><span data-ttu-id="24f30-104">GDPR および CCPA に関する Visual Studio ファミリ データ主体要求</span><span class="sxs-lookup"><span data-stu-id="24f30-104">Visual Studio Family Data Subject Requests for the GDPR and CCPA</span></span>

<span data-ttu-id="24f30-105">欧州連合の [一般データ保護規制 （GDPR）](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) は、ユーザー (規制では _データ主体_ と呼ばれます) に、自分の個人データを管理する権利を付与します。</span><span class="sxs-lookup"><span data-stu-id="24f30-105">The European Union [General Data Protection Regulation (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) gives rights to people (known in the regulation as _data subjects_) to manage their personal data.</span></span> <span data-ttu-id="24f30-106">GDPR における個人データは、特定された自然人または特定可能な自然人に関連するすべてのデータとして広範囲に定義されています。</span><span class="sxs-lookup"><span data-stu-id="24f30-106">Personal data is defined broadly under the GDPR as any data that relates to an identified or identifiable natural person.</span></span> <span data-ttu-id="24f30-107">GDPR では、個人データに対するデータ主体固有の権限が付与されます。このような権限には、個人データのコピーの取得、個人データの修正の要求、個人データの処理の制限、または個人データの削除、または電子的な形式での個人データの受け取りが含まれます。</span><span class="sxs-lookup"><span data-stu-id="24f30-107">The GDPR gives data subjects specific rights to their personal data; these rights include obtaining copies of personal data, requesting corrections to it, restricting the processing of it, deleting it, or receiving it in an electronic format.</span></span> <span data-ttu-id="24f30-108">データ主体がデータ管理者 (個人データを管理する雇用者またはその他の種類の機関または組織) に対して、そのデータ主体の個人データに関する行為を行うよう正式に要求することを、_データ主体の要求_ または DSR といいます。</span><span class="sxs-lookup"><span data-stu-id="24f30-108">A formal request by a data subject to a data controller (an employer or other type of agency or organization that has control over personal data) to take an action on that data subject's personal data is called a _data subject request_ or DSR.</span></span>

<span data-ttu-id="24f30-109">同様に、カリフォルニア州消費者プライバシー法 (CCPA) では、個人情報の削除、アクセスおよび受信 (移植性) など、GDPR のデータ主体の権利に類似している権利を含む、カリフォルニア州の消費者のプライバシーの権利および義務を規定します。</span><span class="sxs-lookup"><span data-stu-id="24f30-109">Similarly, the California Consumer Privacy Act (CCPA), provides privacy rights and obligations to California consumers, including rights similar to GDPR's Data Subject Rights, such as the right to delete, access, and receive (portability) their personal information.</span></span>  <span data-ttu-id="24f30-110">また、CCPA では、特定の開示、権利の行使を選択する際の差別に対する保護、"売上" として分類された特定のデータ転送の "オプトアウト/オプトイン" 要件を規定します。</span><span class="sxs-lookup"><span data-stu-id="24f30-110">The CCPA also provides for certain disclosures, protections against discrimination when electing exercise rights, and "opt-out/ opt-in" requirements for certain data transfers classified as "sales".</span></span> <span data-ttu-id="24f30-111">「販売」は広く定義されており、有価約因に関するデータの共有を含みます。</span><span class="sxs-lookup"><span data-stu-id="24f30-111">Sales are broadly defined to include the sharing of data for a valuable consideration.</span></span> <span data-ttu-id="24f30-112">CCPA の詳細については、「[カリフォルニア州消費者プライバシー法](offering-ccpa.md)」と「[カリフォルニア州消費者プライバシー法に関する FAQ](ccpa-faq.yml)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24f30-112">For more information about the CCPA, see the [California Consumer Privacy Act](offering-ccpa.md) and the [California Consumer Privacy Act FAQ](ccpa-faq.yml).</span></span>

<span data-ttu-id="24f30-113">GDPR の一般的な情報については、[Service Trust Portal の GDPR セクション](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24f30-113">For general information about GDPR, see the [GDPR section of the Service Trust portal](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted).</span></span>

## <a name="products-covered-by-this-guide"></a><span data-ttu-id="24f30-114">このガイドの対象製品</span><span class="sxs-lookup"><span data-stu-id="24f30-114">Products covered by this guide</span></span>

<span data-ttu-id="24f30-p103">このガイドでは、Microsoft ツールを使用して、Visual Studio、Visual Studio for Mac、およびそれらと Visual Studio Code に対する Microsoft 拡張機能の認証済み (サインイン済み) セッション使用時に収集された個人データをエクスポートまたは削除する方法について説明します。また、Visual Studio 開発者コミュニティ、NuGet.org、および ASP.NET Web サイトの使用時に収集された個人データに対するデータ主体要求の発行方法についても説明します。これらの製品を使用すれば、Microsoft 以外のツールと拡張機能の使用が可能になりますが、Microsoft はこれらのツールと拡張機能のデータ プロセッサまたはコントローラーではありません。ユーザーは、これらのツールまたは拡張機能のプロバイダーに問い合わせて、個人データと収集に関するポリシーを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="24f30-p103">This guide discusses how to use Microsoft tools to export or delete personal data collected during authenticated (signed-in) session usage of Visual Studio and Visual Studio for Mac and Microsoft extensions to them and to Visual Studio Code. This guide also covers how to make data subject requests for personal data collected when using Visual Studio Developer Community, NuGet.org, and the ASP.NET website. These products may enable the use of non-Microsoft tools and extensions, and Microsoft is not a data processor or controller for these tools and extensions. Users should contact the tool or extension provider to understand the personal data and collection policies for these tools and extensions.</span></span>

## <a name="additional-privacy-information"></a><span data-ttu-id="24f30-119">その他のプライバシー情報</span><span class="sxs-lookup"><span data-stu-id="24f30-119">Additional privacy information</span></span>

<span data-ttu-id="24f30-120">製品に付属しているマイクロソフト ソフトウェア ライセンス条項、[Microsoft プライバシーに関する声明](https://go.microsoft.com/fwlink/?LinkId=660726)、および [Microsoft の GDPR コミットメント](/legal/gdpr)にデータ処理慣行が記載されています。</span><span class="sxs-lookup"><span data-stu-id="24f30-120">The Microsoft Software License Terms accompanying the products, the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?LinkId=660726), and [Microsoft's GDPR Commitments](/legal/gdpr) describe our data processing practices.</span></span>

## <a name="visual-studio-visual-studio-for-mac-and-visual-studio-code"></a><span data-ttu-id="24f30-121">Visual Studio、Visual Studio for Mac、および Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="24f30-121">Visual Studio, Visual Studio for Mac, and Visual Studio Code</span></span>

### <a name="personal-data-we-collect"></a><span data-ttu-id="24f30-122">Microsoft が収集する個人データ</span><span class="sxs-lookup"><span data-stu-id="24f30-122">Personal data we collect</span></span>

<span data-ttu-id="24f30-p104">GDPR に基づくデータ プロセッサとして、Microsoft は、Visual Studio、Visual Studio for Mac、およびそれらと Visual Studio Code に対する Microsoft 拡張機能に対するエクスペリエンスを提供し、これらを改善するために必要なデータをユーザーから収集します。データは、顧客データとシステム生成ログという 2 つのカテゴリに分けられます。顧客データには、これらの製品が提供しているサービスを実行するために必要なユーザーを特定できるトランザクション データと相互作用データが含まれます。たとえば、ユーザーにローミング設定などの個人的なエクスペリエンスを提供するには、ユーザー アカウント情報と設定データを収集する必要があります。システム生成ログは、問題を特定してトラブルシューティングし、弊社の製品やサービスを向上させるために使用される、利用状況データまたは診断データで、ユーザー名などのエンドユーザーに関する特定可能な情報が含まれている場合もあります。システム生成ログは、少なくとも 18 か月間保持されます。例として、システム生成ログは、次のサンプルで示すように、製品使用の日ごとに集計され、使用日、使用された製品 ("Visual Studio 2017" など)、実行されたアクション ("vs/core/packagecostsummary/solutionload" など)、およびアクションの実行回数が記録されます。</span><span class="sxs-lookup"><span data-stu-id="24f30-p104">As a data processor under the GDPR, Microsoft collects the data we need from users to provide experiences for and improve Visual Studio and Visual Studio for Mac and Microsoft extensions to them and to Visual Studio Code. There are two categories of data: customer data and system-generated logs. Customer data includes user-identifiable transactional and interactional data that these products need to perform the service they provide. For example, to provide users with personalized experiences such as roaming settings, we need to collect user account information and settings data. System-generated logs are usage or diagnostic data that are used to help identify and troubleshoot problems and improve our products and services, and may also contain identifiable information about end users, such as a user name. System-generated logs are retained for no more than 18 months. As an example, system-generated logs are aggregated for each day of product usage and include the usage date, the product used (for example, "Visual Studio 2017"), the action you took (for example, "vs/core/packagecostsummary/solutionload"), and the number of times the action was taken, as shown in this sample:</span></span>

```Log
{Time":"2/23/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/core/packagecostsummary/solutionload","Target":"1 times",
"DevicePlatform":"Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}

{Time":"2/23/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/ide/connected/accountmanagement/account","Target":"1 times",
"DevicePlatform": "Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}

{"Time":"2/27/2018 12:00:00 AM","AppName":"Visual Studio 2017","Action":"vs/core/perf/satellitepagefileusage","Target":"23 times",
"DevicePlatform":"Windows 10 Enterprise","IP":null,"InputMethod":null,
"SearchTerm":null,"SearchResult":null}
```

<span data-ttu-id="24f30-130">詳細については、「[Visual Studio によって収集されるシステム生成ログ](/visualstudio/ide/diagnostic-data-collection)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24f30-130">For more information, see [System-generated logs collected by Visual Studio](/visualstudio/ide/diagnostic-data-collection).</span></span>

<span data-ttu-id="24f30-p105">認証済みの ID に関連付けられた個人データのみが DSR で処理されます。そのため、たとえば、Visual Studio Code はサインインをサポートしていないため、そこからのシステム生成ログは認証済みの ID に関連付けられず、処理されません。ただし、Visual Studio Code に対する一部の Microsoft 拡張機能が認証済みのデータを提供するため、このデータは DSR で処理されます。詳細については、「[GDPR と Visual Studio Code](https://code.visualstudio.com/docs/supporting/faq#_gdpr-and-vs-code)」を参照してください。一般に、Visual Studio 2013 以前のデータは保存されませんが、後述するように、特定の拡張機能とコンポーネントが、認証済みの ID に関連付けられたデータを提供する場合があるため、DSR で処理されます。</span><span class="sxs-lookup"><span data-stu-id="24f30-p105">Only personal data that is attached to authenticated identities can be serviced by a DSR. So, for example, because Visual Studio Code does not support sign-in, system-generated logs from it are not attached to an authenticated identity and cannot be serviced. However, some Microsoft extensions for Visual Studio Code may provide authenticated data, and this data can be serviced by a DSR. For more information, see [GDPR and Visual Studio Code](https://code.visualstudio.com/docs/supporting/faq#_gdpr-and-vs-code). In general, we do not store data for Visual Studio 2013 and earlier; however, certain extensions and components may provide data attached to authenticated identities and can be serviced by a DSR as outlined below.</span></span>

### <a name="how-users-can-control-personal-data"></a><span data-ttu-id="24f30-136">ユーザーによる個人データの管理方法</span><span class="sxs-lookup"><span data-stu-id="24f30-136">How users can control personal data</span></span>

<span data-ttu-id="24f30-137">Visual Studio 2015 以降、Visual Studio for Mac、および Visual Studio Code は、ユーザーがデータ収集を停止したり、コントローラーが既に収集されたデータをエクスポートまたは削除したりするための以下の手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="24f30-137">Visual Studio 2015 and later, Visual Studio for Mac, and Visual Studio Code provide the following means for your users to stop data collection, and for you as controller to export, or delete data that has already been gathered.</span></span>

#### <a name="in-app-settings"></a><span data-ttu-id="24f30-138">アプリ内設定</span><span class="sxs-lookup"><span data-stu-id="24f30-138">In-app settings</span></span>

<span data-ttu-id="24f30-p106">ユーザーは、これらの製品のプライバシー設定を管理できます。詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24f30-p106">Users can control the privacy settings for these products. For more information, see the following</span></span>

- <span data-ttu-id="24f30-141">[Visual Studio でプライバシー設定を管理する方法](/visualstudio/ide/visual-studio-experience-improvement-program)</span><span class="sxs-lookup"><span data-stu-id="24f30-141">[How to manage privacy settings in Visual Studio](/visualstudio/ide/visual-studio-experience-improvement-program).</span></span>
- <span data-ttu-id="24f30-142">[Visual Studio for Mac でプライバシー設定を管理する方法](/visualstudio/mac/visual-studio-experience-improvement-program)</span><span class="sxs-lookup"><span data-stu-id="24f30-142">[How to manage privacy settings in Visual Studio for Mac](/visualstudio/mac/visual-studio-experience-improvement-program).</span></span>
- <span data-ttu-id="24f30-143">[Visual Studio Code でテレメトリ レポート機能を無効にする方法](https://code.visualstudio.com/docs/supporting/faq#_how-to-disable-telemetry-reporting)</span><span class="sxs-lookup"><span data-stu-id="24f30-143">[How to disable telemetry reporting in Visual Studio Code](https://code.visualstudio.com/docs/supporting/faq#_how-to-disable-telemetry-reporting).</span></span>

#### <a name="exporting-or-deleting-data"></a><span data-ttu-id="24f30-144">データのエクスポートまたは削除</span><span class="sxs-lookup"><span data-stu-id="24f30-144">Exporting or deleting data</span></span>

<span data-ttu-id="24f30-p107">コントローラーは、Visual Studio ファミリ製品または Microsoft 拡張機能が登録された方法に応じて、2 つの方法のどちらかでデータ主体から収集された顧客データとシステム生成ログを管理できます。両方の方法を使用しなければならない場合もあります。両方の方法を使用すれば、コントローラーは、その方法によって管理されているアクティビティ履歴のコピーをダウンロードすることができます。AAD または MSA アカウントを閉鎖すると、関連する Visual Studio 顧客データが削除され、これらの製品に関するシステム生成ログ内の個人を特定できるデータが匿名化されます。匿名化されたシステム生成ログは少なくとも 18 か月間保持されます。</span><span class="sxs-lookup"><span data-stu-id="24f30-p107">Controllers can manage customer data and system-generated logs collected from their data subjects by one of two methods, depending upon how their Visual Studio Family product or Microsoft extensions were registered. In some cases, both methods must be used. Both methods allow Controllers to download a copy of their activity history managed by that method. Closure of an AAD or MSA account deletes associated Visual Studio customer data, and anonymizes personally identifiable data in system-generated logs pertaining to these products. Anonymized system-generated logs are retained for no more than 18 months.</span></span>

- <span data-ttu-id="24f30-150">Azure サブスクリプションに関連付けられた AAD アカウントや MSA アカウントなどの Azure テナントにより裏付けられるアカウントを使用して、Visual Studio ファミリ製品を登録したユーザーは、「[GDPR のための Azure データ主体要求](gdpr-dsr-azure.md)」の手順に従うことができます。</span><span class="sxs-lookup"><span data-stu-id="24f30-150">Users that have registered a Visual Studio Family product by using an account that is backed by an Azure tenant, for example, AAD account or  MSA account associated with an Azure subscription, can follow the instructions in [Azure Data Subject Requests for the GDPR](gdpr-dsr-azure.md).</span></span>
- <span data-ttu-id="24f30-151">Microsoft アカウント (MSA) を使用した複数のアカウントなど、Azure テナントによって裏付けられたアカウントを使用せずに Visual Studio ファミリ製品を登録したユーザーは、Microsoft アカウント経由で [Ｗeb ベースの Microsoft Privacy Response Center](https://aka.ms/userprivacysite) を使用して、複数の Microsoft サービスで Microsoft アカウントに紐づけられたアクティビティ データを表示、管理、および削除できます。</span><span class="sxs-lookup"><span data-stu-id="24f30-151">Users that have registered a Visual Studio Family product without an account that is backed by an Azure tenant, for example many accounts using a Microsoft Account (MSA), can use [the web-based Microsoft Privacy Response Center](https://aka.ms/userprivacysite) available through their Microsoft account to view, control, and delete activity data tied to their Microsoft account across multiple Microsoft services.</span></span> <span data-ttu-id="24f30-152">このシナリオでは、ユーザーは個人データのコントローラーです。</span><span class="sxs-lookup"><span data-stu-id="24f30-152">In this scenario, the user is a controller for their own personal data.</span></span>

> [!NOTE]
> <span data-ttu-id="24f30-153">MSA アカウント所有者がアカウントを削除すると、アカウントが Azure テナントによって裏付けされているかどうかに関係なく、これらの製品に関するすべての個人を特定できるデータが削除され、システム生成ログが匿名化されます。</span><span class="sxs-lookup"><span data-stu-id="24f30-153">When an MSA account holder deletes their account, all their personally identifiable data pertaining to these products is deleted, whether the account is backed by an Azure tenant or not, and system-generated logs are anonymized.</span></span>

<span data-ttu-id="24f30-p109">Visual Studio 2013 では、収集されたデータが匿名化されます。Visual Studio 2012 以前のリリースでは、データが受信時に即座に削除されます。どちらの場合も、後で表示、エクスポート、または削除するものはありません。</span><span class="sxs-lookup"><span data-stu-id="24f30-p109">For Visual Studio 2013, the data we collect is anonymized. For Visual Studio 2012 and prior releases, we immediately delete the data upon receipt. In both cases, there is nothing to view, export, or delete at a later time.</span></span>

## <a name="visual-studio-developer-community"></a><span data-ttu-id="24f30-157">Visual Studio 開発者コミュニティ</span><span class="sxs-lookup"><span data-stu-id="24f30-157">Visual Studio Developer Community</span></span>

<span data-ttu-id="24f30-p110">[開発者コミュニティ](https://developercommunity.visualstudio.com) Web サイト経由の[一般データ保護規則 (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) 要求がサポートされています。フィードバック データを表示、エクスポート、または削除できます。</span><span class="sxs-lookup"><span data-stu-id="24f30-p110">We support [General Data Protection Regulation (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) requests through the [Developer Community](https://developercommunity.visualstudio.com) website. You can View, Export, or Delete your feedback data.</span></span>

### <a name="personal-data-we-collect"></a><span data-ttu-id="24f30-160">Microsoft が収集する個人データ</span><span class="sxs-lookup"><span data-stu-id="24f30-160">Personal data we collect</span></span>

<span data-ttu-id="24f30-p111">Microsoft は、Visual Studio ファミリ製品を使用して報告された問題を再現してトラブルシューティングするためのデータを収集します。このデータには、個人データとパブリック フィードバックが含まれます。個人データには、以下が含まれます。</span><span class="sxs-lookup"><span data-stu-id="24f30-p111">Microsoft collects data to help us reproduce and troubleshoot issues you report with Visual Studio Family products. This data includes personal data and public feedback. Personal data includes:</span></span>

- <span data-ttu-id="24f30-164">[開発者コミュニティ](https://developercommunity.visualstudio.com) プロファイル情報</span><span class="sxs-lookup"><span data-stu-id="24f30-164">Your [Developer Community](https://developercommunity.visualstudio.com) profile information;</span></span>
- <span data-ttu-id="24f30-165">ユーザー設定と通知</span><span class="sxs-lookup"><span data-stu-id="24f30-165">Preferences and notifications;</span></span>
- <span data-ttu-id="24f30-166">[Visual Studio で問題を報告する](/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)ことによって、または、[開発者コミュニティ](https://developercommunity.visualstudio.com)経由で提供された添付ファイルとシステム生成ログ</span><span class="sxs-lookup"><span data-stu-id="24f30-166">Attachments and system-generated logs you provided by [reporting a problem in Visual Studio](/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) or through [Developer Community](https://developercommunity.visualstudio.com);</span></span>
- <span data-ttu-id="24f30-167">投票</span><span class="sxs-lookup"><span data-stu-id="24f30-167">Your votes.</span></span>

<span data-ttu-id="24f30-168">パブリック フィードバックには、問題、コメント、および解決策が含まれます。</span><span class="sxs-lookup"><span data-stu-id="24f30-168">Public feedback includes: reported problems, comments, and solutions.</span></span>

### <a name="how-users-can-control-personal-data"></a><span data-ttu-id="24f30-169">ユーザーによる個人データの管理方法</span><span class="sxs-lookup"><span data-stu-id="24f30-169">How users can control personal data</span></span>

#### <a name="view"></a><span data-ttu-id="24f30-170">表示</span><span class="sxs-lookup"><span data-stu-id="24f30-170">View</span></span>

<span data-ttu-id="24f30-171">フィードバック関連データを表示するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="24f30-171">To View your feedback-related data, follow these steps:</span></span>

1. <span data-ttu-id="24f30-172">[開発者コミュニティ](https://developercommunity.visualstudio.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="24f30-172">Sign into [Developer Community](https://developercommunity.visualstudio.com).</span></span> <span data-ttu-id="24f30-173">右上で、プロファイルをクリックして、**[プロファイルとユーザー設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="24f30-173">From the top-right corner, click on your profile and select **Profile and Preferences**.</span></span>
2. <span data-ttu-id="24f30-174">**[プロファイル]**、**[通知]**、**[アクティビティ]**、および **[添付ファイル]** タブのいずれかをクリックして、フィードバック システムに送信されたデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="24f30-174">Click on any of the **Profile**, **Notifications**, **Activity**, and **Attachments** tabs to view the data submitted to the feedback systems.</span></span>
   1. <span data-ttu-id="24f30-175">**プロファイル** は、[開発者コミュニティ](https://developercommunity.visualstudio.com) プロファイルを意味し、ユーザー名、電子メール アドレス、自己紹介などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="24f30-175">**Profile** refers to your [Developer Community](https://developercommunity.visualstudio.com) profile, including user name, email address, about, etc.</span></span>
   2. <span data-ttu-id="24f30-176">\*\*通知は、受信する電子メール通知の管理方法です。</span><span class="sxs-lookup"><span data-stu-id="24f30-176">\*\*Notifications are how you control the email notifications you receive.</span></span>
   3. <span data-ttu-id="24f30-177">**アクティビティ** は、アクティブだったフィードバック項目 (投稿済み、コメント済みなど) と実行されたアクティビティを表示します。</span><span class="sxs-lookup"><span data-stu-id="24f30-177">**Activity** will give you the feedback items you have been active on (posted, commented, etc.), and the activities performed.</span></span>
   4. <span data-ttu-id="24f30-178">**添付ファイル** は、`FileName was attached to the problem "ProblemName" Tue, Apr 10, 18 2:27 PM` のような形式の添付ファイル履歴のリストです。</span><span class="sxs-lookup"><span data-stu-id="24f30-178">**Attachments** is a list of your attachment history in a format like `FileName was attached to the problem "ProblemName" Tue, Apr 10, 18 2:27 PM`.</span></span>

#### <a name="export"></a><span data-ttu-id="24f30-179">エクスポート</span><span class="sxs-lookup"><span data-stu-id="24f30-179">Export</span></span>

<span data-ttu-id="24f30-p113">DSR の一部として、フィードバック データをエクスポートすることができます。次のデータを含む 1 つ以上の .zip アーカイブが作成されます。</span><span class="sxs-lookup"><span data-stu-id="24f30-p113">You can export your feedback data as part of DSR. We will create one or more .zip archives that will include:</span></span>

- <span data-ttu-id="24f30-182">[開発者コミュニティ](https://developercommunity.visualstudio.com) プロファイル情報</span><span class="sxs-lookup"><span data-stu-id="24f30-182">Your [Developer Community](https://developercommunity.visualstudio.com) profile information;</span></span>
- <span data-ttu-id="24f30-183">ユーザー設定と通知設定</span><span class="sxs-lookup"><span data-stu-id="24f30-183">Preferences and notification settings;</span></span>
- <span data-ttu-id="24f30-184">[Visual Studio で問題を報告する](/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)ことによって、または、[開発者コミュニティ](https://developercommunity.visualstudio.com)経由で提供された添付ファイル</span><span class="sxs-lookup"><span data-stu-id="24f30-184">Attachments you provided by [reporting a problem in Visual Studio](/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) or through [Developer Community](https://developercommunity.visualstudio.com).</span></span>

> [!NOTE]
> <span data-ttu-id="24f30-185">入力されたパブリック フィードバック (コメント、解決策、および報告済みの問題) がアーカイブから除外されます。</span><span class="sxs-lookup"><span data-stu-id="24f30-185">We will exclude the following public feedback you have provided from your archive: comments, solutions, reported problems.</span></span>

<span data-ttu-id="24f30-186">エクスポートを開始するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="24f30-186">To start an Export, follow these steps:</span></span>

1. <span data-ttu-id="24f30-187">[開発者コミュニティ](https://developercommunity.visualstudio.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="24f30-187">Sign into [Developer Community](https://developercommunity.visualstudio.com).</span></span> <span data-ttu-id="24f30-188">右上で、プロファイルをクリックして、**[プロファイルとユーザー設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="24f30-188">From the top-right corner, click on your profile and select **Profile and Preferences**.</span></span>
2. <span data-ttu-id="24f30-189">**[プライバシー]** タブをクリックしてから、**[アーカイブの作成]** をクリックし、データのエクスポートを要求します。</span><span class="sxs-lookup"><span data-stu-id="24f30-189">Click the **Privacy** tab, and then click **Create an archive** to request exporting your data.</span></span>
3. <span data-ttu-id="24f30-p115">**[アーカイブ状態]** が、データの準備中であることを示すように更新されます。データが使用可能になるまでの時間の長さは、エクスポートする必要があるデータ量に依存します。</span><span class="sxs-lookup"><span data-stu-id="24f30-p115">The **Archive Status** will update to show that we are preparing the data. The length of time before the data is available depends on the amount of data we need to export.</span></span>
4. <span data-ttu-id="24f30-192">データの準備ができると、電子メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="24f30-192">Once the data is ready, we will send you an email.</span></span>
5. <span data-ttu-id="24f30-193">電子メール内の **[アーカイブのダウンロード]** をクリックするか、[プライバシー] タブに戻ってデータをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="24f30-193">Click **Download Archive** in the email, or go back to the Privacy tab to download your data.</span></span>

> [!NOTE]
> - <span data-ttu-id="24f30-194">[通知] タブで通知を受信しないように選択した場合は、電子メールが送信されません。</span><span class="sxs-lookup"><span data-stu-id="24f30-194">We will not send email if you chose not to receive notifications in the Notifications tab.</span></span>
> - <span data-ttu-id="24f30-195">再度エクスポートを要求すると、古いアーカイブが削除され、新しいアーカイブが作成されます。</span><span class="sxs-lookup"><span data-stu-id="24f30-195">If you request Export again, we will remove your old archive and create a new one.</span></span>

#### <a name="delete"></a><span data-ttu-id="24f30-196">削除</span><span class="sxs-lookup"><span data-stu-id="24f30-196">Delete</span></span>

<span data-ttu-id="24f30-197">削除すると、[開発者コミュニティ](https://developercommunity.visualstudio.com)から次の情報が削除されます。</span><span class="sxs-lookup"><span data-stu-id="24f30-197">Deleting will remove the following information about you from [Developer Community](https://developercommunity.visualstudio.com):</span></span>

- <span data-ttu-id="24f30-198">プロファイル情報</span><span class="sxs-lookup"><span data-stu-id="24f30-198">Profile information;</span></span>
- <span data-ttu-id="24f30-199">ユーザー設定と通知設定</span><span class="sxs-lookup"><span data-stu-id="24f30-199">Preferences and notification settings;</span></span>
- <span data-ttu-id="24f30-200">[Visual Studio で問題を報告する](/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)ことによって、または、[開発者コミュニティ](https://developercommunity.visualstudio.com)経由で提供された添付ファイル</span><span class="sxs-lookup"><span data-stu-id="24f30-200">Attachments you provided by [reporting a problem in Visual Studio](/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017) or through [Developer Community](https://developercommunity.visualstudio.com).</span></span>
- <span data-ttu-id="24f30-201">投票</span><span class="sxs-lookup"><span data-stu-id="24f30-201">Your votes</span></span>

> [!NOTE]
> <span data-ttu-id="24f30-202">公開情報 (コメント、解決策、報告済みの問題) は削除されずに、匿名化されます。</span><span class="sxs-lookup"><span data-stu-id="24f30-202">We will not delete, but will anonymize, the following public information: your comments, your solutions, problems that you reported.</span></span>
>
> [!IMPORTANT]
> <span data-ttu-id="24f30-203">AAD または MSA アカウントを削除すると、[開発者コミュニティ](https://developercommunity.visualstudio.com)の削除プロセスがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="24f30-203">Delete of an AAD or MSA account triggers the Delete process for [Developer Community](https://developercommunity.visualstudio.com).</span></span>

<span data-ttu-id="24f30-204">削除を開始するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="24f30-204">To initiate a Delete, follow these steps:</span></span>

1. <span data-ttu-id="24f30-205">[開発者コミュニティ](https://developercommunity.visualstudio.com) にサインインします。</span><span class="sxs-lookup"><span data-stu-id="24f30-205">Sign into [Developer Community](https://developercommunity.visualstudio.com).</span></span> <span data-ttu-id="24f30-206">右上のプロファイルをクリックして、**[プロファイルとユーザー設定]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="24f30-206">From the top-right corner, click on your profile and select **Profile and Preferences**.</span></span>
2. <span data-ttu-id="24f30-207">**[プライバシー]** タブをクリックしてから、**[データとアカウントの削除]** をクリックし、データの削除を開始します。</span><span class="sxs-lookup"><span data-stu-id="24f30-207">Click the **Privacy** tab, and then click **Delete your data and account** to start deleting your data.</span></span>
3. <span data-ttu-id="24f30-208">確認画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="24f30-208">A confirmation screen will appear.</span></span>
4. <span data-ttu-id="24f30-209">ボックスに "delete" と入力してから、**[マイ アカウントの削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24f30-209">Type "delete" in the box, and then click **Delete my account**.</span></span>

<span data-ttu-id="24f30-210">**[マイ アカウントの削除]** をクリックすると:</span><span class="sxs-lookup"><span data-stu-id="24f30-210">Once you click **Delete my account:**</span></span>

- <span data-ttu-id="24f30-211">サインアウトされます。</span><span class="sxs-lookup"><span data-stu-id="24f30-211">We will sign you out.</span></span>
- <span data-ttu-id="24f30-212">[開発者コミュニティ](https://developercommunity.visualstudio.com) アカウント、個人データ、および添付ファイルが削除されます。</span><span class="sxs-lookup"><span data-stu-id="24f30-212">We will delete your [Developer Community](https://developercommunity.visualstudio.com) account, your personal data, and attachments.</span></span>
- <span data-ttu-id="24f30-p117">パブリック フィードバックが匿名化されます。パブリック フィードバックは、開発者コミュニティでは使用可能なままで、匿名ユーザーから報告されたかのように表示されます。</span><span class="sxs-lookup"><span data-stu-id="24f30-p117">We will anonymize your public feedback. Your public feedback will remain available on Developer Community, and will be indicated as reported by an Anonymous user.</span></span>
- <span data-ttu-id="24f30-215">アカウントを削除しても、電子メールは送信されません。これは、システム内に存在しなくなるためです。</span><span class="sxs-lookup"><span data-stu-id="24f30-215">We won't email you after we delete your account, because you will no longer be present in the system.</span></span>
- <span data-ttu-id="24f30-216">新しい問題を報告するか、[開発者コミュニティ](https://developercommunity.visualstudio.com)にログインすると、新しいユーザーとして識別されます。</span><span class="sxs-lookup"><span data-stu-id="24f30-216">If you report a new problem or log into [Developer Community](https://developercommunity.visualstudio.com), you will be identified as a new user.</span></span>
- <span data-ttu-id="24f30-217">[開発者コミュニティ](https://developercommunity.visualstudio.com)からアカウントを削除しても、他の Microsoft サービスからは削除されません。</span><span class="sxs-lookup"><span data-stu-id="24f30-217">If you delete your account from [Developer Community](https://developercommunity.visualstudio.com), we will not delete it from other Microsoft services.</span></span>

## <a name="xamarin-forums"></a><span data-ttu-id="24f30-218">Xamarin フォーラム</span><span class="sxs-lookup"><span data-stu-id="24f30-218">Xamarin Forums</span></span>

### <a name="personal-data-we-collect"></a><span data-ttu-id="24f30-219">Microsoft が収集する個人データ</span><span class="sxs-lookup"><span data-stu-id="24f30-219">Personal Data We Collect</span></span>

<span data-ttu-id="24f30-220">Microsoft は、[Xamarin フォーラム](https://forums.xamarin.com/) ユーザー コミュニティを通して、Microsoft 製品とサービスに関する問題を再現してトラブルシューティングするためにユーザーが提供するデータを 収集します。</span><span class="sxs-lookup"><span data-stu-id="24f30-220">Through the [Xamarin Forums](https://forums.xamarin.com/) user community, Microsoft collects data you provide to help us reproduce and troubleshoot issues you may have with Microsoft products and services.</span></span> <span data-ttu-id="24f30-221">このデータには、個人データと公的フィードバックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="24f30-221">This data includes personal data and public feedback.</span></span> <span data-ttu-id="24f30-222">収集する個人データは、ユーザー アカウント データ (Xamarin フォーラムに関連付けられているユーザー名とメールアドレスなど) で、収集する公的フィードバックは、ユーザーが Xamarin フォーラムで提供するバグ、問題、コメント、解決方法を含みます。</span><span class="sxs-lookup"><span data-stu-id="24f30-222">The personal data we collect is user account data (for example, user names and email addresses associated with your Xamarin Forums), and the public feedback we collect includes bugs, problems, comments, and solutions you provide via the Xamarin Forums.</span></span>

### <a name="how-you-can-control-your-data"></a><span data-ttu-id="24f30-223">データの管理方法</span><span class="sxs-lookup"><span data-stu-id="24f30-223">How You Can Control Your Data</span></span>

#### <a name="xamarin-forums"></a><span data-ttu-id="24f30-224">Xamarin フォーラム</span><span class="sxs-lookup"><span data-stu-id="24f30-224">Xamarin Forums</span></span>

##### <a name="view"></a><span data-ttu-id="24f30-225">表示</span><span class="sxs-lookup"><span data-stu-id="24f30-225">View</span></span>

<span data-ttu-id="24f30-p119">アクティブな Xamarin フォーラム アカウントを持っているユーザーは、Xamarin フォーラム アカウント ページから個人データとパブリック フィードバック (投稿済みのスレッドと投稿のすべてなど) を表示できます。ユーザーは、アカウント ページ経由で個人データを編集することもできます。</span><span class="sxs-lookup"><span data-stu-id="24f30-p119">Users with active Xamarin Forums accounts may view their personal data and public feedback (for example, all of their posted threads and posts) from their Xamarin Forums account page. Users may also edit their personal data through their account page.</span></span>

##### <a name="export"></a><span data-ttu-id="24f30-228">エクスポート</span><span class="sxs-lookup"><span data-stu-id="24f30-228">Export</span></span>

<span data-ttu-id="24f30-p120">Xamarin フォーラムは、サードパーティの Vanilla フォーラムでホストされます。公開データのエクスポートを要求するには、ユーザーが forums@xamarin.com (Xamarin チームによって監視される) に問い合わせる必要があります。その後で、Vanilla フォーラムを直接操作してこの要求を処理します。</span><span class="sxs-lookup"><span data-stu-id="24f30-p120">Xamarin Forums are hosted by a third party, Vanilla Forums. To request export of your public data, users should contact forums@xamarin.com (monitored by the Xamarin team). We will then work directly with Vanilla Forums to process this request.</span></span>

##### <a name="delete"></a><span data-ttu-id="24f30-232">削除する</span><span class="sxs-lookup"><span data-stu-id="24f30-232">Delete</span></span>

<span data-ttu-id="24f30-p121">Xamarin Forumは、サードパーティの Vanilla Forums によりホストされています。個人データと公開データの削除を依頼するには、forums@xamarin.com (Xamarin チームによってモニターされています) にお問い合わせください。その後に、ユーザーからの個人データ削除依頼を手動で処理いたします。</span><span class="sxs-lookup"><span data-stu-id="24f30-p121">Xamarin Forums are hosted by a third party, Vanilla Forums. To request deletion of your personal and public data, users should contact forums@xamarin.com (monitored by the Xamarin team). We will then manually service the user's personal data deletion request.</span></span>

> [!NOTE]
> <span data-ttu-id="24f30-236">Xamarin の Bugzilla は、新しい問題を受け付けていません。</span><span class="sxs-lookup"><span data-stu-id="24f30-236">Bugzilla for Xamarin no longer accepts new issues.</span></span> <span data-ttu-id="24f30-237">以前の Xamarin Bugzilla アカウントを持っているユーザーは、ユーザーが報告したすべてのバグのアーカイブおよびユーザーがバグに追加したすべてのコメントを [https://xamarin.github.io/bugzilla-archives/](https://xamarin.github.io/bugzilla-archives/) で見ることができます。</span><span class="sxs-lookup"><span data-stu-id="24f30-237">Former Xamarin Bugzilla accounts holders can view an archive of all bugs they've reported and all comments they've added to bugs at [https://xamarin.github.io/bugzilla-archives/](https://xamarin.github.io/bugzilla-archives/).</span></span> <span data-ttu-id="24f30-238">アーカイブに含まれる個人データの削除を要求するには、ユーザーは [https://github.com/xamarin/bugzilla-archives/issues/new/choose](https://github.com/xamarin/bugzilla-archives/issues/new/choose) で問題を提出できます。</span><span class="sxs-lookup"><span data-stu-id="24f30-238">To request deletion of personal data contained in the archive, users can file and issue at [https://github.com/xamarin/bugzilla-archives/issues/new/choose](https://github.com/xamarin/bugzilla-archives/issues/new/choose).</span></span> <span data-ttu-id="24f30-239">削除要求の受理後、ユーザーが Xamarin Bugzilla に投稿したパブリック フィードバック (バグ、問題、コメント、解決策など) は削除されません。</span><span class="sxs-lookup"><span data-stu-id="24f30-239">Public feedback (for example, bugs, problems, comments, and solutions) that users have posted to the Xamarin Bugzilla will not be deleted after receipt of a delete request.</span></span> <span data-ttu-id="24f30-240">その代わり、削除要求の送信者によって作成されたパブリック フィードバックに関連付けられている名前とメール アドレスを削除することによりパブリック フィードバックは匿名化されます。</span><span class="sxs-lookup"><span data-stu-id="24f30-240">Public feedback will instead be anonymized by removing the name and email address associated with any public feedback created by the user submitting the delete request.</span></span>

## <a name="nuget"></a><span data-ttu-id="24f30-241">NuGet</span><span class="sxs-lookup"><span data-stu-id="24f30-241">NuGet</span></span>

<span data-ttu-id="24f30-242">NuGet.org の DSR の詳細については、「[NuGet ユーザー データ要求](/nuget/policies/data-requests)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24f30-242">For more information on DSR for NuGet.org, see [NuGet User Data Requests](/nuget/policies/data-requests).</span></span>

## <a name="aspnet"></a><span data-ttu-id="24f30-243">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="24f30-243">ASP.NET</span></span>

<span data-ttu-id="24f30-244">ASP.NET Web サイトの DSR については、「[ASP.NET Web サイトと GDPR データ主体要求の処理](https://www.asp.net/gdpr)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24f30-244">For information on DSR for the ASP.NET website, see [The ASP.NET Website and GDPR Data Subject Request processing](https://www.asp.net/gdpr).</span></span>

## <a name="iisnet"></a><span data-ttu-id="24f30-245">IIS.NET</span><span class="sxs-lookup"><span data-stu-id="24f30-245">IIS.NET</span></span>

<span data-ttu-id="24f30-246">IIS.NET Web サイトの DSR については、「[IIS.NET Web サイトと GDPR データ主体要求の処理](https://www.iis.net/gdpr)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24f30-246">For information on DSR for the IIS.NET website, see [The IIS.NET Website and GDPR Data Subject Request processing](https://www.iis.net/gdpr).</span></span>

## <a name="other-visual-studio-family-services"></a><span data-ttu-id="24f30-247">その他の Visual Studio ファミリ サービス</span><span class="sxs-lookup"><span data-stu-id="24f30-247">Other Visual Studio Family Services</span></span>

### <a name="survey-monkey"></a><span data-ttu-id="24f30-248">Survey Monkey</span><span class="sxs-lookup"><span data-stu-id="24f30-248">Survey Monkey</span></span>

<span data-ttu-id="24f30-249">時々、これらの製品に関するお客様からのフィードバックを Survey Monkey を介して募集することもあります。</span><span class="sxs-lookup"><span data-stu-id="24f30-249">From time to time, we invite customers to provide feedback on these products via Survey Monkey.</span></span> <span data-ttu-id="24f30-250">このデータは、28 日以内に Survey Monkey から削除されます。</span><span class="sxs-lookup"><span data-stu-id="24f30-250">This data is deleted from Survey Monkey within 28 days.</span></span> <span data-ttu-id="24f30-251">Microsoft は、このデータを最大 18 か月間、社内で保持する場合があります。</span><span class="sxs-lookup"><span data-stu-id="24f30-251">Microsoft may retain this data internally for up to 18 months.</span></span> <span data-ttu-id="24f30-252">アンケートの回答が認証されている場合は、これらの製品のデータ主体の要求に対応するときに、データ主体の要求をエクスポートおよび削除に含めます。</span><span class="sxs-lookup"><span data-stu-id="24f30-252">If survey responses are authenticated, then we include them in export and delete data subject requests when servicing data subject requests for these products.</span></span>

## <a name="learn-more"></a><span data-ttu-id="24f30-253">詳細情報</span><span class="sxs-lookup"><span data-stu-id="24f30-253">Learn more</span></span>

- [<span data-ttu-id="24f30-254">一般公開されているエンタープライズ ソフトウェア製品のお客様に対する Microsoft の GDPR コミットメント</span><span class="sxs-lookup"><span data-stu-id="24f30-254">Microsoft's GDPR Commitments to Customers of our Generally Available Enterprise Software Products</span></span>](/legal/gdpr)
- [<span data-ttu-id="24f30-255">Microsoft Trust Center</span><span class="sxs-lookup"><span data-stu-id="24f30-255">Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
- [<span data-ttu-id="24f30-256">Service Trust Portal</span><span class="sxs-lookup"><span data-stu-id="24f30-256">Service Trust portal</span></span>](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)
- [<span data-ttu-id="24f30-257">Microsoft プライバシー ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="24f30-257">Microsoft Privacy Dashboard</span></span>](https://account.microsoft.com/privacy)
- [<span data-ttu-id="24f30-258">Microsoft Privacy Response Center</span><span class="sxs-lookup"><span data-stu-id="24f30-258">Microsoft Privacy Response Center</span></span>](https://aka.ms/userprivacysite)
- [<span data-ttu-id="24f30-259">GDPR のための Azure データ サブジェクト要求</span><span class="sxs-lookup"><span data-stu-id="24f30-259">Azure Data Subject Requests for the GDPR</span></span>](gdpr-dsr-azure.md)
