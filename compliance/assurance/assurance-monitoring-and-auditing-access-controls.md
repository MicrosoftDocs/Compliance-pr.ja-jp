---
title: Microsoft 365 の監視および監査アクセス制御
description: '概要: Microsoft 365 で利用可能なさまざまな監視および監査アクセス制御の概要について説明します。'
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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- MS-Compliance
f1.keywords:
- NOCSH
titleSuffix: Microsoft Service Assurance
ms.openlocfilehash: 138c2664a5771d15ad9177a56f0f7cb766f4ef5e
ms.sourcegitcommit: 626b0076d133e588cd28598c149a7f272fc18bae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2020
ms.locfileid: "49508149"
---
# <a name="monitoring-and-auditing-access-controls-in-microsoft-365"></a>Microsoft 365 でのアクセス制御の監視と監査

Microsoft では、Microsoft 365 内で発生するすべての委任、特権、および操作の広範な監視と監査を行います。 Microsoft 365 のアクセス制御は、最小限の特権の原則に基づいて構築された自動化されたプロセスであり、データアクセス制御と監査を組み込んでいます。

- 許可されたすべてのアクセスは、一意のユーザーに追跡できます。 管理者はお客様のコンテンツを取り扱う責任があります。
- アクセス制御の要求、承認、および管理操作ログは、セキュリティおよび悪意のあるイベントを分析するためにキャプチャされます。
- アクセスレベルは、セキュリティグループのメンバーシップに基づいてほぼリアルタイムで確認されており、ビジネスの正当な妥当性を持つユーザーのみがシステムにアクセスできるようにします。
- Microsoft 365、そのアクセス制御、および Azure Active Directory と物理データセンターを含むサポートサービスは、 [ISO/IEC 27001](https://www.microsoft.com/TrustCenter/Compliance/iso-iec-27001)、 [iso/IEC 27018](https://www.microsoft.com/TrustCenter/Compliance/iso-iec-27018)、 [SOC](https://www.microsoft.com/TrustCenter/Compliance/SOC)、 [fedramp (Office 365)](https://www.microsoft.com/TrustCenter/Compliance/FedRAMP)、その他の [標準](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)に準拠するために、独立したサードパーティによって定期的に監査されます。
- Microsoft 365 のエンジニアは、毎年セキュリティトレーニングを実施し、昇格したアクセスのベストプロシージャを確認し、Microsoft のセキュリティおよびプライバシーポリシーに同意して、サービスに対する権限を維持する必要があります。

短時間に複数の失敗したログインなど、疑わしい動作が検出されたときに自動アラートがトリガーされます。 Microsoft 365 セキュリティ対応チームは、機械学習と大規模データ分析を使用して、アクティビティのレビューと分析、不規則なアクセスパターンの検索、および異常で不法なアクティビティへの予防的な対応を行います。 また、Microsoft は、一連の侵入テスト担当者を採用しており、定期的に赤色のチームと青のチームの練習を行い、サービスのセキュリティとアクセス制御の問題を見つけます。 お客様は、Microsoft 365 によって提供される監査レポートと管理アクティビティ API を使用して、アクセス制御システムの有効性を確認できます。

詳細については、「 [office 365 Management ACTIVITY API reference](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference) and [Auditing And reporting in Microsoft 365](assurance-auditing-and-reporting-overview.md)」を参照してください。
