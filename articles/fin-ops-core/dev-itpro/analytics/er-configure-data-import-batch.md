---
title: استيراد البيانات من ملفات محددة يدويًا في الوضع الدُفعي
description: يشرح هذا الموضوع كيفية استيراد البيانات من ملفات محددة يدويًا في الوضع الدُفعي.
author: NickSelin
ms.date: 01/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERImportFormatSourceTable, ERWorkspace
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2022-01-01
ms.dyn365.ops.version: Release 10.0.25
ms.openlocfilehash: 8615b5a0623fd696c64f4ec03e481a2bcb16c0ac
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 01/31/2022
ms.locfileid: "8075594"
---
# <a name="import-data-from-manually-selected-files-in-batch-mode"></a>استيراد البيانات من ملفات محددة يدويًا في الوضع الدُفعي

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]

لاستخدام إطار عمل [التقارير الإلكترونية (ER)](general-electronic-reporting.md) لاستيراد البيانات من ملفات محددة واردة في الوضع الدُفعي، عليك تكون [تنسيق](er-overview-components.md#format-component) تقارير إلكترونية يدعم الاستيراد. ثم شغّل [تعيين نموذج](er-overview-components.md#model-mapping-component) من النوع **إلى الوجهة** يستخدم هذا التنسيق كمصدر بيانات لاستيراد البيانات، استعرض وصولاً إلى الملف الذي تريد استيراده، ثم حدده يدويًا. 

تسمح إمكانية إعداد التقارير الإلكترونية الجديدة التي تدعم استيراد البيانات في الوضع الدُفعي بتنفيذ هذه العملية كعملية غير مراقبة. يمكنك استخدام تكوينات التقارير الإلكترونية لتنفيذ عملية استيراد البيانات من خلال جدولة وظيفة دُفعية جديدة من واجهة مستخدم (UI) التقارير الإلكترونية.

يشرح هذا الموضوع كيفية إكمال استيراد البيانات من ملف محدد يدويًا في الوضع الدُفعي. تستخدم الأمثلة حركات المورد كبيانات الأعمال. يمكن إكمال الخطوات الخاصة بهذه الأمثلة في شركة **USMF**. الترميز غير مطلوب.

## <a name="prerequisites"></a>المتطلبات الأساسية

لإكمال الأمثلة في هذا الموضوع، يجب أن يكون لديك الوصول التالي:

- أحد الأدوار التالية:

    - مطور إعداد التقارير الإلكتروني
    - مستشار وظيفي لإعداد التقارير الإلكتروني
    - مسؤول النظام

- تنسيق التقارير الإلكترونية وتكوينات النموذج لمدفوعات 1099

### <a name="create-the-required-er-configurations"></a>إنشاء تكوينات التقارير الإلكترونية المطلوبة

لإنشاء تكوينات التقارير الإلكترونية المطلوبة والحصول على المتطلبات الأساسية الأخرى، اتبع إحدى الخطوات التالية:

- شغّل دلائل المهام **التقارير الإلكترونية ـ استيراد بيانات من ملف Microsoft Excel**، التي تعتبر جزءًا من العملية التجاري **7.5.4.3 اكتساب/تطوير خدمة تكنولوجيا المعلومات/مكونات الحلول (10677)**. تُطلعك دلائل المهام هذه على عملية تصميم واستخدام تكوينات التقارير الإلكترونية التي تستورد حركات المورّد بشكل تفاعلي من ملفات Microsoft Excel. للحصول على مزيد من المعلومات، راجع [توزيع المستندات الواردة بتنسيق Excel](parse-incoming-documents-excel.md).
- أكمل الأمثلة في [تكوين استيراد البيانات من SharePoint](er-configure-data-import-sharepoint.md). تُطلعك هذه الأمثلة على عملية تصميم واستخدام تكوينات التقارير الإلكترونية التي تستورد حركات المورّد بطريقة تفاعلية من ملفات Excel المخزنة في مجلد SharePoint.

### <a name="download-the-required-er-configurations"></a>تنزيل تكوينات التقارير الإلكترونية المطلوبة

1. قم بتنزيل تكوينات التقارير الإلكترونية التالية واحفظها محليًا.

    | وصف المحتوى | ملف |
    |---------------------|------|
    | تكوين نموذج بيانات التقارير الإلكترونية **نموذج مدفوعات 1099** | [1099model.xml](https://download.microsoft.com/download/b/d/9/bd9e8373-d558-4ab8-aa9b-31981adc97ea/1099model.xml) |
    | تكوين تنسيق التقارير الإلكترونية **لاستيراد حركات المورّد (Excel)** | [1099format-import-from-excel.xml](https://download.microsoft.com/download/b/3/8/b38faf0a-fbaf-4e9e-84c2-dedae7464880/1099format-import-from-excel.xml) |

2. استخدم خيار التقارير الإلكترونية [تحميل من ملف XML](er-defer-sequence-element.md#import-the-sample-er-configurations) لاستيراد تكوينات التقارير الإلكترونية التي تم تنزيلها إلى مثيلك من Dynamics 365 Finance بالترتيب التالي:

    1. تكوين نموذج بيانات التقارير الإلكترونية
    2. تنسيق تكوين ER

### <a name="download-the-required-excel-files"></a>تنزيل ملفات Excel المطلوبة

- قم بتنزيل مجموعة عينات البيانات التالية، واحفظها محليًا.

    | وصف المحتوى | ملف |
    |---------------------|------|
    | ملف **1099import-data.xlsx** الوارد الذي يحتوي على عينة بيانات لاستيراده | [1099import-data.xlsx](https://download.microsoft.com/download/f/f/4/ff4dbce9-8364-4391-adee-877945ff01f7/1099import-data.xlsx) |

### <a name="review-the-prerequisites"></a>مراجعة المتطلبات الأساسية

1. انتقل إلى **إدارة المؤسسة** \> **التقارير الإلكترونية** \> **التكوينات**.
2. في صفحة **التكوينات**، راجع حل التقارير الإلكترونية الذي تم إعدادها لاستيراد البيانات في الوضع الدُفعي.
3. راجع تكوين التنسيق **لاستيراد حركات المورّد (Excel)**.

    - تم تصميم مكون التنسيق الخاص بهذا التكوين لتحليل ملف Excel وارد.
    - يتم استخدام مكون تعيين النموذج الخاص بهذا التكوين لتعبئة نموذج البيانات الأساسي باستخدام بيانات من ملف Excel الذي تم تحليله.

    ![تكوين تنسيق التقارير الإلكترونية لاستيراد البيانات في الوضع الدُفعي من واجهة مستخدم التقارير الإلكترونية.](./media/er-configure-data-import-batch-configurations-1.png)

4. راجع تكوين نموذج بيانات **نموذج مدفوعات 1099**.

    - يمثل مكون النموذج لهذا التكوين بنية نموذج البيانات المستخدم لتمرير البيانات بين مكونات التقارير الإلكترونية قيد التشغيل.
    - يتم استخدام مكون تعيين النموذج لهذا التكوين لسحب البيانات من مكون التنسيق المنفذ ثم تحديث جداول التطبيق.

    ![نموذج بيانات التقارير الإلكترونية لاستيراد البيانات في الوضع الدُفعي من واجهة مستخدم التقارير الإلكترونية.](./media/er-configure-data-import-batch-configurations-2.png)

5. افتح الملف **1099import-data.xlsx** في Excel.

    ![عينة ملف Excel مع بيانات لاستيرادها في الوضع الدُفعي.](./media/er-configure-data-import-batch-excel-content.png)

## <a name="enable-batch-data-import-for-er-from-the-ui"></a>تمكين استيراد بيانات دُفعية للتقارير الإلكترونية من واجهة المستخدم

1. انتقل إلى **إدارة النظام** \> **مساحات العمل** \> **إدارة الميزات**.
2. في مساحة عمل **إدارة الميزات**، حدد الميزة **تشغيل استيراد التقارير الإلكترونية (ER) للمستندات التي تم تحميلها يدويًا على دُفعات‬**، ثم حدد **التمكين الآن**.

## <a name="import-data-from-manually-selected-excel-files"></a>استيراد البيانات من ملفات Excel محددة يدويًا

1. انتقل إلى **إدارة المؤسسة** \> **التقارير الإلكترونية** \> **التكوينات**.
2. في صفحة **التكوينات**، حدد تكوين نموذج البيانات **نموذج مدفوعات 1099**.
3. على علامة التبويب السريعة **مكونات التكوين**، حدد الارتباط **لاستيراد الحركات اليدوية 1099**.
4. في صفحة **تعيين النموذج إلى مصدر البيانات**، يكون تعيين النموذج **لاستيراد الحركات اليدوية 1099** محددًا بشكل مسبق. حدد **تشغيل**.
5. على علامة التبويب **المعلمات** ، حدد **استعراض**. ابحث عن الملف **1099import-data.xlsx** وحدده، ثم حدد **موافق**.
6. في حقل **إدخال معرف الإيصال**، أدخل **‎V-00001**.
7. على علامة التبويب **التشغيل في الخلفية**، قم بتعيين خيار **المعالجة الدُفعية‬** إلى **نعم**.

    لاحظ أنه تم تعيين حقل **وصف المهمة** إلى تكوين **تشغيل تعيين النموذج 'لاستيراد الحركات اليدوية 1099'، 'نموذج مدفوعات'**. تشير هذه القيمة إلى أنه سيتم جدولة تنفيذ تعيين النموذج المحدد كوظيفة دُفعية جديدة.

    ![تحديد تفاصيل استيراد البيانات في الوضع الدُفعي في مربع الحوار معلمات التقارير الإلكترونية.](./media/er-configure-data-import-batch-execution-parameters.png)

8. حدد **موافق**. تُعلمك رسالة بجدولة وظيفة دُفعية جديدة.

    ![رسالة حول وظيفة دُفعية جديدة مجدولة في صفحة تعيين النموذج إلى مصدر البيانات.](./media/er-configure-data-import-batch-scheduled-job-info.png)

## <a name="review-the-data-import-results-on-the-batch-job-page"></a>مراجعة نتائج استيراد البيانات في صفحة الوظيفة الدُفعية

1. انتقل إلى **عام** \> **الاستعلامات** \> **الوظائف الدفعية** \> **الوظائف الدفعية الخاصة بي**.
2. في صفحة **الوظيفة الدُفعية**، قم بتصفية قائمة الوظائف الدُفعية للعثور على الدُفعة المجدولة، ثم حددها.
3. حدد ارتباط **معرف الوظيفة** لمراجعة تفاصيل الوظيفة.
4. على علامة التبويب السريعة **المهام الدُفعية**، حدد **سجل**.

    ![الزر سجل في صفحة الوظيفة الدُفعية.](./media/er-configure-data-import-batch-scheduled-job-record.png)

5. راجع تفاصيل التنفيذ.

    ![سجل التنفيذ الخاص بالوظيفة الدُفعية المجدولة في الصفحة الوظيفة الدُفعية.](./media/er-configure-data-import-batch-scheduled-job-log.png)

## <a name="change-the-data-import-parameters"></a>تغيير معلمات استيراد البيانات

بعد جدولة الدُفعة، وبينما لم يتم تشغيلها بعد، يمكنك تغيير معلمات استيراد البيانات المجدول.

1. انتقل إلى **عام** \> **الاستعلامات** \> **الوظائف الدفعية** \> **الوظائف الدفعية الخاصة بي**.
2. في صفحة **الوظيفة الدُفعية**، قم بتصفية قائمة الوظائف الدُفعية للعثور على الدُفعة المجدولة، ثم حددها.
3. حدد **تغيير الحالة**.
4. في مربع الحوار **تحديد حالة جديدة**، حدد **اقتطاع‬‏‫‬‏‫**، ثم حدد **موافق**.
5. حدد ارتباط **معرف الوظيفة** للوصول إلى تفاصيل الوظيفة.
6. على علامة التبويب السريعة **المهام الدُفعية**، حدد **معلمات**.
7. في مربع الحوار **معلمات التقارير الإلكترونية**، اتبع هذه الخطوات.

    1. حدد **استعراض** لتحديد الملف البديل لاستيراد البيانات.
    2. خدد **إدخال معرف الإيصال** لتغيير رقم الإيصال الخاص باستيراد حركات المورّد.

        ![تغيير معلمات استيراد البيانات للوظيفة الدُفعية المجدولة في مربع الحوار معلمات التقارير الإلكترونية.](./media/er-configure-data-import-batch-scheduled-job-parameters.png)

    3. حدد **موافق**.

8. تأكد من استمرار تحديد الدُفعة، ثم حدد **تغيير الحالة** مرة أخرى.
9. في مربع الحوار **تحديد حالة جديدة**، حدد **انتظار‬‏‫‬‏‫**، ثم حدد **موافق**.

## <a name="review-the-data-import-results-on-the-er-source-page"></a>مراجعة نتائج استيراد البيانات في صفحة مصدر التقارير الإلكترونية

1. انتقل إلى **إدارة المؤسسة** \> **إعداد التقارير الإلكترونية** \> **مصدر إعداد التقارير الإلكترونية**.
2. حدد سجل **لاستيراد حركات المورّد (Excel)** الذي تم إنشاؤه تلقائيًا اثناء استيراد البيانات.

    ![تكوين سجل "لاستيراد حركات المورّد (Excel) في صفحة مصدر إعداد التقارير الإلكترونية.](./media/er-configure-data-import-batch-files-source-1.png)

3. حدد **حالات الملف للمصادر**.
4. على علامتي التبويب السريعتين **الملفات** و **سجلات المصادر لتنسيق الاستيراد‬‏‫**، راجع تفاصيل الاستيراد.
5. على علامة التبويب السريعة **الملفات**، حدد السجل. لاحظ أن الملف المستورد مرفق بهذا السجل.

    ![الملف المستورد مرفق بالسجل الموجود في الصفحة "حالات الملف للمصادر".](./media/er-configure-data-import-batch-files-source-2.png)

6. حدد **المرفقات** لمراجعة الملف المستورد.

    ![ملف مستورد في صفحة عرض المستند.](./media/er-configure-data-import-batch-files-source-3.png)

    > [!TIP]
    > للاحتفاظ بهذه المرفقات، يستخدم إطار عمل التقارير الإلكترونية نوع مستند تم [تعيينه](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) للشركة الحالية في الحقل **غير ذلك** في معلمات التقارير الإلكترونية.

## <a name="review-the-data-import-results-on-the-vendor-settlement-for-1099s-page"></a>مراجعه نتائج استيراد البيانات في الصفحة "تسوية المورد لنموذج 1099"

1. انتقل إلى **الحسابات الدائنة** \> **المهام الدورية** \> **الضريبة 1099** \> **تسوية المورد لنموذج 1099**.
2. في حقل **من تاريخ**، أدخل **12/31/2017**‏ (31 ديسمبر 2017).
3. حدد **حركات 1099 اليدوية**.

    ![حركات المورّد المستوردة في صفحة حركات الضريبة 1099.](./media/er-configure-data-import-batch-imported-data.png)

## <a name="additional-resources"></a>الموارد الإضافية

[نظرة عامة حول التقارير الإلكترونية](general-electronic-reporting.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]