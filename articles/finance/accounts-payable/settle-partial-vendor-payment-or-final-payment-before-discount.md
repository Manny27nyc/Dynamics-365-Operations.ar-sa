---
title: تسوية دفعة جزئية لمورد وتسوية الدفعة النهائية بالكامل قبل تاريخ الخصم
description: ترشدك هذه المقالة عبر سيناريو حيث يتم تسديد دفعات جزئية لفاتورة مورّد ويتم أخذ خصم نقدي.
author: abruer
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14431
ms.assetid: 6b8e3420-b4c9-4e02-9588-598fe6d3df0d
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 90aeff9872e72950f42b6227300933d562c0a3d0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/03/2022
ms.locfileid: "8889979"
---
# <a name="settle-a-partial-vendor-payment-and-the-final-payment-in-full-before-the-discount-date"></a>تسوية دفعة جزئية لمورد وتسوية الدفعة النهائية بالكامل قبل تاريخ الخصم

[!include [banner](../includes/banner.md)]

ترشدك هذه المقالة عبر سيناريو حيث يتم تسديد دفعات جزئية لفاتورة مورّد ويتم أخذ خصم نقدي.

‏‫تشتري شركة الاتحاد للتصنيع السلع من المورد 3064. ويمنح المورد هذه الشركة خصمًا نقديًا بنسبة 1 في المائة، إذا تم دفع الفاتورة في غضون 14 يومًا.‬ ويجب دفع الفواتير في غضون 30 يومًا. كما يتيح المورد لشركة الاتحاد للتصنيع الحصول على الخصومات النقدية على دفعات جزئية. وتوجد معلمات التسوية في صفحة **معلمات الحسابات الدائنة**. في 25 حزيران/يونيو، تقوم فوزية بإدخال فاتورة بمبلغ 1000.00 للمورد 3064.

## <a name="vendor-invoice-on-june-25"></a>فاتورة المورد في 25 يونيو
‏‫وفي 25 حزيران/يونيو، تقوم فوزية بإدخال وترحيل فاتورة بمبلغ 1000.00 للمورد 3064. وتستطيع فوزية عرض هذه الحركة في صغحة **حركات المورد**.

| الإيصال   | التاريخ      | الفاتورة | المبلغ في خصم بعملة الحركة | المبلغ في الائتمان بعملة الحركة | الرصيد   | عملة |
|-----------|-----------|---------|--------------------------------------|---------------------------------------|-----------|----------|
| Inv-10010 | 6/25/2015 | 10010   |                                      | 1000.00                              | -1000.00 | دولار أمريكي      |

ومن صفحة **الموردين**، تفتح فوزية صفحة **تسوية الحركات**. يمكنها استخدام صفحة **تسوية الحركات** لعرض التواريخ ومبالغ الخصومات النقدية. وتاريخ الاستحقاق هو تاريخ 25 تموز/يوليو، ويتوفر خصم نقدي بمبلغ -10.00، إذا تم دفع الفاتورة بحلول تاريخ 9 تموز/يوليو.

| وضع علامة | استخدام الخصم النقدي | الإيصال   | الحساب | التاريخ      | تاريخ الاستحقاق  | الفاتورة | المبلغ بعملة الحركة | عملة | المبلغ المراد تسويته |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | عادي            | Inv-10010 | 3064    | 6/25/2015 | 7/25/2015 | 10010   | 1000.00                       | دولار أمريكي      | 990.00           |

تظهر معلومات الخصم أسفل صفحة **تسوية الحركات المفتوحة**.

|       &nbsp;                 | &nbsp;    |
|------------------------------|-----------|
| تاريخ الخصم النقدي           | 7/09/2015 |
| مبلغ الخصم النقدي         | -10.00    |
| استخدام الخصم النقدي            | عادي    |
| الخصم النقدي المستقطع          | 0.00      |
| مبلغ الخصم النقدي المطلوب استقطاعه | -10.00    |

تنقر فوزية فوق علامة التبويب **الخصم النقدي** لعرض مبلغ الخصم.

| تاريخ الخصم النقدي | مبلغ الخصم النقدي | المبلغ بعملة الحركة |
|--------------------|----------------------|--------------------------------|
| 7/9/2015           | 10.00                | 990.00                         |
| 7/25/2015          | 0.00                 | 1000.00                       |

## <a name="partial-payment-on-july-1-by-using-the-settle-transactions-page"></a>الدفعة الجزئية في الأول من يوليو باستخدام صفحة تسوية الحركات
تستطيع فوزية إنشاء دفتر يومية مدفوعات لهذه الدفعة عن طريق فتح صفحة **دفتر يومية المدفوعات** في الحسابات الدائنة. ‏‫وتقوم بإنشاء دفتر يومية جديدة وتقوم بإدخال بند للمورد 3064. وتقوم فيما بعد بفتح صفحة **تسوية الحركات** حتى يمكنها تمييز الفاتورة للتسوية.‬ وتضع فوزية علامة على الفاتورة وتقوم بتغيير القيمة في حقل **المبلغ المُراد تسويته** إلى **-500.00**. وتشاهد أن القيمة في حقل **مبلغ الخصم النقدي** هي **-10.00** للفاتورة الكاملة، وأن القيمة في حقل **مبلغ الخصم النقدي المراد الحصول عليه** هو **-5.05**. لذلك، تقوم فوزية بتسوية مبلغ -505.05 من هذه الفاتورة.

| وضع علامة     | استخدام الخصم النقدي | الإيصال   | الحساب | التاريخ      | تاريخ الاستحقاق  | الفاتورة | المبلغ بعملة الحركة | عملة | المبلغ المراد تسويته |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| محدَد | عادي            | FTI-10010 | 4028    | 6/25/2015 | 7/25/2015 | 10010   | 1000.00                       | دولار أمريكي      | -500.00          |

تظهر معلومات الخصم أسفل صفحة **تسوية الحركات المفتوحة**.

|  &nbsp;                      |  &nbsp;   |
|------------------------------|-----------|
| تاريخ الخصم النقدي           | 7/09/2015 |
| مبلغ الخصم النقدي         | -10.00    |
| استخدام الخصم النقدي            | عادي    |
| الخصم النقدي المستقطع          | 0.00      |
| مبلغ الخصم النقدي المطلوب استقطاعه | -5.05     |

تريد فوزية تسوية نصف الفاتورة بالضبط. ولذلك، تقوم بتغيير القيمة في حقل **المبلغ المُراد تسويته** إلى **-495.00**. المبلغ الإجمالي الذي تمت تسويته الآن هو 500.00. ويتضمن هذا المبلغ خصمًا نقديًا بمبلغ -5.00.

| وضع علامة     | استخدام الخصم النقدي | الإيصال   | الحساب | التاريخ      | تاريخ الاستحقاق  | الفاتورة | المبلغ بعملة الحركة | عملة | المبلغ المراد تسويته |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| محدَد | عادي            | FTI-10010 | 4028    | 6/25/2015 | 7/25/2015 | 10010   | 1000.00                       | دولار أمريكي      | -495.00          |

تظهر معلومات الخصم أسفل صفحة **تسوية الحركات المفتوحة**.

|  &nbsp;                      |  &nbsp;   |
|------------------------------|-----------|
| تاريخ الخصم النقدي           | 7/09/2015 |
| مبلغ الخصم النقدي         | -10.00    |
| استخدام الخصم النقدي            | عادي    |
| الخصم النقدي المستقطع          | 0.00      |
| مبلغ الخصم النقدي المطلوب استقطاعه | -5.00     |

تُغلق فوزية صفحة **تسوية الحركات**. ويتم إنشاء بند دفعة بمبلغ 495.00 في دفتر اليومية، ثم تقوم فوزية بترحيل دفتر اليومية. ‏‫وتستطيع فوزية مراجعة حركات المورد في صفحة **حركات المورد**. وترى أن الفاتورة تشتمل على رصيد بمبلغ -500.00.‬ كما تشاهد دفعة بمبلغ 495.00 وخصمًا نقديًا بمبلغ 5.00.

| الإيصال    | نوع الحركة | التاريخ      | الفاتورة | المبلغ في خصم بعملة الحركة | المبلغ في الائتمان بعملة الحركة | الرصيد | عملة |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10010  | الفاتورة          | 6/25/2015 | 10010   |                                      | 1000.00                              | -500.00 | دولار أمريكي      |
| APP-10010  | الدفع          | 7/1/2015  |         | 495.00                               |                                       | 0.00    | دولار أمريكي      |
| DISC-10010 | الخصم النقدي    | 7/1/2015  |         | 5.00                                 |                                       | 0.00    | دولار أمريكي      |

## <a name="remaining-amount-paid-on-july-8"></a>باقي المبلغ المدفوع في 8 تموز/يوليو
تدفع فوزية ما تبقى من الفاتورة للمورد 3064 في يوم 8 يوليو، وهو ما يوجد في فترة الخصم النقدي. وتُنشئ فوزية دفتر يومية المدفوعات يوم 8 يوليو وتقوم بتمييز الحركة للتسوية. وترى أن المبلغ الذي يجب تسويته قدره 495.00. القيمة الواردة في حقل **الخصم النقدي المقدر** هي **-5.00**، لأنه تم خصم 5.00 مسبقاً.

|  &nbsp;                 |  &nbsp; |
|-------------------------|--------|
| تم وضع علامة على الإجمالي            | 495.00 |
| الخصم النقدي المقدر | -5.00  |

تظهر المعلومات المتعلقة بالحركة المميزة في الشبكة في صفحة **تسوية الحركات المفتوحة**.

| وضع علامة     | استخدام الخصم النقدي | الإيصال   | الحساب | التاريخ      | تاريخ الاستحقاق  | الفاتورة | المبلغ بعملة الحركة | عملة | المبلغ المراد تسويته |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| محدَد | عادي            | FTI-10010 | 4028    | 6/25/2015 | 7/25/2015 | 10010   | 1000.00                       | دولار أمريكي      | 495.00           |

تظهر معلومات الخصم أسفل صفحة **تسوية الحركات المفتوحة**.

|  &nbsp;                      | &nbsp;    |
|------------------------------|-----------|
| تاريخ الخصم النقدي           | 7/09/2015 |
| مبلغ الخصم النقدي         | 10.00     |
| استخدام الخصم النقدي            | عادي    |
| الخصم النقدي المستقطع          | 5.00      |
| مبلغ الخصم النقدي المطلوب استقطاعه | 5.00      |

تقوم فوزية بترحيل دفتر يومية المدفوعات ومراجعة حركات المورد في صفحة **حركات المورد**. ويبلغ رصيد الفاتورة الآن 0.00، وتشاهد فوزية الدفعتين والخصمين النقديين.

| الإيصال    | نوع الحركة | التاريخ      | الفاتورة | المبلغ في خصم بعملة الحركة | المبلغ في الائتمان بعملة الحركة | الرصيد | عملة |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10010  | الفاتورة          | 6/25/2015 | 10010   |                                      | 1000.00                              | 0.00    | دولار أمريكي      |
| APP-10010  |  الدفع         | 7/1/2015  |         | 495.00                               |                                       | 0.00    | دولار أمريكي      |
| DISC-10010 | الخصم النقدي    | 7/1/2015  |         | 5.00                                 |                                       | 0.00    | دولار أمريكي      |
| APP-10011  | الدفع          | 7/8/2015  |         | 495.00                               |                                       | 0.00    | دولار أمريكي      |
| DISC-10011 | الخصم النقدي    | 7/8/2015  |         | 5.00                                 |                                       | 0.00    | دولار أمريكي      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
