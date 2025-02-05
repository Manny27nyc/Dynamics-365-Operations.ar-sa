---
title: المبلغ بالكامل وخيارات حساب الفترات لأكواد ضريبة المبيعات
description: تشرح هذه المقالة خيارات حقل أسلوب حساب على أكواد ضريبة المبيعات وكيفية حساب ضريبة المبيعات للفترات والمبالغ كاملة.
author: kailiang
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxData, TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom: 5624
ms.assetid: 96166db4-b7ca-470b-aeb7-0a66fe0554c4
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5b02a0ced8b556cfc5a984d24ceaf982629fd69c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874450"
---
# <a name="whole-amount-and-interval-calculation-options-for-sales-tax-codes"></a>المبلغ بالكامل وخيارات حساب الفترات لأكواد ضريبة المبيعات

[!include [banner](../includes/banner.md)]

توضح هذه المقالة الخيار لحقل **أسلوب الحساب** على أكواد ضريبة المبيعات وكيفية حساب ضريبة المبيعات للفترات والمبالغ كاملة.

يمكنك إعداد كود ضريبة مبيعات ليتم حسابه على أساس مبلغ كامل أو مبلغ فترة. في صفحة **أكواد ضريبة المبيعات**، استخدام حقل **طريقة الحساب** في علامة التبويب السريع **الحساب** لتحديد كيفية حساب كود ضريبة المبيعات.
- المبلغ الكامل – يتم تطبيق معدل الضريبة على المبلغ الخاضع للضريبة بالكامل.
- الفترة – يتم تقسيم المبلغ الخاضع للضريبة إلى أجزاء، يقع كل جزء منها في نطاق يحتوي على معدل ضريبة محدد. ويتم احتساب الضريبة على جزء المبلغ الذي يقع في فترة محددة وذلك وفقًا لمعدل الضريبة لهذه الفترة. ومعدل الضريبة هو مجموع مبالغ الضريبة التي يتم حسابها لكل فترة مبلغ.
  > [!NOTE]                                                                                                                              
  > يتوفر خيار الفترة فقط عند تحديد بند في حقل طريقة الحساب في منطقة ضريبة المبيعات في صفحة معلمات دفتر الأستاذ العام. 

يتم إعداد الفواصل الزمنية في صفحة قيم أكواد ضريبة المبيعات عن طريق إدخال الحد الأدنى والحد الأقصى للمبالغ لكل معدل الضريبة. بالنسبة للضرائب التي ينبغي حسابها على كافة المبالغ الخاضعة للضريبة، بغض النظر عن الطريقة التي يتم تحديدها، فيجب أن تتوافق الفترات مع القواعد التالية:
-   يجب أن تشتمل الفترة الأولى حد أدنى قيمته صفر.
-   يجب أن تشتمل الفترة الأخيرة على حد أقصى قيمته صفر يشير إلى اللانهاية.
-   يجب أن يساوي الحد الأقصى للفترة الحد الأدنى للفترة التالية.

إذا كان المبلغ هو الحد الأقصى للفترة السابقة والحد الأدنى للفترة التالية، فسيتم تطبيق معدل ضريبة المبيعات الفترة الأولى على المبلغ. إذا وقع المبلغ خارج الفترات المحددة وفقًا للحدين الأدنى والأعلى، فسيتم تطبيق معدل ضريبة مبيعات بمبلغ صفر.

## <a name="example-whole-amount-method-of-calculation"></a>مثال: طريقة حساب إجمالي المبلغ
في صفحة قيم أكواد ضريبة المبيعات، يتم إعداد معدلات ضريبة المبيعات في الفترات التالية:

| حد الحد الأدنى     | الحد الأقصى     | معدل الضريبة     |
|-------------------|-------------------|--------------|
| 0.00              | 50.00             | 30%          |
| 50.00             | 100.00            | 20%          |
| 100.00            | 0.00              | 10%          |

يتم حساب ضريبة المبيعات على إجمالي المبلغ الخاضع للضريبة.

| مبلغ خاضع للضريبة (السعر) | حساب    | ضريبة المبيعات |
|------------------------|----------------|-----------|
| 35.00                  | 35.00 \* 0.30  | 1050     |
| 50.00                  | 50.00 \* 0.30  | 15.00     |
| 85.00                  | 85.00 \* 0.20  | 17.00     |
| 305.00                 | 305.00 \* 0.10 | 30.50     |

## <a name="example-interval-method-of-calculation"></a>مثال: طريقة حساب الفترة
في صفحة القيم، يتم إعداد معدلات ضرائب المبيعات في الفترات التالية:

| حد الحد الأدنى     | الحد الأقصى     | معدل الضريبة     |
|-------------------|-------------------|--------------|
| 0.00              | 50.00             | 30%          |
| 50.00             | 100.00            | 20%          |
| 100.00            | 0.00              | 10%          |

ومعدل الضريبة هو مجموع مبالغ الضريبة التي يتم حسابها لكل فترة مبلغ.

| مبلغ خاضع للضريبة (السعر) | حساب                                                               | ضريبة المبيعات |
|------------------------|---------------------------------------------------------------------------|-----------|
| 35.00                  | 35.00 \* 0.30                                                             | 1050     |
| 50.00                  | 50.00 \* 0.30                                                             | 15.00     |
| 85.00                  | (50.00 \* 0.30 =‏ 15.00) + (35.00 \* ‏0.20 =‏ 7.00)                          | 22.00     |
| 305.00                 | (50.00 \* ‏0.30 =‏ 15.00) + (50.00 \* ‏0.20 =‏ 10.00) + (205 \* ‏0.10 =‏ 20.50) | 45.50     |



لمزيد من المعلومات، راجع [تحديد معدلات ضريبة المبيعات استنادًا إلى حقلي "القاعدة الهامشية" وأساليب الحساب](marginal-base-field.md).







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
