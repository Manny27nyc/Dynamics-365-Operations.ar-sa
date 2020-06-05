---
title: إهلاك العامل
description: توفر هذه المقالة نظرة عامة على أسلوب الإهلاك بالمعامل.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13831
ms.assetid: 2b6c4fe4-02ff-4191-bcad-32f1f34c15f2
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c5c36441e926cd5a82c802a350adf6b2ed6d6387
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176209"
---
# <a name="factor-depreciation"></a>إهلاك العامل

[!include [banner](../includes/banner.md)]

توفر هذه المقالة نظرة عامة على أسلوب الإهلاك بالمعامل.

العوامل هي النسب المئوية المُستخدمة في إهلاك الأصول. فعند إعداد ملف تعريف إهلاك الأصل الثابت وتحديد **المعامل** في حقل **الطريقة** في صفحة **ملفات تعريف الإهلاك**، يمكنك إعداد إهلاك القسط الثابت أو التقدمي أو غير التقدمي.

-   إذا قمت بتحديد الإهلاك التقدمي، فسيزيد مبلغ الإهلاك مع كل فترة إهلاك.
-   وفي الإهلاك غير التقدمي، سينخفض مبلغ الإهلاك لكل فترة بمرور الوقت.
-   في إهلاك القسط الثابت، يكون الإهلاك نفس الشيء في كل فترة.

تشير القواعد والأمثلة أدناه إلى كيفية إعداد عوامل لكل نوع إهلاك. 

> [!NOTE] 
> عندما تحدد **المعامل** في حقل **الطريقة**، يتم عرض حقل **المعامل** وحقل **الفترة**.

## <a name="progressive-depreciation"></a>الإهلاك المتتالي
القيمة في حقل **المعامل** أكبر من **50**.

### <a name="example"></a>مثال

يساوي مبلغ الاستحواذ 100000، والمعامل هو 70، ومدة الخدمة 10 سنوات، ويبدأ الإهلاك في 1 يناير. ويتم عرض مبالغ الإهلاك ومبالغ القيم الدفترية الصافية فقط لست سنوات من مدة الخدمة.‬

| سنة | الفترة      | مبلغ الإهلاك | مبلغ صافي القيمة الدفترية |
|------|-------------|---------------------|-----------------------|
| 1    | 31 ديسمبر | 307.69              | 99692.31             |
| 2    | 31 ديسمبر | 1447.21            | 98245.10             |
| 3    | 31 ديسمبر | 3104.50            | 95140.60             |
| 4    | 31 ديسمبر | 5150.21            | 89990.39             |
| 5    | 31 ديسمبر | 7522.95            | 82467.44             |
| 6    | 31 ديسمبر | 10184.06           | 72283.38             |

## <a name="digressive-depreciation"></a>الإهلاك الاستطرادي
القيمة في حقل **المعامل** أقل من **50**.

### <a name="example"></a>مثال

‏‫يساوي مبلغ الاستحواذ 100000، والمعامل هو 20، ومدة الخدمة 10 سنوات، ويبدأ الإهلاك في 1 يناير. ويتم عرض مبالغ الإهلاك ومبالغ القيم الدفترية الصافية فقط لست سنوات من مدة الخدمة.‬

| سنة | الفترة      | مبلغ الإهلاك | مبلغ صافي القيمة الدفترية |
|------|-------------|---------------------|-----------------------|
| 1    | 31 ديسمبر | 56080.43           | 43919.57             |
| 2    | 31 ديسمبر | 10665.70           | 33253.87             |
| 3    | 31 ديسمبر | 7156.22            | 26097.65             |
| 4    | 31 ديسمبر | 5538.06            | 20559.59             |
| 5    | 31 ديسمبر | 4579.89            | 15979.70             |
| 6    | 31 ديسمبر | 3937.36            | 12042.34             |

## <a name="straight-line-depreciation"></a>إهلاك القسط الثابت
القيمة في حقل **المعامل** تساوي **50**. في هذه الحالة، يكون الإهلاك نفس الشيء في كل فترة، ويجب أن تأخذ في الاعتبار آثار القيم التي حددتها في حقول أخرى، كما هو موضح في [إهلاك مدة خدمة القسط الثابت‬](straight-line-service-life-depreciation.md).


