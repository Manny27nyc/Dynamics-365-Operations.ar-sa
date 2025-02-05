---
title: تنظيم مكونات التقرير في مصمم التقارير
description: تشرح هذه المقالة كيفية تنظيم التقارير وكتل الإنشاء والكائنات الموجودة في مصمم التقارير.
author: aprilolson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: twheeloc
ms.custom: 59161
ms.assetid: 32e728c5-3b06-4049-8070-ade01e951d49
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: a6abad01232d05e94321d0d568d2e801d92875ae
ms.sourcegitcommit: 6b209919de39c15e0ebe4abc9cbcd30618f2af0b
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/11/2022
ms.locfileid: "9135868"
---
# <a name="organize-report-components-in-report-designer"></a>تنظيم مكونات التقرير في مصمم التقارير

[!include [banner](../includes/banner.md)]

بعد أن تنتهي من تصميم كتل الإنشاء والتقارير التي تم إنشاؤها، من المستحسن تنظيم هذه الكائنات لتمكين المستخدمين من تحديد موقعها بسهولة. تشرح هذه المقالة كيفية تنظيم التقارير وكتل الإنشاء والكائنات الموجودة في مصمم التقارير.

يمكنك إعادة تسمية المجلدات والتقارير وكتل الإنشاء والكائنات الأخرى في مصمم التقارير لمساعدتك في تنظيم ملفاتك. واستنادًا إلى نوع الكائن الذي قمت بإعادة تسميته، فقد تحتاج إلى تحديث الاقترانات مع ذلك الكائن.

## <a name="rename-a-folder-or-building-block-in-report-designer"></a>إعادة تسمية مجلد أو كتلة إنشاء في مصمم تقرير
باستخدام مصمم التقارير، يمكنك إعادة تسمية المجلدات وتعريفات كل من التقارير والصفوف والأعمدة وشجرة التقارير.

### <a name="rename-a-folder-or-building-block-in-report-designer"></a>إعادة تسمية مجلد أو كتلة إنشاء في مصمم التقارير

1. في مصمم التقارير، استخدم جزء التنقل لتحديد المجلد أو العنصر المطلوب إعادة تسميته.
2. انقر نقراً مزدوجاً فوق المجلد أو الكائن، ثم انقر **إعادة تسمية**. يصبح حقل **الاسم** في جزء التنقل متوفرًا.
3. اكتب اسماً جديداً، ثم اضغط على Enter.
4. إذا كانت كتلة الإنشاء عبارة عن تعريف صف أو تعريف عمود أو تعريف شجرة تقارير، فيجب عليك تحديث كتل الإنشاء الأخرى المقترنة بها. انقر بزر الماوس الأيمن فوق كتلة الإنشاء التي قمت بإعادة تسميتها في الخطوة 3، وحدد **اقترانات**، ثم حدد صنفًا في القائمة لتحديثه.
5. كرر الخطوة 4 حتى يتم تحديث كافة الأصناف المقترنة.

## <a name="create-and-manage-report-groups"></a>إنشاء مجموعات التقارير وإدارتها
يمكنك تجميع تعريفات التقارير لإنشاء تقارير متعددة في نفس الوقت. لإنشاء مجموعات تقارير وتعديلها وحذفها وتوليدها، يجب أن يكون لديك دور المصمم أو المسؤول. باستطاعة المستخدمين الذين لديهم دور المنشئ إنشاء وعرض مجموعات التقارير، ويمكنهم أيضًا تعديل إعداد تعريفات تقارير المستخدمين لمجموعات التقارير.

### <a name="create-a-report-group"></a>إنشاء مجموعة تقارير

1. في مصمم التقارير، في جزء التنقل، انقر فوق **مجموعات التقارير**.
2. في قائمة **ملف**، انقر فوق **جديد** &gt; **تعريف مجموعة التقارير** لفتح مجموعة تقارير جديدة في نافذة العارض. بدلاً من ذلك، انقر فوق زر **مجموعة التقارير** ![مجموعة التقارير.](media/report-group.gif "مجموعة التقارير") على شريط الأدوات.
3. انقر فوق علامة تبويب **مجموعة التقارير‬**. ولتجاوز المعلومات الواردة في تعريفات التقارير الفردية من أجل إنشاء هذا التقرير، حدد خانة الاختيار **تجاوز إعدادات التاريخ والتفاصيل والشركة من تعريفات التقارير الفردية**. يتم إدخال معلومات حول اسم الشركة ومستوى التفاصيل والإعداد المؤقت والتاريخ بشكل تلقائي، ولكن يمكنك إجراء التحديثات.
4. لإنشاء تقارير متعددة تعرض عملات التقارير، حدد خانة الاختيار **تضمين كافة عملات التقارير**. يمكنك عندئذٍ الوصول إلى طرق عرض متعددة بالنقر فوق الزر **العملة** في عارض الويب عند عرض التقرير.
5. في حقل **التقارير في مجموعة**، انقر فوق **إضافة** لتحديد التقارير المراد تضمينها في مجموعة التقارير. ولتحديد عدة تقارير في مربع الحوار **إضافة**، اضغط مع الاستمرار على مفتاح Ctrl أثناء تحديد التقارير. عند الانتهاء من تحديد التقارير، انقر فوق **موافق**.
6. انقر فوق **ملف** &gt; **حفظ** لحفظ مجموعة التقارير الجديدة.

### <a name="modify-a-report-group"></a>تعديل مجموعة تقارير

1. في مصمم التقارير، في جزء التنقل، انقر فوق **مجموعات التقارير**.
2. انقر نقراً مزدوجاً فوق مجموعة التقارير لتعديلها.
3. على علامة التبويب **مجموعة التقارير**، أدخل التغييرات التي تريدها.
4. في القائمة **ملف**، انقر فوق **حفظ** لحفظ مجموعة التقارير المعدلة، وبدلاً من ذلك، انقر فوق الزر **حفظ** ![حفظ.](media/save.gif "حفظ") على شريط الأدوات.

> [ملاحظة] إذا قمت بجدولة التقارير لإنشائها في فواصل زمنية محددة، فيمكنك تجاوز هذه الإعدادات وإنشاء تقرير فورًا.

### <a name="generate-a-report-group-report"></a>إنشاء تقرير مجموعة تقارير

1. في مصمم التقارير، في جزء التنقل، انقر فوق **مجموعات التقارير**.
2. افتح مجموعة التقارير المراد إنشاؤها.
3. انقر فوق الزر **إنشاء تقرير** ![إنشاء تقرير.](media/generate-report.gif "إنشاء تقرير") لإنشاء التقارير.

### <a name="delete-a-report-group"></a>حذف مجموعة تقارير

1. في مصمم التقارير، في جزء التنقل، انقر فوق **مجموعات التقارير**.
2. انقر بزر الماوس الأيمن فوق مجموعة التقارير التي تريد حذفها، ثم حدد **حذف**.
3. عندما تظهر رسالة تأكيد، انقر فوق **نعم**.

## <a name="report-group-tab-controls"></a>عناصر تحكم علامة تبويب مجموعة التقارير
يصف الجدول التالي عناصر التحكم على علامة التبويب **مجموعة التقارير**.

<table>
<thead>
<tr>
<th>التحكم</th>
<th>الوصف</th>
</tr>
</thead>
<tbody>
<tr>
<td>تجاوز إعدادات التاريخ والتفاصيل والشركة من تعريفات التقارير الفردية</td>
<td>حدد خانة الاختيار هذه لتجاوز تعريفات التقارير الفردية للتقارير الموجودة في مجموعة التقارير هذه لإنشاء هذه التقارير فقط.</td>
</tr>
<tr>
<td>اسم الشركة</td>
<td>تحديد الشركة المراد استخدامها في التقارير.</td>
</tr>
<tr>
<td>مستوى التفاصيل</td>
<td>تحديد مستوى التفاصيل الذي يتضمنه التقرير.
<ul>
<li><strong>المالية</strong>- تقرير ملخص عالي المستوى. لا يمكنك التنقل في الحسابات والأبعاد، باستثناء تلك الحسابات والأبعاد التي تمت إضافتها عبر شجرة تقارير.</li>
<li><strong>المالي والحساب</strong> − تقرير يحتوي على تفاصيل حساب وملخص عالي المستوى.</li>
<li><strong>المالي والحساب والحركة</strong> - تقرير يحتوي على تفاصيل حركة وملخص عالي المستوى.</li>
</ul></td>
</tr>
<tr>
<td>مؤقتة</td>
<td>تحديد أنواع الأنشطة التي يتضمنها التقرير.
<ul>
<li><strong>النشاط المُرّحل فقط</strong> − يتضمن فقط الحركات والأرصدة المرحّلة في بياناتك المالية.</li>
<li><strong>النشاط المُرحّل وغير المُرحّل</strong> − يتضمن كافة الحركات والأرصدة التي يتم إدخالها وترحيلها في بياناتك المالية.</li>
<li><strong>النشاط غير المُرحّل فقط</strong> − يتضمن فقط الحركات والأرصدة التي يتم إدخالها، ولكن لم يتم ترحيلها بعد، في بياناتك المالية.</li>
</ul></td>
</tr>
<tr>
<td>تضمين جميع عملات التقارير</td>
<td>ستكون أي عملات تقارير إضافية تم تكوينها في نظام Microsoft Dynamics ERP مدرجة هنا. حدد خانة الاختيار هذه لإنشاء تقارير إضافية بالعملات المُشار إليها. لعرض هذه التقارير في عارض الويب، انقر فوق زر <strong>العملة</strong> ثم حدد عملة.</td>
</tr>
<tr>
<td>عدم حفظ معلومات التاريخ في تعريف التقرير</td>
<td><ul>
<li>الفترة الأساسية‬</li>
<li>السنة الأساسية‬</li>
<li>الفترة المشمولة</li>
</ul>
يتم حفظ إعدادات الفترة الأساسية الافتراضية فقط في تعريف التقرير.</td>
</tr>
<tr>
<td>حفظ معلومات التاريخ في تعريف التقرير</td>
<td><ul>
<li>تاريخ التقرير</li>
<li>فترة الأساسية الافتراضية</li>
</ul></td>
</tr>
<tr>
<td>التقارير في مجموعة</td>
<td>إضافة وإزالة وإعادة ترتيب التقارير في مجموعة التقارير.
<ul>
<li>لإضافة تعريفات تقارير إلى مجموعة تقارير، انقر نقراً مزدوجاً فوق مجموعة تقارير لفتحها، ثم انقر فوق <strong>إضافة</strong>. حدد التقارير التي تريد تضمينها في مجموعة التقارير، ثم انقر فوق <strong>موافق</strong>.</li>
<li>لإزالة تقرير من مجموعة تقارير، حدده، ثم انقر فوق <strong>إزالة</strong>.</li>
<li>لتعديل الترتيب الذي يتم به إنشاء التقارير، حدد تقريرًا في القائمة، ثم انقر فوق <strong>تحريك لأعلى</strong> أو <strong>تحريك لأسفل</strong>.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>الموارد الإضافية

[Financial reporting](financial-reporting-intro.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
