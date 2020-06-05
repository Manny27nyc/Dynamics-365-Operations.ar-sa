---
title: تسوية شيك بتاريخ لاحق من عميل
description: يمكنك تسوية شيك بتاريخ لاحق بعد أن تتم تسوية الشيك من قبل البنك.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPostDatedChecks, SystemDate, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0bc6f90e7adb3facdfa1facb50fecb0de4ccb04d
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141570"
---
# <a name="settle-a-postdated-check-from-a-customer"></a>تسوية شيك بتاريخ لاحق من عميل

[!include [banner](../../includes/banner.md)]

يمكنك تسوية شيك بتاريخ لاحق بعد أن تتم تسوية الشيك من قبل البنك. تعمل هذه الحركة المالية أيضًا على تسوية حركة الحساب الوسيط للشيك بتاريخ لاحق. 

يجب إكمال المهام التالية قبل بدء هذه المهمة.

1) إعداد شيكات بتاريخ لاحق

2) تسجيل شيك بتاريخ لاحق لعميل وترحيله 



ويتمثل دور دلائل المهام هذه في أمين الخزانة.



يستخدم هذا الإجراء شركة بيانات العرض التوضيحي USMF.

1. انتقل إلى الائتمان والتحصيلات > الاستعلامات والتقارير > المدفوعات > شيكات العميل ذات التواريخ اللاحقة.
2. انقر فوق "تسوية".
3. انقر فوق "تسوية إدخالات التسوية".
    * قم بتسوية حساب العميل لحركة الشيك.  
4. قم بإغلاق الصفحة.
5. انتقل إلى دفتر الأستاذ العام > إدخالات دفتر اليومية > دفاتر اليومية العامة‬.
6. في الحقل "إظهار"، حدد خيارًا.
7. حدد خانة اختيار "إظهار العناصر التي أنشاها المستخدم فقط" أو قم بإلغاء تحديدها.
8. في القائمة، قم بالبحث عن السجل المطلوب وحدده.
9. انقر فوق البنود.
10. انقر فوق "الإيصال".
11. قم بإغلاق الصفحة.
