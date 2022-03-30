---
title: تصميم حل جديد لإعداد التقارير الإلكترونية لطباعة تسميات ZPL
description: يشرح هذا الموضوع كيفية تصميم حل جديد لإعداد التقارير الإلكترونية (ER) لطباعة ملصقات لغة برمجة Zebra (ZPL).
author: NickSelin
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-02-01
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: 4fb89f4b56ce8189482bf1a86582ef7e3684b15a
ms.sourcegitcommit: 411874545d7c326fc4aa877948a059371f0ccb3c
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/07/2022
ms.locfileid: "8392953"
---
# <a name="design-a-new-er-solution-to-print-zpl-labels"></a>تصميم حل جديد لإعداد التقارير الإلكترونية لطباعة تسميات ZPL

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

يشرح هذا الموضوع كيف يمكن للمستخدم في دور مسؤول النظام أو مطور التقارير الإلكترونية أو المستشار الوظيفي لإعداد التقارير الإلكترونية تكوين معلمات إطار عمل [التقارير الإلكترونية (ER)](general-electronic-reporting.md)، وتصميم [تكوينات](general-electronic-reporting.md#Configuration)  التقارير الإلكترونية المطلوبة لحل ER جديد للوصول إلى بيانات نظام إدارة المستودعات، وإنشاء ملصقات مخصصة لموقع المستودع بتنسيق Zebra Programming Language (ZPL) II. يمكن تنفيذ هذه الخطوات في شركة **USRT**.

## <a name="business-scenario"></a>سيناريو الأعمال

أنت تمثل شركة نفذت إدارة المستودعات في Microsoft Dynamics 365 Finance. يجب تسمية كل موقع من مواقع المستودعات بملصق ذاتي اللصق يتضمن رمزًا شريطيًا. سيستخدم عمال المستودعات قارئات الباركود المحمولة باليد لمسح الرموز الشريطية.

تم تصنيف جميع مواقع المستودعات في نطاق أنشطة ما قبل بدء التشغيل. ومع ذلك، يجب أيضا ان تكون قادرا علي طباعه تسميات موقع المستودع حسب الطلب إذا كانت التسميات الموجودة اما تالفة أو تمت أعاده تكوين المستودع شيلفينج. باستخدام وظيفة التقارير الإلكترونية التي تم إصدارها مؤخرًا، يمكنك تكوين حل ER جديد يتيح لمشرف المستودع طباعة الملصقات مباشرة إلى طابعة ملصقات حرارية.

## <a name="configure-the-er-framework"></a>تكوين إطار عمل ER

اتبع الخطوات في [تكوين إطار عمل التقارير الإلكترونية](er-quick-start2-customize-report.md#ConfigureFramework) لإعداد الحد الأدنى لمجموعة معلمات التقارير الإلكترونية. يجب عليك إكمال هذا الإعداد قبل البدء في استخدام إطار عمل إعداد التقارير الإلكترونية لتصميم حل ER جديد.

## <a name="design-a-domain-specific-data-model"></a>تصميم نموذج بيانات خاص بالمجال

أنشئ تكوين إعداد تقارير إلكترونية جديد يحتوي على مكون [نموذج بيانات](er-overview-components.md#data-model-component) لمجال إدارة المستودعات. سيتم استخدام نموذج البيانات هذا كمصدر بيانات لاحقًا، عندما تقوم بتصميم تنسيق تقارير إلكترونية لإنشاء تسميات موقع المستودع.

### <a name="import-a-data-model-configuration"></a>استيراد تكوين نموذج بيانات

اتبع هذه الخطوات لاستيراد نموذج البيانات المطلوب من ملف XML الذي توفره Microsoft. بدلاً من ذلك، يمكنك إنشاء نموذج البيانات الخاص بك كما هو موضح في القسم التالي.

1. قم بتنزيل الملف [Warehouse model.version.1.xml](https://download.microsoft.com/download/9/f/1/9f136e9b-bf5f-403a-b089-a2b2ed1da2ba/Warehouse-model.version.1.xml) واحفظه في جهاز الكمبيوتر المحلي.
2. انتقل إلى **إدارة المؤسسة** \> **مساحات العمل** \> **التقارير الإلكترونية**.
3. في مساحة عمل **إعداد التقارير الإلكترونية**، حدد **تكوينات إعداد التقارير**.
4. في صفحة **التكوينات**، في جزء الإجراءات، حدد **Exchange** \> **تحميل من ملف XML**.
5. حدد **استعراض** ثم ابحث عن الملف **Warehouse model.version.1.xml** وحدده.
6. حدد **موافق** لاستيراد التكوين.

![تكوين نموذج بيانات التقارير الإلكترونية المستوردة في صفحة التكوينات.](./media/er-design-zpl-labels-imported-model.png)

### <a name="create-a-data-model-configuration"></a>إنشاء تكوين نموذج البيانات

بدلاً من استيراد ملف نموذج البيانات المقدم من Microsoft، يمكنك إنشاء نموذج بيانات من البداية. للحصول على مثال يوضح كيفية إكمال هذه المهمة، راجع [إنشاء تكوين نموذج بيانات جديد](er-quick-start1-new-solution.md#DesignDataModel).

### <a name="review-the-data-model"></a>مراجعة نموذج البيانات

يمكنك عرض نسخة قابلة للتحرير من نموذج البيانات المكون على صفحة **مصمم نموذج البيانات**.

![هيكل نموذج بيانات التقارير الإلكترونية في صفحة مصمم نموذج البيانات.](./media/er-design-zpl-labels-model.png)

## <a name="design-a-model-mapping-for-the-configured-data-model"></a>تصميم تعيين نموذج لنموذج البيانات المكوّن

بصفتك مستخدمًا في دور مطور التقارير الإلكترونية، يجب عليك إنشاء تكوين تقارير إلكترونية جديد يحتوي على مكون [تعيين نموذج](er-overview-components.md#model-mapping-component) لنموذج بيانات المستودع. يقوم هذا المكون بتنفيذ نموذج البيانات المكون لـ Dynamics 365 Finance وهو خاص بهذا التطبيق. يجب عليك تكوينه لتحديد كائنات التطبيق التي سيتم استخدامها لملء نموذج البيانات المكون ببيانات التطبيق في وقت التشغيل. لإكمال هذه المهمة، يجب أن تفهم كيفية تنفيذ بنية البيانات الخاصة بمجال أعمال إدارة المستودعات في Finance.

### <a name="import-a-model-mapping-configuration"></a>استيراد تكوين تعيين نموذج

اتبع هذه الخطوات لاستيراد تعيين النموذج المطلوب من ملف XML الذي توفره Microsoft. بدلاً من ذلك، يمكنك إنشاء تعيين النموذج الخاص بك كما هو موضح في القسم التالي.

1. قم بتنزيل الملف [Warehouse model mapping.version.1.1.xml](https://download.microsoft.com/download/1/c/c/1cc94d28-3d90-4ffd-a118-77d6c322904f/Warehouse-model-mapping.version.1.1.xml) واحفظه في جهاز الكمبيوتر المحلي.
2. انتقل إلى **إدارة المؤسسة** \> **مساحات العمل** \> **التقارير الإلكترونية**.
3. في مساحة عمل **إعداد التقارير الإلكترونية**، حدد **تكوينات إعداد التقارير**.
4. في صفحة **التكوينات**، في جزء الإجراءات، حدد **Exchange** \> **تحميل من ملف XML**.
5. حدد **استعراض** ثم ابحث عن الملف **Warehouse model mapping.version.1.1.xml** وحدده.
6. حدد **موافق** لاستيراد التكوين.

![تكوين تعيين نموذج التقارير الإلكترونية الذي تم استيراده في صفحة التكوينات.](./media/er-design-zpl-labels-imported-mapping.png)

### <a name="create-a-model-mapping-configuration"></a>إنشاء تكوين لتعيين نموذج

بدلاً من استيراد ملف تعيين النموذج المقدم من Microsoft، يمكنك إنشاء تعيين نموذج من البداية. للحصول على مثال يوضح كيفية إكمال هذه المهمة، راجع [إنشاء تكوين تعيين نموذج جديد](er-quick-start1-new-solution.md#CreateModelMapping).

### <a name="review-the-model-mapping"></a>مراجعة تعيين النموذج

يمكنك عرض نسخة قابلة للتحرير من تعيين النموذج المكون على صفحة **مصمم تعيين النموذج**.

![هيكل تعيين نموذج التقارير الإلكترونية في صفحة مصمم تعيين النموذج.](./media/er-design-zpl-labels-mapping.png)

## <a name="design-a-format"></a>تصميم تنسيق

كمستخدم في دور المستشار الوظيفي للتقارير الإلكترونية، يجب عليك إنشاء تكوين تقارير إلكترونية جديد يحتوي على مكون [التنسيق](er-overview-components.md#format-component). لتكوين هذا المكون، سوف تستخدم كود ZPL II لتحديد تخطيط ملصق موقع المستودع الخاص بك.

### <a name="import-a-format-configuration"></a>استيراد تكوين تنسيق

اتبع هذه الخطوات لاستيراد التنسيق المطلوب من ملف XML الذي توفره Microsoft. بدلاً من ذلك، يمكنك إنشاء التنسيق الخاص بك كما هو موضح في القسم التالي.

1. قم بتنزيل الملف [Warehouse location labels.version.1.1.xml](https://download.microsoft.com/download/5/7/5/5758b551-69a5-45bd-a2b2-21c3db73a6fc/Warehouse-location-labels.version.1.1.xml) واحفظه في جهاز الكمبيوتر المحلي.
2. انتقل إلى **إدارة المؤسسة** \> **مساحات العمل** \> **التقارير الإلكترونية**.
3. في مساحة عمل **إعداد التقارير الإلكترونية**، حدد **تكوينات إعداد التقارير**.
4. في صفحة **التكوينات**، في جزء الإجراءات، حدد **Exchange** \> **تحميل من ملف XML**.
5. حدد **استعراض** ثم ابحث عن الملف **Warehouse location labels.version.1.1.xml** وحدده.
6. حدد **موافق** لاستيراد التكوين.

![تكوين تنسيق التقارير الإلكترونية الذي تم استيراده في صفحة التكوينات.](./media/er-design-zpl-labels-imported-format.png)

### <a name="create-a-format-configuration"></a>إنشاء تكوين التنسيق

بدلاً من استيراد ملف التنسيق المقدم من Microsoft، يمكنك إنشاء تنسيق من البداية. للحصول على مثال يوضح كيفية إكمال هذه المهمة، راجع [إنشاء تكوين تنسيق جديد](er-quick-start1-new-solution.md#FormatCreate).

### <a name="review-the-format"></a>مراجعة التنسيق

يمكنك عرض نسخة قابلة للتحرير من التنسيق الذي تم تكوينه في صفحة **مصمم التنسيق**.

![هيكل تنسيق التقارير الإلكترونية في صفحة مصمم التنسيق.](./media/er-design-zpl-labels-format.png)

تم تكوين مصدر بيانات `model.Location.Label` لهذا التنسيق لإنشاء تسميات تحتوي على المعلومات التالية:

- عنوان المستودع كنص
- عنوان المستودع كرمز شريطي
- عنوان الموقع
- أرقام الفحص

في صفحة **مصمم المعادلة** لمصدر البيانات، تتضمن صيغة التقارير الإلكترونية المستخدمة لإنشاء تسميات تتضمن وظيفة `CONCATENATE` التي تجمع المعلومات في التخطيط المطلوب.

![معادلة لمصدر البيانات في صفحة مصمم الصيغة.](./media/er-design-zpl-labels-review-formula.png)

> [!TIP]
> تم تصميم تخطيط الملصق بحيث تتم محاذاة عنوان الموقع وأرقام التحقق في وسط الملصق. ومع ذلك، لا يدعم ZPL II المحاذاة المركزية للرموز الشريطية. لذلك، يتم استخدام صيغة مصدر بيانات `model.Location.Warehouse.Alignment` لمحاذاة الرمز الشريطي في وسط الملصق. تحسب هذه الصيغة الإزاحة اليسرى للرمز الشريطي، بناءً على عدد الأحرف في عنوان المستودع.

## <a name="prepare-your-environment-for-previewing-generated-labels"></a>جهز بيئتك لمعاينة التسميات المُنشأة

يستخدم المثال التالي تطبيق محاكي الطابعة لملصقات ZPL لإظهار معاينة للملصقات التي تم إنشاؤها على الشاشة. اتبع هذه الخطوات لتمكين هذا الخيار.

1. أضف واجهة التقارير الإلكترونية لـ [الطابعة](er-destination-type-print.md) لتنسيق التقارير الإلكترونية **تسمية موقع المستودع**، وقم بتكوينها لإرسال التسميات المنشأة من Finance إلى [مندوب توجيه المستندات (DRA)](install-document-routing-agent.md).
2. قم بتثبيت وتكوين DRA لتوجيه الملصقات التي تم إنشاؤها من Finance إلى طابعة محلية يمكن الوصول إليها من محطة العمل الحالية.
3. أضف طابعة محلية لمحطة العمل الحالية، وقم بتكوينها لتمرير الملصقات التي تم إنشاؤها من DRA إلى تطبيق محاكي الطابعة.
4. قم بتثبيت تطبيق محاكي الطابعة باعتباره امتدادًا لمتصفح الويب Chrome، وقم بتكوينه لتمرير الملصقات التي تم إنشاؤها من طابعة محلية إلى خدمة ويب ستعرض الملصقات التي تم إنشاؤها وإعادتها إلى محاكي الطابعة للمعاينة.

<table>
<tbody>
<tr align="center">
<td>
<p>Finance</p>
<p>تقرير ER</p>
<p>وجهة الطابعة</p>
</td>
<td><img src="./media/er-design-zpl-labels-flow1.png" alt="Data flow direction: from Finance to the DRA."></td>
<td>مندوب توجيه المستندات</td>
<td><img src="./media/er-design-zpl-labels-flow1.png" alt="Data flow direction: from the DRA to a local printer."></td>
<td>طابعة محلية</td>
<td><img src="./media/er-design-zpl-labels-flow1.png" alt="Data flow direction: from a local printer to a printer emulator."></td>
<td>محاكي الطابعة</td>
<td><img src="./media/er-design-zpl-labels-flow2.png" alt="Data flow direction: from a printer emulator to a rendering web service and then back to the printer emulator."></td>
<td>عرض خدمة الويب</td>
</td>
</tr>
</tbody>
</table>

### <a name="install-and-configure-a-printer-emulator-application"></a>تثبيت وتكوين تطبيق محاكي الطابعة

أضف تطبيق محاكي الطابعة لمحرك التقديم ZPL إلى متصفح الويب Chrome. يستخدم هذا المثال محاكي [طابعة Zpl](https://chrome.google.com/webstore/detail/zpl-printer/phoidlklenidapnijkabnfdgmadlcmjo) المستند إلى [خدمة ويب Labelary ZPL](http://labelary.com/service.html). سيقوم تطبيق محاكي الطابعة بتمرير الملصقات التي تم إنشاؤها بتنسيق ZPL من طابعة محلية إلى خدمة الويب ثم إرجاع الملصقات كملفات PDF أو PNG للمعاينة.

1. في متجر ويب Chrome، ابحث عن تطبيق محاكي الطابعة الذي تريد استخدامه وحدده. بعد ذلك، حدد **إضافة إلى Chrome** لإضافته إلى مستعرض ويب Chrome.

    ![إضافة تطبيق محاكي الطابعة إلى متصفح الويب Chrome من متجر ويب Chrome.](./media/er-design-zpl-labels-add-app.png)

2. حدد **تشغيل التطبيق** لتشغيل تطبيق محاكي الطابعة من متصفح ويب Chrome.

    ![تشغيل تطبيق محاكي الطابعة من متصفح ويب Chrome.](./media/er-design-zpl-labels-run-app.png)

3. تكوين تطبيق التشغيل:

    1. قم بإيقاف تشغيل التطبيق.
    2. في إعدادات الطابعة، قم بتعيين المضيف إلى **127.0.0.1**.
    3. قم بتعيين المنفذ إلى **9100**.

        ![تكوين تطبيق محاكي الطابعة.](./media/er-design-zpl-labels-configure-app.png)

    4. أعد تشغيل التطبيق. يجب أن تتلقى رسالة تنص على بدء تشغيل الطابعة على المضيف والمنفذ المحددين.

        ![تم تشغيل تطبيق محاكي الطابعة مرة أخرى.](./media/er-design-zpl-labels-turn-on-app.png)

> [!NOTE]
> نظرًا لأن تطبيق محاكي الطابعة المستخدم في هذا المثال يعتمد على خدمة ويب لتقديم الملصقات، تأكد من أن إعدادات الأمان الخاصة بك تسمح لك بالاتصال بالخدمة. بخلاف ذلك، لن يتلقى التطبيق التسميات المعروضة، ولن تتوفر معاينة لهذه التسميات.

### <a name="add-and-configure-a-local-printer"></a>إضافة طابعة محلية وتكوينها

[أضف طابعة محلية جديدة](https://support.microsoft.com/windows/install-a-printer-in-windows-10-cc0724cf-793e-3542-d1ff-727e4978638b) التي يمكن للجهاز الحالي استخدامها لتمرير الملصقات التي تم إنشاؤها من DRA إلى تطبيق محاكي الطابعة.

1. في Windows، حدد **تشغيل** \> **الإعدادات** \> **الأجهزة** \> **الطابعات \& الطابعات الضوئية**.
2. حدد **إعدادات الطابعات \& الماسحات الضوئية**.
3. من أجل **إضافة طابعة أو ماسح ضوئي**، حدد **إضافة الجهاز**.
4. بالنسبة إلى **الطابعة التي أريدها وغير المدرجة**، حدد **إضافة يدويًا**.
5. في حقل **البحث عن طابعة بواسطة الخيارات الأخرى**، حدد **إضافة طابعة محلية أو طابعة شبكة بإعدادات يدوية**.
6. في حقل **اختيار منفذ طابعة**، حدد **إنشاء منفذ جديد**، ثم اتبع الخطوات التالية:

    1. في حقل **نوع المنفذ**، حدد **منفذ TCP/IP القياسي**.
    2. في حقل **اسم المضيف أو عنوان IP**، أدخل **127.0.0.1**.
    3. في حقل **اسم المنفذ**، أدخل **ZPL**.
    4. انتظر حتى تكتمل عملية **الكشف عن منفذ TCP/IP**.
    5. في حقل **نوع الجهاز**، حدد **مخصص**، ثم حدد **الإعدادات**.
    6. تأكد من تحديد إعدادات المنفذ التالية:

        - **اسم المنفذ:** ZPL
        - **اسم الطابعة أو عنوان IP:** 127.0.0.1
        - **البروتوكول:** أولي
        - **رقم المنفذ:** 9100

7. في حقل **تثبيت برنامج تشغيل الطابعة**، حدد **عام/النص فقط**.
8. في حقل **اسم الطابعة**، أدخل **ZebraPrinter**.

![إضافة طابعة محلية للجهاز الحالي.](./media/er-design-zpl-labels-configure-printer.png)

### <a name="install-and-configure-the-dra"></a>تثبيت DRA وتكوينه

قم بإعداد DRA لتمرير الملصقات التي تم إنشاؤها من Finance إلى الطابعة المحلية المكونة.

1. [تثبيت DRA](install-document-routing-agent.md#install-the-document-routing-agent).
2. [تكوين DRA](install-document-routing-agent.md#configure-the-document-routing-agent).
3. [قم بتسجيل الطابعة المحلية](install-document-routing-agent.md#register-network-printers) في DRA.
4. [قم بتنشيط الطابعة المحلية](install-document-routing-agent.md#administer-network-printers) في بيئة Finance الخاصة بك.

![إعداد DRA لطباعة الملصقات التي تم إنشاؤها.](./media/er-design-zpl-labels-configure-dra.png)

### <a name="configure-the-er-destination"></a>تكوين وجهة التقارير الإلكترونية

قم بإعداد وجهة التقارير الإلكترونية لتمرير الملصقات التي تم إنشاؤها من Finance إلى DRA.

1. انتقل إلى **إدارة المؤسسة** \> **التقارير الإلكترونية** \> **وجهة إعداد التقارير الإلكترونية**.
2. في صفحة **وجهة التقارير الإلكترونية**، في جزء الإجراءات، حدد **جديد**.
3. في حقل **المرجع**، حدد **تسميات موقع المستودع**.
4. على علامة التبويب السريعة **وجهة الملف**، حدد **جديد‏‎**.
5. في حقل **الاسم**، أدخل **التسميات**.
6. في حقل **اسم مكون الملف**، حدد **تقرير**.
7. حدد **الإعدادات**.
8. في مربع الحوار **إعدادات الوجهة**، في علامة التبويب **البريد الإلكتروني**، قم بتعيين خيار **ممكن** إلى **نعم**.
9. في حقل **اسم الطابعة**، حدد **ZebraPrinter**.
10. في حقل **نوع توجيه المستندات**، حدد **ZPL**.
11. حدد **موافق**.

![تكوين وجهة التقارير الإلكترونية لتنسيق تسميات موقع المستودع على صفحة وجهة التقارير الإلكترونية.](./media/er-design-zpl-labels-configure-destination.png)

## <a name="review-warehouse-locations"></a>مراجعة مواقع المستودع

1. انتقل إلى **إدارة المستودعات** \> **الإعداد** \> **المستودع** \> **المواقع**.
2. في صفحة **المواقع**، قم بالتصفية لعرض المواقع التي لها قيمة في حقل **تدقيق الأرقام**.

![مراجعة مواقع المستودعات في صفحة المواقع.](./media/er-design-zpl-labels-review-locations.png)

## <a name="print-warehouse-location-labels"></a>طباعة ملصقات موقع المستودع

1. انتقل إلى **إدارة المؤسسة** \> **التقارير الإلكترونية** \> **التكوينات**.
2. في الصفحة **تكوينات**، في شجرة التكوين، قم بتوسيع **نموذج المستودع**، وحدد **تسميات موقع المستودع**.
3. في جزء الإجراءات، حدد **تشغيل**.
4. في مربع حوار **معلمات التقارير الإلكترونية**، في علامة التبويب **السجلات المطلوب تضمينها**، حدد **عامل التصفية**.
5. في علامة التبويب **النطاق**، ابحث عن الصف الذي تم فيه تعيين حقل **الجدول** إلى **المواقع** وحقل **الحقل** إلى **الموقع**. في حقل **المعايير**، أدخل **LPEnabled**.
6. حدد **موافق**.
7. حدد **موافق**. يتم إنشاء التسمية وعرضها في صفحه المعاينة في تطبيق محاكي الطابعة.

![مراجعة التسمية التي تم إنشاؤها في صفحة المعاينة لتطبيق محاكي طابعة Zpl.](./media/er-design-zpl-labels-preview-label.png)

## <a name="modify-the-layout-of-a-label"></a>تعديل تخطيط التسمية

يمكنك تغيير التخطيط الحالي لملصقات موقع المستودع الخاص بك. يوضح المثال التالي كيفية تغيير التخطيط بحيث تتضمن التسميات المُنشأة معرف ملف تعريف الموقع.

1. انتقل إلى **إدارة المؤسسة** \> **التقارير الإلكترونية** \> **التكوينات**.
2. قم بتعيين **استخدام الوجهات للحالة مسودة** [معلمة مستخدم التقارير الإلكترونية](electronic-reporting-destinations.md#applicability) إلى **نعم**.
3. في الصفحة **تكوينات**، في شجرة التكوين، قم بتوسيع **نموذج المستودع**، وحدد **تسميات موقع المستودع**.
4. حدد **المصمم**.
5. في صفحة **مصمم التنسيق**، في علامة التبويب **تعيين**، حدد مصدر بيانات `model.Location.Label`.
6. في مربع حوار **خصائص مصدر البيانات**، حدد **تحرير** \> **تحرير الصيغة**.
7. في صفحة **مصمم الصيغة**، في حقل **الصيغة**، راجع صيغة التقارير الإلكترونية المستخدمة لإنشاء التسميات.

    ```vb
    CONCATENATE(
    "^XA",CrLf,
    "^CF0,30,30^FO0,30^FB800,1,0,C,0^FD",Warehouse,"\&^FS",CrLf,
    "^BY2,2,50^FT",@.Warehouse.Alignment,",126^BCN,,N,N,N,A^FD",Warehouse,"\&^FS",CrLf,
    "^FO0,150^FB800,1,0,C,0^FD",@.Name,"\&^FS",CrLf,
    "^CF0,20,20^FO0,200^FB800,1,0,C,0^FD",@.CheckDigits,"\&^FS",CrLf,
    "^XZ")
    ```

8. قم بتحديث الصيغة لإضافة معرف ملف تعريف الموقع إلى التسميات التي تم إنشاؤها.

    ```vb
    CONCATENATE(
    "^XA",CrLf,
    "^CF0,30,30^FO0,30^FB800,1,0,C,0^FD",Warehouse,"\&^FS",CrLf,
    "^BY2,2,50^FT",@.Warehouse.Alignment,",126^BCN,,N,N,N,A^FD",Warehouse,"\&^FS",CrLf,
    "^FO0,150^FB800,1,0,C,0^FD",@.Name,"\&^FS",CrLf,
    "^CF0,20,20^FO0,200^FB800,1,0,C,0^FD",@.CheckDigits,"\&^FS",CrLf,
    "^CF0,40,40^FO0,240^FB800,1,0,C,0^FD",@.ProfileID,"\&^FS",CrLf,
    "^XZ")
    ```

9. حدد **حفظ**.
10. حدد **موافق**.
11. في جزء الإجراءات، حدد **تشغيل**.
12. في مربع حوار **معلمات التقارير الإلكترونية**، في علامة التبويب **السجلات المطلوب تضمينها**، حدد **عامل التصفية**.
13. في علامة التبويب **النطاق**، ابحث عن الصف الذي تم فيه تعيين حقل **الجدول** إلى **المواقع** وحقل **الحقل** إلى **الموقع**. في حقل **المعايير**، أدخل **دفع**.
14. حدد **موافق**.
15. حدد **موافق**. يتم إنشاء التسمية وعرضها في صفحه المعاينة في تطبيق محاكي الطابعة.

![مراجعة التسمية التي تم إنشاؤها والتي تتضمن معرف ملف تعريف الموقع على صفحة المعاينة لتطبيق محاكي طابعة Zpl.](./media/er-design-zpl-labels-preview-label2.png)

## <a name="encoding"></a>ترميز

> [!NOTE]
> يجب عليك مزامنة إعداد الترميز لمكون **الملف\\العام** لتنسيق التقارير الإلكترونية القابل للتحرير والإعداد المناسب للتسمية المصممة. يجب ألا تتعارض قيمة حقل **[الترميز](er-suppress-bom-characters.md)** في مكون **الملف\\العام** مع أمر ZPL المستخدم للتحكم في ترميز التسمية (على سبيل المثال، أمر `^CI`). لا تتحقق التقارير الإلكترونية من مزامنة هذه الإعدادات.

## <a name="additional-resources"></a>الموارد الإضافية

[وجهة الطابعة](er-destination-type-print.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]