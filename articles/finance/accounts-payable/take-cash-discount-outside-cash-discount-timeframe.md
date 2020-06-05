---
title: الحصول على خصم نقدي خارج فترة الخصم النقدي
description: توفر هذه المقالة سيناريوهين يظهران كيف يمكن أخذ خصم نقدي حتى لو تم إجراء الدفع خارج فترة الخصم النقدي.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14301
ms.assetid: bad10b7f-e550-4742-9261-8a094c9c624d
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e4a166e9a0d43da80986dd63d6739b104745b115
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189466"
---
# <a name="take-a-cash-discount-outside-the-cash-discount-period"></a>الحصول على خصم نقدي خارج فترة الخصم النقدي

[!include [banner](../includes/banner.md)]

توفر هذه المقالة سيناريوهين يظهران كيف يمكن أخذ خصم نقدي حتى لو تم إجراء الدفع خارج فترة الخصم النقدي.

في 28 حزيران/يونيو، تقوم فوزية بإنشاء فاتورة بمبلغ 2,000.00 للمورد 3052. وتشمل الفاتورة خصمًا نقديًا قدره 1 في المائة، إذا تم دفع الفاتورة في غضون 14 يومًا.‬

## <a name="use-cash-discount-option--always"></a>استخدم خيار الخصم النقدي = دوماً
تقوم فوزية بإنشاء دفعة في الأول من يوليو، بعد تاريخ الخصم. وتقوم فوزية بفتح صفحة **تسوية الحركات** لعرض الحركات التي يمكن تسويتها. 

وتقوم فوزية بتمييز فاتورة الدفع. لم يتم الحصول على أي خصم نقدي، لأن الدفع بعد تاريخ الخصم. ‏‫ومع ذلك، أعطى المورد فوزية موافقة لإدخال الخصم النقدي على أية حال. ولذلك، تقوم فوزية بتغيير القيمة في حقل **استخدام الخصم النقدي** إلى **دوماً**.

| وضع علامة     | استخدام الخصم النقدي | الإيصال   | الحساب | تاريخ الخصم النقدي | تاريخ الاستحقاق  | الفاتورة | المبلغ بعملة الحركة | عملة | المبلغ المراد تسويته |
|----------|-------------------|-----------|---------|--------------------|-----------|---------|--------------------------------|----------|------------------|
| محدَد | دائمًا            | Inv-10030 | 3052    | 6/28/2015          | 7/12/2015 | 10030   | -2,000.00                      | دولار أمريكي      | -1,980.00        |

تظهر معلومات الخصم أسفل صفحة **تسوية الحركات**.

|                              |           |
|------------------------------|-----------|
| تاريخ الخصم النقدي           | 7/12/2015 |
| مبلغ الخصم النقدي         | -20.00    |
| استخدام الخصم النقدي            | دائمًا    |
| الخصم النقدي المستقطع          | 0.00      |
| مبلغ الخصم النقدي المطلوب استقطاعه | -20.00    |

## <a name="date-to-use-for-calculating-discounts--selected-date"></a>التاريخ المستخدم لحساب الخصومات = التاريخ المحدد
إذا تم ترحيل الفاتورة والدفع على حد سواء، فإنه لا يزال يمكن الحصول على الخصم النقدي عند تسوية الحركات في صفحة **تسوية الحركات**. وتقوم فوزية بتغيير القيمة في حقل **التاريخ المطلوب استخدامه لحساب الخصومات** إلى **التاريخ المحدد**. وتقوم فيما بعد بإدخال تاريخ 28 يونيو، في فترة الخصم النقدي للفاتورة. ويتم استخدام هذا التاريخ لحساب خصم نقدي للحركة. وفي صفحة **تسوية الحركات المفتوحة** تشاهد فوزية الخصم الكامل بمبلغ 20.00  يظهر بشكل افتراضي، يعرض بند الفاتورة المبلغ المراد تسويته بمبلغ 1,980.00.

| وضع علامة                     | استخدام الخصم النقدي | الإيصال   | الحساب | تاريخ الخصم النقدي | تاريخ الاستحقاق  | الفاتورة | المبلغ بعملة الحركة | عملة | المبلغ المراد تسويته |
|--------------------------|-------------------|-----------|---------|--------------------|-----------|---------|--------------------------------|----------|------------------|
| المحددة والمميزة | عادي            | Inv-10030 | 3052    | 6/28/2015          | 7/12/2015 | 10030   | -2,000.00                      | دولار أمريكي      | -1,980.00        |
| محدَد                 | عادي            | APP-10030 | 3052    | 7/15/2015          | 7/15/2015 |         | 500.00                         | دولار أمريكي      | 500.00           |

تظهر معلومات الخصم أسفل صفحة **تسوية الحركات المفتوحة**. مبلغ الخصم الذي يتم الحصول عليه هو 20.00، لأن مبلغ المراد تسويته للفاتورة هو المبلغ الافتراضي 1,980.00.

|                              |           |
|------------------------------|-----------|
| تاريخ الخصم النقدي           | 7/12/2015 |
| مبلغ الخصم النقدي         | -20.00    |
| استخدام الخصم النقدي            | عادي    |
| الخصم النقدي المستقطع          | 0.00      |
| مبلغ الخصم النقدي المطلوب استقطاعه | -20.00    |

تقوم فوزية بتحديث القيمة في حقل **المبلغ المُراد تسويته** إلى **500.00**. ويتم حساب القيمة في حقل **مبلغ الخصم النقدي المراد الحصول عليه** بمبلغ **5.05**.

| وضع علامة                     | استخدام الخصم النقدي | الإيصال   | الحساب | التاريخ      | تاريخ الاستحقاق  | الفاتورة | المبلغ بعملة الحركة | عملة | المبلغ المراد تسويته |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| المحددة والمميزة | عادي            | Inv-10030 | 3052    | 6/28/2015 | 7/12/2015 | 10030   | 2,000.00                       | دولار أمريكي      | -500.00          |
| محدَد                 | عادي            | APP-10030 | 3052    | 7/15/2015 | 7/15/2015 |         | 500.00                         | دولار أمريكي      | 500.00           |

تظهر معلومات الخصم أسفل صفحة **تسوية الحركات المفتوحة**. والقيمة في حقل **مبلغ الخصم النقدي المراد الحصول عليه** هو **5.05**، لأن المبلغ المراد تسويته للفاتورة تم تغييره إلى مبلغ الدفع 500.00.

|                              |           |
|------------------------------|-----------|
| تاريخ الخصم النقدي           | 7/12/2015 |
| مبلغ الخصم النقدي         | -20.00    |
| استخدام الخصم النقدي            | عادي    |
| الخصم النقدي المستقطع          | 0.00      |
| مبلغ الخصم النقدي المطلوب استقطاعه | -5.05     |




