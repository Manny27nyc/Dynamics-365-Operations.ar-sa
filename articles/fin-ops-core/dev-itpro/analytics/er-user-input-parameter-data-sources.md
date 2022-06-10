---
title: استخدام مصادر بيانات USER INPUT PARAMETER لتحديد المعلمات لتقرير
description: يشرح هذا الموضوع كيفية استخدام مصادر بيانات USER INPUT PARAMETER لتحديد المعلمات للتقارير التي ترغب في إنشائها.
author: NickSelin
ms.date: 04/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Version 10.0.27
ms.openlocfilehash: 4e431c9dd59080af17fa073547073037ba233288
ms.sourcegitcommit: 6c1bf233748c4bc70fc5a1a9711758cdfd9e07dc
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/19/2022
ms.locfileid: "8782305"
---
# <a name="use-user-input-parameter-data-sources-to-specify-parameters-for-a-report"></a>استخدام مصادر بيانات USER INPUT PARAMETER لتحديد المعلمات لتقرير

[!include[banner](../includes/banner.md)]

عندما تقوم بتصميم [تعيين نموذج](general-electronic-reporting.md) [التقارير الإلكترونية](er-overview-components.md#model-mapping-component) ومكونات [تنسيق](er-overview-components.md#format-component) التقارير الإلكترونية، يمكنك استخدام مصادر بيانات من النوع *USER INPUT PARAMETER* للحصول على القيم المطلوبة التي يمكن تحديدها في حقول إدخال البيانات في مربع الحوار في وقت التشغيل. يصف هذا الموضوع مصادر بيانات *USER INPUT PARAMETER* المدعومة في الوقت الحالي.

## <a name="mandatory-properties"></a><a name="mandatory-properties"></a>الخصائص الإلزامية

يجب تحديد الخصائص التالية لمصادر البيانات لكل نوع *USER INPUT PARAMETER*:

- في حقل **الاسم**، أدخل الاسم الداخلي لمصدر البيانات. يمكنك استخدام هذا الاسم في [تعبيرات](er-formula-language.md) وروابط أخرى لتعيين النموذج الذي تم تكوينه أو مكون التنسيق.

## <a name="optional-properties"></a><a name="optional-properties"></a>الخصائص الاختيارية

يجب تحديد الخصائص التالية، بشكل اختياري، لمصادر البيانات من النوع *USER INPUT PARAMETER*:

- في الحقل **التسمية**، حدد التسمية المستخدمة لحقل إدخال البيانات ذي الصلة في مربع الحوار في وقت التشغيل. يمكنك إضافة نص تسمية مختلف لأكواد لغات مختلفة عن طريق تنشيط حقل **التسمية** ثم تحديد **ترجمة**.
- في حقل **المساعدة**، حد نص المساعدة الذي يظهر في وقت التصميم في أسفل صفحة **مصمم التنسيق** أو صفحة **مصمم تعيين النموذج** عن تحديد مصدر بيانات قابل للتحرير من النوع *USER INPUT PARAMETER*. قد يوفر هذا النص تفاصيل إضافية حول مصدر البيانات لمساعدة المستخدمين عند تكوين التنسيق القابل للتحرير أو مكون تعيين النموذج. يمكنك إضافة نص مساعدة لأكواد اللغات المختلفة عن طريق تحديد **ترجمة**.

    > [!NOTE]
    > يصبح الزر **ترجمة** الذي يمكنك استخدامه لإضافة [نصوص وتسميات خاصة باللغة](er-design-multilingual-reports.md#format-component) متاحًا فقط بعد إضافة مصدر البيانات وحفظ التغييرات، ثم إعادة فتح مصدر البيانات للتحرير

- في الحقل **للقراءة فقط**، قم بتكوين تعبير يقوم بإرجاع قيمة *[منطقية](er-formula-supported-data-types-primitive.md#boolean)*.

    - إذا قام التعبير المكوّن بإرجاع قيمة **صواب** في وقت التشغيل، يظهر حقل إدخال البيانات ذو الصلة خافتًا في مربع الحوار، ولا يمكنك تغيير قيمته.
    - إذا قام التعبير المكوّن بإرجاع قيمة **خطأ** في وقت التشغيل أو إذا لم يتم تكوين أي تعبير، يتوفر حقل إدخال البيانات ذو الصلة في مربع الحوار، ويمكنك تغيير قيمته.

- في حقل القيمة **القيمة الافتراضية**، قم بتكوين تعبير يرجع قيمة نوع المعلمة المشار اليها. يمكن استخدام هذه القيمة لتعبئة قيمة افتراضية لحقل إدخال البيانات ذي الصلة في مربع الحوار في وقت التشغيل.

    عند تشغيل تنسيق التقارير الإلكترونية، يتم حفظ القيمة التي تدخلها في حقل إدخال البيانات ذي الصلة في مربع الحوار في وقت التشغيل في الذاكرة كالقيمة المستخدمة في وقت سابق. يتم حفظ القيم المستخدمة في وقت سابق بشكل فردي لكل حقل، وتنسيق التقارير الإلكترونية قيد التشغيل، والمستخدم الحالي، والمؤسسة الحالية (الشركة).

    - عيّن الخيار **إعادة التعيين إلى القيمة الافتراضية دائمًا‬** إلى **نعم** إذا كان يجب استخدام القيمة المرتجعة بواسطة تعبير **القيمة الافتراضية** دائمًا باعتبارها القيمة الافتراضية‏‎ للقيمة التي تم استخدامها في وقت سابق.
    - عيّن الخيار **إعادة التعيين إلى القيمة الافتراضية دائمًا‬** إلى **لا** إذا كان يجب استخدام القيمة المرتجعة بواسطة قيمة تعبير **القيمة الافتراضية** باعتبارها القيمة الافتراضية‏‎ فقط عندما تكون القيمة التي تم استخدامها في وقت سابق مفقودة.

    > [!NOTE]
    > إذا عيّنت الخيار **إعادة التعيين إلى القيمة الافتراضية دائمًا‬** إلى **نعم**، فيجب تكوين تعبير في حقل **القيمة الافتراضية**.

- إذا عيّنت الخيار **السماح بالتحديد المتعدد‬** إلى **نعم**، فيمكنك تحديد قيم متعددة للمعلمة التي تم تكوينها في وقت التشغيل. إذا عيّنته إلى **لا**، فيمكنك تحديد قيمة واحدة فقط.

    > [!NOTE]
    > هذا الخيار غير قابل للتطبيق على جميع أنواع *USER INPUT PARAMETER*. في وقت التصميم، تم طرح استثناء لإبلاغ المستخدم بأن معلمة إدخال المستخدم التي تم تكوينها لا تدعم التحديد المتعدد، وأنه لا يمكن تحديد أو إدخال سوى قيمة واحدة.
    >
    > إذا قمت بتعيين الخيار السماح **السماح بالتحديد المتعدد** إلى **نعم**، وحددت تعبيرًا في حقل **القيمة الافتراضية**، فيمكنك استخدام ذلك التعبير لتعين قيمة افتراضية واحدة فقط.

- حدد الخيار **تحرير إمكانية الرؤية‬** لتحديد ما إذا كان يجب عرض المعلمة المكوّنة في مربع الحوار في وقت التشغيل.

    > [!NOTE]
    > تتوقف إمكانية الرؤية الافتراضية لمصادر بيانات من النوع *USER INPUT PARAMETER* على مكون التقارير الإلكترونية الذي يحتويها.
    >
    > - إذا تم تكوين مصدر بيانات في مكون التنسيق، فسيكون مرئيًا بشكل افتراضي.
    > - يتم تكوين مصدر البيانات في مكون تعيين النموذج، فسيكون مرئيًا فقط إذا كانت قيمة مصدر البيانات تؤثر على النتيجة عند تشغيل أحد مكونات التقارير الإلكترونية. على سبيل المثال، قمت بإضافة مصدر بيانات ولكنك لم تستخدمه في التعبيرات والروابط الخاصة بمكون تعيين النموذج الحالي. في هذه الحالة، بشكل افتراضي، لن يتم عرض حقل إدخال البيانات ذي الصلة في مربع الحوار في وقت التشغيل. 

    في الصفحة **مصمم الصيغة**، في حقل **الصيغة**، قم بتكوين يرجع قيمة *منطقية*.

    - إذا قام التعبير المكوّن بإرجاع قيمة **صواب** في وقت التشغيل أو إذا لم يتم تكوين أي تعبير، يكون حقل إدخال البيانات ذو الصلة مرئيًا في مربع الحوار في وقت التشغيل.
    - إذا قام التعبير المكوّن بإرجاع قيمة **خطأ**، يكون حقل إدخال البيانات ذو الصلة مخفيًا في مربع الحوار في وقت التشغيل. عند استدعائه بواسطة تعبيرات أخرى في وقت التشغيل، يرجع القيمة الافتراضية أو القيمة المستخدمة في وقت سابق أو القيمة الافتراضية لقيمة نوع البيانات الحالي بالاستناد إلى الإعدادات الأخرى.

## <a name="type-specific-properties"></a>الخصائص الخاصة بالنوع

### <a name="application-dependent-user-input-parameter"></a>معلمة إدخال المستخدم التي تعتمد على التطبيق

استخدم مصدر بيانات من النوع **عام** \> **معلمة إدخال المستخدم** للحصول على القيمة أو القيم المطلوبة لنوع بيانات محدد للمثيل الحالي من تطبيق Microsoft Dynamics 365 Finance. عند أضافه مصدر بيانات من هذا النوع إلى مكون ER، حدد الخصائص التالية:

- في الحقل **اسم نوع بيانات العمليات‬‏‫ (نوع البيانات الموسعة، التعداد)**، حدد تطبيق [نوع البيانات الموسعة (EDT)](../extensibility/extensible-edts.md) أو تعداد تطبيق.

> [!NOTE]
> نوصي بمراجعة التعبيرات التي تم تكوينها في الحقلين **للقراءة فقط** و **القيمة الافتراضية** عندما تقوم بتغيير مرجع **اسم نوع بيانات العمليات (نوع البيانات الموسعة، التعداد‬)** في مصدر بيانات قابل للتحرير من نوع *USER INPUT PARAMETER* هذا.

يبين الرسم التوضيحي التالي خصائص مصدر بيانات `$TaxRegNum` الذي تم تكوينه في تكوين تنسيق التقارير الإلكترونية **XML في نظام المعلومات الإحصائية (DE)‬**. يتم تكوين مصدر البيانات هذا لاستخدام نوع البيانات الموسعة (EDT) *يتم تكوين مصدر البيانات هذا لاستخدام نوع البيانات الموسعة (EDT)* لتقديم حقل إدخال بيانات **رقم التسجيل الضريبي** في مربع الحوار في وقت التشغيل.

![خصائص مصدر البيانات من النوع USER INPUT PARAMETER في مربع الحوار لصفحة "مصمم التنسيق".](./media/er-user-input-parameter-data-sources-01.png)

يبين الرسم التوضيحي التالي مربع الحوار الذي يظهر في وقت التشغيل عند تشغيل تكوين تنسيق التقارير الإلكترونية **XML في نظام المعلومات الإحصائية (DE)‬** بهدف [إنشاء](../../../finance/localizations/tasks/eur-00002-eu-intrastat-declaration.md) إقرار نظام جمع المعلومات التجارية بين دول الاتحاد الأوروبي. لاحظ أن حقل رقم **رقم التسجيل الضريبي** المكوّن متوفر لإدخال البيانات.

![مربع الحوار "تقرير نظام جمع المعلومات التجارية بين دول الاتحاد الأوروبي"‬ لتنسيق التقارير الإلكترونية الحالي في صفحة نظام جمع المعلومات التجارية بين دول الاتحاد الأوروبي](./media/er-user-input-parameter-data-sources-02.png)

### <a name="data-model-enumeration-user-input-parameter"></a>معلمة إدخال مستخدم تعداد نموذج البيانات

استخدم مصدر بيانات من النوع **نموذج البيانات** \> **معلمة إدخال مستخدم التعداد‬‬** للحصول على القيمة أو القيم المطلوبة لنموذج بيانات واحد [التعداد‬‬‏‎](er-formula-supported-data-types-primitive.md#enumeration). عند أضافه مصدر بيانات من هذا النوع إلى مكون ER، حدد الخصائص التالية:

- في حقل **النموذج**، حدد مرجعًا لنموذج البيانات الأساسي.
- في الحقل **تعداد النموذج**، حدد مرجعًا لتعداد نموذج البيانات المشار اليه.
- في حقل **الإصدار**، حدد رقم مراجعة مكون نموذج بيانات التقارير الإلكترونية الذي يحتوي على تعداد النموذج المشار إليه.

    > [!TIP]
    > في وقت التصميم ، يمكنك ترك حقل **الإصدار** فارغًا للوصول إلى قائمة التعدادات الخاصة بمكون نموذج البيانات المشار إليه الموجود في الإصدار التمهيدي لتكوين نموذج بيانات التقارير الإلكترونية المقابل. بهذه الطريقة، يمكنك تحرير الإصدار التمهيدي من تعيين النموذج أو مكون التنسيق والإصدار التمهيدي لمكون نموذج البيانات الأساسي في نفس الوقت.
    >
    > ومع ذلك، يمكن ترك حقل **الإصدار** فارغًا فقط في الإصدار التمهيدي لتعيين النموذج أو مكون التنسيق. عندما تقوم بتغيير حاله تكوين التنسيق أو تعيين النموذج في التقارير الإلكترونية من **مسودة** إلى **مكتمل**، يتم ملء هذا الحقل تلقائيًا بواسطة رقم مراجعة النموذج الأعلى المتوفر من مثيل Finance. إذا أدخلت تعدادًا جديدًا أو قيمة تعداد جديدة في الإصدار التمهيدي لنموذج البيانات الأساسي وقمت بالإشارة إليه في تعيين النموذج القابل للتحرير أو مكون التنسيق، فأكمل الإصدار التمهيدي لتكوين نموذج البيانات الأساسي قبل إكمال الإصدار التمهيدي من تكوين التنسيق أو تعيين النموذج في التقارير الإلكترونية. بخلاف ذلك، سيظهر الاستثناء "لم يتم العثور على المسار" عندما تقوم بتغيير حالية تعيين النموذج أو تكوين التنسيق من **مسودة** إلى **مكتمل**. ستعلمك الرسالة بأن قيمة التعداد أو التعداد المشار اليه مفقودة في نموذج البيانات الأساسي.

يبين الرسم التوضيحي التالي خصائص مصدر بيانات `$ReportDirection` الذي تم تكوينه في تكوين تنسيق التقارير الإلكترونية **XML في نظام المعلومات الإحصائية (DE) Contoso‬**. تم [اشتقاق](general-electronic-reporting.md#Configuration) تكوين **XML في نظام المعلومات الإحصائية (DE) Contoso** من تكوين **XML في نظام المعلومات الإحصائية (DE)**. تم تكوين مصدر البيانات هذا لاستخدام تعداد النموذج *ReportDirection* لتقديم حقل البحث المناسب في مربع الحوار في وقت التشغيل.

![خصائص مصدر البيانات من النوع USER INPUT PARAMETER في مربع الحوار لصفحة "مصمم التنسيق".](./media/er-user-input-parameter-data-sources-03.png)

### <a name="format-enumeration-user-input-parameter"></a>معلمة إدخال مستخدم تعداد التنسيق ‬

استخدم مصدر بيانات من النوع **تعداد التنسيق** \> **معلمة إدخال مستخدم التعداد** للحصول على القيمة أو القيم المطلوبة لتعداد تنسيق واحد. عند أضافه مصدر بيانات من هذا النوع إلى مكون ER، حدد الخصائص التالية:

- في الحقل **تنسيق التعداد**، حدد تعدادًا للتنسيق القابل للتحرير.

> [!NOTE]
> يمكن تكوين مصادر البيانات من هذا النوع فقط في نطاق مكون التنسيق القابل للتحرير.

## <a name="additional-resources"></a>الموارد الإضافية

[مصمم المعادلات في التقارير الإلكترونية](general-electronic-reporting-formula-designer.md)

[بدء قيم مصدر البيانات لنوع USER INPUT PARAMETER من كود المصدر](er-initiate-uip-data-source-value-from-source-code.md)