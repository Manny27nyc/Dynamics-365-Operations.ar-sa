---
title: استخدام مصادر بيانات الأكواد الشريطية لإنشاء صور للكود الشريطي
description: يشرح هذا الموضوع كيفية استخدام مصادر بيانات الأكواد الشريطية لإنشاء صور الأكواد الشريطية.
author: NickSelin
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Version 10.0.13
ms.openlocfilehash: c549a476f854ffcf962ffb62e430b459d3445734
ms.sourcegitcommit: cc78f9bf585082ce65c2ab0b011ff62620fa883d
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 10/21/2020
ms.locfileid: "4088187"
---
# <a name="use-barcode-data-sources-to-generate-bar-code-images"></a>استخدام مصادر بيانات الأكواد الشريطية لإنشاء صور للكود الشريطي

[!include[banner](../includes/banner.md)]

يمكنك استخدام إطار عمل [التقارير الإكترونية (ER)](general-electronic-reporting.md) لتصميم [مكونات تنسيق ER](general-electronic-reporting.md#FormatComponentOutbound) التي يمكنك تشغيلها لإنشاء مستندات صادرة إلكترونية وقابلة للطباعة تتطلب الحصول عليها. لإنشاء مستند صادر في تنسيق Microsoft Office، فإنه يجب تحديد التقرير باستخدام إما مستند Microsoft Excel أو مستند Microsoft Word كقالب تقرير. يسمح لك [مصمم عمليات ER](general-electronic-reporting.md#building-a-format-that-uses-a-data-model-as-a-base) بإرفاق مستند Excel أو Word كقالب لتنسيق ER. يتم إقتران العناصر التالية التي تمت تسميتها في القالب المرفق بعناصر مكون التنسيق الذي تم تكوينه:

- عناصر تحكم المحتوى في Word
- كشوف والنطاقات والخلايا والأشكال والصور التي تمت تسميتها في Excel

يتم استخدام هذه العناصر التي تمت تسميتها كعناصر نائبة للبيانات التي يتم إدخالها في المستند الذي تم إنشاؤه عند تشغيل تنسيق ER. يتم ربط عناصر التنسيق ER إلى مصادر البيانات. وتحدد مصادر البيانات هذه البيانات التي سيتم إدخالها في المستندات التي تم إنشاؤها في وقت التشغيل. للمزيد من المعلومات، راجع [تضمين الصور والأشكال في المستندات التي تقوم بإنشائها باستخدام التقارير الإلكترونية](electronic-reporting-embed-images-shapes.md).

يدعم ER الآن نوع مصدر البيانات **الكود الشريطي**. وبالتالي، يمكنك الآن إنشاء صورة تمثل الكود الشريطي للنص المعين. عندما تقوم بتكوين تنسيق ER، فإنه يمكنك تحديد مصادر البيانات لنوع **الكود الشريطي** لإنشاء صور الكود الشريطي. ثم يمكنك بعد ذلك إضافة تلك الصور إلى مستندات العمل التي تم إنشاؤها، مثل الأوامر والفواتير وإيصال التعبئة والإيصالات. يمكنك أيضًا إضافتها إلى أنواع مختلفة من التسميات، مثل تسميات المنتج والرف وتسميات التعبئة والشحن.

يمكن استخدام العناصر النائبة التالية في قوالب التقارير لإدخال صور الأكواد الشريطية:

- [صورة](https://docs.microsoft.com/office/client-developer/word/content-controls-in-word) التحكم بمحتوى Word
- [صورة](https://support.office.com/article/insert-pictures-3c51edf4-22e1-460a-b372-9329a8724344) كائن في Excel

باستخدام مصدر بيانات من نوع **الكود الشريطي** ، يمكنك إنشاء الأكواد الشريطية بالتنسيقات التالية:

- الأكواد الشريطية أحادية الأبعاد:

    - Codabar
    - Code 39
    - Code 93
    - Code 128
    - EAN-8
    - EAN-13
    - ITF-14
    - البريد الذكي
    - MSI
    - Plessey
    - PDF417
    - UPC-A
    - UPC-E

- الأكواد الشريطية ثنائية الأبعاد:

    - Aztec
    - مصفوفة البيانات
    - شفرة استجابة سريعة (QR)

عندما تقوم بتكوين مصدر بيانات **كود شريطي** ، فإنه يمكنك تعريف معلمات عرض معينة يتم استخدامها لإنشاء صورة:

- **العرض** – تحديد عرض الكود الشريطي بالبكسل. وتشير القيمة **0** (صفر) إلى أنه يتم استخدام العرض الافتراضي. يمكن أن يختلف المعنى بالنسبة للتنسيقات المختلفة.
- **الارتفاع** – تحديد ارتفاع الكود الشريطي بالبكسل. وتشير القيمة **0** (صفر) إلى أنه يتم استخدام الارتفاع الافتراضي. يمكن أن يختلف المعنى بالنسبة للتنسيقات المختلفة.
- **الهامش** – حدد حجم هامش الكود الشريطي بالبكسل. الهامش هو المنطقة الموجودة على كل جانب من جوانب الكود الشريطي والتي يجب الاحتفاظ بمسحها (المنطقة الهادئة). وتشير القيمة **0** (صفر) إلى أنه يتم استخدام الهامش الافتراضي. يمكن أن يختلف المعنى بالنسبة للتنسيقات المختلفة.
- **محتوى الإخراج** – قم بتعيين القيمة إلى **نعم** لإنشاء صورة كود شريطي تحتوي على المعلومات المرمزة كنص. القيمة الافتراضية هي **لا**.
- **الترميز** – يحدد نوع الحروف التي يتم ترميزها في صورة الكود الشريطي الذي تم إنشاؤه. افتراضيًا، يتم استخدام الترميز **UTF-8**.

> [!IMPORTANT]
> عندما تقوم بإضافة مصدر بيانات **الكود الشريطي** ، فإنه يجب عليك وضعه ضمن عنصر آخر (الحاوية) كعنصر متداخل.
>
> عند ربط مصدر بيانات **كود شريطي** بعنصر خلية في تنسيق، ويمثل عنصر الخلية إما عنصر تحكم محتوى Word أو صورة Excel، فإنه يتم تقديم مصدر البيانات في ذلك الربط كوظيفة تحتوي على معلمة واحدة من نوع **السلسلة**. يجب عليك استخدام هذه المعلمة لتحديد النص الذي يجب تحويله إلى صورة كود شريطي والقراءة عند فحص الكود الشريطي الذي تم إنشاؤه.

لمعرفة المزيد من المعلومات حول هذه الميزة، أكمل الامثلة في هذا الموضوع.

## <a name="example-generate-a-payment-check-that-contains-a-bar-code-that-encodes-the-payable-amount"></a>مثال: إنشاء شيك دفع يحتوي على كود شريطي يقوم بترميز المبلغ المستحق الدفع

يوضح هذا المثال كيف يمكن لمستخدم في دور **مسؤول النظام** أو **مستشار وظائف التقارير الإلكترونية** تكوين تنسيق ER يحتوي على قالب يتم استخدامه لإنشاء مستند صادر بتنسيق Excel يحتوي على كود شريطي. وفيما يلي نظرة عامة على الخطوات المضمنة.

1. [أكمل المتطلبات الأساسية](#ExamplePrerequisites).
2. [تنشيط موفر تكوين](#ExampleProvider).
3. [استيراد حل التقاير الإلكترونية المتوفرة](#ExampleImportSolution).
4. [إنشاء شيك دفع](#ExampleGenerateCheque).
5. [مراجعة شيك دفع تم إنشاؤه](#ExampleReviewGeneratedCheque).
6. [تعديل تنسيق حل ER المتوفر](#ExampleModifyFormat).

    1. [تطبيق قالب شيك جديد](#ExampleModifyFormatApplyTemplate).
    2. [إضافة مصدر بيانات كود شريطي](#ExampleModifyFormatAddDataSource).
    3. [ربط عنصر تنسيق جديد](#ExampleModifyFormatBindFormatElement).
    4. [قم بإتاحة الإصدار الذي تم تعديله لتشغيل الاختبار](#ExampleModifyFormatMakeVersionAvailable).

        1. [أكمل إصدار التنسيق المعدل](#CompleteToRun).
        2. [اجعل إصدار المسودة متاحًا للاستخدام](#MarkToRun).

7. [إنشاء شيك دفع](#ExampleGenerateCheque2).
8. [قم بتحويل الشيك الذي تم إنشاؤه إلى PDF](#ExampleConvertToPDF).

في هذا المثال، ستستخدم الحل ER المتوفر الذي تم تكوينه لإنشاء شيكات دفع. يقوم هذا الحل بإنشاء شيكات الدفع حيث تتم كتابة المبلغ الدائن كرقم وكنص. ستقوم بتعديل حل ER هذا بحيث يتضمن الفحص أيضًا الكود الشريطي الذي تم إنشاؤه حيث يتم ترميز المبلغ الدائن ويمكن قراءته باستخدام الماسح الضوئي للكود الشريطي.

يمكن إكمال الخطوات في شركة **USMF** في Microsoft Dynamics 365 Finance.

### <a name="complete-the-prerequisites"></a><a name="ExamplePrerequisites"></a>إكمال المتطلبات الأساسية

لإكمال هذا المثال، يجب أن يكون لديك حق الوصول إلى شركة USMF في Finance لأحد الأدوار التالية:

- مستشار وظيفي لإعداد التقارير الإلكتروني
- مسؤول النظام

إذا لم تكن قد أكملت بعد المثال الموجود في [تضمين الصور والأشكال في المستندات التي تقوم بإنشائها باستخدام موضوع ER](electronic-reporting-embed-images-shapes.md)، قم بتنزيل التكوينات التالية لنموذج حل ER.

| وصف المحتوى         | اسم الملف                   |
|-----------------------------|-----------------------------|
| تكوين نموذج بيانات التقارير الإلكترونية | Model for cheques.xml       |
| تنسيق تكوين ER     | Cheques printing format.xml |

بالإضافة إلى ذلك، قم بتنزيل ملف Excel التالي الذي يحتوي على القالب المعدل الخاص بحل ER المتوفر.

| وصف المحتوى | اسم الملف                 |
|---------------------|---------------------------|
| قالب التقرير     | Check template Excel.xlsx |

### <a name="activate-a-configuration-provider"></a><a name="ExampleProvider"></a>تنشيط موفر تكوين

1. انتقل إلى **إدارة المؤسسة** \> **مساحات العمل** \> **التقارير الإلكترونية**.
2. في صفحة **تكوينات الترجمة** ، في القسم **موفري التكوين** ، تحقق من أنه يتم إدراج [موفر التكوين](general-electronic-reporting.md#Provider) لنموذج الشركة **Litware, Inc.** ، وأنه يتم وضع علامة عليه كنشط. في حالة عدم الإدراج، أو عدم وضع علامة عليه كنشط، اتبع الخطوات الموجودة في الموضوع [إنشاء موفر تكوين ووضع علامة عليه على أنه نشط.](tasks/er-configuration-provider-mark-it-active-2016-11.md).

![تعيين نموذج الشركة إلى نشط في صفحة تكوينات الترجمة](./media/er-barcode-data-source-active-provider.png)

### <a name="import-the-provided-er-solution"></a><a name="ExampleImportSolution"></a>استيراد حل التقاير الإلكترونية المتوفرة

1. انتقل إلى **إدارة المؤسسة** \> **مساحات العمل** \> **التقارير الإلكترونية**.
2. في الصفحة **تكوينات الترجمة** ، في قسم **التكوينات** ، حدد تجانب **تكوينات إعداد التقارير** .
3. في صفحة **التكوينات** ، في حالة عدم توفر تكوين **نموذج للشيكات** في شجرة التكوين، ابتع هذه الخطوات لاستيراد تكوين نموذج بيانات التقارير الإلكترونية:

    1. في جزء الإجراءات، حدد **التبادل** \> **تحميل من ملف XML**.
    2. في مربع الحوار، حدد **استعراض** ، وابحث عن ملف **Model for cheques.xml** ، ثم حدد **موافق**.

4. في حالة عدم توفر التكوين **تنسيق طباعة الشيكات** في شجرة التكوين، اتبع هذه الخطوات لاستيراد تكوين تنسيق التقارير الإلكترونية:

    1. في جزء الإجراءات، حدد **التبادل** \> **تحميل من ملف XML**.
    2. في مربع الحوار، حدد **استعراض** ، ابحث وحدد عن ملف **Cheques printing format.xml** ، ثم حدد **موافق**.

5. في شجرة التكوين، قم بتوسيع **نموذج للشيكات**.
6. راجع قائمة تكوينات إعداد التقارير الإلكترونية المستوردة في شجرة التكوين.

### <a name="generate-a-payment-check"></a><a name="ExampleGenerateCheque"></a>إنشاء شيك دفع

1. انتقل إلى **إدارة النقد والبنوك** \> **الحسابات البنكية** \> **الحسابات البنكية**.
2. في الصفحة **الحسابات البنكية** ، حدد الحساب **USMF OPER**.
3. في صفحة تفاصيل الحساب البنكي، في جزء الإجراء، في علامة التبويب **إعداد** ، في المجموعة **تخطيط** ، حدد **شيك**.
4. في الصفحة **مخطط الشيكات** ، حدد **تحرير**.
5. في علامة التبويب السريعة **عام** ، قم بتعيين خيار **تنسيق التصدير الإلكتروني العام‬** إلى **نعم**.
6. في الحقل **تكوين التنسيق التصدير** ، حدد تنسيق التقرير الإلكتروني **تنسيق طباعة الشيكات** الذي الذي قمت باستيراده سابقًا.
7. في جزء الإجراءات، حدد **اختبار طباعة**.
8. في مربع الحوار، قم بتعيين خيار **تنسيق الشيك القابل للتداول** إلى **نعم** ، ثم حدد **موافق**.

    ![مخطط الشيكات - مربع حوار اختبار الطباعة](./media/er-barcode-data-source-check-layout.png)

### <a name="review-the-generated-payment-check"></a><a name="ExampleReviewGeneratedCheque"></a>مراجعة شيك دفع تم إنشاؤه

- افتح الشيك الذي تم إنشاؤه في Excel.
2. راجع الشيك الذي تم إنشاؤه.

    ![شيك الدفع الذي تم إنشاؤه في Excel](./media/er-barcode-data-source-cheque1.png)

### <a name="modify-the-format-of-the-provided-er-solution"></a><a name="ExampleModifyFormat"></a>تعديل تنسيق حل التقرير الإلكتروني المتوفر

#### <a name="apply-a-new-check-template"></a><a name="ExampleModifyFormatApplyTemplate"></a>تطبيق قالب شيك جديد

يمكنك استخدام تطبيق سطح مكتب Excel لفتح الملف **Cheque template Excel.xlsx** الذي قمت باستيراده سابقًا. لاحظ أن هذا القالب يختلف عن القالب الذي استخدمته لإنشاء شيك دفع في حل التقرير الإلكتروني المتوفر. بالإضاف إلى ذلك، يتضمن العنصر **AmountBarcode** لصورة الكود الشريطي.

![عنصر AmountBarcode في قالب Excel](./media/er-barcode-data-source-cheque2.png)

يجب الآن تعديل حل التقرير الإلكتروني ، ثم [إعادة تطبيق](modify-electronic-reporting-format-reapply-excel-template.md) القالب المعدل.

1. انتقل إلى **إدارة المؤسسة** \> **مساحات العمل** \> **التقارير الإلكترونية**.
2. في الصفحة **تكوينات الترجمة** ، في قسم **التكوينات** ، حدد **تكوينات إعداد التقارير** .
3. في الصفحة **تكوينات** ، في شجرة التكوين، قم بتوسيع **نموذج للشيكات** ، وحدد **تنسيق طباعة الشيكات**.
4. في جزء الإجراءات، حدد **المصمم**.
5. في مصمم عمليات التقرير الإلكتروني، حدد علامة التبويب **تعيين** على الجانب الأيمن للصفحة، ثم، في جزء شجرة التنسيق على الجانب الأيسر، ثم حدد **توسيع/طي**.
6. لاحظ أنه يتم ربط كافة عناصر تنسيق الخلايا بمصادر البيانات المناسبة.

    ![ربط عناصر تنسيق الخلية بمصادر البيانات في مصمم عمليات التقارير الإلكترونية](./media/er-barcode-data-source-cells-bound.png)

7. حدد علامة التبويب **تنسيق** على الجانب الأيمن من الصفحة.
8. في جزء الإجراء، حدد علامة الحذف ( **...** )، ثم حدد **استيراد**.
9. في المجموعة **استيراد** ، حدد **تحديث من Excel** ، ثم حدد **تحديث القالب**.
10. في مربع الحوار، استعرض الملف **Cheque template Excel.xlsx** الذي يتم حفظه على جهاز الكمبيوتر الخاص بك، وحدده، ثم حدد **موافق** للتأكد من أنه يجب تطبيق القالب المحدد.
11. حدد علامة التبويب **تعيين** على الجانب الأيمن للصفحة، ثم، في جزء شجرة التنسيق على الجانب الأيسر، ثم حدد **توسيع/طي**.
12. لاحظ أنه تتم إضافة عنصر الخلية **AmountBarcode** إلى التنسيق. يتم ربط هذا العنصر بالعنصر **AmountBarcode** الذي تمت إضافته إلى قالب Excel المعدل كعنصر نائب لصورة الكود الشريطي.

    ![عنصر AmountBarcode المُضاف إلى التنسيق في مصمم عمليات التقارير الإلكترونية](./media/er-barcode-data-source-cell-added.png)

#### <a name="add-a-new-barcode-data-source"></a><a name="ExampleModifyFormatAddDataSource"></a>إضافة مصدر بيانات كود شريطي جديد

بعد ذلك، يجب إضافة مصدر بيانات جديد لنوع **الكود الشريطي**.

1. في مصمم عمليات التقارير الإلكترونية، ضمن علامة التبويب **تعيين** على الجانب الأيمن من الصفحة، حدد مصدر بيانات **طباعة**.
2. حدد **إضافة** ، ثم، في المجموعة  **الوظائف** ، حدد نوع مصدر البيانات **الكود الشريطي**.

    ![تحديد نوع مصدر بيانات الكود الشريطي](./media/er-barcode-data-source-add.png)

3. في مربع الحوار، في الحقل **الاسم** ، أدخل **الكود الشريطي**.
4. في **تنسيق الكود الشريطي** ، حدد **الكود 128**.
5. في الحقل **العرض** ، أدخل **500**.
6. حدد **موافق**.

    ![مربع حوار خصائص مصدر البيانات](./media/er-barcode-data-source-add2.png)

#### <a name="bind-a-new-format-element"></a><a name="ExampleModifyFormatBindFormatElement"></a>ربط عنصر تنسيق جديد

بعد ذلك، يجب ربط عنصر التنسيق الجديد بمصدر البيانات الذي قمت بإضافته.

1. في مصمم عمليات التقارير الإلكترونية، ضمن علامة التبويب **تعيين** على الجانب الأيمن من الصفحة، حدد مصدر البيانات **طباعة\\الكود الشريطي**.
2. في جزء شجرة التنسيق على اليسار، حدد عنصر الخلية **AmountBarcode** ، ثم حدد **ربط**.
3. في جزء الإجراءات، حدد **عرض التفاصيل**.
4. لاحظ أنه نظرًا لأنه يتم تمثيل مصدر بيانات **الكود الشريطي** في الربط كوظيفة تحتوي على معلمة واحدة، فإنه تم أخذ اسم عنصر التنسيق المنضم تلقائيًا كوسيطة لتلك المعلمة.

    ![تفاصيل مصدر بيانات الكود الشريطي في مصمم عمليات التقارير الإلكترونية](./media/er-barcode-data-source-bind1.png)

5. حدد **تحرير المعادلة** لضبط الربط.

    إنك لا تريد أن يتم إرجاع اسم عنصر الخلية. وبالتالي، يجب عليك تكوين تعبير يرجع النص الذي يحتوي على المبلغ الدائن للشيك الحالي. نظرًا لأن نطاق **ChequeLines** مرتبط بـ **model.cheques** ، يتوفر المبلغ الدائن للشيك الحالي في الحقل **model.cheques.attributes.amount** لنوع البيانات **فعلي**.

6. في الحقل **معادلة** ، أدخل **print.barcode(NUMBERFORMAT(@.attributes.amount, "F2"))**.
7. حدد **حفظ** ، ثم أغلق [مصمم معادلة التقارير الإلكترونية](general-electronic-reporting-formula-designer.md).
8. لاحظ أنه تم تعديل الربط.

    ![الربط المعدل في مصمم العمليات التقارير الإلكترونية](./media/er-barcode-data-source-bind2.png)

9. حدد **حفظ** ، ثم أغلق مصمم عمليات التقارير الإلكترونية.

#### <a name="make-the-modified-version-available-for-test-runs"></a><a name="ExampleModifyFormatMakeVersionAvailable"></a>القيام بالإصدار المعدل المتاحة لتشغيل الاختبار

افتراضيًا، يتم استخدام الإصدارات التي تكون حالتها **مكتمل** و **مشترك** فقط عند تشغيل تنسيق التقارير الإلكترونية.

إذا قمت بإنهاء التغييرات الخاصة بك، فإنه يمكنك إكمال عملك مع إصدار المسودة الحالي وتوفير التغييرات الخاصة بك للاستخدام. للحصول على التعليمات، راجع القسم [إكمال إصدار التنسيق المعدل](#CompleteToRun) الذي يليه.

إذا كنت ترغب في متابعة العمل مع إصدار المسودة الحالي، ولكن يجب عليك استخدامه لإصدار الشيكات، يجب عليك تحديد ما إذا كنت ترغب في استخدام إصدار المسودة من التنسيق لتنفيذه بشكل صريح. للحصول على الإرشادات، راجع القسم [جعل إصدار المسودة متاحًا للاستخدام](#MarkToRun).

##### <a name="complete-the-modified-format-version"></a><a name="CompleteToRun"></a>إكمال إصدار التنسيق المعدل

1. انتقل إلى **إدارة المؤسسة** \> **مساحات العمل** \> **التقارير الإلكترونية**.
2. في الصفحة **تكوينات الترجمة** ، في قسم **التكوينات** ، حدد **تكوينات إعداد التقارير** .
3. في الصفحة **تكوينات** ، في شجرة التكوين، قم بتوسيع **نموذج للشيكات** ، وحدد **تنسيق طباعة الشيكات**.
4. في علامة التبويب السريعة **الإصدارات** ، حدد السجل الذي بحالة **مسودة**.
5. حدد **حالة التغيير** ، ثم حدد **إكمال**.
6. في مربع الحوار، حدد **موافق**.

يتم تغيير حالة الإصدار الحالي من **المسودة** إلى **مكتمل** ، يتم إنشاء إصدار جديد به حالة **مسودة**. يمكنك استخدام إصدار المسودة الجديد هذا لتطبيق تغييرات إضافية.

##### <a name="make-the-draft-version-available-for-use"></a><a name="MarkToRun"></a>إتاحة إصدار المسودة للاستخدام

1. انتقل إلى **إدارة المؤسسة** \> **مساحات العمل** \> **التقارير الإلكترونية**.
2. في الصفحة **تكوينات الترجمة** ، في قسم **التكوينات** ، حدد **تكوينات إعداد التقارير** .
3. في صفحة **التكوينات** ، في جزء الإجراءات، في علامة التبويب **التكوينات** ، في مجموعة **الإعدادات المتقدمة** ، حدد **معلمات المستخدمين**.
4. في مربع الحوار، قم بتعيين الخيارات **تشغيل الإعداد** إلى **نعم** ، ثم حدد **موافق**.
5. في شجرة التكوين، قم بتوسيع **نموذج للشيكات** ، حدد **تنسيق طباعة الشيكات**.
6. عيّن الخيار **تشغيل المسودة** إلى **نعم**.
7. حدد **حفظ**.

يتم وضع علامة على إصدار المسودة للتنسيق المحدد على أنه متوفر للاستخدام عند تشغيل التنسيق المحدد.

### <a name="generate-a-payment-check"></a><a name="ExampleGenerateCheque2"></a>إنشاء شيك دفع

1. انتقل إلى **إدارة النقد والبنوك** \> **الحسابات البنكية** \> **الحسابات البنكية**.
2. في الصفحة **الحسابات البنكية** ، حدد الحساب **USMF OPER**.
3. في صفحة تفاصيل الحساب البنكي، في جزء الإجراء، في علامة التبويب **إعداد** ، في المجموعة **تخطيط** ، حدد **شيك**.
4. في الصفحة **مخطط الشيكات** ، في جزء الإجراء، حدد **طباعة الاختبار**.
5. في مربع الحوار، قم بتعيين الخيار **تنسيق الشيك القابل للتداول** إلى **نعم**.
6. حدد **موافق**.
7. راجع الشيك الذي تم إنشاؤه. لاحظ أنه قد تم إنشاء كود شريطي لترميز المبلغ الدائن الخاص بالشيك.

    ![شيك الدفع الذي تم إنشاؤه باستخدام الكود الشريطي في Excel](./media/er-barcode-data-source-cheque3.png)

> [!IMPORTANT]
> يتم طرح استثناء إذا كانت وسيطة مصدر بيانات **الكود الشريطي** لا تتوافق مع المتطلبات المناسبة المحددة لتنسيق الكود الشريطي. على سبيل المثال، عندما يتم استدعاء مصدر بيانات **الكود الشريطي** لإنشاء كود شريطي [EAN-8](https://wikipedia.org/wiki/EAN-8) للنص المقدم، يتم عرض استثناء إذا كان طول النص يتجاوز سبعة أحرف.

### <a name="convert-the-generated-check-to-a-pdf"></a><a name="ExampleConvertToPDF"></a>تحويل الشيك الذي تم إنشاؤه إلى PDF

كما هو موضح في الموضوع [إنشاء نماذج فاتورة ذات نص حر](er-generate-printable-fti-forms.md#finland)، يمكنك استخدام خط خاص لإنتاج الأكواد الشريطية في المستند الذي تم إنشاؤه. في هذه الحالة، قد تعتمد التحويلات الإضافية للمستند الذي تم إنشاؤه على توفر ذلك الخط في بيئة التحويل. على سبيل المثال، إذا حاولت تحويل وثيقة إلى تنسيق PDF أو معاينتها في بيئة لا يكون الخط فيها مفقودًا، فإن الأكواد الشريطية لن يتم عرضها بشكل صحيح.

ومع ذلك، عندما تقوم باستخدام مصدر بيانات **الكود الشريطي** لإنتاج الأكواد الشريطية، لا يعتمد عرض تلك الرموز الشريطية على أي خط. لذلك، يمكنك بسهولة تحويل المستندات التي تحتوي على أكواد شريطية إلى تنسيق PDF. تبين الرسوم التوضيحية التالية معاينة شيك الدفع الذي تم إنشاؤه أنه تم [تحويل](electronic-reporting-destinations.md#OutputConversionToPDF) إلى ملف PDF، استنادًا إلى إعداد وجهة التقارير الإلكترونية [المكونة](electronic-reporting-destinations.md).

![معاينة ملف PDF الخاص بشيك الدفع](./media/er-barcode-data-source-cheque4.png)

## <a name="limitations"></a>قيود

> [!NOTE]
> تحتوي بعض أنواع الأكواد الشريطية التي يتم إنشاؤها على نسبة أبعاد ثابتة. يكون هذا السلوك مفيدًا إذا قمت بتشغيل الميزة **تمكين استخدام مكتبة EPPlus في إطار عمل التقارير الإلكترونية** للعمل باستخدام مستندات Excel في التقارير الإلكترونية. في تلك الحالة، يتم إدخال صورة في عنصر نائب بنسبة العرض إلى الارتفاع المؤمنة. وبالتالي، عندما تتوافق أبعاد العنصر النائب في أحد القوالب مع نسبة العرض إلى الارتفاع لصورة تم إدخالها، قد يتم تغيير حجم صورة حقيقية في مستند تم إنشائها للحفاظ على نسبة العرض إلى الارتفاع المطلوبة. لمنع تغيير حجم الصورة، استخدم عنصرًا نائبًا له نسبة العرض إلى الارتفاع المتوقعة.

## <a name="additional-resources"></a>الموارد الإضافية

- [نظرة عامة حول التقارير الإلكترونية](general-electronic-reporting.md)
- [وجهات إعداد التقارير الإلكترونية‬](electronic-reporting-destinations.md)
- [لغة تركيبة التقارير الإلكترونية](er-formula-language.md)
- [وظيفة NUMBERFORMAT](er-functions-text-numberformat.md)