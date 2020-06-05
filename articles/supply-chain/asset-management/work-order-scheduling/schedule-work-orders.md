---
title: جدولة أوامر العمل
description: يوضح هذا الموضوع كيفية جدولة أوامر العمل في إدارة الأصول.
author: josaw1
manager: tfehr
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e98a30a03856f5532d420e516cb35d66acffb278
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383471"
---
# <a name="schedule-work-orders"></a>جدولة أوامر العمل

[!include [banner](../../includes/banner.md)]

 

يوضح هذا الموضوع كيفية جدولة أوامر العمل في إدارة الأصول. 

يتحدد عدد الساعات المطلوبة لأمر العمل بواسطة مجموع الساعات التي تم التنبؤ بها مطروحة من الساعات المرحلة. عند الحاجة إلى مزيد من الوقت، يجب تعديل التنبؤ وفقًا لذلك. في **إدارة الأصول** > **عام** > **أوامر العمل** > **جميع أوامر العمل** أو **أوامر العمل النشطة**، يمكنك عرض التنبؤات أو تحريرها في أمر عمل عن طريق تحديد أمر العمل والنقر فوق **التنبؤ** على علامة تبويب **أمر العمل**. عند إنشاء أوامر العمل وتقديرها، الخطوة التالية هي تخصيص عاملي الصيانة المطلوبين والأدوات المطلوبة.

يمكن جدولة فقط أوامر العمل التي لها حالة دورة حياه أمر عمل تسمح بالجدولة. يتم إعداد السماح بالجدولة في **إدارة الأصول** > **الإعداد** > **أوامر العمل** > **حالات دورة الحياة** > علامة التبويب **عام** زر التبديل > **السماح بالجدولة**.

1. انقر فوق **إدارة الأصول** > **عام** > **أوامر العمل** > **جميع أوامر العمل**.

2. حدد أوامر العمل التي تريد جدولتها في القائمة. على سبيل المثال، يمكنك فرز القائمة حسب **حالة دورة الحياة الحالية**.

3. في علامة التبويب **عام** انقر فوق **الجدول**.

4. في مربع الحوار **جدولة أوامر العمل**، يمكنك إضافة تحديدات فيما يتعلق بتاريخ البدء ومستوى الخدمة المتوقعين، إذا كان ذلك مطلوبًا. إذا كان من الضروري أن تأخذ عملية الجدولة في الاعتبار القيود على القدرة الإنتاجية فيما يتعلق بالموارد المجدولة لمهام أخرى، تأكد من تعيين أزرار التبديل **الأصل** و**الأداة** و**العامل** إلى "نعم".

    [!NOTE]
    إذا قمت بتعيين أزرار التبديل **الأصل** و**الأداة** و**العامل** إلى "لا"، فسيتم تجاهل الحجوزات الموجودة. في سجل المعلومات، سيتم عرض قائمة بجداول أوامر العمل المتداخلة، ويمكنك النقر فوق الرسائل لفتح أمر العمل وإعادة جدولته، إذا لزم الأمر.

5. للاطلاع على معلومات مفصلة حول عملية الجدولة، حدد "نعم" على زر التبديل **مطولّ‬**. وهذا يعني أن معلومات تفصيلية حول الدرجات المحسوبة على أوامر العمل وعاملي الصيانة سوف تظهر في سجل المعلومات.

6. انقر فوق **موافق** لبدء عملية الجدولة.

7. عند الانتهاء من الجدولة، يعرض سجل المعلومات عدد أوامر العمل المجدولة بالإضافة إلى معلومات أكثر تفصيلاً إذا تم تعيين زر التبديل **مطوّل** إلى "نعم".

>[!NOTE]
>تتم جدولة أوامر العمل في دورة واحدة لكل أمر عمل، وليس لكل وظيفة أمر عمل. يمكنك أيضًا فتح مربع الحوار **جدولة أوامر العمل** مباشرةً في **إدارة الأصول** > **دوري** > **أوامر العمل** > **جدولة أوامر العمل**. بعد إجراء التحديدات، انقر فوق **موافق** لبدء جدولة أمر العمل. من الممكن إعداد جدولة أمر العمل كوظيفة دفعية في مربع الحوار **جدولة أوامر العمل** > علامة التبويب السريعة **تشغيل في الخلفية**.

*مثال:* في الشكل الموجود أدناه، ستقوم المعادلة المدرجة في حقل **البدء المتوقع** بإنشاء جدولة أمر العمل لجميع أوامر العمل ذات تاريخ بدء متوقع اعتبارًا من أسبوع من الآن وما بعده. قد تكون هذه المعادلة مفيدة عند تشغيل جدولة أمر العمل على أساس مستمر، ولكنك تريد التأكد من عدم إعادة جدولة أوامر العمل المجلدة لفترة الأيام الخمسة إلى الستة التالية.

![الشكل 1](media/03-work-order-scheduling.png)

بإمكان نوع أمر العمل المرتبط بأوامر عمل إعداد الجدولة لعامل صيانة واحد (**إدارة الأصول** > **الإعداد** > **أوامر العمل** > **أنواع أوامر العمل** > زر التبديل **عامل صيانة واحد** معين إلى "نعم"). وهذا يعني انه إذا تم استخدام نوع أمر العمل على أمر عمل، يتم تعيين زر التبديل **عامل صيانة واحد** إلى "نعم" بشكل تلقائي في صفحة تفاصيل **جميع أوامر العمل** > طريقة عرض **الرأس** > علامة التبويب السريعة **الجدول**. أثناء جدولة أمر العمل، ستتم جدولة كافة وظائف أمر العمل التي تم إنشاؤها في أمر العمل فيما بعد إلى عامل الصيانة نفسه. إذا لزم الأمر، يمكنك تحرير التحديد على زر التبديل **عامل صيانة واحد** في **جميع أوامر العمل** للسماح بجدولة عدة عاملين أو عامل واحد على وظائف أمر العمل.

تتضمن عملية الجدولة في إدارة الأصول العديد من العوامل في حساب الجدولة:

- حساب الدرجات لكل من أوامر العمل وعاملي الصيانة. يتم إعداد الدرجات الخاصة بأوامر العمل وعاملي الصيانة في **محددات إدارة الأصول**. 
- البحث عن الاختصاصات المطابقة، التي تعني المهارات والشهادات، المطلوبة لأداء الوظيفة. يتم إعداد المهارات والشهادات على عاملي الصيانة في الوحدة النمطية **الموارد البشرية** (**الموارد البشرية** > **العاملون‏‎** > **العاملون** > حدد عاملاً في القائمة > علامة تبويب **العامل** > قسم **الاختصاصات‬** > أزرار **المهارات** و**الشهادات**). كما يمكن إضافة المهارات والشهادات إلى أنواع مهام الصيانة ومعاملات مهام الصيانة. اقرأ المزيد حول الاختصاصات وأنواع مهام الصيانة في [فئات أنواع مهام الصيانة وأنواع مهام الصيانة، ومتغيرات أنواع مهام الصيانة، ومعاملات مهام الصيانة، وقوائم فحص الصيانة](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).  

## <a name="scores-used-in-work-order-scheduling"></a>الدرجات المستخدمة في جدولة أمر العمل

يستند حساب الدرجات لوظيفة أمر عمل إلى تاريخ البدء المتوقع ومستوى الخدمة في أمر العمل.

حساب **تاريخ‏‎ البدء**: لكل تاريخ مستقبلي محسوب من تاريخ البدء المتوقع، يتم طرح درجات تاريخ البدء وضربها في الدرجات، وهي "10" في الأمثلة أدناه.

حساب **مستوى الأهمية**: درجة مستوى الأهمية مضروبة في مستوى الأهمية على أمر العمل.

حساب **مستوى الخدمة**: درجة مستوى الخدمة مقسومة على مستوى الخدمة في أمر العمل.

في الأمية الموجودة أدناه، درجة مستوى الأهمية هي "2"، ودرجات مستوى الخدمة هي "5" و"100".

**المثال 1:**

| معرّف أمر العمل | تاريخ البدء المتوقع | مستوى أهمية أمر العمل | مستوى خدمة أمر العمل | حساب               | النتيجة      |
|---------------|---------------------|------------------------|--------------------------|---------------------------|------------|
| WO-00010816   | غدًا            | 2                      | 20              | (-1 \* 10) + (2 \* 2) + 5 / 20     | \- 5.75    |
| WO-00010817   | يومان من الآن   | 2                      | 20              | (-2 \* 10) + (2 \* 2) + 5 / 20     | \- 15.75   |
| WO-00010818   | يومان من الآن   | 3                      | 5               | (-2 \* 10) + (2 \* 3) + 5 / 5      | \- 13      |

ستتم جدولة أوامر العمل بالترتيب التالي: WO-000108**16**،‏ WO-000108**18**،‏ WO-000108**17**.

**المثال 2:**

| معرّف أمر العمل | تاريخ البدء المتوقع | مستوى أهمية أمر العمل | مستوى خدمة أمر العمل | حساب                 | النتيجة    |
|---------------|---------------------|------------------------|---------------------|----------------------------------|----------|
| WO-00010816   | غدًا            | 2                      | 20                  | (-1 \* 10) + (2 \* 2) + 100 / 20 | \- 1     |
| WO-00010817   | يومان من الآن   | 2                      | 20                  | (-2 \* 10) + (2 \* 2) + 100 / 20 | \- 11    |
| WO-00010818   | يومان من الآن   | 3                      | 5                   | (-2 \* 10) + (2 \* 3) + 100 / 5  | 6        |

إذا تمت زيادة نقاط مستوى الخدمة إلى '100' بدلاً من'5'،سيكون ترتيب الجدولة كما يلي: WO-000108**18**‏، WO-000108**16**،‏ WO-000108**17**.

يتم إعداد درجات التقييم كلها المتعلقة بحساب عاملي الصيانة الذي يتعين عليهم العمل على أوامر العمل كأرقام، تُضاف إلى كل حساب عامل صيانة أثناء جدولة أمر العمل. يتم تحديد عامل الصيانة الذي يحصل على أعلى درجة على أمر العمل. فيما يلي وصف مختصر لدرجات عامل الصيانة:

| نقاط عامل الصيانة| الوصف |
|---|---|
| عامل مسؤول | إذا تم تحديد عامل الصيانة كعامل مسؤول في أمر العمل، تُضاف الدرجة. |
| مجموعة عامل الصيانة المسؤولة | إذا كان عامل الصيانة جزءًا من مجموعة عاملي صيانة مسؤولين على أمر العمل، تُضاف الدرجة. |
| عامل الصيانة المفضل         | إذا تم تحديد العامل كعامل صيانة مفضل على الأصل، تُضاف الدرجة. |
| مجموعة عامل الصيانة المفضل   | إذا كان العامل جزءًا من مجموعة عاملي صيانة مفضلين على الأصل، تُضاف الدرجة.  |
| الموقع  | إذا كانت شركتك تستخدم مواقع عمل، فسيحصل عاملو الصيانة على الدرجة الكاملة في حال وجودهم في موقع العمل نفسه المرتبط بالأصل. عند وجود موقع أساسي لموقع العمل الخاص بالأصل، سيحصل عاملو الصيانة في موقع العمل هذا على 1/2 درجة. وفي حال وجود أصل لهذا الموقع، سيحصل عاملو الصيانة في هذا الموقع على 1/3 درجة. وفي حال وجود أصل لهذا الموقع، سيحصل عاملو الصيانة في هذا الموقع على 1/4 درجة، وهكذا. إذا كانت شركتك تستخدم موقع الأصل، وهو أمر لا ننصح به، فسيتم استخدام الموقع والمنطقة لحساب درجات الموقع. يحصل العاملون على درجات كاملة في حال وجودهم في الموقع والمنطقة المرتبطة بالأصل. إذا تطابق موقع العامل مع الموقع والمنطقة فقط، فإن درجة تقييم عامل الصيانة هي 2/3 من الدرجة الكاملة. إذا تطابق موقع عامل الصيانة مع الموقع والمنطقة فقط، فإن درجة تقييم عامل الصيانة هي 1/3 من الدرجة الكاملة. |
| تاريخ البدء للعامل  | لكل تاريخ حيث تاريخ البدء المجدول يقع بعد تاريخ البدء المتوقع، يتم طرح الدرجات.  |

>[!NOTE]
>إذا تم تعيين الدرجة إلى "0"، لا يتم حساب هذه الدرجة. ويكون ذلك مفيدًا إذا كنت لا تريد تضمين عامل مسؤول في جدولك.

## <a name="competencies-used-in-work-order-scheduling"></a>الاختصاصات المستخدمة في جدولة أمر العمل

يمكن إعداد متطلبات المهارات والشهادات على أنواع مهام الصيانة (**إدارة الأصول** > **الإعداد** > **المهام** > **أنواع مهام الصيانة**) ومعاملات مهام الصيانة (**إدارة الأصول** > **الإعداد‏‎** > **المهام** > **معاملات مهام الصيانة**). 

يتم تحديد أنواع مهام الصيانة ومعاملات مهام الصيانة على أوامر العمل. إذا تم تحديد المهارات أو الشهادات على نوع مهمة صيانة أو معاملات مهمة صيانة، وتم استخدام نوع مهمة الصيانة هذا أو معاملات مهمة الصيانة هذه على وظيفة أمر عمل، فلن يتم اختيار سوى عاملي الصيانة الذين لديهم مهارات وشهادات متطابقة للعمل على أمر العمل.

<a name="gantt"></a>

## <a name="work-with-scheduled-work-orders-using-a-gantt-chart"></a>العمل مع أوامر العمل المجدولة باستخدام مخطط gantt

يوفر **مخطط gantt لأوامر العمل المخططة** واجهة رسومية حيث يمكنك عرض أوامر العمل وإعادة جدولتها.

لعرض مخطط gantt والتعامل معه:

1. انتقل إلى **إدارة الأصول > أوامر العمل > مخطط gantt لأوامر العمل المخططة**.

1. استخدم القوائم المنسدلة والحقول الموجودة في القسم **إعدادات** لإعداد الموقع الوظيفي والنطاق الزمني والمقياس الزمني الذي سيتم إظهاره في مخطط gantt.

1. حدد **تطبيق**.

    - يتم تحديث مخطط gantt لعرض أوامر العمل المجدولة التي تتوافق مع الإعدادات الخاصة بك. ويجري تمثيل كل أمر عمل بواسطة مستطيل أزرق.
    - لإعادة جدولة أمر عمل معروض، حدده ثم اسحبه إلى الوقت والتاريخ الجديدين المناسبين.

1. إذا قمت بإجراء أية تغييرات، فحدد **حفظ** في جزء الإجراءات لحفظها.