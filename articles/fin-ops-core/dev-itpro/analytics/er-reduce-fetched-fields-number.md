---
title: تحسين أداء حلول التقارير الإلكترونية‬ عن طريق تقليل عدد حقول الجداول التي يتم إحضارها في وقت التشغيل
description: يشرح هذا الموضوع كيف يمكنك المساعدة في تحسين الأداء‬ عن طريق تقليل عدد حقول الجداول التي يتم إحضارها في وقت التشغيل.
author: NickSelin
ms.date: 05/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: dd192a7718ac4fd8bcb636ede6c005ca29ee5f08
ms.sourcegitcommit: 336a0ad772fb55d52b4dcf2fafaa853632373820
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/28/2022
ms.locfileid: "8811947"
---
# <a name="improve-performance-of-er-solutions-by-reducing-the-number-of-table-fields-that-are-fetched-at-runtime"></a>تحسين أداء حلول التقارير الإلكترونية‬ عن طريق تقليل عدد حقول الجداول التي يتم إحضارها في وقت التشغيل

[!include[banner](../includes/banner.md)]

يمكنك تصميم [تنسيقات](general-electronic-reporting.md) [التقارير الإلكترونية](er-overview-components.md#format-components-for-outgoing-electronic-documents) التي تنشئ مستندات صادرة بتنسيقات متعددة. عندما يتم إنشاء مستند، يستدعي تنسيق التقارير الإلكترونية مصادر البيانات التي تم تكوينها في [تعيين نموذج](er-overview-components.md#model-mapping-component) التقارير الإلكترونية المقابل. لتكوين الوصول إلى جداول التطبيق أو الاستعلامات أو الكيانات لاسترداد السجلات، يمكنك استخدام مصادر بيانات التقارير الإلكترونية من النوع *سجلات الجدول*. بشكل افتراضي، يقوم مصدر بيانات من النوع *سجلات الجدول* باسترداد قيم كافة الحقول في السجلات المطلوبة. ومع ذلك، يمكنك تكوين هذا النوع من مصادر البيانات بحيث يُحضر فقط قيم الحقول المطلوبة لتنسيق التقارير الإلكترونية قيد التشغيل. يساعد هذا التكوين في تقليل استهلاك الذاكرة لخادم التطبيق الذي يقوم باسترجاع البيانات والمزيد من التخزين المؤقت للسجلات.

لمعرفة المزيد حول كيفية تقييد قائمة الحقول التي تم إحضارها لمصادر البيانات من النوع *سجلات الجدول*، أكمل المثال في هذا الموضوع.

## <a name="example-reduce-the-number-of-table-fields-that-are-fetched-at-runtime"></a>مثال: تقليل عدد حقول الجدول التي يتم إحضارها في وقت التشغيل

توضح الإجراءات التالية كيف يمكن لمستخدم لديه دور مسؤول النظام أو مطور التقارير الإلكترونية تكوين تعيين نموذج التقارير الإلكترونية بحيث يُحضر فقط الحقول المطلوبة لتشغيل تنسيق التقارير الإلكترونية، للمساعدة في تقليل استهلاك ذاكرة خادم التطبيق.

يمكن إكمال جميع هذه الإجراءات في شركة **USMF** في Microsoft Dynamics 365 Finance. الترميز غير مطلوب.

لإكمال هذا المثال، يجب أن يكون لديك حق الوصول إلى شركة **USMF** لأحد الأدوار التالية:

- مستشار وظيفي لإعداد التقارير الإلكتروني
- مسؤول النظام

في هذا المثال، ستستخدم [تكوينات](general-electronic-reporting.md#Configuration) التقارير الإلكترونية التي تم توفيرها للشركة النموذجية **Litware, Inc.**. تأكد من أن موفر التكوين للشركة النموذجية **Litware, Inc.** (`http://www.litware.com`) تم إدراجه لإطار عمل إعداد التقارير الإلكترونية، وتم تمييزه على أنه **نشط**. في حالة عدم إدراج موفر التكوين، أو عدم وضع علامة عليه كـ **نشط**، اتبع الخطوات الموجودة في [إنشاء موفر تكوين ووضع علامة عليه على أنه نشط.](tasks/er-configuration-provider-mark-it-active-2016-11.md).

### <a name="configure-the-er-framework"></a>تكوين إطار عمل ER

اتبع الخطوات في [تكوين إطار عمل التقارير الإلكترونية](er-quick-start2-customize-report.md#ConfigureFramework) لإعداد الحد الأدنى لمجموعة معلمات التقارير الإلكترونية. يجب عليك إكمال هذا الإعداد قبل بدء استخدام إطار عمل التقارير الإلكترونية لتعديل مصادر البيانات لحل التقارير الإلكترونية المتوفر.

### <a name="import-the-sample-er-configurations"></a>استيراد نموذج تكوينات إعداد التقارير الإلكترونية.

إذا لم تكن قد أكملت بعد المثال في الموضوع [تصميم حل جديد للتقارير الإلكترونية لطباعة تقرير مخصص‬](er-quick-start1-new-solution.md)، فعليك تنزيل ملفات XML وتخزينها محليًا للتكوينات التالية لحل التقارير الإلكترونية المتوفر.

| وصف المحتوى            | اسم الملف |
|--------------------------------|-----------|
| تكوين نموذج بيانات التقارير الإلكترونية    | [Questionnaires model.version.1.xml](https://download.microsoft.com/download/b/6/3/b633bd34-d200-4422-96d9-8f62eb5218f8/Questionnaires_model.version.1.xml) |
| تكوين تعيين نموذج إعداد التقارير الإلكترونية | [Questionnaires mapping.version.1.1.xml](https://download.microsoft.com/download/7/b/2/7b258e4e-4bd5-46a4-8114-27419ae4acd8/Questionnaires_mapping.version.1.1.xml) |
| تنسيق تكوين ER        | [Questionnaires format.version.1.1.xml](https://download.microsoft.com/download/1/b/a/1ba39ec2-257a-44d8-972f-25bf7d18fb41/Questionnaires_format.version.1.1.xml) |

ثم اتبع الخطوات التالية لتحميل تكوينات حل التقارير الإلكترونية المتوفرة إلى المثيل المالي.

1. انتقل إلى **إدارة المؤسسة** \> **مساحات العمل** \> **التقارير الإلكترونية**.
2. حدد **تكوينات إعداد التقارير‬**.
3. في صفحة **التكوينات**، استورد نموذج بيانات التقارير الإلكترونية.

    1. حدد **استبدال**، ثم حدد **تحميل من ملف XML**.
    2. حدد **استعراض‏‎**، وابحث عن الملف **Questionnaires model.version.1.xml** وحدده، ثم حدد **موافق**.

4. استورد تكوين تعيين نموذج التقارير الإلكترونية.

    1. حدد **استبدال**، ثم حدد **تحميل من ملف XML**.
    2. حدد **استعراض**، وابحث عن الملف **Questionnaires mapping.1.1.xml** وحدده، ثم حدد **موافق**.

5. استورد تكوين تنسيق التقارير الإلكترونية.

    1. حدد **استبدال**، ثم حدد **تحميل من ملف XML**.
    2. حدد **استعراض**، وابحث عن الملف **Questionnaires format.1.1.xml** وحدده، ثم حدد **موافق**.

6. في شجرة التكوين، قم بتوسيع **نموذج الاستبيانات‬**.
7. راجع قائمة تكوينات إعداد التقارير الإلكترونية المستوردة في شجرة التكوين.

    ![مراجعة قائمة تكوينات التقارير الإلكترونية المستوردة على صفحة التكوينات.](./media/er-reduce-fetched-fields-number-configurations.png)

### <a name="review-the-provided-er-model-mapping"></a>مراجعة تعيين نموذج التقارير الإلكترونية المتوفر

1. في صفحة **التكوينات**، حدد **تعيين الاستبيانات**.
2. في جزء الإجراءات، حدد **المصمم**.
3. في صفحة **تعيين النموذج إلى مصدر البيانات**، حدد **المصمم**.
4. في صفحة **مصمم تعيين النموذج**، في جزء الإجراءات، حدد **طريقة عرض المجموعة** لتشغيل طريقة عرض **المجموعة‏‎**.
5. في جزء **نموذج البيانات** ، وسّع **الاستبيان‏‎** .

    تم تكوين مصدر بيانات **الاستبيان‏‎** للوصول إلى جدول تطبق `KMCollection`.

6. في جزء **مصادر البيانات**، وسّع **سجلات الجدول** \> **الاستبيان** \> **الحقول**.

    لاحظ عدد الحقول من جدول التطبيق `KMCollection` التي تم عرضها بواسطة مصدر بيانات **الاستبيان** من النوع *سجلات الجدول*.

    ![مراجعة تعيين النموذج المقدم في صفحة "مصمم تعيين النموذج" عند تشغيل "طريقة عرض المجموعة".](./media/er-reduce-fetched-fields-number-mapping1.png)

7. في جزء الإجراءات، حدد **طريقة عرض المجموعة** مرة أخر لإيقاف تشغيل طريقة عرض **المجموعة‏‎**، ثم حدد **إظهار الكل** \> **إظهار العناصر المعينة فقط‬**.

    يتم استخدام عدد قليل من الحقول الموجودة في جدول تطبيق `KMCollection` لملء قائمة سجلات **الاستبيان** في نموذج بيانات التقارير الإلكترونية.

    - `Active`
    - `Description`
    - `questionMode`
    - `kmCollectionId`

    ![مراجعة تعيين النموذج المقدم في صفحة "مصمم تعيين النموذج" عند إيقاف تشغيل "طريقة عرض المجموعة".](./media/er-reduce-fetched-fields-number-mapping2.png)

### <a name="turn-on-the-er-performance-trace"></a>تشغيل تتبع أداء التقارير الإلكترونية

اتبع الخطوات المذكورة في [تشغيل تتبع أداء التقارير الإلكترونية‬](trace-execution-er-troubleshoot-perf.md#turn-on-the-er-performance-trace) لتعيين معلمات مستخدم التقارير الإلكترونية لتمكين تنفيذ مكونات التقارير الإلكترونية التي سيتم تتبعها.

### <a name="run-the-provided-er-format-by-using-the-provided-model-mapping"></a>تشغيل تنسيق التقارير الإلكترونية المتوفر باستخدام تعيين النموذج المتوفر

اتبع الخطوات في [تشغيل تنسيق مصمّم من التقارير الإلكترونية](er-quick-start1-new-solution.md#RunFormatFromER) لتشغيل تنسيق التقارير الإلكترونية المتوفر لاستبيان واحد من صفحة **التكوينات**.

### <a name="review-the-execution-trace-of-the-first-run"></a>مراجعة تتبع التنفيذ في التشغيل الأول

1. انتقل إلى **إدارة المؤسسة** \> **التقارير الإلكترونية \> التكوينات‏‎**.
2. في صفحة **التكوينات‏‎**، وسّع **نموذج الاستبيانات‏‎**، وحدد **تعيين الاستبيانات**.

    > [!NOTE]
    > تشير تفاصيل علامة التبويب السريعة **الإصدارات** إلى أنك حددت إصدار المسودة من تكوين **تعيين الاستبيانات**. وبالتالي، يمكنك تعديل محتوي تعيين النموذج هذا.

3. في جزء الإجراءات، حدد **المصمم**.
4. في صفحة **تعيين النموذج إلى مصدر البيانات**، حدد **المصمم**.
5. في صفحة **مصمم تعيين النموذج**، في جزء الإجراءات، حدد **تتبع الأداء**.
6. في مربع الحوار **إعدادات نتائج تتبع الأداء**‬، حدد التتبع الذي تم إنشاؤه اثناء تشغيل التنسيق الأخير.

    ![تحديد التتبع في مربع الحوار إعدادات نتائج تتبع الأداء.](./media/er-reduce-fetched-fields-number-select-trace-1.png)

7. حدد **موافق**. 
8. على علامة التبويب السريعة **التفاصيل**، قم بتصفية مسار **الاستبيان** الذي يشير إلى مصدر بيانات **الاستبيان**.
9. مراجعة تفاصيل استعلام قاعدة البيانات الذي تم إنشاؤه عندما تم استدعاء مصدر بيانات **الاستبيان** .

    تم إحضار جميع حقول جدول التطبيق `KMCollection` في وقت التشغيل عندما تم استدعاء مصدر بيانات **الاستبيان**.

    ![مراجعة تفاصيل استعلام قاعدة البيانات في صفحة مصمم تعيين النموذج.](./media/er-reduce-fetched-fields-number-query1.png)

### <a name="modify-the-provided-er-model-mapping"></a>تعديل تعيين نموذج التقارير الإلكترونية المتوفر

1. في صفحة **مصمم تعيين النموذج**، في جزء **مصادر البيانات**، حدد مصدر بيانات **الاستبيان**.
2. في جزء **مصادر البيانات**، حدد **تحرير‏‎** .
3. في مربع الحوار **خصائص مصدر البيانات**، حدد **تحديد الحقول** لتحديد قائمة الحقول الخاصة بجدول تطبيق `KMCollection` المشار إليها والتي سيتم إحضارها في وقت التشغيل عند استدعاء مصدر بيانات **الاستبيان** القابل للتحرير .

    ![تحديد الخيار "تحديد الحقول" في مربع الحوار "خصائص مصدر البيانات" لبدء تكوين قائمة الحقول التي سيتم إحضارها من جدول التطبيق باستخدام مصدر البيانات القابل للتحرير .](./media/er-reduce-fetched-fields-number-select-fields1.png)

4. في الصفحة **تحديد الحقول**، حدد **تعبئة تلقائية**.

    تتم تعبئة قائمة **الحقول المحددة** تلقائيًا، بالاستناد إلى البيانات الاصطناعية الخاصة بنموذج التعيين والتي تم تكوينها بشكل مسبق. تُضاف كافة حقول وعلاقات الجدول المشاري إليها المذكورة في أي ربط أو صيغة أو مصدر بيانات لتعيين النموذج إلى القائمة.

    ![تكوين قائمة الحقول التي سيتم إحضارها من جدول التطبيق في الصفحة "تحديد الحقول"](./media/er-reduce-fetched-fields-number-select-fields2.png)

5. حدد **حفظ**، ثم أغلق صفحة **تحديد الحقول**.
6. حدد **موافق** لتخزين التغييرات التي أجريتها على إعدادات مصدر البيانات.
7. في جزء الإجراءات، حدد **إظهار الكل**.

    يعرض مصدر بيانات **الاستبيان** الآن النص **\<Fields are filtered\>**. يشير هذا النص إلى أنه تم تكوين مصدر البيانات لإحضار عدد محدود من الحقول من جدول التطبيق المشار إليه.

    ![مراجعة تعيين النموذج المحدّث الفاتورة في صفحة مصمم تعيين النموذج.](./media/er-reduce-fetched-fields-number-mapping3.png)

8. حدد **حفظ** لتخزين التغييرات التي أجريتها في تعيين النموذج القابل للتحرير.

    > [!NOTE]
    > في وقت التشغيل، تحلل التقارير الإلكترونية العلاقات المضافة وتضيف جميع الحقول المستخدمة فيها إلى استعلام قاعدة البيانات، حتى إذا لم تتم إضافة هذه الحقول بشكل صريح إلى قائمة الحقول التي تم إحضارها في وقت التصميم.

### <a name="run-the-provided-er-format-by-using-the-updated-model-mapping"></a>تشغيل تنسيق التقارير الإلكترونية المتوفر باستخدام تعيين النموذج المحدّث

اتبع الخطوات في [تشغيل تنسيق مصمّم من التقارير الإلكترونية](er-quick-start1-new-solution.md#RunFormatFromER) لتشغيل تنسيق التقارير الإلكترونية المتوفر لاستبيان واحد من صفحة **التكوينات**.

### <a name="review-the-execution-trace-of-the-second-run"></a>مراجعة تتبع التنفيذ في التشغيل الثاني

1. انتقل إلى **إدارة المؤسسة** \> **التقارير الإلكترونية** \> **التكوينات**.
2. في صفحة **التكوينات‏‎**، وسّع **نموذج الاستبيانات‏‎**، وحدد **تعيين الاستبيانات**.
3. في جزء الإجراءات، حدد **المصمم**.
4. في صفحة **تعيين النموذج إلى مصدر البيانات**، حدد **المصمم**.
5. في صفحة **مصمم تعيين النموذج**، في جزء الإجراءات، حدد **تتبع الأداء**.
6. في مربع الحوار **إعدادات نتائج تتبع الأداء**‬، حدد التتبع الذي تم إنشاؤه اثناء تشغيل التنسيق الأخير.
7. حدد **موافق**.
8. على علامة التبويب السريعة **التفاصيل**، قم بتصفية مسار **الاستبيان** الذي يشير إلى مصدر بيانات **الاستبيان**.
9. مراجعة تفاصيل استعلام قاعدة البيانات الذي تم إنشاؤه عندما تم استدعاء مصدر بيانات **الاستبيان** .

    تم إحضار فقط الحقول المطلوبة لملء مصدر البيانات في وقت التشغيل من جدول تطبيق `KMCollection` عندما تم استدعاء مصدر بيانات **الاستبيان**.

    > [!NOTE]
    > تُضاف بعض الحقول، مثل الحقول الخاصة بمعرف القسم ومعرف منطقة البيانات ومعرف السجل، تلقائيًا بواسطة إطار عمل إدارة البيانات لتطبيق Finance.

    ![مراجعة تفاصيل استعلام قاعدة البيانات لتعيين النموذج المحدّث في صفحة مصمم تعيين النموذج.](./media/er-reduce-fetched-fields-number-query2.png)

يمكنك استخدام هذا الأسلوب لتقليل عدد السجلات التي تم إحضارها عندما يتعين عليك تقليل استهلاك الذاكرة عن طريق تعيين نموذج التقارير الإلكترونية قيد التشغيل وتنسيق التقارير الإلكترونية.

## <a name="limitations"></a>قيود

عندما تحدد عدد الحقول التي تم إحضارها لمصدر بيانات من النوع *سجلات الجدول*، لا يمكنك استخدام طرق جدول التطبيق الذي يشير إليه مصدر البيانات، لأن بيانات تعريف التطبيق لا توفر معلومات حول حقول الجدول المطلوبة لاستدعاء هذه الأساليب.

## <a name="usage-notes"></a>ملاحظات الاستخدام

على الرغم من أن الأمر **تعبئة تلقائية** يضيف الحقول تلقائيًا، فهو لا يحذف الحقول المضافة مسبقًا بشكل تلقائي، حتى لو لم تعد مستخدمة في الروابط والصيغ ومصادر البيانات لتعيين النموذج القابل للتحرير.

عندما تحدد **تعبئة تلقائية**، تحلل التقارير الإلكترونية الارتباطات والصيغ ومصادر البيانات التي كانت موجودة في تعيين النموذج القابل للتحرير عند فتحه للتحرير. إذا قمت بتغيير الروابط والصيغ ومصادر البيانات لتعيين النموذج القابل للتحرير، وأردت استخدام الأمر **تعبئة تلقائية**، فأغلق مصمم تعيين النموذج، ثم أعد فتحه لتحريره تعيين النموذج. 

## <a name="additional-resources"></a>الموارد الإضافية

- [تتبع تنفيذ تنسيقات التقارير الإلكترونية لاستكشاف مشكلات الأداء وإصلاحها](trace-execution-er-troubleshoot-perf.md)
- [استكشاف مشكلات الأداء وإصلاحها في تكوينات التقارير الإلكترونية](er-troubleshoot-perf-issues-in-configurations.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]