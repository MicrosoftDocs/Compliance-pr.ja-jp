---
title: Skype for Business Server の GDPR
description: オンプレミスの Skype for Business Server および Lync Server での GDPR の要件に対応する方法について説明します。
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.collection: MS-Compliance
hideEdit: true
ms.openlocfilehash: f0c59e0b4fb6fd80fd13521a3ed4996e787474bc
ms.sourcegitcommit: 024137a15ab23d26cac5ec14c36f3577fd8a0cc4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51496009"
---
# <a name="gdpr-for-skype-for-business-server-and-lync-server"></a><span data-ttu-id="8281d-103">Skype for Business Server および Lync Server の GDPR</span><span class="sxs-lookup"><span data-stu-id="8281d-103">GDPR for Skype for Business Server and Lync Server</span></span>

<span data-ttu-id="8281d-p101">Skype for Business Server および Lync Server のデータのほとんどは、Exchange Server に保存されます。それには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8281d-p101">Most Skype for Business Server and Lync Server data is stored in Exchange Server. This includes:</span></span>

-   <span data-ttu-id="8281d-106">会話の履歴</span><span class="sxs-lookup"><span data-stu-id="8281d-106">Conversation history</span></span>

-   <span data-ttu-id="8281d-107">ボイスメールの通知とトランスクリプション</span><span class="sxs-lookup"><span data-stu-id="8281d-107">Voicemail notifications and transcriptions</span></span>

-   <span data-ttu-id="8281d-108">会議の招待</span><span class="sxs-lookup"><span data-stu-id="8281d-108">Meeting invites</span></span>

<span data-ttu-id="8281d-109">[GDPR for Exchange Server](gdpr-for-exchange-server.md) について概要が示されている手順を使用して、GDPR 要求のこれらのデータ タイプを検索、エクスポート、削除します。</span><span class="sxs-lookup"><span data-stu-id="8281d-109">Use the procedures outlined for [GDPR for Exchange Server](gdpr-for-exchange-server.md) to find, export, or delete these types of data for GDPR requests.</span></span>

<span data-ttu-id="8281d-p102">連絡先リストは、SQL Server のデータベースに保存されます。それらは、次の方法でエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="8281d-p102">Contact lists are stored in the SQL Server database. They can be exported in the following ways:</span></span>

-   <span data-ttu-id="8281d-p103">エンド ユーザー自身がグループ ヘッダーを右クリックして [コピー] を選択することにより、連絡先をエクスポートできます。この場合、そのグループのすべての連絡先がクリップボードにコピーされ、任意のアプリに貼り付けることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="8281d-p103">End users themselves can export the contacts by right clicking the group header and selecting Copy. This will copy all the contacts in that group into the clipboard, which can then be pasted into any app.</span></span>

-   <span data-ttu-id="8281d-114">[Export-CsUserData](/powershell/module/skype/export-csuserdata) コマンドレットを使用することにより、このデータをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="8281d-114">You can use the [Export-CsUserData](/powershell/module/skype/export-csuserdata) cmdlet to export this data.</span></span>

<span data-ttu-id="8281d-p104">会議にアップロードされるコンテンツ (PowerPoint のファイルや配布資料など) または会議で生成されるコンテンツ (ホワイトボード、投票、Q/A など) は、ファイラーに保存されます。また、これらは、エンド ユーザーがまだ期限切れでない会議に再びログインして、アップロードされたコンテンツをダウンロードしたり、生成されたコンテンツの場合にはスクリーンショットを撮ってエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="8281d-p104">Content uploaded into meetings (such as PowerPoint files or handouts) or content generated in a meeting (such as whiteboard, polls, or Q/A) is stored in the filer. This can also be exported if end users log back into any meeting that has not expired and download any uploaded content or take screenshots in the case of generated content.</span></span>

<span data-ttu-id="8281d-p105">Exchange の予定表および連絡先リストにない MeetNow 会議および連絡先権限 (家族や同僚など) は、ユーザー データベース内にあります。Lync Server 2013 以降の場合は、[Export-CsUserData](/powershell/module/skype/export-csuserdata) コマンドレットを使用することにより、このデータをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="8281d-p105">MeetNow meetings that are not in the Exchange Calendar and Contact List and contact rights (family, co-worker, etc.) are in the User Database. In Lync Server 2013 and later, you can use the [Export-CsUserData](/powershell/module/skype/export-csuserdata) cmdlet to export this data.</span></span>
