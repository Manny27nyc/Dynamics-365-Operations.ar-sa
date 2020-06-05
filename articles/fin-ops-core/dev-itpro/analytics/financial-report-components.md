---
title: مكونات التقرير المالي
description: توضح هذه المقالة كيفية استخدام مكونات أو كتل إنشاء تعريفات التقرير في إعداد التقارير المالية. تتضمن كتل الإنشاء هذه تعريفات الصفوف وتعريفات الأعمدة وتعريفات شجرة التقارير. توضح هذه المقالة كيفية تنظيم كتل الإنشاء وتأمينها وكيفية العمل مع مجموعات كتل الإنشاء.
author: aprilolson
manager: AnnBe
ms.date: 10/27/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 59071
ms.assetid: a201cfcb-1672-45f6-897d-2db2dd181d9a
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 27a6745be62185b23a7e81c9aed78879e36b3a9d
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181716"
---
# <a name="financial-report-components"></a>مكونات التقرير المالي

[!include [banner](../includes/banner.md)]

توضح هذه المقالة كيفية استخدام مكونات أو كتل إنشاء تعريفات التقرير في إعداد التقارير المالية. تتضمن كتل الإنشاء هذه تعريفات الصفوف وتعريفات الأعمدة وتعريفات شجرة التقارير. توضح هذه المقالة كيفية تنظيم كتل الإنشاء وتأمينها.

تُبنى فلسفة التصميم خلف مصمم التقارير المالية على تقسيم المعلومات إلى أصغر مكون أو كتلة إنشاء، ثم خلط المكونات ومطابقتها كما تقتضي الحاجة. وبالتالي، يكون تنسيق التقارير منفصلاً عن البيانات المالية، ويمكنك تغيير تصميم التقرير دون تعديل البيانات المالية في نظام Microsoft Dynamics ERP system. باستخدام نهج كتلة الإنشاء هذا، يمكنك دمج النص والمبالغ والعمليات الحسابية لإنتاج التقارير التي تحتاجها. علاوةً على ذلك، تشجع هذه المرونة على الإبداع عن طريق تسهيل الأمر عليك في عرض العمليات بطرق مختلفة. تشبه كتل الإنشاء الفردية في تعريف تقرير جدول بيانات ثلاثي الأبعاد، ولكنها تتميز بقدر أكبر من الفعالية. يحدد تعريف التقرير تعريف الصف وتعريف العمود وتعريف شجرة التقارير الاختيارية التي يجب استخدامها في التقرير. ويتضمن أيضًا معلومات حول مكان تخزين التقرير الذي تم إنشاؤه وكيفية تنسيقه.

## <a name="building-blocks-of-a-report"></a>كتل إنشاء تقرير

| كتلة الإنشاء            | ‏‏الوصف | لمزيد من المعلومات |
|---------------------------|-------------|----------------------|
| تعريف الصف            | يحدد تعريف الصف البنود الوصفية (على سبيل المثال، المرتبات أو المبيعات) في تقرير. كما يسرد الأبعاد أو قيم الشرائح التي تحتوي على القيم لكل صنف بند ويتضمن تنسيق الصفوف والعمليات الحسابية. | [تعريفات الصفوف](row-definitions-financial-reporting.md) |
| تعريف العمود         | يحدد تعريف العمود الفترة التي يجب استخدامها عند استخراج البيانات من الأبعاد المالية. كما يتضمن تنسيق الأعمدة والعمليات الحسابية. | [تعريفات الأعمدة](column-definitions-financial-reports.md) |
| تعريف شجرة التقارير | يشبه تعريف شجرة التقارير مخططًا تنظيميًا. ويحتوي على وحدات التقارير الفردية التي تمثل كل مربع في المخطط. ويمكن أن تكون الوحدات أقسام فردية من البيانات المالية لو وحدات عالية المستوى تلخص البيانات من وحدات التقارير الأخرى. | [تعريفات شجرة التقارير](financial-reporting-tree-definitions.md) |
| تعريف التقرير         | يستخدم تعريف التقرير تعريف الصف وتعريف العمود وتعريف شجرة التقارير الاختيارية لتصميم تقرير. كما يوفر إعدادات وخيارات إضافية يمكنك استخدامها لتخصيص التقرير. | [تعريف التقرير](design-financial-report-definitions.md) |

إذا كنت حديث العهد في تصميم تقارير، فقد ترغب في استخدام معالج التقارير لكي تتمكن من إنشاء تعريف تقرير بسرعة يمكنك تخصيصه لاحقًا. وإذا كان لديك خبرة في تصميم التقارير وتريد المزيد من المرونة لتصميم التقارير، فيمكنك دمج كتل إنشاء جديدة أو موجودة لإنشاء تعريف تقرير جديد. لا يلزمك أن تفهم كافة خيارات تعريف التقرير المتوفرة بشكل كامل لإنتاج تقارير جيدة. وعندما تصبح على دراية بتصميم التقارير، يمكنك توسيع تعريفات التقرير الخاص بك للاستفادة من ميزات أكثر تقدمًا. بعد إنشاء تقرير أساسي، يمكنك تخصيص تعريف التقرير وأي من كتل الإنشاء في تعريف التقرير.

## <a name="organize-the-building-blocks"></a>تنظيم كتل الإنشاء
استخدم المجلدات لتنظيم كتل الإنشاء الخاصة بك في مصمم التقارير. وتعتبر كافة المجلدات خاصة بنوع كتل الإنشاء التي تحتوي عليها. على سبيل المثال، توجد كافة المجلدات التي تحتوي على تعريفات الصفوف في جزء **تعريفات الصفوف‬** في مصمم التقارير.

### <a name="create-a-folder"></a>إنشاء مجلد

1. في مصمم التقارير، حدد نوع كتل الإنشاء لتنظيمها في "جزء التنقل". على سبيل المثال، لفرز تعريف صف، انقر فوق **تعريفات الصف**.
2. في جزء التنقل، حدد المجلد الموجود الذي سيتم إنشاء المجلد الجديد ضمنه، ثم اتبع إحدى الخطوات التالية:

    - انقر بزر الماوس الأيمن فوق المجلد الأصلي، ثم انقر فوق **مجلد جديد**.
    - حدد المجلد الأصلي، وانقر فوق **ملف**، ثم انقر فوق **مجلد جديد**.

3. عندما يظهر المجلد الجديد، أدخل اسم المجلد الجديد، ثم اضغط على Enter.

## <a name="lock-a-building-block"></a> تأمين كتلة الإنشاء
يمكنك إنشاء كلمة مرور لتأمين كتلة الإنشاء والمساعدة على حمايتها. ومن خلال هذه الطريقة، يمكنك إضافة مستوى من الأمان إلى مكون التقرير من دون تأمين النظام بأكمله. بإمكان كلمة المرور أن توفر الحماية لمعلومات كتل الإنشاء والتي تُعد مهمة لعملية إعداد التقارير في نهاية الشهر. بإمكان مستخدم يؤدي أي دور تأمين كتلة الإنشاء. ومع ذلك، ستتوفر للمستخدمين الآخرين على الدوام إمكانية الوصول للقراءة فقط إلى أحد المكونات المؤمنة. باستطاعة المستخدمين فتح المكون المؤمن وتغييره وحفظه باسم جديد. باستطاعة المستخدم الذي يؤدي دور المسؤول أن يصل دومًا إلى كتلة إنشاء مؤمنة وتغييرها.

1. في مصمم التقارير، افتح مكون التقرير لتأمينه، مثل تعريف صف أو تعريف عمود أو تعريف تقرير أو تعريف شجرة التقارير.
2. في قائمة **أدوات**، انقر فوق **حماية/إلغاء حماية‬‏‫**. كما يمكنك النقر فوق **حماية/إلغاء حماية‬‏‫** (أيقونة التأمين) في شريط الأدوات.
3. في مربع الحوار **حماية**، أدخل كلمة مرور وأكدها, ثم انقر فوق **موافق**. يتم تمييز أيقونة التأمين في شريط الأدوات عند تأمين كتلة إنشاء مفتوحة.

لإلغاء تأمين كتلة إنشاء مؤمنة، افتح كتلة الإنشاء، ثم انقر فوق **حماية/إلغاء حماية** على شريط الأدوات. أو، في قائمة **أدوات**، انقر فوق **إلغاء حماية‬‏‫**.

## <a name="building-block-groups"></a>مجموعات كتل الإنشاء

كتل الإنشاء عبارة عن تعريفات الصفوف وتعريفات الأعمدة وتعريفات شجرة التقارير وتعريفات التقارير التي تقوم بإنشائها لتقرير. مجموعات كتل الإنشاء هي مجموعات من التعريفات ومجموعات الأبعاد.

### <a name="view-a-building-block-group"></a>عرض مجموعة كتل إنشاء

يمكنك عرض جميع كتل الإنشاء التي يتم تعيينها إلى مجموعة كتل إنشاء. يمكنك أيضًا تصدير أو استيراد مجموعة كتل الإنشاء.

1. في مصمم التقارير، في قائمة **الشركة**، انقر فوق **مجموعات كتل الإنشاء**.
2. في مربع حوار **مجموعات كتل الإنشاء**، حدد كتلة الإنشاء لعرضها.
3. انقر فوق **عرض** لفتح مربع حوار **عرض مجموعة كتل الإنشاء**، حيث يمكنك عرض محتويات مجموعة كتل الإنشاء.
4. انقر فوق **إغلاق** لإغلاق مربعات الحوار.

### <a name="export-a-building-block-group"></a>تصدير مجموعة كتل إنشاء

يمكنك تصدير مجموعة كتل الإنشاء أو كتل إنشاء تقارير محددة في مجموعة كتل إنشاء. يمكنك استخدام مجموعة كتل الإنشاء التي تم تصديرها كنسخة احتياطية. يمكنك أيضًا نسخ البيانات المصدّرة بين عمليات التثبيت. يتضمن مصمم التقارير مجموعات أنماط الخطوط والأبعاد المشار إليها مع مجموعة كتل الإنشاء.

1. في مصمم التقارير، في قائمة **الشركة**، انقر فوق **مجموعات كتل الإنشاء**.
2. في مربع حوار **مجموعات كتل الإنشاء**، حدد مجموعة كتل الإنشاء المطلوب تصديرها، ثم انقر فوق **تصدير**.
3. في مربع الحوار **تصدير**، حدد تعريفات التقرير للتصدير:

    - لتصدير كافة تعريفات التقارير وكتل الإنشاء المقترنة، انقر فوق **تحديد الكل**.
    - لتصدير مجموعات محددة من التقارير أو الصفوف أو الأعمدة أو الأشجار أو الأبعاد، انقر فوق علامة التبويب المناسبة ثم حدد العناصر المراد تصديرها. اضغط مع الاستمرار على مفتاح Ctrl لتحديد عناصر متعددة في علامة التبويب.

    > [!NOTE]
    > عند تحديد تقارير لتصديرها، سيتم تحديد الصفوف والأعمدة والأشجار ومجموعات الأبعاد ذات الصلة.

4. عندما تنتهي من تحديد العناصر المراد تصديرها، انقر فوق **تصدير**.
5. في مربع الحوار **حفظ باسم**، حدد موقع لتصدير مجموعة كتل الإنشاء إليه.
6. في حقل **اسم الملف**، أدخل اسمًا للملف. يضيف مصمم التقارير ملحق اسم ملف tdbx. تلقائيًا.
7. انقر فوق **حفظ**. يتم حفظ مجموعة كتل الإنشاء في الموقع الذي تحدده.

### <a name="import-a-building-block-group"></a> استيراد مجموعة كتل الإنشاء

يمكنك استيراد مجموعة كتل إنشاء إلى مجموعة كتل إنشاء موجودة. تحتفظ جميع كتل الإنشاء المستوردة بأنماط خطوطها الأصلية ومراجع شركاتها، وتتضمن مجموعات أبعاد ذات صلة.

1. في مصمم التقارير، في قائمة **الشركة**، انقر فوق **مجموعات كتل الإنشاء**.
2. في مربع حوار **مجموعات كتل الإنشاء**، حدد كتلة الإنشاء المطلوب استيراد مجموعة كتل الإنشاء إليها، ثم انقر فوق **استيراد**.
3. في مربع حوار **فتح**، حدد مجموعة كتل الإنشاء المطلوب استيرادها، ثم انقر فوق **فتح**.
4. في مربع الحوار **استيراد**، حدد تعريفات التقرير المراد استيرادها.

    - لاستيراد كافة تعريفات التقارير وكتل الإنشاء الداعمة، انقر فوق **تحديد الكل**.
    - لاستيراد تقارير أو صفوف أو أعمدة أو أشجار أو مجموعات أبعاد محددة، حدد التقارير أو الصفوف أو الأعمدة أو الأشجار أو مجموعات الأبعاد لاستيرادها.

5. عندما تنتهي من تحديد العناصر المراد استيرادها، انقر فوق **استيراد**.

### <a name="undo-a-checkout-of-a-building-block"></a>التراجع عن سحب كتلة إنشاء

عندما تفتح كتلة إنشاء، ستتوفر للمستخدمين الآخرين إمكانية الوصول للقراءة فقط إلى كتلة الإنشاء هذه. وفي بعض الأحيان، ينسى المستخدم إغلاق كتلة إنشاء أو يقوم بإيقاف تشغيل النظام من دون إغلاق كتلة الإنشاء. ونتيجة لذلك، تبقى كتلة الإنشاء مسحوبة، وسيتعذر على أي مستخدم آخر فتحها. وفي هذه الحالات، بإمكان مسؤول التقارير المالية استخدام مربع حوار **الأصناف المسحوبة** لإيداع كتل الإنشاء التي تركها المستخدمون مسحوبة.

> [!NOTE]
> ويجب أن يكود لديك دور المسئول لإيداع كتل الإنشاء باستخدام مربع الحوار **عناصر تم سحبها**.

1. في مصمم التقارير، في قائمة **الأدوات**، انقر فوق **الأصناف المسحوبة**.
2. في مربع حوار **عناصر تم سحبها**، حدد **عرض العناصر من كل المستخدمين**. يتم تحديث القائمة لعرض جميع كتل الإنشاء التي تم سحبها والمستخدمين الذين قاموا بسحبها.
3. حدد كتلة إنشاء، ثم انقر فوق، **التراجع عن السحب**.
4. انقر فوق **نعم** لإيداع كتلة الإنشاء.

## <a name="additional-resources"></a>الموارد الإضافية

[التقارير المالية](financial-reporting-intro.md)