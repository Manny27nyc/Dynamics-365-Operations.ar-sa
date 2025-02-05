---
title: استخدام دفعة واحدة لتسوية فواتير متعددة تمتد عبر عدة فترات خصم
description: توضح هذه المقالة كيفية دفع فواتير متعددة حين تتأهل كل فاتورة للحصول على خصم نقدي. تقوم السيناريوهات في هذه المقالة بتسليط الضوء على اختلاف الخصومات النقدية التي يتم أخذها باختلاف الوقت الذي يتم فيه تسديد الدفع.
author: ShivamPandey-msft
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: kfend
ms.custom: 14511
ms.assetid: 3e42ccb5-b9d7-4a70-8db9-4206d10fd433
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e6035973abea9dacd4b6d4d8bf2fd3c7d6b10fb0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872633"
---
# <a name="use-one-payment-to-settle-invoices-that-span-multiple-discount-periods"></a>استخدام دفعة واحدة لتسوية فواتير متعددة تمتد عبر عدة فترات خصم

[!include [banner](../includes/banner.md)]

توضح هذه المقالة كيفية دفع فواتير متعددة حين تتأهل كل فاتورة للحصول على خصم نقدي. تقوم السيناريوهات في هذه المقالة بتسليط الضوء على اختلاف الخصومات النقدية التي يتم أخذها باختلاف الوقت الذي يتم فيه تسديد الدفع.

‏‫شركة الاتحاد للتصنيع تبيع السلع للعميل 4032. تقدم هذه الشركة خصمًا نقديًا بنسبة 1 في المائة، إذا تم دفع الفاتورة في غضون 14 يومًا.‬ كما تقدم شركة الاتحاد للتصنيع الخصومات النقدية في دفعات جزئية. وتوجد معلمات التسوية في صفحة **معلمات الحسابات المدينة**.

## <a name="invoices"></a>الفواتير
لدى العملاء 4032 ثلاث فواتير بإجمالي 3000.00:

-   ‏‫تم إدخال فاتورة FTI-10040 بمبلغ 1000.00 في 15 أيار/مايو. وهذه الفاتورة مؤهلة للحصول على خصم نقدي بنسبة 1 في المائة، إذا تم الدفع في غضون 14 يومًا.‬
-   ‏‫تم إدخال فاتورة FTI-10041 بمبلغ 1000.00 في 25 حزيران/يونيو. وهذه الفاتورة مؤهلة للحصول على خصم نقدي بنسبة 1 في المائة، إذا تم الدفع في غضون 14 يومًا.‬
-   ‏‫تم إدخال فاتورة FTI-10042 بمبلغ 1000.00 في 25 حزيران/يونيو. وهذه الفاتورة مؤهلة للحصول على خصم نقدي بنسبة 2 في المائة، إذا دُفعت في ظرف خمسة أيام، وخصم بنسبة 1 في المائة، إذا تم الدفع في غضون 14 يومًا.‬

## <a name="settle-all-invoices-on-june-29"></a>تسوية كافة الفواتير في 29 حزيران/يونيو
إذا قام جمال بإنشاء دفتر يومية مدفوعات لتسوية هذه الفواتير بالكامل في 29 يونيو، تساوي الدفعة 2970.00. مجموع كافة مبالغ الخصم هو 30.00. يُنشئ جمال دفعة للعميل 4032، ثم يقوم بفتح صفحة **تسوية الحركات**. في صفحة **تسوية الحركات**، يقوم جمال بتمييز كافة بنود الفاتورة الثلاثة للتسوية:

-   تساوي دفعة فاتورة FTI-10040 مبلغ 1000.00. ولم يتم الحصول على أي خصم نقدي.
-   تساوي دفعة فاتورة FTI-10041 مبلغ 990.00. يتم الحصول على خصم نقدي بنسبة 1 في المائة أو 10.00.
-   تساوي دفعة فاتورة FTI-10042 مبلغ 980.00. يتم الحصول على خصم نقدي بنسبة 2 في المائة أو 20.00.

| وضع علامة                     | استخدام الخصم النقدي | الإيصال   | الحساب | التاريخ      | تاريخ الاستحقاق  | الفاتورة | المبلغ في خصم بعملة الحركة | المبلغ في الائتمان بعملة الحركة | عملة | المبلغ المراد تسويته |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| محدَد                 | عادي            | FTI-10040 | 4032    | 5/15/2015 | 6/15/2015 | 10040   | 1000.00                             |                                       | دولار أمريكي      | 1000.00         |
| محدَد                 | عادي            | FTI-10041 | 4032    | 6/25/2015 | 7/25/2015 | 10041   | 1000.00                             |                                       | دولار أمريكي      | 990.00           |
| المحددة والمميزة | عادي            | FTI-10042 | 4032    | 6/25/2015 | 7/25/2015 | 10042   | 1000.00                             |                                       | دولار أمريكي      | 980.00           |

بعد ترحيل الدفعة، يبلغ رصيد العميل 0.00.

## <a name="settle-all-invoices-on-july-1"></a>تسوية كافة الفواتير في 1 يوليو
إذا قام جمال بإنشاء دفتر يومية مدفوعات لتسوية هذه الفواتير بالكامل في 1 يوليو، تساوي الدفعة 2980.00. يُنشئ جمال دفعة للعميل 4032، ثم يقوم بفتح صفحة **تسوية الحركات**. في صفحة **تسوية الحركات**، يقوم جمال بتمييز كافة بنود الفاتورة الثلاثة للتسوية:

-   تساوي دفعة فاتورة FTI-10040 مبلغ 1000.00. ولم يتم الحصول على أي خصم نقدي.
-   تساوي دفعة فاتورة FTI-10041 مبلغ 990.00. يتم الحصول على خصم نقدي بنسبة 1 في المائة أو 10.00.
-   تساوي دفعة فاتورة FTI-10042 مبلغ 990.00. يتم الحصول على خصم نقدي بنسبة 1 في المائة أو 10.00. وعلى الرغم من أن 1 يوليو يأتي بعد الفترة التي تؤهب للحصول على خصم بنسبة 2 في المائة، إلا أنه لا يزال في الفترة التي تؤهل للحصول على خصم بنسبة 1 بالمائة.

| وضع علامة                     | استخدام الخصم النقدي | الإيصال   | الحساب | التاريخ      | تاريخ الاستحقاق  | الفاتورة | المبلغ في خصم بعملة الحركة | المبلغ في الائتمان بعملة الحركة | عملة | المبلغ المراد تسويته |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| محدَد                 | عادي            | FTI-10040 | 4032    | 5/15/2015 | 6/15/2015 | 10040   | 1000.00                             |                                       | دولار أمريكي      | 1000.00         |
| محدَد                 | عادي            | FTI-10041 | 4032    | 6/25/2015 | 7/25/2015 | 10041   | 1000.00                             |                                       | دولار أمريكي      | 990.00           |
| المحددة والمميزة | عادي            | FTI-10042 | 4032    | 6/25/2015 | 7/25/2015 | 10042   | 1000.00                             |                                       | دولار أمريكي      | 990.00           |

## <a name="partial-settlement-on-june-29"></a>التسوية الجزئية في 29 يونيو
يمكن للعميل 4032 دفع مبلغ جزئي، مثل النصف لكل فاتورة. يُنشئ جمال دفعة للعميل 4032، ثم يقوم بفتح صفحة **تسوية الحركات**. وفي صفحة **تسوية الحركات**، يقوم جمال بتمييز كافة بنود الفاتورة الثلاثة للتسوية. وفي كل بند، يقوم جمال بإدخال مبلغ للتسوية، استنادًا إلى تعليمات التي قدمها العميل. وعندما يحدد جمال بندًا، يشاهد جمال الخصم النقدي الخاص بهذا البند ومبلغ الخصم النقدي الذي يتم الحصول عليه. ولأن العميل يقوم بدفع نصف الفاتورة، يشاهد جمال أن القيمة الموجودة في حقل **مبلغ الخصم النقدي** الخاص بفاتورة FTI-10042 يساوي **20.00**، ولكن القيمة في حقل **الخصم النقدي الذي تم الحصول عليه** تساوي **10.00**. مبلغ الدفعة يساوي 1485.00.

| وضع علامة                     | استخدام الخصم النقدي | الإيصال   | الحساب | التاريخ      | تاريخ الاستحقاق  | الفاتورة | المبلغ في خصم بعملة الحركة | المبلغ في الائتمان بعملة الحركة | عملة | المبلغ المراد تسويته |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| محدَد                 | عادي            | FTI-10040 | 4032    | 5/15/2015 | 6/15/2015 | 10040   | 1000.00                             |                                       | دولار أمريكي      | 500.00           |
| محدَد                 | عادي            | FTI-10041 | 4032    | 6/25/2015 | 7/25/2015 | 10041   | 1000.00                             |                                       | دولار أمريكي      | 495.00           |
| المحددة والمميزة | عادي            | FTI-10042 | 4032    | 6/25/2015 | 7/25/2015 | 10042   | 1000.00                             |                                       | دولار أمريكي      | 490.00           |

‏‫كما يستطيع جمال يدويًا إدخال مبلغ الدفعة 1485.00 قبل فتح صفحة **تسوية الحركات**. وإذا قام جمال يدويًا بإدخال مبلغ الدفعة، ثم قام بتمييز كافة الحركات الثلاث، ولكن لا يمكنه تعديل القيمة الواردة في حقل **‬‏‫المبلغ المُراد تسويته** لكل حركة، فإنه يتلقى الرسالة التالية عندما يتم إغلاق الصفحة:‬

> إجمالي مبلغ الحركات المحددة مختلف عن مبلغ دفتر اليومية. هل تريد تغيير مبلغ دفتر اليومية؟

إذا أراد جمال أن يكون مبلغ الدفعة 1485.00 فقط، فإنه ينقر فوق **لا**، ثم يقوم بترحيل دفتر اليومية. فيما يلي الحركات التي تمت تسويتها:

1.  تمت تسوية فاتورة FTI-10040 بالكامل لمبلغ 1000.00، لأنه تم إدخالها في 15 أيار/مايو في الفواتير الأقدم. ولم يتم الحصول على أي خصم نقدي. المبلغ المتبقي في حركة الدفع هو 485.00.
2.  لم تتم تسوية فاتورة FTI-10041 على الإطلاق. تم إدخال فاتورتي FTI-10041 وFTI-10042 في نفس التاريخ. ومع ذلك، يتوفر خصم بنسبة 1 بالمائة للفاتورة FTI-10041، ويتوفر خصم بنسبة 2 بالمائة للفاتورة FTI-10042. ونظرًا لتوفر خصم أفضل للفاتورة FTI-10042، فإنه تتم تسوية المبلغ المتبقي 485.00 المتبقية بالفاتورة FTI-10042.
3.  تتم تسوية فاتورة FTI-10042 بالمبلغ المتبقي 485.00. تقدم شركة الاتحاد للتصنيع خصومات جزئية. في هذه الحالة، يساوي الخصم 9.90 (= 485.00 ÷ 0.98 × 0.02). وتتم قسمة المبلغ (485.00) على 0.98، لأن هناك خصم بنسبة 2 في المائة (وبالتالي، يدفع العميل 98 في المائة من الفاتورة). ويتم فيما بعد ضرب النتيجة في النسبة المئوية للخصم أو 2 بالمائة. الدفعة بمبلغ 485.00 زائد الخصم بمبلغ 9.90 يساوي 494.90. مبلغ الفاتورة الأصلية كان 1000.00. ولذلك، تشتمل الحركة على رصيد 505.10 (= 1000.00 – 494.90).

يعرض جمال المعلومات الواردة في صغحة **حركات العميل**.

| الإيصال    | نوع الحركة | التاريخ      | الفاتورة | المبلغ في خصم بعملة الحركة | المبلغ في الائتمان بعملة الحركة | الرصيد  | عملة |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10040  | الفاتورة          | 5/15/2015 | 10040   | 1000.00                             |                                       | 0.00     | دولار أمريكي      |
| FTI-10041  | الفاتورة          | 6/25/2015 | 10041   | 1000.00                             |                                       | 1000.00 | دولار أمريكي      |
| FTI-10042  | الفاتورة          | 6/25/2015 | 10042   | 1000.00                             |                                       | 505.10   | دولار أمريكي      |
| ARP-10040  | الدفع          | 6/29/2015 |         |                                      | 1485.00                              | 0.00     | دولار أمريكي      |
| DISC-10040 | الخصم النقدي    | 6/29/2015 |         |                                      | 9.90                                  | 0.00     | دولار أمريكي      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
