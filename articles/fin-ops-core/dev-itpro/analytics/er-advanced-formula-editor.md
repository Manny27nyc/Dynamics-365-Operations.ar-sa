---
title: محرر المعادلات المتقدم لإعداد التقارير الإلكترونية
description: يوضح هذا الموضوع كيفية استخدام محرر المعادلات المتقدم لتكوين التعبيرات في تعيين نموذج ‏‫إعداد التقارير الإلكترونية (ER) ومكونات التنسيق.
author: NickSelin
manager: AnnBe
ms.date: 04/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: d9911c858d6832aa70378d37e0fd5cf7d7831b1b
ms.sourcegitcommit: dce8c5d3b2fc4a752d676cf9ba91e0dea2fa80d8
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/10/2020
ms.locfileid: "3257051"
---
# <a name="electronic-reporting-advanced-formula-editor"></a>محرر المعادلات المتقدم ل‏‫إعداد التقارير الإلكترونية

[!include [banner](../includes/banner.md)]

وبالإضافة إلى [محرر صيغ](general-electronic-reporting.md) [إعداد التقارير الإلكترونية](general-electronic-reporting-formula-designer.md)، يمكنك استخدام محرر المعادلات المتقدم لإعداد التقارير الإلكترونية لتحسين تجربة تكوين تعبيرات التقارير الإلكترونية (ER).. يستند المحرر المتقدم إلى المستعرض ويُشغل بواسطة [محرر موناكو](https://microsoft.github.io/monaco-editor). يتناول هذا الموضوع توضيح ميزات المحرر المتقدم الاكثر استخدامًا:

- [إعداد تنسيق الكود تلقائيًا](#Autoformatting)
- [IntelliSense](#IntelliSense)
- [إكمال الكود](#CodeCompletion)
- [تنقل الكود](#CodeNavigation)
- [هيكلة الكود](#CodeStructuring)
- [بحث واستبدال](#FindAndReplace)
- [لصق البيانات](#DataPasting)
- [تلوين بناء الجملة](#SyntaxColorization)

## <a name=""></a><a name="ActivateAdvEditor">تنشيط محرر المعادلات المتقدم</a>

أكمل الخطوات التالية لبدء استخدام محرر المعادلات المتقدم في مثيل Microsoft Dynamics 365 Finance..

1.  انتقل إلى **إدارة المؤسسة** \> **إعداد التقارير الإلكترونية** \> **التكوينات**.
2.  في صفحة  **التكوينات** ، في جزء الإجراءات، في علامة التبويب  **التكوينات** ، في مجموعة  **الإعدادات المتقدمة** ، حدد  **معلمات المستخدم**.
3.  في مربع الحوار  **معلمات المستخدم** ، في قسم  **تنفيذ التتبع** ، عيِّن المعلمة **تمكين محرر المعادلات المتقدم** على **نعم**.

[![صفحة تكوينات التقارير الإلكترونية](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)

> [!NOTE]
> لاحظ أن هذه المعلمة خاصة بالمستخدم والشركة.

## <a name=""></a><a name="Autoformatting">إعداد تنسيق الكود تلقائيًا</a>

عند كتابة تعبير معقد يتكون من عدة صفوف من الاكواد، سيتم إجراء المسافة البادئة للسطر الجديد الذي تم إدخاله تلقائيًا استنادًا إلى المسافة البادئة للصف السابق. يمكنك تحديد السطور وتغيير المسافات البادئة بكتابة **Tab** أو **Shift+Tab**.

[![محرر معادلات إعداد التقارير الإلكترونية](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)

يسمح لك إعداد التنسيق تلقائيًا بالاحتفاظ بالتنسيق الجيد للتعبير بالكامل لتسهيل عمليات الصيانة المستقبلية وتبسيط فهم المنطق المكون.

## <a name=""></a><a name="IntelliSense">IntelliSense</a>

يوفر المحرر إكمال الكلمة لمساعدتك في كتابة التعبير أسرع وتجنب أخطاء الكتابة. عند بدء إضافة نص جديد، يقدم المحرر تلقائيًا قائمة بالوظائف المدعومة في وظائف إعداد التقارير الإلكترونية التي تحتوي على الأحرف التي أدخلتها. ويمكنك أيضًا تشغيل IntelliSense في أي مكان لتعبير مكون بكتابة **Ctrl+Space**.

[![محرر معادلات إعداد التقارير الإلكترونية](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)

## <a name=""></a><a name="CodeCompletion">إكمال الكود</a>

يوفر المحرر إكمال الكود تلقائيًا بواسطة:

- إدراج قوس إغلاق عند إدخال قوس فتح، مع إبقاء المؤشر داخل الأقواس.
- إدراج رمز الاقتباس الثاني عند إدخال الأول، مع إبقاء المؤشر داخل علامتي الاقتباس.
- إدراج رمز الاقتباس المزدوج الثاني عند إدخال الأول، مع إبقاء المؤشر داخل علامتي الاقتباس.

[![محرر معادلات إعداد التقارير الإلكترونية](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)

عند الإشارة إلى القوس المكتوب، يتم تمييز القوس الثاني من هذا الزوج تلقائيًا لإظهار البناء الذي يدعمه.

## <a name=""></a><a name="CodeNavigation">تنقل الكود</a>

يمكنك تحديد موقع الرموز أو السطور المطلوبة في التعبير بكتابة الأمر **انتقال إلى** باستخدام لوح الأوامر أو قائمة السياق.

على سبيل المثال، للانتقال إلى السطر **8**، اتبع ما يلي:

- اضغط على **Ctrl+G**، وأدخل القيمة **8**، ثم اضغط على **Enter**.

  -أو -

- اضغط على **F1**، واكتب **G**، وحدد **انتقال إلى السطر**، وأدخل القيمة **8**، واضغط على **Enter**.

[![محرر معادلات إعداد التقارير الإلكترونية](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)

## <a name=""></a><a name="CodeStructuring">هيكلة الكود</a>

يتم بناء الكود لبعض الوظائف، مثل [IF](er-functions-logical-if.md) أو [CASE](er-functions-logical-case.md) تلقائيًا. يمكنك توسيع وطي أيًا من مناطق الطي لهذا الكود او كلها لتقليل الجزء القابل للتحرير من التعبير للتركيز فقط على جزء الكود الذي يتطلب انتباهك. يمكن استخدام أوامر تبديل الطي/التوسيع لذلك.

على سبيل المثال، لطي كل المناطق، اتبع ما يلي:

- اضغط على **Ctrl+K**

  -أو -

- اضغط على **F1**، واضغط على **FO**، وحدد **Fold all**، ثم اضغط على **Enter**

لتوسيع كل المناطق، اتبع ما يلي:

- اضغط على **Ctrl+J**

  -أو -
  
- اضغط على **F1**، واكتب **UN**، وحدد **Unfold all**، ثم اضغط على **Enter**

[![محرر معادلات إعداد التقارير الإلكترونية](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)

## <a name=""></a><a name="FindAndReplace">بحث واستبدال</a>

للبحث عن تكرارات نص معين، حدد النص في التعبير، ونفذ الإجراءات التالية:

- اضغط على **Ctrl+F** ثم اضغط **F3** للبحث عن التواجد التالي للنص المحدد، أو اضغط **Shift+F3** للبحث عن التواجد السابق.

  -أو -
  
- اضغط **F1**، واكتب **F**، ثم حدد الخيار المطلوب للبحث عن النص المحدد.

لاستبدال تكرارات نص معين، حدد النص في التعبير، ونفذ الإجراءات التالية:

- اضغط على **Ctrl+H** ادخل النص البديل وحدد الخيار استبدال لاستبدال النص المحدد أو كافة تكرارات هذا النص في التعبير الحالي.

  -أو -
  
- اضغط **F1**، واكتب **R**، ثم حدد الخيار المطلوب لاستبدال النص المحدد. ادخل النص البديل وحدد الخيار استبدال لاستبدال النص المحدد أو كافة تكرارات هذا النص في التعبير الحالي.

لتغيير تكرارات نص معين، حدد النص في التعبير، ونفذ الإجراءات التالية:

- اضغط على **Ctrl+F2**، ثم أدخل النص البديل.

  -أو -
  
- اضغط **F1**، واكتب **C**، ثم حدد الخيار المطلوب لتغيير النص المحدد. أدخل النص البديل.

[![محرر معادلات إعداد التقارير الإلكترونية](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)

## <a name=""></a><a name="DataPasting">مصادر البيانات ولصق الوظائف</a>

يمكنك تحديد **إضافة مصدر بيانات**، الذي يلصق بالتعبير الحالي مصدر البيانات المحدد حاليًا على لوحة **مصدر البيانات** اليمنى. وبالمثل، يمكنك تحديد **إضافة وظيفة**، الذي يلصق بالتعبير الحالي مصدر البيانات المحدد حاليًا على لوحة **الوظائف** اليسرى. عند استخدام محرر معادلات إعداد التقارير الإلكترونية، دائمًا ما يتم لصق الوظيفة المحددة أو مصدر البيانات المحدد إلى نهاية التعبير المكون. عند استخدام ‏‫محرر المعادلات المتقدم ل‏‫إعداد التقارير الإلكترونية، يمكن لصق الوظيفة المحددة أو مصدر البيانات المحدد في أي جزء بالتعبير المكون. ستحتاج إلى استخدام المؤشر لتحديد المكان الذي تريد لصق البيانات فيه.

[![محرر معادلات إعداد التقارير الإلكترونية](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)

## <a name=""></a><a name="SyntaxColorization">تلوين بناء الجملة</a>

يتم حاليًا استخدام ألوان مختلفة لتمييز الأجزاء التالية من التعبيرات:

- النص الموجود داخل الأقواس المزدوجة والذي يمكن أن يمثل معرف تسمية ثابت نصي.

[![محرر معادلات إعداد التقارير الإلكترونية](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)

## <a name="limitations"></a>قيود

المحرر معتمد حاليًا في مستعرضات الويب التالية:

- Chrome
- Edge
- Firefox
- Opera
- Safari

## <a name="additional-resources"></a>الموارد الإضافية

- [نظرة عامة على إعداد التقارير الإلكترونية (ER)](general-electronic-reporting.md)
- [مصمم المعادلات في التقارير الإلكترونية](general-electronic-reporting-formula-designer.md)
- [محرر موناكو](https://microsoft.github.io/monaco-editor)