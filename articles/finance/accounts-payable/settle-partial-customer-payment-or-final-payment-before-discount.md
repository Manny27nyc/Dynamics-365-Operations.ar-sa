---
title: تسوية دفعة جزئية والدفعات النهائية بالكامل قبل تاريخ الخصم
description: توفر هذه المقالة السيناريوهات التي تظهر كيفية تسجيل مدفوعات جزئية للعميل وأخذ الخصومات النقدية خلال فترة الخصم النقدي.
author: abruer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 14491
ms.assetid: 0f07d3ce-a439-43ed-a22e-957ccd36a37b
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
ms.openlocfilehash: 7acc4655be35eff73dc5f2cad1fd0f511a0a7fc3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/12/2022
ms.locfileid: "9281314"
---
# <a name="settle-partial-and-final-payments-in-full-before-the-discount-date"></a>تسوية دفعة جزئية والدفعات النهائية بالكامل قبل تاريخ الخصم

[!include [banner](../includes/banner.md)]

توفر هذه المقالة السيناريوهات التي تظهر كيفية تسجيل مدفوعات جزئية للعميل وأخذ الخصومات النقدية خلال فترة الخصم النقدي.

‏‫شركة الاتحاد للتصنيع تبيع السلع للعميل 4028. تقدم هذه الشركة خصمًا نقديًا بنسبة 1 في المائة، إذا تم دفع الفاتورة في غضون 14 يومًا.‬ ويجب دفع الفواتير في غضون 30 يومًا. كما تقدم شركة الاتحاد للتصنيع الخصومات النقدية في دفعات جزئية. وتوجد معلمات التسوية في صفحة **معلمات الحسابات المدينة**.

## <a name="customer-invoice"></a>فاتورة العميل
في 25 حزيران/يونيو، يقوم جمال بإدخال وترحيل فاتورة بمبلغ 1000.00 للعميل 4028. يستطيع جمال عرض هذه الحركة في صغحة **حركات العميل**.

| الإيصال   | نوع الحركة | التاريخ      | الفاتورة | المبلغ في خصم بعملة الحركة | المبلغ في الائتمان بعملة الحركة | الرصيد  | عملة |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10010 | الفاتورة          | 6/25/2015 | 10010   | 1000.00                             |                                       | 1000.00 | دولار أمريكي      |

من صفحة **العميل** أو **حركات العميل**، يستطيع جمال فتح صفحة **تسوية الحركات** لعرض تواريخ ومبالغ الخصومات النقدية المتوفرة للفاتورة. وتاريخ الاستحقاق هو تاريخ 25 تموز/يوليو، ويتوفر خصم نقدي بمبلغ 10.00، إذا تم دفع الفاتورة بحلول تاريخ 9 تموز/يوليو.

| وضع علامة     | استخدام الخصم النقدي | الإيصال   | الحساب | التاريخ      | تاريخ الاستحقاق  | الفاتورة | المبلغ بعملة الحركة | عملة | المبلغ المراد تسويته |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| محدَد | عادي            | FTI-10010 | 4028    | 6/25/2015 | 7/25/2015 | 10010   | 1000.00                       | دولار أمريكي      | 990.00           |

تظهر معلومات الخصم الخاصة بإشعار الدائن أسفل صفحة **تسوية الحركات** للفاتورة المميزة.

|    &nbsp;                    |  &nbsp;   |
|------------------------------|-----------|
| تاريخ الخصم النقدي           | 7/09/2015 |
| مبلغ الخصم النقدي         | 10.00     |
| استخدام الخصم النقدي            | عادي    |
| الخصم النقدي المستقطع          | 0.00      |
| مبلغ الخصم النقدي المطلوب استقطاعه | 10.00     |

ينقر جمال فوق علامة التبويب **الخصم النقدي** لعرض مبلغ الخصم.

| تاريخ الخصم النقدي | مبلغ الخصم النقدي | المبلغ بعملة الحركة |
|--------------------|----------------------|--------------------------------|
| 7/9/2015           | 10.00                | 990.00                         |
| 7/25/2015          | 0.00                 | 1000.00                       |

## <a name="partial-payment-by-using-the-enter-customer-payments-page"></a>دفعة جزئية باستخدام صفحة إدخال مدفوعات العميل
‏‫يُرسل العميل 4028 دفعة بمبلغ 500.00 في الأول من يوليو. ولإدخال هذا الدفعة، لا ينقر جمال فوق **بنود‬‏‫**. وبدلاً من ذلك، يقوم جمال بتسجيل الدفع بإنشاء دفتر يومية مدفوعات جديد، ثم فتح صفحة **إدخال مدفوعات العميل**. ويقوم جمال بإدخال المعلومات المتعلقة بالدفع ويميز الفاتورة التي قام بإدخالها. وعندما يقوم جمال بإدخال **500.00** كمبلغ، فإنه يقوم أيضًا بإدخال **500.00** في حقل **المبلغ المطلوب دفعه** في الشبكة. ولأن شركة الاتحاد للتصنيع تسمح بخصم نقدي على المدفوعات الجزئية، يشاهد جمال أنه سيتم الحصول على خصم نقدي جزئي بمبلغ 5.05 أيضًا. والعملية الحسابية لهذا الخصم هي 500.00 ÷ 0.99 × 0.01 = 5.05. (في هذه العملية الحسابية، تتم قسمة 500.00 على 0.99، لأن هناك خصم بنسبة 1 في المائة. ولذلك، يدفع العميل 99 في المائة من الفاتورة. ويتم فيما بعد ضرب النتيجة في النسبة المئوية للخصم، وهي 1 في المائة أو 0.01. إذا حصل العميل على الخصم الكامل بمبلغ 10.00، فسيساوي المبلغ الذي يجب تسويته 990.00.)‬ ‏‫تظهر معلومات الخصم في الشبكة أسفل صفحة **‬‏‫إدخال مدفوعات العميل**.

| مبلغ الخصم النقدي المطلوب استقطاعه | الخصم النقدي المستقطع | المبلغ المطلوب دفعه |
|------------------------------|---------------------|---------------|
| 5.05                         | 0.00                | 500.00        |

## <a name="partial-payment-by-using-the-journal-lines"></a>دفعة جزئية باستخدام بنود دفتر اليومية
بدلاً من فتح صفحة **إدخال مدفوعات العميل** في دفتر يومية المدفوعات، ينقر جمال فوق **بنود** لإدخال دفعة. ‏‫ويتم عرض دفتر يومية المدفوعات، حيث يستطيع جمال إدخال بند للعميل 4028. ويقوم جمال فيما بعد بفتح صفحة **تسوية الحركات** حتى يتمكن من تمييز الفاتورة للتسوية. ويضع جمال علامة على الفاتورة وتقوم بتغيير القيمة في حقل **المبلغ المُراد تسويته** إلى **-500.00**. ومرة أخرى، يرى جمال أن القيمة في حقل **مبلغ الخصم النقدي** هي **10.00** للفاتورة الكاملة، وأن القيمة في حقل **مبلغ الخصم النقدي المراد الحصول عليه** هو **5.05**. لذلك، يقوم جمال بتسوية مبلغ 505.05 من هذه الفاتورة.

| وضع علامة     | استخدام الخصم النقدي | الإيصال   | الحساب | التاريخ      | تاريخ الاستحقاق  | الفاتورة | المبلغ بعملة الحركة | عملة | المبلغ المراد تسويته |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| محدَد | عادي            | FTI-10010 | 4028    | 6/25/2015 | 7/25/2015 | 10010   | 1000.00                       | دولار أمريكي      | 500.00           |

تظهر معلومات الخصم أسفل صفحة **تسوية الحركات المفتوحة**.

|        &nbsp;                | &nbsp;    |
|------------------------------|-----------|
| تاريخ الخصم النقدي           | 7/09/2015 |
| مبلغ الخصم النقدي         | 10.00     |
| استخدام الخصم النقدي            | عادي    |
| الخصم النقدي المستقطع          | 0.00      |
| مبلغ الخصم النقدي المطلوب استقطاعه | 5.05      |

إذا كان العميل يريد تسوية نصف الفاتورة بالضبط، فإنه يُرسل دفعة بمبلغ 495.00. وفي هذه الحالة، يقوم جمال بإدخال **495.00** في حقل **المبلغ المُراد تسويته**. كما سيتم الحصول على الخصم النقدي بمبلغ 5.00، بحيث يساوي المبلغ الإجمالي الذي تمت تسويته 500.00.

| وضع علامة     | استخدام الخصم النقدي | الإيصال   | الحساب | التاريخ      | تاريخ الاستحقاق  | الفاتورة | المبلغ بعملة الحركة | عملة | المبلغ المراد تسويته |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| محدَد | عادي            | FTI-10010 | 4028    | 6/25/2015 | 7/25/2015 | 10010   | 1000.00                       | دولار أمريكي      | 495.00           |

تظهر معلومات الخصم أسفل صفحة **تسوية الحركات المفتوحة**.

|     &nbsp;                   | &nbsp;    |
|------------------------------|-----------|
| تاريخ الخصم النقدي           | 7/09/2015 |
| مبلغ الخصم النقدي         | 10.00     |
| استخدام الخصم النقدي            | عادي    |
| الخصم النقدي المستقطع          | 0.00      |
| مبلغ الخصم النقدي المطلوب استقطاعه | 5.00      |

يُغلق جمال صفحة **تسوية الحركات**. ويتم إنشاء بند دفعة بمبلغ 495.00 في دفتر اليومية، ثم يقوم جمال بترحيل دفتر اليومية. ويمكن لجمال مراجعة حركات العميل في صغحة **حركات العميل**. وفي هذه الصفحة، يرى جمال أن الفاتورة بها رصيد قدره 500.00. كما يشاهد جمال دفعة بمبلغ 495.00 وخصمًا بمبلغ 5.00.

| الإيصال    | نوع الحركة | التاريخ      | الفاتورة | المبلغ في خصم بعملة الحركة | المبلغ في الائتمان بعملة الحركة | الرصيد | عملة |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10010  | الفاتورة          | 6/25/2015 | 10010   | 1000.00                             |                                       | 500.00  | دولار أمريكي      |
| ARP-10010  |  الدفع         | 7/1/2015  |         |                                      | 495.00                                | 0.00    | دولار أمريكي      |
| DISC-10010 |  الخصم النقدي   | 7/1/2015  |         |                                      | 5.00                                  | 0.00    | دولار أمريكي      |

## <a name="payment-for-the-remaining-amount"></a>دفع المبلغ المتبقي
يدفع العميل 4028 المبلغ المتبقي من 495.00 يوم 8 يوليو، وهو ضمن في فترة الخصم النقدي. ويُنشئ جمال دفتر يومية المدفوعات يوم 8 يوليو ويقوم بتمييز الحركة للتسوية. ويرى جمال أن المبلغ الذي يجب تسويته قدره 495.00. القيمة الواردة في حقل **الخصم النقدي المقدر** هي **5.00**، لأنه تم خصم 5.00 مسبقاً.

|   &nbsp;                | &nbsp; |
|-------------------------|--------|
| تم وضع علامة على الإجمالي            | 495.00 |
| الخصم النقدي المقدر | 5.00   |

تظهر المعلومات المتعلقة بالحركة المميزة في الشبكة في صفحة **تسوية الحركات المفتوحة**.

| وضع علامة     | استخدام الخصم النقدي | الإيصال   | الحساب | التاريخ      | تاريخ الاستحقاق  | الفاتورة | المبلغ بعملة الحركة | عملة | المبلغ المراد تسويته |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| محدَد | عادي            | FTI-10010 | 4028    | 6/25/2015 | 7/25/2015 | 10010   | 1000.00                       | دولار أمريكي      | 495.00           |

تظهر معلومات الخصم أسفل صفحة **تسوية الحركات المفتوحة**.

|  &nbsp;                      |  &nbsp;   |
|------------------------------|-----------|
| تاريخ الخصم النقدي           | 7/09/2015 |
| مبلغ الخصم النقدي         | 10.00     |
| استخدام الخصم النقدي            | عادي    |
| الخصم النقدي المستقطع          | 5.00      |
| مبلغ الخصم النقدي المطلوب استقطاعه | 5.00      |

يقوم جمال بترحيل دفتر اليومية هذا ومراجعة حركات العميل في صفحة **حركات العميل**. ويبلغ رصيد الفاتورة الآن 0.00، ويشاهد جمال الدفعتين والخصمين النقديين.

| الإيصال    | نوع الحركة | التاريخ      | الفاتورة | المبلغ في خصم بعملة الحركة | المبلغ في الائتمان بعملة الحركة | الرصيد | عملة |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10010  | الفاتورة          | 6/25/2015 | 10010   | 1000.00                             |                                       | 0.00    | دولار أمريكي      |
| ARP-10010  | الدفع          | 7/1/2015  |         |                                      | 495.00                                | 0.00    | دولار أمريكي      |
| DISC-10010 | الخصم النقدي    | 7/1/2015  |         |                                      | 5.00                                  | 0.00    | دولار أمريكي      |
| ARP-10011  | الدفع          | 7/8/2015  |         |                                      | 495.00                                | 0.00    | دولار أمريكي      |
| DISC-10011 | الخصم النقدي    | 7/8/2015  |         |                                      | 5.00                                  | 0.00    | دولار أمريكي      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
