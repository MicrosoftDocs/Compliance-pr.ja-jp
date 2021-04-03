---
title: Project Server での GDPR 対応
description: オンプレミスの Project Server で一般データ保護規則 (GDPR) の要件に対応する方法について説明します。
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
ms.custom: seo-marvel-apr2020
ms.collection: MS-Compliance
hideEdit: true
ms.openlocfilehash: ddbf22523caf1869d0253599216fff07ee14f751
ms.sourcegitcommit: 024137a15ab23d26cac5ec14c36f3577fd8a0cc4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51495951"
---
# <a name="gdpr-for-project-server"></a><span data-ttu-id="c21ce-103">Project Server での GDPR 対応</span><span class="sxs-lookup"><span data-stu-id="c21ce-103">GDPR for Project Server</span></span>

<span data-ttu-id="c21ce-p101">Project Server では、Project Web App でユーザー データをエクスポートしたり編集したりするために、カスタム スクリプトが使用されます。基本的な処理は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c21ce-p101">Project Server uses custom scripts to export and redact user data in Project Web App. The basic process is:</span></span>

1.  <span data-ttu-id="c21ce-106">ファーム内で Project Web App のサイトを検索します。</span><span class="sxs-lookup"><span data-stu-id="c21ce-106">Find the Project Web App sites in your farm.</span></span>

2.  <span data-ttu-id="c21ce-107">各サイトの中で、ユーザーが含まれているプロジェクトを検索します。</span><span class="sxs-lookup"><span data-stu-id="c21ce-107">Find the projects in each site that contain the user.</span></span>

3.  <span data-ttu-id="c21ce-108">確認対象となるタイプのデータをエクスポートし、確認します。</span><span class="sxs-lookup"><span data-stu-id="c21ce-108">Export and review the types of data that you want to review.</span></span>

4.  <span data-ttu-id="c21ce-109">必要に応じてデータを編集します。</span><span class="sxs-lookup"><span data-stu-id="c21ce-109">Redact data as needed.</span></span>

<span data-ttu-id="c21ce-110">これらの手順について、以下の記事で詳細に説明します。</span><span class="sxs-lookup"><span data-stu-id="c21ce-110">These steps are covered in detail in the following articles:</span></span>

- [<span data-ttu-id="c21ce-111">Project Server からユーザー データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="c21ce-111">Export user data from Project Server</span></span>](/Project/export-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)

- [<span data-ttu-id="c21ce-112">Project Server からユーザー データを削除する</span><span class="sxs-lookup"><span data-stu-id="c21ce-112">Delete user data from Project Server</span></span>](/Project/delete-user-data-from-project-server?toc=/Office365/Enterprise/toc.json)


<span data-ttu-id="c21ce-p102">Project Server は SharePoint Server 上に構築されており、SharePoint ULS のログおよび利用状況データベースにイベントのログが出力されることに注意してください。詳細は「[SharePoint Server での GDPR への対応](gdpr-for-sharepoint-server.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c21ce-p102">Note that Project Server is built on top of SharePoint Server and logs events to the SharePoint ULS logs and Usage database. See [GDPR for SharePoint Server](gdpr-for-sharepoint-server.md) for more information.</span></span>
