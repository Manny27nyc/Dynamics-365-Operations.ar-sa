---
title: التخطيط الرئيسي مع تنبؤات الطلب
description: يوضح هذا الموضوع كيفيه تضمين تنبؤات الطلب اثناء التخطيط الرئيسي مع تحسين التخطيط.
author: ChristianRytt
manager: tfehr
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 8b47aee41494394a32ffc0ea0c42a512e5051532
ms.sourcegitcommit: b86576e1114e4125eba8c144d40c068025f670fc
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 12/03/2020
ms.locfileid: "4666712"
---
# <a name="master-planning-with-demand-forecasts"></a>التخطيط الرئيسي مع تنبؤات الطلب

[!include [banner](../../includes/banner.md)]

يمكنك استخدام التنبؤ بالطلب مع تحسين التخطيط بالنسبة لحساب الطلب المتوقع في التخطيط الرئيسي الخاص بك. يمكنك إنشاء تنبؤ طلب يدويا أو استيراده أو إنشاؤه باستخدام وظيفة التنبؤ بالطلب في Microsoft Dynamics 365 Supply Chain Management. لمزيد من المعلومات حول التنبؤ بالطلب ، راجع [نظره عامه حول التنبؤ بالطلب](../introduction-demand-forecasting.md).

> [!NOTE]
> تخطيط التنبؤ المنفصل غير مدعوم مع تحسين التخطيط. لذلك، لا يكون لاعداد **خطه التنبؤ الحالي** في الصفحة **معلمات التخطيط الرئيسية** اي تاثير عند استخدام تحسين أداء التخطيط.

## <a name="set-up-a-master-plan-to-include-a-demand-forecast"></a>اعداد خطه رئيسيه لتضمين التنبؤ بالطلب

لتكوين خطه رئيسيه بحيث تتضمن التنبؤ بطلب ، اتبع الخطوات التالية.

1. انتقل إلى **التخطيط الرئيسي \> الإعداد \> الخطط \> الخطط الرئيسية**.
1. حدد خطه موجودة أو قم بإنشاء خطه جديده.
1. في علامة التبويب السريعة **عام**، اضبط الحقول التالية:

    - **نموذج التنبؤ** - تحديد نموذج التنبؤ المطلوب تطبيقه. سيتم اعتبار هذا النموذج عند إنشاء اقتراح توريد للخطة الرئيسية الحالية.
    - **تضمين التنبؤ بالطلب**- يتم تعيين هذا الخيار على *نعم* لتضمين التنبؤ بالطلب في الخطة الرئيسية الحالية. إذا قمت بتعيينه إلى *لا*، لن يتم تضمين حركات التنبؤ بالطلب في الخطة الرئيسية.
    - **الطريقة المستخدمة لتقليل متطلبات التنبؤ** – تحديد الأسلوب الذي ينبغي استخدامه لتقليل متطلبات التنبؤ. لمزيد من المعلومات، راجع قسم [مفاتيح تقليل التنبؤ](#reduction-keys)، لاحقًا في هذا الموضوع.

1. في علامة التبويب السريعة **الحد الزمني بالأيام**، يمكنك تعيين الحقول التالية لتحديد الفترة التي يتم تضمين التنبؤ بالطلب خلالها:

    - **خطه التنبؤ** - قم بتعيين هذا الخيار علي *نعم* لتجاوز الحد الزمني الخاص بخطه التنبؤ التي تنشا من مجموعات التغطية الفردية. ويتم تعيينها إلى *لا* لاستخدام القيم الموجودة في مجموعات التغطية الفردية الخاصة بالخطة الرئيسية الحالية.
    - **الفترة الزمنيه للتنبؤ** – إذا قمت بتعيين خيار **خطه التنبؤ** إلى *نعم*، حدد عدد الأيام (بدءا من تاريخ اليوم) التي يجب تطبيق التنبؤ بالطلب عليها.

    > [!IMPORTANT]
    > إعداد **تخطيط التنبؤ** غير مدعوم مع تحسين التخطيط.

## <a name="set-up-a-coverage-group-to-include-a-demand-forecast"></a>اعداد مجموعة تغطية لتضمين التنبؤ بالطلب

لتكوين مجموعة تغطية بحيث تتضمن التنبؤ بطلب، اتبع الخطوات التالية.

1. انتقل إلى **التخطيط الرئيسي \> الإعداد \> الخطط \> مجموعات التغطية**.
1. حدد مجموعه تغطيه موجودة ، أو قم بإنشاء مجموعه جديده.
1. في علامة التبويب السريعة **أخرى**، اضبط الحقول التالية:

    - **الحد الزمني لخطه التنبؤ** -ادخل عدد الأيام (بدءا من تاريخ اليوم) التي يجب تطبيق التنبؤ بالطلب عليها. يمكن تجاوز هذه القيمة باستخدام خيار **خطه التنبؤ** في الخطة الرئيسية، كما هو موضح في القسم السابق.
    - **مفتاح الخفض** - حدد مفتاح الخفض الذي سيتم تطبيقه. لمزيد من المعلومات ، راجع قسمي [إنشاء مفتاح خفض التنبؤ واعداده](#create-reduction-key)[ واستخدام مفتاح الخفض](#use-reduction-key) لاحقا في هذا الموضوع.
    - **تقليل التنبؤ حسب** – بالنسبة للخطط الرئيسية حيث يتم تعيين الحقل **الطريقة المستخدمة في خفض متطلبات التنبؤ** إلى *الحركات - مفتاح الخفض* أو *الحركات - الفترة الديناميكية*، حدد الحركات التي يجب ان تقلل من التنبؤ. حدد إحدى القيم التالية:

        - **كافة الحركات** - يجب ان تقلل كافة الحركات من التنبؤ.
        - **الأوامر** – يجب علي أوامر التوريد فقط تقليل التنبؤ.

        > [!NOTE]
        > إذا قمت بتحديد *كافة الحركات*، يتم اعتبار الحركات التي لها طلب وتوريد في نفس ابعاد المخزون محايده ويتم تجاهلها اثناء تقليل التنبؤ. علي سبيل المثال ، إذا تم تعيين بعد التخطيط علي موقع فقط ، وليس المستودع ، ويتم تجاهل أمر التحويل بين الموقع 1 والمستودع 11 والموقع 1 ولن يقوم المستودع 13 بتخفيض التنبؤ بالطلبات المتبقية.

    - **تضمين أوامر بين الشركات الشقيقة** - يتم تعيين هذا الخيار إلى *نعم* في حاله ضرورة تضمين الأوامر بين الشركات الشقيقة عند تقليل التنبؤ. والا، قم بتعيينه إلى *لا*.
    - **تضمين التنبؤ بالعميل في التنبؤ بالطلب** – حدد ما إذا كان يجب تضمين التنبؤ بالعميل في التنبؤ الإجمالي ام لا. يحدد هذا الخيار كيفيه تصغير الطلب الفعلي للطلب المتوقع. يمكنك استخدامه للتاكد من ان التخطيط الرئيسي يغطي توريد الأصناف التي تم شراؤها بواسطة عملاء محددين.

        - يتم تعيين هذا الخيار علي *نعم* لتضمين التنبؤ بالعميل في التنبؤ الإجمالي. في هذه الحالة، يقوم طلب العميل الفعلي بتقليل التنبؤ بالعميل والتنبؤ الإجمالي. يقوم التخطيط الرئيسي بإنشاء أوامر مخططه لتغطيه كميه التنبؤ الاجماليه فقط.
        - يتم تعيين هذا الخيار علي *لا* لتضمين التنبؤ بالعميل في التنبؤ الإجمالي. في هذه الحالة ، يقوم طلب العميل الفعلي بتقليل تنبؤ العميل فقط. يقوم التخطيط الرئيسي بإنشاء أوامر مخططه لتغطيه كل من كميه التنبؤ الاجماليه والتنبؤ لكل كميه من العملاء.

## <a name="forecast-reduction-keys"></a><a name="reduction-keys"></a>طرق خفض التنبؤ

يوفر هذا القسم معلومات حول مختلف الطرق المستخدمة لتقليل متطلبات التنبؤ. وهو يتضمن أمثلة عن نتائج كل أسلوب. ويشرح أيضًا كيفية إنشاء طريقة خفض التنبؤ وإعدادها واستخدامها. تستخدم بعض الأساليب طريقة خفض التنبؤ لتقليل متطلبات التنبؤ.

### <a name="methods-that-are-used-to-reduce-forecast-requirements"></a>الطرق المستخدمة لتقليل متطلبات التنبؤ

عندما تقوم بتضمين تنبؤ في خطة رئيسية، يمكنك تحديد كيف يتم تقليل متطلبات التنبؤ عند تضمين الطلب الفعلي. لاحظ أن التخطيط الرئيسي يستبعد متطلبات التنبؤ من الماضي، مما يعني أن كافة متطلبات التنبؤ هي قبل تاريخ اليوم.

لتضمين تنبؤ في خطة رئيسية وتحديد الأسلوب المستخدم لتقليل متطلبات التنبؤ، انتقل إلى **التخطيط الرئيسي \> الإعداد \> خطط \> الخطط الرئيسية**. حدد نموذج التنبؤ في الحقل **نموذج التنبؤ**. في **الطريقة المستخدمة لتقليل متطلبات التنبؤ‬**، حدد طريقة. وتتوفر الخيارات التالية:

- لا شيء
- النسبة – طريقة الخفض
- الحركات – مفتاح الخفض (غير معتمد بعد مع تحسين التخطيط)
- الحركات – الفترة الديناميكية

توفر الأقسام التالية معلومات إضافية حول كل خيار.

#### <a name="none"></a>بلا

إذا حددت **بلا**، لا يتم تقليل متطلبات التنبؤ أثناء الجدولة الرئيسية. وفي هذه الحالة، ينشئ التخطيط الرئيسي أوامر مخططة لتوريد الطلب المتوقع (متطلبات التنبؤ). تحافظ هذه الأوامر المخططة على الكمية المقترحة، بصرف النظر عن أنواع الطلبات الأخرى. على سبيل المثال، إذا تم وضع أوامر مبيعات، فسينشئ التخطيط الرئيسي أوامر مخططة إضافية لتوريد أوامر المبيعات. ولا يتم تقليل عدد متطلبات التنبؤ.

#### <a name="percent--reduction-key"></a>النسبة – طريقة الخفض

إذا حددت **النسبة - طريقة الخفض‬**، يتم تقليل متطلبات التنبؤ وفقًا للنسب المئوية والفترات الزمنية التي تم تحديدها باستخدام طريقة الخفض. وفي هذه الحالة، ينشئ التخطيط الرئيسي أوامر مخططة حيث تُحتسب الكمية ككمية متوقعة × طريقة الخفض في كل فترة. في حال وجود أنواع طلبات أخرى، ينشئ التخطيط الرئيسي أيضًا أوامر مخططة لتوريد هذا الطلب.

##### <a name="example-percent--reduction-key"></a>مثال: النسبة – طريقة الخفض

يوضح هذا المثال إلى أي مدى تقلل طريقة خفض من متطلبات التنبؤ بالطلب وفقًا للنسب المئوية والفترات الزمنية التي تم تحديدها باستخدام طريقة الخفض.

بالنسبة إلى هذا المثال، ستقوم بتضمين التنبؤ بالطلب التالي التنبؤ في خطة رئيسية.

| الشهر    | التنبؤ بالطلب |
|----------|-----------------|
| يناير  | 1,000           |
| فبراير | 1,000           |
| مارس    | 1,000           |
| أبريل    | 1,000           |

في صفحة **طرق الخفض**، يمكنك إعداد البنود التالية.

| التغيير | الوحدة  | النسبة المئوية |
|--------|-------|---------|
| 1      | الشهر | 100     |
| 2      | الشهر | 75      |
| 3      | الشهر | 50      |
| 4      | الشهر | 25      |

إنك تعيّن طريقة الخفض إلى مجموعة تغطية العناصر. بعد ذلك، في صفحة **الخطط الرئيسية**، في الحقل **الطريقة المستخدمة لتقليل متطلبات التنبؤ‬**، حدد **النسبة - طريقة الخفض**.

في هذه الحالة، إذا قمت بتشغيل جدولة التنبؤ في 1 يناير، يتم استهلاك متطلبات التنبؤ بالطلب وفقًا للنسب المئوية التي أعددتها في صفحة **طرق الخفض**. يتم تحويل كميات المتطلبات التالية إلى الخطة الرئيسية.

| الشهر                | كمية الأمر المخطط | حساب    |
|----------------------|------------------------|----------------|
| يناير              | 0                      | = 0% × 1,000   |
| فبراير             | 250                    | = 25% × 1,000  |
| مارس                | 500                    | = 50% × 1,000  |
| أبريل                | 750                    | = 75% × 1,000  |
| من مايو حتى ديسمبر | 1,000                  | = 100% × 1,000 |

#### <a name="transactions--reduction-key"></a>الحركات – طريقة الخفض

إذا حددت **الحركات - طريقة الخفض**، يتم تقليل متطلبات التنبؤ وفقًا للحركات التي تحدث خلال الفترات الزمنية التي تم تحديدها باستخدام طريقة الخفض.

##### <a name="example-transactions--reduction-key"></a>مثال: الحركات – طريقة الخفض

يوضح هذا المثال إلى أي مدى تقلل الأوامر الفعلية التي تحدث أثناء الفترات المحددة بواسطة طريقة الخفض من متطلبات التنبؤ بالطللب.

بالنسبة إلى هذا المثال، في صفحة **الحركات - طريقة الخفض‬**، في الحقل **الطريقة المستخدمة لتقليل متطلبات التنبؤ‬**، حدد **الخطط الرئيسية**.

توجد أوامر المبيعات التالية في 1 يناير.

| الشهر    | عدد القطع المطلوبة |
|----------|--------------------------|
| يناير  | 956                      |
| فبراير | 1,176                    |
| مارس    | 451                      |
| أبريل    | 119                      |

إذا استخدمت التنبؤ بالطلب نفسه لعدد 1,000 قطعة لكل شهر الذي تم استخدامه في المثال السابق، سيتم تحويل كميات المتطلبات التالية إلى الخطة الرئيسية.

| شهر                | عدد القطع المطلوبة |
|----------------------|---------------------------|
| يناير              | 44                        |
| فبراير             | 0                         |
| مارس                | 549                       |
| أبريل                | 881                       |
| من مايو حتى ديسمبر | 1,000                     |

#### <a name="transactions--dynamic-period"></a>الحركات – الفترة الديناميكية

إذا حددت **الحركات - الفترة الديناميكية**، يتم تقليل متطلبات التنبؤ بواسطة حركات الأوامر الفعلية التي تحدث أثناء الفترة الديناميكية. تغطي الفترة الديناميكية تواريخ التنبؤ الحالية وتنتهي عند بداية التنبؤ التالي. وفي هذه الحالة، ينشئ التخطيط الرئيسي أوامر مخططة لتوريد الطلب المتوقع (متطلبات التنبؤ). ومع ذلك، عندما يتم وضع حركات الأوامر الفعلية، تنخفض متطلبات التنبؤ. تستهلك الحركات الفعلية جزءًا من متطلبات التنبؤ.

عند استخدام هذا الخيار، يحدث السلوك التالي:

- لا يتم طلب طرق الخفض أو استخدامها. 
- إذا قل التنبؤ تمامًا، تصبح متطلبات التنبؤ للتنبؤ الحالي 0 (صفر).
- إذا لم يكن هناك أي تنبؤ مستقبلي، يتم تخفيض طلبات التنبؤ من التنبؤ الأخيرة الذي تم إدخاله.
- يتم تضمين الحدود الزمنية في عملية حساب خفض التنبؤ.
- يتم تضمين الأيام الموجبة في عملية حساب خفض التنبؤ.
- إذا تجاوزت حركات الأوامر الفعلية المتطلبات التي تم التنبؤ بها، لا يتم توجيه الحركات المتبقية إلى فترة التنبؤ التالية.

##### <a name="example-1-transactions--dynamic-period"></a>مثال 1: الحركات – الفترة الديناميكية

فيما يلي مثال بسيط يوضح كيفية عمل طريقة **الحركات - الفترة الديناميكية**.

بالنسبة إلى هذا المثال، ستقوم بتضمين التنبؤ بالطلب التالي التنبؤ في خطة رئيسية.

| التاريخ       | التنبؤ بالطلب |
|------------|-----------------|
| 1 يناير  | 1,000           |
| 1 فبراير | 1,000             |

يمكنك أيضًا إنشاء أوامر المبيعات التالية.

| التاريخ        | كمية أمر المبيعات |
|-------------|----------------------|
| 15 يناير  | 200                  |
| 15 فبراير | 400                  |

في هذه الحالة، يتم إنشاء الأوامر المخططة التالية.

| تاريخ التنبؤ بالطلب | الكمية | الشرح                           |
|--------------------- |----------|---------------------------------------|
| 1 يناير            | 800      | متطلبات التنبؤ (= 1,000 – 200) |
| 15 يناير           | 200      | متطلبات أوامر المبيعات             |
| 1 فبراير           | 600      | متطلبات التنبؤ (= 1,000 – 400) |
| 15 فبراير          | 400      | متطلبات أوامر المبيعات             |

##### <a name="example-2-transactions--dynamic-period"></a>مثال 2: الحركات – الفترة الديناميكية

في معظم الحالات، يتم إعداد الأنظمة بحيث تقلل الحركات من التنبؤ بالطلب في فترات تنبؤ محددة: الأسابيع، والشهور، وهكذا. ويتم تحديد هذه الفترات في طريقة الخفض. ومع ذلك، قد *يعني* الوقت بين بندي التنؤ بالطلب فترة كذلك.

بالنسبة إلى هذا المثال، تنشئ طلب تنبؤ للتواريخ والكميات التالية.

| التاريخ       | التنبؤ بالطلب |
|------------|-----------------|
| 1 يناير  | 1,000           |
| 5 يناير  | 500             |
| 12 يناير | 1,000           |

لاحظ عدم وجود فترة واضحة بين تواريخ التنبؤ، في هذا التنبؤ. بين التاريخين الأول والثاني يوجد نطاق زمني من أربعة أيام، وبين التاريخين الثاني والثالث يوجد نطاق زمني من سبعة أيام. هذه النطاقات الزمنية هي الفترات الحيوية.

يمكنك أيضًا إنشاء بنود أوامر المبيعات التالية.

| التاريخ                             | كمية أمر المبيعات |
|----------------------------------|----------------------|
| 15 كانون الأول/ديسمبر في السنة السابقة | 500                  |
| 3 يناير                        | 100                  |
| 10 يناير                       | 200                  |

في هذه الحالة، يتم خفض التنبؤ بالطريقة التالية:

- نظرًا لعدم وجود أمر المبيعات الأول خلال أي فترة، فهو لا يخفض أي تنبؤ.
- نظرًا لوجود أمر المبيعات الثاني في الفترة بين 1 كانون الثاني/يناير و5 كانون الثاني/يناير، فهو سيخفض التنبؤ بتاريخ 1 كانون الثاني/يناير بـ 100.
- نظرًا لوجود أمر المبيعات الثالث في الفترة بين 5 كانون الثاني/يناير و12 كانون الثاني/يناير، فهو سيخفض التنبؤ بتاريخ 5 كانون الثاني/يناير بـ 200.

وبالتالي، يتم إنشاء الأوامر المخططة التالية.

| تاريخ التنبؤ بالطلب             | الكمية | الشرح                                                         |
|----------------------------------|----------|---------------------------------------------------------------------|
| 15 كانون الأول/ديسمبر في السنة السابقة | 500      | متطلبات أوامر المبيعات                                            |
| 1 يناير                        | 900      | متطلبات التنبؤ للفترة من 1 يناير حتى 5 يناير (= 1,000 – 100) |
| 3 يناير                        | 100      | متطلبات أوامر المبيعات                                            |
| 5 يناير                        | 300      | متطلبات التنبؤ للفترة من 5 يناير حتى 10 يناير (= 500 – 200)  |
| 12 يناير                       | 1,000    | متطلبات التنبؤ للفترة من 12 يناير حتى آخر يناير                      |

### <a name="create-and-set-up-a-forecast-reduction-key"></a><a name="create-reduction-key"></a>إنشاء وإعداد طريقة خفض التنبؤ

يتم استخدام طريقة خفض التنبؤ في الأسلوبين **الحركات - طريقة الخفض‬** و **النسبة - طريقة الخفض‬** لتقليل متطلبات التنبؤ. اتبع هذه الخطوات لإنشاء وإعداد طريقة خفض.

1. انتقل إلى **التخطيط الرئيسي \> الإعداد \> تغطية \> طرق الخفض**.
2. حدد **جديد** أو اضغط على **على Ctrl + N** لإنشاء طريقة خفض.
3. في حقل **طريقة الخفض**، أدخل معرّفًا فريدًا لطريقة خفض التنبؤ. ثم في حقل **الاسم**، أدخل اسمًا. 
4. حدد الفترات الزمنية ونسبة طريقة الخفض في كل فترة:

    - يشير حقل **تاريخ السريان** إلى تاريخ بدء إنشاء الفترات الزمنية. عند تعيين الخيار **استخدام تاريخ السريان‬** إلى **نعم**، تبدأ الفترات في تاريخ السريان. وعند تعيينه إلى **لا**، تبدا الفترات في التاريخ الذي يتم فيه تشغيل التخطيط الرئيسي.
    - حدد الفترات التي يجب أن يحدث فيها خفض التنبؤ.
    - بالنسبة إلى معينة، حدد النسب المئوية التي يجب أن يتم بها خفض متطلبات التنبؤ. ويمكنك إدخال قيم موجبة لتقليل المتطلبات أو قيم سالبة لزيادة المتطلبات.

### <a name="use-a-reduction-key"></a><a name="use-reduction-key"></a>استخدام طريقة خفض

يجب تعيين مفتاح خفض التنبؤ إلى مجموعة التغطية للصنف. اتبع هذه الخطوات لتعيين طريقة خفض إلى بمجموعة تغطية الصنف.

1. انتقل إلى **التخطيط الرئيسي \> الإعداد \> تغطية \> مجموعات التغطية**.
2. على علامة التبويب السريعة **غير ذلك**، في الحقل **طريقة الخفض**، حدد طريقة الخفض لتعيينها إلى مجموعة التغطية. عندئذٍ، يتم تطبيق طريقة الخفض على جميع العناصر التي تنتمي إلى مجموعة التغطية.
3. لاستخدام طريقة لحساب خفض التنبؤ أثناء الجدولة الرئيسية، يجب تحديد هذا الإعداد في إعداد خطة التنبؤ أو الخطة الرئيسية. انتقل إلى أحد المواقع التالية:

    - التخطيط الرئيسي \> الإعداد \> الخطط \> خطط التنبؤ
    - التخطيط الرئيسي \> الإعداد \> الخطط \> الخطط الرئيسية

4. في صفحة **خطط التنبؤ** أو **الخطط الرئيسية**، على علامة التبويب السريعة **عام**، في الحقل **الطريقة المستخدمة لتقليل متطلبات التنبؤ‬**، حدد **النسبة - طريقة الخفض** أو **الحركات - طريقة الخفض‏‎**.

### <a name="reduce-a-forecast-by-transactions"></a>خفض تنبؤ بواسطة الحركات

عندما تحدد **الحركات - طريقة الخفض** أو **الحركات - الفترة الديناميكية** كطريقة لتقليل متطلبات التنبؤ، يمكنك تحديد الحركات التي تقلل التنبؤ. في صفحة **مجموعات التغطية**، في علامة التبويب السريعة **غير ذلك**، في حقل **تقليل التنبؤ حسب‬**، حدد **كافة الحركات** إذا كان يجب على كافة الحركات تقليل التنبؤ أو **الأوامر** إذا كان يجب على أوامر المبيعات فقط تقليل التنبؤ.