---
title: طرق خفض التنبؤ
description: توفر هذه المقالة أمثلة تعرض كيفية إعداد طريقة الخفض. وهي تتضمن معلومات حول مختلف إعدادات طريقة الخفض ونتائج كل إعداد. يمكنك استخدام طريقة الخفض لتعريف كيفية خفض متطلبات التنبؤ.
author: t-benebo
ms.date: 04/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqPlanSched, ReqReduceKeyDefaultDataWizard, ReqReduceKey
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19251
ms.assetid: aa9e0dfb-6052-4a2e-9378-89507c02fdf2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b7eaf57e0f02c0b9dd6454a58184db7bb3f58c04
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/23/2022
ms.locfileid: "9337119"
---
# <a name="forecast-reduction-keys"></a>طرق خفض التنبؤ

[!include [banner](../includes/banner.md)]

يوفر هذا المقال معلومات حول مختلف الطرق المستخدمة لتقليل متطلبات التنبؤ. وهو يتضمن أمثلة عن نتائج كل أسلوب. ويشرح أيضًا كيفية إنشاء طريقة خفض التنبؤ وإعدادها واستخدامها. تستخدم بعض الأساليب طريقة خفض التنبؤ لتقليل متطلبات التنبؤ.

## <a name="methods-that-are-used-to-reduce-forecast-requirements"></a>الطرق المستخدمة لتقليل متطلبات التنبؤ

عندما تقوم بتضمين تنبؤ في خطة رئيسية، يمكنك تحديد كيف يتم تقليل متطلبات التنبؤ عند تضمين الطلب الفعلي. لاحظ أن التخطيط الرئيسي يستبعد متطلبات التنبؤ من الماضي، مما يعني أن كافة متطلبات التنبؤ هي قبل تاريخ اليوم.

لتضمين تنبؤ في خطة رئيسية وتحديد الأسلوب المستخدم لتقليل متطلبات التنبؤ، انتقل إلى **التخطيط الرئيسي \> الإعداد \> خطط \> الخطط الرئيسية**. حدد نموذج التنبؤ في الحقل **نموذج التنبؤ**. في **الطريقة المستخدمة لتقليل متطلبات التنبؤ‬**، حدد طريقة. وتتوفر الخيارات التالية:

- بلا
- النسبة – طريقة الخفض
- الحركات – طريقة الخفض
- الحركات – الفترة الديناميكية

توفر الأقسام التالية معلومات إضافية حول كل خيار.

### <a name="none"></a>بلا

إذا حددت **بلا**، لا يتم تقليل متطلبات التنبؤ أثناء الجدولة الرئيسية. وفي هذه الحالة، ينشئ التخطيط الرئيسي أوامر مخططة لتوريد الطلب المتوقع (متطلبات التنبؤ). تحافظ هذه الأوامر المخططة على الكمية المقترحة، بصرف النظر عن أنواع الطلبات الأخرى. على سبيل المثال، إذا تم وضع أوامر مبيعات، فسينشئ التخطيط الرئيسي أوامر مخططة إضافية لتوريد أوامر المبيعات. ولا يتم تقليل عدد متطلبات التنبؤ.

### <a name="percent--reduction-key"></a>النسبة – طريقة الخفض

إذا حددت **النسبة - طريقة الخفض‬**، يتم تقليل متطلبات التنبؤ وفقًا للنسب المئوية والفترات الزمنية التي تم تحديدها باستخدام طريقة الخفض. وفي هذه الحالة، ينشئ التخطيط الرئيسي أوامر مخططة حيث تُحتسب الكمية ككمية متوقعة × طريقة الخفض في كل فترة. في حال وجود أنواع طلبات أخرى، ينشئ التخطيط الرئيسي أيضًا أوامر مخططة لتوريد هذا الطلب.

#### <a name="example-percent--reduction-key"></a>مثال: النسبة – طريقة الخفض

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

### <a name="transactions--reduction-key"></a>الحركات – طريقة الخفض

إذا قمت بتعيين حقل **الطريقة المستخدمة لتقليل متطلبات التنبؤ** إلى *الحركات - طريقة الخفض*، فسيتم تخفيض متطلبات التنبؤ حسب حركات الطلب المؤهلة التي تقع خلال الفترات المحددة بواسطة طريقة الخفض.

يتم تحديد الطلب المؤهل من خلال حقل **تخفيض التنبؤ حسب** في صفحة **مجموعات التغطية**. إذا قمت بتعيين حقل **تقليل التنبؤ حسب** إلى *الأوامر*، سيتم اعتبار حركات أوامر المبيعات فقط هي الطلب المؤهل. إذا قمت بتعيينه على *كافة الحركات*، فسيتم اعتبار أي حركات مخزون صادرة لغير الشركات الشقيقة طلباً مؤهلاً. إذا كان يجب أيضًا اعتبار المبيعات بين الشركات الشقيقة طلبًا مؤهلاً، فقم يتعيين خيار **تضمين الأوامر بين الشركات الشقيقة** إلى *نعم*.

يبدأ خفض التنبؤ بسجل تنبؤ الطلب الأول (المبكر) في فترة طريقة الخفض. إذا كانت كمية حركات المخزون المؤهلة أكبر من كمية بنود التنبؤ بالطلب في نفس فترة طريقة الخفض، فسيتم استخدام رصيد كمية حركات المخزون لتقليل كمية التنبؤ بالطلب في الفترة السابقة (إذا كان هناك تنبؤ غير مستهلك).

في حالة عدم وجود أي تنبؤ غير مستهلك في فترة طريقة الخفض السابقة، فسيتم استخدام رصيد كمية حركات المخزون لتقليل كمية التنبؤ في الشهر التالي (في حالة وجود تنبؤ غير مستهلك).

لا يتم استخدام قيمة حقل **النسبة المئوية** في بنود مفتاح الخفض عند تعيين حقل **الطريقة المستخدمة لتقليل متطلبات التنبؤ** إلى *الحركات - طريقة الخفض*. يتم استخدام التواريخ فقط لتحديد فترة طريقة الخفض.

> [!NOTE]
> سيتم تجاهل أي تنبؤ تم ترحيله في تاريخ اليوم أو قبله، ولن يتم استخدامه لإنشاء أوامر مخططه. على سبيل المثال، إذا تم إنشاء التنبؤ بالطلب للشهر في 1 يناير، وقمت بتشغيل التخطيط الرئيسي الذي يتضمن التنبؤ بالطلب في 2 يناير، فسيتجاهل الحساب بند التنبؤ بالطلب بتاريخ 1 يناير.

#### <a name="example-transactions--reduction-key"></a>مثال: الحركات – طريقة الخفض

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

### <a name="transactions--dynamic-period"></a>الحركات – الفترة الديناميكية

إذا حددت **الحركات - الفترة الديناميكية**، يتم تقليل متطلبات التنبؤ بواسطة حركات الأوامر الفعلية التي تحدث أثناء الفترة الديناميكية. تغطي الفترة الديناميكية تواريخ التنبؤ الحالية وتنتهي عند بداية التنبؤ التالي. وفي هذه الحالة، ينشئ التخطيط الرئيسي أوامر مخططة لتوريد الطلب المتوقع (متطلبات التنبؤ). ومع ذلك، عندما يتم وضع حركات الأوامر الفعلية، تنخفض متطلبات التنبؤ. تستهلك الحركات الفعلية جزءًا من متطلبات التنبؤ.

عند استخدام هذا الخيار، يحدث السلوك التالي:

- لا يتم طلب طرق الخفض أو استخدامها. 
- إذا قل التنبؤ تمامًا، تصبح متطلبات التنبؤ للتنبؤ الحالي 0 (صفر).
- إذا لم يكن هناك أي تنبؤ مستقبلي، يتم تخفيض طلبات التنبؤ من التنبؤ الأخيرة الذي تم إدخاله.
- لا يتم تضمين الحد الزمني لتقليل التنبؤ بالطلب في حساب تقليل التنبؤ. بدلا من ذلك ، يتم استخدام الحد الزمني لمجموعه التغطية لتقليل التنبؤ.
- يتم تضمين الأيام الموجبة في عملية حساب خفض التنبؤ.
- إذا تجاوزت حركات الأوامر الفعلية المتطلبات التي تم التنبؤ بها، لا يتم توجيه الحركات المتبقية إلى فترة التنبؤ التالية.

#### <a name="example-1-transactions--dynamic-period"></a>مثال 1: الحركات – الفترة الديناميكية

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

#### <a name="example-2-transactions--dynamic-period"></a>مثال 2: الحركات – الفترة الديناميكية

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

## <a name="create-and-set-up-a-forecast-reduction-key"></a>إنشاء وإعداد طريقة خفض التنبؤ

يتم استخدام طريقة خفض التنبؤ في الأسلوبين **الحركات - طريقة الخفض‬** و **النسبة - طريقة الخفض‬** لتقليل متطلبات التنبؤ. اتبع هذه الخطوات لإنشاء وإعداد طريقة خفض.

1. انتقل إلى **التخطيط الرئيسي \> الإعداد \> تغطية \> طرق الخفض**.
2. حدد **جديد** لإنشاء طريقة الخفض‬.
3. في حقل **طريقة الخفض**، أدخل معرّفًا فريدًا لطريقة خفض التنبؤ. ثم في حقل **الاسم**، أدخل اسمًا. 
4. حدد الفترات الزمنية ونسبة طريقة الخفض في كل فترة:

    - يشير حقل **تاريخ السريان** إلى تاريخ بدء إنشاء الفترات الزمنية. عند تعيين الخيار **استخدام تاريخ السريان‬** إلى **نعم**، تبدأ الفترات في تاريخ السريان. وعند تعيينه إلى **لا**، تبدا الفترات في التاريخ الذي يتم فيه تشغيل التخطيط الرئيسي.
    - حدد الفترات التي يجب أن يحدث فيها خفض التنبؤ.
    - بالنسبة إلى معينة، حدد النسب المئوية التي يجب أن يتم بها خفض متطلبات التنبؤ. ويمكنك إدخال قيم موجبة لتقليل المتطلبات أو قيم سالبة لزيادة المتطلبات.

## <a name="use-a-reduction-key"></a>استخدام طريقة خفض

يجب تعيين مفتاح خفض التنبؤ إلى مجموعة التغطية للصنف. اتبع هذه الخطوات لتعيين طريقة خفض إلى بمجموعة تغطية الصنف.

1. انتقل إلى **التخطيط الرئيسي \> الإعداد \> تغطية \> مجموعات التغطية**.
2. على علامة التبويب السريعة **غير ذلك**، في الحقل **طريقة الخفض**، حدد طريقة الخفض لتعيينها إلى مجموعة التغطية. عندئذٍ، يتم تطبيق طريقة الخفض على جميع العناصر التي تنتمي إلى مجموعة التغطية.
3. لاستخدام طريقة لحساب خفض التنبؤ أثناء الجدولة الرئيسية، يجب تحديد هذا الإعداد في إعداد خطة التنبؤ أو الخطة الرئيسية. انتقل إلى أحد المواقع التالية:

    - التخطيط الرئيسي \> الإعداد \> الخطط \> خطط التنبؤ
    - التخطيط الرئيسي \> الإعداد \> الخطط \> الخطط الرئيسية

4. في صفحة **خطط التنبؤ** أو **الخطط الرئيسية**، على علامة التبويب السريعة **عام**، في الحقل **الطريقة المستخدمة لتقليل متطلبات التنبؤ‬**، حدد **النسبة - طريقة الخفض** أو **الحركات - طريقة الخفض‏‎**.

## <a name="reduce-a-forecast-by-transactions"></a>خفض تنبؤ بواسطة الحركات

عندما تحدد **الحركات - طريقة الخفض** أو **الحركات - الفترة الديناميكية** كطريقة لتقليل متطلبات التنبؤ، يمكنك تحديد الحركات التي تقلل التنبؤ. في صفحة **مجموعات التغطية**، في علامة التبويب السريعة **غير ذلك**، في حقل **تقليل التنبؤ حسب‬**، حدد **كافة الحركات** إذا كان يجب على كافة الحركات تقليل التنبؤ أو **الأوامر** إذا كان يجب على أوامر المبيعات فقط تقليل التنبؤ.

## <a name="additional-resources"></a>الموارد الإضافية

[نظرة عامة على الخطط الرئيسية](master-plans.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
