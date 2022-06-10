---
title: المهام الدورية في فواتير العقود المتكررة
description: يصف هذا الموضوع المهام الدورية المتوفرة في فوترة العقد المتكررة.
author: JodiChristiansen
ms.date: 04/29/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 80f65d82881bb000f626c4225b3eac7dd1a2a44a
ms.sourcegitcommit: 1877696fa05d66b6f51996412cf19e3a6b2e18c6
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/20/2022
ms.locfileid: "8786960"
---
# <a name="periodic-tasks-in-recurring-contract-billing"></a>المهام الدورية في فواتير العقود المتكررة

يصف هذا الموضوع المهام الدورية المتوفرة في فوترة العقد المتكررة.

## <a name="generate-invoice"></a>إنشاء فاتورة

استخدم صفحة **إنشاء الفاتورة** لإنشاء فواتير متكررة شهرية جماعية من المعلومات التي أعددتها في صفحتي **جميع جداول الفواتير** و **عرض تفاصيل الفواتير**. عند إنشاء فاتورة، يتم تحديث وصف البند لبند معالجة أمر المبيعات مع وصف الصنف وتواريخ بدء الفواتير وانتهائها لبند الجدول الذي تم تحرير فاتورة به.

## <a name="generate-invoice-batch-processing"></a>إنشاء معالجة دفعة الفاتورة

استخدم صفحة **إنشاء معالجة دُفعة الفواتير** لإنشاء فواتير متكررة من خلال عملية دُفعات متكررة. المعلمات المتوفرة هي نفس المعلمات الموجودة في صفحة **إنشاء الفاتورة**، ولكن يمكن حفظها في عملية دفعية يمكن تشغيلها عدة مرات.

## <a name="price-update"></a>تحديث السعر

استخدم الأداة المساعدة لتحديث الأسعار لتحديث أسعار العديد من العناصر في جداول فوترة متعددة في إجراء واحد. يمكن تحديث الأسعار بناءً على نسبة مئوية محددة أو مبلغ محدد. تعرض قائمة السطور أسعار الوحدات الحالية فقط للعناصر. لا تظهر الأسعار بعد تحديث الأسعار.

لاحظ النقاط التالية حول الأداة المساعدة لتحديث الأسعار:

- إذا تم بالفعل إنشاء أمر المبيعات لسنة معينة (أي تمت فوترة الأصناف)، فلن يتأثر سعر البنود.
- يمكن استخدام أداة تحديث الأسعار للبنود التي لها حالة **نشطة** أو **قيد الانتظار**. بالنسبة للعناصر المعلقة، يجب تعيين خيار **تعديل الجدول** إلى **لا** عند التعليق.
- لا يمكن استخدام الأداة المساعدة لتحديث الأسعار للعناصر التي هي عناصر استخدام أو تستخدم التصعيد أو فوترة الأحداث الهامة أو تقسيم الإيرادات.

### <a name="price-update-example"></a>مثال على تحديث الأسعار

يتم إنشاء جدول الفواتير وإضافة بند التجديد. سعر الوحدة 750 دولار. يتم دفع السنة الأولى للعنصر في 15 ديسمبر 2021. يتم إنشاء جدول الفواتير للفترة من 1 يناير حتى 31 ديسمبر 2022.

في وقت التجديد، تنشئ عملية **إنشاء الفاتورة** أمر المبيعات لعام 2022. بعد تشغيل الأداة المساعدة لتحديث الأسعار، يتم تحديث السعر من 750 دولارًا إلى 800 دولار.

لا يتأثر أمر المبيعات وجدول الفوترة لعام 2022، ويظل سعر الوحدة 750 دولارًا، لأن جدول الفواتير لعام 2022 قد تم تحرير فاتورة به بالفعل. تم تحديث بند جدول الفواتير وتفاصيل السطر لعام 2023 إلى 800 دولار أمريكي، لأن جدول الفواتير لعام 2023 لم يتم تحرير فاتورة به بعد.

### <a name="update-prices--flat-pricing-method"></a>تحديث الأسعار - طريقة تسعير ثابتة

عندما تقوم بتحديث أسعار الأصناف التي تستخدم طريقة التسعير الثابت، يمكنك تحديد نسبة أو مبلغ لزيادة السعر.

لتشغيل الأداة المساعدة لتحديث الأسعار للعناصر التي تستخدم طريقة التسعير الثابت، اتبع هذه الخطوات.

1. في صفحة الأداة المساعدة **تحديث الأسعار**، حدد طريقة الأسعار **الثابتة**.
2. في الحقل **طريقة الزيادة**، حدد طريقة الزيادة المستخدمة لتحديث سعر العناصر.
3. بناءً على طريقة الزيادة التي حددتها، حدد النسبة المئوية في حقل **بالمائة** أو المبلغ في حقل **المبلغ**.
4. في علامة التبويب السريعة **السجلات المراد تضمينها**، استخدم الزر **تصفية** لإضافة عوامل تصفية البيانات.
5. حدد **عرض الإصدار الأولي** لعرض مجموعة السجلات.
6. إذا كنت لا تريد معالجة بعض الخطوط، فضع علامة عليها، ثم حدد **إزالة**.
7. حدد **موافق**.

### <a name="update-prices--standard-pricing-method"></a>تحديث الأسعار - طريقة تسعير قياسية

إذا تم تغيير سعر عنصر ما في سجل الصنف، فيمكن تحديثه لجميع بنود جدول الفواتير إذا كان الصنف يستخدم طريقة التسعير القياسية.

1. في صفحة الأداة المساعدة **تحديث الأسعار**، حدد طريقة الأسعار **القياسية**.
2. في علامة التبويب السريعة **السجلات المراد تضمينها**، استخدم الزر **تصفية** لإضافة عوامل تصفية البيانات.
3. حدد **عرض الإصدار الأولي** لعرض مجموعة السجلات.
4. إذا كنت لا تريد معالجة بعض الخطوط، فضع علامة عليها، ثم حدد **إزالة**.
5. حدد **موافق**.

## <a name="mass-hold-processing"></a>معالجة التعليق الجماعي

استخدم صفحة **التعليق الجماعي** لتطبيق خيارات الحجز على العديد من جداول الفواتير في نفس الوقت.

لوضع جدول فوترة واحد فقط أو سطر واحد في جدول الفوترة قيد الانتظار، افتح صفحة **جميع جداول الفوترة**، وحدد **وضع قيد التعليق**. لإزالة تعليق، استخدم صفحة **إزالة تعليق**.

### <a name="put-billing-schedules-on-hold"></a>وضع جداول الفواتير قيد التعليق

لتعليق العديد من جداول الفواتير، اتبع هذه الخطوات.

1. في صفحة **التعليق الجماعي**، قم بتعيين حقل **خيار العملية** إلى **تطبيق تعليق**.
2. في حقل **كود السبب**، حدد كود السبب.
3. حدد خيار **تعديل الجدول**:

    - **نعم** – إذا قمت بتعيين الخيار إلى **نعم**، حدد تاريخ تعليق في حقل **تاريخ التعليق**. تتم إزالة أي بنود في جدول الفواتير بعد تاريخ التعليق.
    - **لا** – لم يتم تغيير بنود جدول الفوترة. فقط الحالة هي التي تغيرت. تم تحديثها إلى **التعليق**.

4. في علامة التبويب السريعة **السجلات المراد تضمينها**، استخدم الزر **تصفية** لإضافة عوامل تصفية البيانات.
5. حدد **عرض الإصدار الأولي** لعرض مجموعة السجلات.
6. إذا كنت لا تريد معالجة بعض الخطوط، فضع علامة عليها، ثم حدد **إزالة**.
7. حدد **موافق**.

عند العودة إلى قائمة جداول الفواتير، يجب أن ترى أنه تم تغيير حالة جداول الفواتير إلى **تعليق**.

### <a name="remove-a-hold-from-several-billing-schedules"></a>إزالة تعليق من عدة جداول فوترة

1. في صفحة **التعليق الجماعي**، قم بتعيين حقل **خيار العملية** إلى **إزالة تعليق**.
2. في حقل **كود السبب**، أدخل كود السبب.
3. في حقل **تاريخ إزالة**، أدخل التاريخ الذي ينبغي فيه إزالة التعليق.
4. قم بتعيين **تاريخ إعادة الاستئناف** و **تاريخ التأجيل** كما تريد. يضاف تاريخ التأجيل لجميع البنود التي يمكن تأجيلها.
5. في علامة التبويب السريعة **السجلات المراد تضمينها**، استخدم الزر **تصفية** لإضافة عوامل تصفية البيانات.
6. حدد **عرض الإصدار الأولي** لعرض مجموعة السجلات.
7. إذا كنت لا تريد معالجة بعض الخطوط، فضع علامة عليها، ثم حدد **إزالة**.
8. حدد **موافق**.

> [!NOTE]
> لإزالة تعليق، يجب عليك تعيين قيمة **إزالة تجاوز مجموعة مستخدمي التعليق‬‬‏‫** في صفحة **معلمات فوترة العقد المتكرر‬**.

على سبيل المثال، يحتوي بند الفوترة على تاريخ بدء في 1 فبراير 2022 وتاريخ انتهاء في 28 فبراير 2022. مبلغ الفوترة هو 200 دولار. تم تعيين **تاريخ التعليق** إلى 10 فبراير 2022. لذلك، يتم تعديل فترة فبراير لاستبعاد أي تاريخ بعد 10 فبراير. الفترة الجديدة من 1 فبراير حتى 9 فبراير، والمبلغ 64.29 دولار (من خلال التقسيم اليومي). تتم إزالة كافة سطور جدول الفوترة في 10 فبراير أو بعده.

إذا اكتملت عملية **إزالة التعليق**، وتم تعيين حقل **تاريخ الإزالة** إلى 10 فبراير 2022، وستكون هناك فترتان للفوترة. تبدأ فترة الفاتورة الأولى من 1 فبراير حتى 9 فبراير، والمبلغ 64.29 دولارًا. تبدأ فترة الفاتورة الثانية من 10 فبراير حتى 28 فبراير، والمبلغ 135.71 دولارًا.

## <a name="mass-termination-processing"></a>معالجة الإنهاء الجماعي

استخدم صفحة **الإنهاء الجماعي** لإنهاء بنود جدول الفواتير المعروضة حاليًا من خلال تحديد تاريخ الإنهاء.

إذا كنت تستخدم تأجيلات الإيرادات والمصروفات، فستجد جداول الفوترة حيث يتم تعيين الحقل **تاريخ الإنهاء** إلى **تعديل الجدول** في صفحة **كل جداول الفوترة** المؤهلة للاسترداد.

لا تظهر جداول الفوترة التي تستخدم وظيفة تخصيص العناصر المتعددة (MEA) في صفحة **الإنهاء الجماعي**. لا يزال بإمكانك إنهاء جدول الفواتير الفردية باستخدام وظيفة الإنهاء في جدول الفواتير.

> [!NOTE]
> بنود جدول الفواتير المضمنة حاليًا في دفعة **إنشاء الفاتورة** غير متاحة لهذه العملية.

للحصول على معلومات حول كل حقل والعملية، راجع [إنهاء جداول الفوترة](terminate-billing-schedule.md).

## <a name="mass-archive-process"></a>عملية الأرشفة الجماعية

استخدم صفحة **الأرشفة الجماعية** لأرشفة جداول الفواتير المتعددة. يمكن أرشفة جداول الفواتير المنتهية فقط.

بعد أرشفة جدول الفواتير، تقع الأحداث التالية:

- تتغير الحالة مرة أخرى إلى **مؤرشفة**.
- جداول الفواتير مؤمنة بشكل دائم.
- لم تعد بنود جدول الفواتير متوفرة على صفحات الاستفسار.

> [!NOTE]
> أرشفة جدول الفواتير هو إجراء دائم ولا يمكن التراجع عنه.

لأرشفة جداول الفواتير، اتبع هذه الخطوات.

1. في صفحة **الأرشفة الجماعية**، في حقل **تاريخ انتهاء الفوترة**، حدد تاريخ انتهاء الفوترة. لعرض كافة جداول الفواتير المنتهية، اترك هذا الحقل فارغًا.
2. في علامة التبويب السريعة **السجلات المراد تضمينها**، استخدم الزر **تصفية** للحد من السجلات المعروضة.
3. حدد **عرض الإصدار الأولي**.
4. إذا كنت لا تريد أرشفة بعض السجلات، فضع علامة عليها، ثم حدد **إزالة**.
5. حدد **موافق** لأرشفة السجلات في الصفحة.

## <a name="mass-stubbing-process"></a>عملية الاقتطاع الجماعي

استخدم **القطع الجماعي** لتمييز كافة سطور جدول الفوترة المحددة على أنها (قطع) مفوتر أو (قطع عكسي) غير مفوتر. غالبًا ما يتم إجراء القطع أو إلغاء القطع على بنود جدول الفواتير المستوردة التي تم تحرير فواتير بها مسبقًا في نظام آخر. تظهر سطور جدول الفوترة المقطوعة على أنها مقطوعة ولن تنشئ فاتورة للعميل.

### <a name="stub-records"></a>قطع السجلات

1. في صفحة **القطع الجماعي**، في حقل **خيارات المعالجة**، حدد **قطع**.
2. في حقل **تاريخ القطع**، عيّن تاريخًا نهائيًا لتحديد الأسطر التي تريد تطبيق العملية عليها. سيتم فقط عرض السجلات التي يكون فيها تاريخ بدء الفوترة في أو قبل تاريخ الانتهاء المحدد.
3. حدد **عرض الإصدار الأولي** لعرض البنود التي تريد قطعها.
4. لاستبعاد بند من العملية، قم بتمييزه، ثم حدد **إزالة**.
5. حدد **عملية** لقطع البنود.

### <a name="reverse-stub-records"></a>إلغاء قطع السجلات

1. في صفحة **القطع الجماعي**، في حقل **خيارات المعالجة**، حدد **إلغاء قطع**.
2. في حقل **تاريخ القطع**، عيّن تاريخًا نهائيًا لتحديد الأسطر التي تريد تطبيق العملية عليها. سيتم فقط عرض السجلات التي يكون فيها تاريخ بدء الفوترة في أو قبل تاريخ الانتهاء المحدد.
3. حدد **عرض الإصدار الأولي** لعرض البنود التي تريد إلغاء قطعها.
4. لاستبعاد بند من العملية، قم بتمييزه، ثم حدد **إزالة**.
5. حدد **عملية** لإلغاء قطع البنود.

## <a name="update-completion-date-process"></a>معالجة تاريخ إكمال التحديث

استخدم صفحة **تحديث تاريخ الانتهاء** لتحديث تاريخ الإكمال لعناصر مهمة محددة لجداول فوترة متعددة أو مستخدمين. يمكنك أيضًا تحديث نسبة الإكمال للعناصر الموجودة في قوالب المعالم التي تستخدم طريقة **النسبة المئوية المكتملة**.

1. في صفحة **تاريخ اكتمال التحديث**، انتقل إلى **معالجة الأحداث الرئيسية**، وحدد **نسبة اكتمال التحديث**.
2. في حقل **مبلغ النسبة المئوية**، أدخل النسبة المئوية الإجمالية التي اكتملت.
3. حدد رقم الصنف المرتبط بقالب الأحداث الرئيسية.
4. في علامة التبويب السريعة **السجلات المراد تضمينها**، حدد **تصفية** لتحديد قيمة **حساب مستخدم نهائي** محدد، أو **رقم جدول الفوترة**، أو **أرقام الأصناف** كمعيار تصفية.
5. حدد **موافق** لمعالجة التغيير. عند اكتمال المعالجة، تتم إضافة بند جديد إلى تخصيص الأحداث الرئيسية. يمثل هذا البند النسبة المئوية التي تم إكمالها لقالب الأحداث الرئيسية.

## <a name="unbilled-revenue-mass-processing"></a>المعالجة الجماعية للإيرادات غير المفوترة

استخدم صفحة **المعالجة الجماعية للإيرادات غير المفوترة** لإنشاء إدخال دفتر يومية الإيرادات غير مفوتر أو إيقاف إدخال دفتر اليومية لواحد أو أكثر محدد جداول الفواتير أو سطور تفاصيل الفواتير.

- **إنشاء إدخال دفتر يومية** – قم بإنشاء إدخالات دفتر يومية الإيرادات غير مفوترة للعديد من بنود جدول الفواتير. استخدم الزر **تصفية** في علامة التبويب السريعة **السجلات المراد تضمينها** لتحديد مجموعة السجلات التي تظهر في القائمة. تعرض القائمة فقط بنود جدول الفوترة التي لم يتم إنشاء إدخالات دفتر يومية الإيرادات غير المفوترة لها. يتم إنشاء إدخالات دفتر اليومية الأولية. بالنسبة لبنود التأجيل، يتم أيضًا إنشاء جداول التأجيل.
- **قطع إدخال دفتر اليومية** – قم بتمييز بنود جدول الفوترة التي تم بالفعل إنشاء إدخالات دفتر اليومية غير المفوترة لها. يتم استخدام هذا الخيار إذا كان قيد اليومية غير المفوترة قد تم ترحيله بالفعل في نظام آخر. يشير إلى أن دفتر اليومية للإيرادات غير المفوترة غير مفوتر ولا يرسل معاملة إلى دفتر الأستاذ العام.
- **إلغاء قطع إدخال دفتر اليومية** – إلغاء قطع إدخالات دفتر اليومية التي تمت معالجتها. إذا حدث خطأ أثناء معالجة **قطع إدخال دفتر اليومية**، فسيؤدي هذا الخيار إلى محو مربع الاختيار **مقطوع** لبند جدول الفوترة.
- **قطع بند تفاصيل الفوترة** – استخدم هذه العملية عندما تتم معالجة الإيرادات التي لم يتم تحرير فواتير بها في نظام خارجي، وتم بالفعل إعداد فاتورة لبعض بنود تفاصيل الفواتير. ستضمن هذه العملية ظهور المبلغ الصحيح في حسابات الإيرادات غير المفوترة.
- **إلغاء قطع بند تفاصيل الفوترة** – إلغاء أي إجراء **قطع بند تفاصيل الفوترة**.

يُستخدم حقل **اسم دفتر اليومية** لترحيل **إنشاء إدخال دفتر اليومية** إلى دفتر الأستاذ العام.

> [!NOTE]
> لا تقوم عملية القطع بترحيل المبالغ إلى دفتر الأستاذ العام. لا يتوفر حقل **اسم دفتر اليومية** لكل عمليات القطع ولكل عمليات إلغاء القطع.

### <a name="unbilled-revenue-stub-example"></a>مثال على قطع الإيرادات غير المفوترة

تم إعداد جدول الفواتير لمدة عام واحد، من أكتوبر 2021 حتى سبتمبر 2022. تمت معالجة الإيرادات غير المفوترة بالفعل في نظام خارجي. تسعة أشهر من جدول الفواتير تم تحريرها بالفعل. مبلغ كل فترة فوترة هو 250 دولارًا. في بداية العام، المبلغ الإجمالي الذي تم ترحيله إلى الإيرادات غير المفوترة هو 3000 دولار. بعد تسعة أشهر، تم إصدار فاتورة بقيمة 2250 دولارًا أمريكيًا، وتبقى 750 دولارًا أمريكيًا في الإيرادات غير المسددة.

لإعداد جدول الفوترة حيث تبقى قيمة ثلاثة أشهر فقط من الإيرادات غير المفوترة، اتبع هذه الخطوات.

1. في صفحة **عرض تفاصيل الفوترة**، قم بإنشاء جدول فوترة للفترة من أكتوبر 2021 حتى سبتمبر 2022، رقم الصنف S0001، ومبلغ 250 دولارًا شهريًا.
2. حدد **إنشاء إدخال دفتر اليومية** لجدول الفوترة. يتم ترحيل مبلغ 3000 دولار إلى الإيرادات غير المفوترة.
3. حدد **قطع بند تفاصيل الفوترة**، وحدد تاريخ الحركة في يونيو 2022 (تسعة أشهر). لن تظهر بنود جدول الفوترة في الإصدار الأولي. تستند البنود المتأثرة إلى تاريخ الحركة.
4. حدد **موافق**.

الأشهر التسعة الأولى التي تم إصدار فاتورة بها قد توقفت.

[![عرض قطع بنود تفاصيل الفوترة.](./media/01_View-billing-detail-stub.png)](./media/01_View-billing-detail-stub.png)

يتم عكس مبلغ 3000 دولار من الإيرادات غير المفوترة، ويتم ترحيل 750 دولارًا أمريكيًا في الإيرادات المتبقية. لعرض ترحيلات الإيرادات غير المفوترة، حدد **تدقيق إدخال دفتر يومية الإيرادات غير المفوترة** في علامة التبويب **التجديدات** في صفحة تفاصيل البند.

[![تدقيق إدخال دفتر يومية الإيرادات غير المفوترة.](./media/02_Unbilled-rev-journal-audit.png)](./media/02_Unbilled-rev-journal-audit.png)

> [!NOTE]
> يمكن إنشاء إدخال دفتر اليومية للإيرادات غير المفوترة لأي فترة تجديد، بشرط أن يتم فوترة جميع سطور تفاصيل الفوترة من المدة السابقة. على سبيل المثال، يحتوي بند جدول الفوترة على فترة تكرار فوترة شهرية لمدة 12 شهرًا، من يناير حتى ديسمبر 2021. يتكون الخط من ثلاث فترات: المدة الأولية، ومدة ثانية (من يناير إلى ديسمبر 2022)، وفترة ثالثة (من يناير حتى ديسمبر 2023). بعد إنشاء الفاتورة لجميع سطور تفاصيل الفوترة من أول 12 شهرًا في عام 2021، يمكن إنشاء إدخال دفتر اليومية للإيرادات غير المفوترة للمدة الثانية.
>
> بالنسبة لبنود التأجيل التي تستخدم ميزة الإيرادات غير المفوترة، تتم معالجة بند الفواتير وبنود الخصم. بالنسبة لهذه العناصر، يتم إنشاء إدخال دفتر يومية الإيرادات غير المفوترة وجدول التأجيل لبند الفوترة وبند الخصم.
>
> تقوم إدخالات دفتر اليومية التي تم إنشاؤها للعناصر غير القابلة للتأجيل والعناصر القابلة للتأجيل بترحيل رصيد إلى حسابات إيرادات مختلفة.