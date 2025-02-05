---
title: ‏‫تعيين قالب فاتورة ذات نص حر إلى عميل
description: توضح هذه المهمة كيفية تعيين قالب فاتورة نص حر إلى عميل.
author: ShivamPandey-msft
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, CustRecurrenceInvoice
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1e8330e26f1450dac27bb837bb56f8bbffefc9bc
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/05/2022
ms.locfileid: "8712191"
---
# <a name="assign-a-free-text-invoice-template-to-a-customer"></a>‏‫تعيين قالب فاتورة ذات نص حر إلى عميل

[!include [banner](../../includes/banner.md)]

توضح هذه المهمة كيفية تعيين قالب فاتورة نص حر إلى عميل. تستخدم هذه المهمة شركة بيانات العرض التوضيحي USMF وهي مخصصة للمستخدم المسؤول عن إدارة فواتير الحسابات المدينة ومعالجتها.

1. في **جزء التنقل**، انتقل إلى **الوحدات النمطية > الحسابات المدينة > العملاء > كافة العملاء**.
2. في القائمة، قم بالبحث عن السجل المطلوب وحدده.
3. في **جزء الإجراءات**، انقر فوق **فاتورة**.
4. انقر فوق **الفواتير المتكررة**. استخدم هذه الصفحة لتعيين قوالب فاتورة النص الحر للعملاء وتحديد مدى تكرار إرسال الفواتير للعميل.  
5. انقر فوق **جديد** لتعيين قالب جديد إلى العميل.
6. في حقل **القالب**، حدد قالب فاتورة النص الحر الذي تريد تعيينه إلى العميل.
7. في القائمة، قم بالبحث عن السجل المطلوب وحدده.
8. في القائمة، انقر فوق الارتباط في الصف المحدد.
9. في الحقل **تاريخ بدء الفوترة**، أدخل التاريخ الذي سيتم فيه إنشاء الفاتورة الأولى.
10. في القسم **انتهاء التكرار‬**، أدخل تاريخ انتهاء التكرار‬.  
    * حدد واحدًا مما يلي: لا يوجد تاريخ انتهاء – سيتم إنشاء الفواتير إلى أجل غير مسمى حتى تتم إزالة القالب من حساب العميل.
    * تاريخ انتهاء الفوترة – حدد هذا الخيار وأدخل آخر تاريخ يمكن إنشاء الفاتورة فيه.  
11. في الحقل **أقصى مبلغ تراكمي‬**، أدخل أقصى مبلغ تراكمي‬ سيتوقف بعده إنشاء الفواتير. أدخل الحد الأقصى للمبلغ التراكمي الذي يمكن الوصول إليه باستخدام القالب المحدد. على سبيل المثال، إذا أدخلت 1,000.00 وأنشأت الفواتير الشهرية لكل 100.00، فسيتوقف إنشاء الفواتير بعد إنشاء الفاتورة العاشرة.  
12. في الحقل **إنشاء فواتير متكررة باستخدام القيم الافتراضية منها‬**، حدد قالب فاتورة النص الحر أو حساب العميل. حدد ما إذا كنت تريد استخدام قالب فاتورة النص الحر أو حساب العميل لتحديد القيم الافتراضية للغة، وترحيل ملف التعريف، ومجموعة ضرائب المبيعات، ومجموعة ضرائب مبيعات الأصناف، وكود القائمة، والبلد/المنطقة للتسليم، والعملة، وشروط الدفع، وطريقة الدفع، ومواصفات الدفع، وجدول الدفع، والخصم النقدي، والأبعاد المالية، وقسيمة التحويل البنكي عندما يتم إنشاء فواتير.  
13. في الحقل **نمط التكرار**، حدد نمط التكرار.
    + يوميًا – حدد هذا الخيار وأدخل عدد الأيام في الحقل "كل". على سبيل المثال، إذا قمت بإدخال 15، فسيتم إنشاء فاتورة كل 15 يومًا لهذا العميل.
    + أسبوعيًا - حدد هذا الخيار وأدخل عدد الأسابيع في الحقل "كل". على سبيل المثال، إذا قمت بإدخال 2، فسيتم إنشاء فاتورة كل أسبوعين لهذا العميل.
    + شهريًا - حدد هذا الخيار وأدخل عدد الأشهر في الحقل "كل". على سبيل المثال، إذا قمت بإدخال 6، فسيتم إنشاء فاتورة كل ستة أشهر لهذا العميل.
    + سنويًا – حدد هذا الخيار وأدخل عدد السنوات في الحقل "كل". على سبيل المثال، إذا قمت بإدخال 2، فسيتم إنشاء فاتورة كل سنتين لهذا العميل.  
14. في الحقل **لكل‬**، أدخل رقمًا.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
