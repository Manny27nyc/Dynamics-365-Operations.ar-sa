---
title: "المبلغ التقريبي لعمليات حساب الإهلاك"
description: "تتناول هذه المقالة حقل \"تقريب الإهلاك\" الموجود في صفحات إعداد الدفتر."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBookTable, AssetDepBookTable
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13931
ms.assetid: faf7db87-046f-41d1-9baf-0df66e373e97
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 8d5a9d9267c14ee045388c3b3b42b26f2fff45ea
ms.contentlocale: ar-sa
ms.lasthandoff: 05/25/2017


---

# <a name="round-off-amount-for-depreciation-calculations"></a>المبلغ التقريبي لعمليات حساب الإهلاك

[!include[banner](../includes/banner.md)]


تتناول هذه المقالة حقل "تقريب الإهلاك" الموجود في صفحات إعداد الدفتر.

‏‫يتم تعيين مبالغ تقريب الإهلاك لكل دفتر. وتُستخدم مبالغ الإهلاك التقريبية في ملف تعريف إهلاك الأصول الثابتة، الذي يوضح الإهلاك المستقبلي وقيمة الأصل الثابت، وكذلك في مقترحات الإهلاك.‬ أدخل الحد الأدنى لمبلغ إهلاك المسموح به للدفتر. 

وبغض النظر عن التقريب الذي تم إعداده، يتم تقريب مبلغ الإهلاك في فترة الإهلاك الأخيرة. وفي نهاية فترة الإهلاك الأخيرة، يجب أن تكون قيمة الأصل الثابت 0 (صفر) أو قيمة الخردة، إذا تم استخدام قيمة الخردة.

### <a name="example"></a>مثال

يتم حساب الإهلاك بدون أي تقريب على شكل 2,444.44. وكما يُظهر الجدول التالي، تختلف المبالغ المقترحة، استنادًا إلى كيفية إعداد التقريب.

| أسلوب التقريب | مبلغ الإهلاك |
|-----------------|---------------------|
| التقريب 0.1    | 2,444.40            |
| التقريب 1.00   | 2,444.00            |
| التقريب 10.00  | 2,440.00            |
| التقريب 100.00 | 2,400.00            |





