---
title: "عرض التقارير المالية"
description: "تصف هذه المقالة كيفية عرض التقارير المالية واستكشافها في Microsoft Dynamics 365 for Finance and Operations, Enterprise edition. وهي تتضمن معلومات حول مختلف الخيارات التي يمكنك تطبيقها على التقارير المالية لتغيير مظهرها والبيانات التي تتضمنها."
author: kweekley
manager: AnnBe
ms.date: 06/08/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 10334
ms.assetid: d20f435f-fb65-4068-ab09-7efc7be683a6
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 102031174417a33b12c32f6b8185556b8c4701e5
ms.contentlocale: ar-sa
ms.lasthandoff: 06/13/2017


---

# <a name="view-financial-reports"></a>عرض التقارير المالية

[!include[banner](../includes/banner.md)]


تصف هذه المقالة كيفية عرض التقارير المالية واستكشافها في Microsoft Dynamics 365 for Finance and Operations, Enterprise edition. وهي تتضمن معلومات حول مختلف الخيارات التي يمكنك تطبيقها على التقارير المالية لتغيير مظهرها والبيانات التي تتضمنها.

<a name="financial-reporting-overview"></a>نظرة عامة على التقارير المالية
----------------------------

## <a name="open-a-financial-report"></a>فتح تقرير مالي
لفتح تقرير، حدد اسم التقرير. وفي المرة الأولى التي يتم فيها فتح تقرير، يتم إنشاؤه تلقائياً للشهر الماضي. على سبيل المثال، إذا قمت بفتح تقرير لأول مرة في أغسطس عام 2015، فيتم إنشاء التقرير لتاريخ 31 يوليو 2015. بعد فتح تقرير، يمكنك بدء استكشافه بالتنقل في قطع معينة من البيانات وتغيير خيارات التقرير.

## <a name="drill-down-on-a-financial-report"></a>تصفح لأسفل في تقرير مالي
يمكن أن تتضمن التقارير المالية عدة مستويات من التفاصيل. المستوى المالي هو المستوى الأول الذي تراه عند فتح تقرير مالي. وللانتقال إلى مستوى الحساب، حدد البيانات للتصفح لأسفل فيها. على سبيل المثال، لعرض تفاصيل الحساب للمبيعات، حدد بيانات المبيعات التي تحتاج إلى استكشافها. ومن مستوى الحساب، يمكنك التنقل لأسفل لعرض الحركات التي تشكل رصيد الحساب. وهناك طريقتان لعرض الحركات: حركات التقارير وحركات الإيصال.

-   **حركات التقارير** – تظهر الحركات بطريقة عرض منسقة يتم تضمينها في التقرير المالي. ولعرض الحركات في عرض منسق، حدد البيانات للتنقل فيها، ثم انقر فوق **التنقل إلى مستوى حركات التقرير‬**.
-   **حركات الإيصال** – يتم فتح استعلام حركة إيصال حيث يمكنك عرض الحركات. لعرض الحركات في استعلام حركة الإيصالات، حدد البيانات للتنقل فيها، ثم انقر فوق **فتح حركات الحساب**.

إذا كانت البيانات عبارة عن بيانات موازنة، يمكنك اختيار فتح إدخالات حساب الموازنة. ولإغلاق أي مستوى من مستويات التقرير والعودة إلى حيث بدأت، يمكن الضغط على المفتاح Esc أو انقر فوق الزر **إغلاق** (**X**) في الجزء العلوي الأيمن.

## <a name="change-report-options"></a>تغيير خيارات التقرير
يمكنك تغيير تاريخ التقرير، وتطبيق عوامل تصفية البُعد والسمة، أو تغيير سيناريو الموازنة في تقرير **القيمة الفعلية مقابل الموازنة**. وفي "جزء الإجراءات"، انقر فوق **خيارات التقرير**، ثم اتبع واحدة أو أكثر من الخطوات التالية:

-   لتغيير الفترة الأساسية والسنة الأساسية لتقرير، حدد فترة أساسية وسنة أساسية، ثم انقر فوق **موافق**.
-   ولاستخدام عوامل تصفية سمات في تقرير، حدد **إضافة عامل تصفية سمة**. حدد السمة، وأدخل قيمة السمة، ثم انقر فوق **موافق**. على سبيل المثال، إذا قمت بتحديد سمة **فئة الحساب**، أدخل **المبيعات** كقيمة سمة. ولإزالة عامل تصفية سمة، انقر فوق **مسح**.
-   ‏‫لتطبيق عوامل التصفية الأبعاد على تقرير، حدد **إضافة عامل تصفية بعد‬‏‫**. حدد البعد، ثم أدخل معرف البعد أو حدد البعد في القائمة.‬ ولإزالة عامل تصفية بعد، انقر فوق **مسح**.
-   لتغيير السيناريو في تقرير **القيمة الفعلية مقابل الموازنة**، حدد سيناريو جديدًا، ثم انقر فوق **موافق**. إذا كان السيناريو المحدد لمدة عام آخر، فتأكد من تحديث السنة الأساسية. على سبيل المثال، إذا كان السيناريو الحالي مخصصًا للعام المالي 2015، يمكنك تحديد سيناريو جديد مخصص للعام المالي 2016، ويجب عليك تغيير السنة الأساسية إلى **2016**.

وعند النقر فوق **موافق**، يتم تطبيق كافة الخيارات التي قمت بتحديدها على التقرير. إذا قررت أنك لا تريد تطبيق الخيارات التي تم تحديدها، انقر فوق **إلغاء**.

## <a name="update-a-financial-report"></a>تحديث تقرير مالي
يمكنك تحديث (ترقية) تقرير مالي بحيث يعرض أحدث البيانات عن الفترة والسنة التي تم إنشاء التقارير لهما. على سبيل المثال، إذا قمت بتحديث تقرير مالي تم إنشاؤه لشهر أكتوبر 2015، فسيعكس التقرير أي حركات جديدة تم ترحيلها لشهر أكتوبر 2015. ولتحديث تقرير مالي، في جزء الإجراءات، انقر فوق **تحديث**. لا يتوفر التقرير المحدث إلا للشخص الذي قام بتحديثه. ولكي يشاهد أشخاص آخرون نفس البيانات، يجب نشر التقرير.

## <a name="publish-a-financial-report"></a>نشر تقرير مالي
بعد تحديث تقرير مالي، يمكنك نشره. سيستطيع الأشخاص في المؤسسة عرضه فيما بعد. ولنشر تقرير، في "جزء الإجراءات"، انقر فوق **نشر**.

## <a name="display-a-financial-report-in-a-different-currency"></a>عرض تقرير مالي بعملة أخرى
يمكن عرض تقرير مالي بأي عملة في أي وقت. ولعرض تقرير بعمله أخرى، في "جزء الإجراءات"، انقر فوق **عملة**، ثم حدد عملة. وتتم ترجمة التقرير إلى تلك العملة، ويتم عرض النتائج. ويتم تحديث أي أكواد أو رموز عملة مضمنة كجزء من تصميم التقرير لإظهار العملة الجديدة. العملات التي تظهر في القائمة هي عملات تقارير تم تكوينها في Finance and Operations.

## <a name="display-a-summarized-view-of-the-financial-report"></a>عرض طريقة العرض ملخصة للتقرير المالي
يمكن أن يحتوي التقرير المالي على بنود تفاصيل وبنود ملخص. بنود التفاصيل عبارة عن بنود تتضمن الحسابات الرئيسية أو الأبعاد. بنود الملخص عبارة عن بنود العملية الحسابية والوصف والإجمالي. ولعرض بنود الملخص لتقرير فقط، انقر فوق **إظهار**، ثم انقر فوق **بنود الملخص فقط**. يتم طي التقرير ويعرض بنود الملخص فقط. ولعرض بنود التفاصيل جنبًا إلى جنب مع بنود الملخص، انقر فوق **إظهار**، ثم انقر فوق **بنود الملخص فقط** مرة أخرى.

## <a name="open-a-financial-report-from-a-previous-month"></a>فتح تقرير مالي من شهر سابق
يمكنك عرض التقارير للشهر الحالي أو الأشهر السابقة دون إعادة إنشاء التقرير. ‏‫ولفتح التقرير لشهر سابق، انقر فوق **إظهار**، ثم فوق **التقارير السابقة**. وتظهر قائمة بالأشهر السابقة التي تم إنشاء التقرير لها.‬ وقم بتوسيع الشهر لعرض التقرير الخاص به، وحدد التاريخ، ثم انقر فوق **موافق**. يتم عرض تقرير الشهر السابق. وللرجوع إلى تقرير الشهر الحالي، انقر فوق **إلغاء**.

## <a name="print-a-financial-report"></a>طباعة تقرير مالي
لطباعة تقرير مالي، في "جزء الإجراءات"، انقر فوق **طباعة**، ثم اتبع واحدة أو أكثر من هذه الخطوات لتعيين خيارات الطباعة:

-   لتضمين مختلف مستويات التفاصيل في التقرير المطبوع، قم بتعيين شريط التمرير إلى **نعم** أو **لا**. إذا كان يستخدم تقرير شجرة تقارير، يمكنك اختيار تضمين كافة وحدات التقارير أو وحدة التقارير الحالية فقط.
-   لتعيين حجم الصفحة، حدد حجم صفحة في القائمة.
-   لإعداد تخطيط الصفحة، حدد تخطيطاً في القائمة. إذا كنت تريد أن تتلائم محتويات التقرير مع العرض الذي قمت بتحديده، فقم بتعيين شريط التمرير إلى **نعم**.
-   لتعيين هوامش الصفحة، أدخل حجم الهامش العلوي والسفلي والأيسر والأيمن بالبوصات.

بعد الانتهاء من إعداد خيارات الطباعة، انقر فوق **طباعة** لطباعة التقرير. إذا قررت أنك لا تريد طباعة التقرير، انقر فوق **إلغاء** بدلاً من ذلك. يتم عرض معاينة للتقرير المطبوع. يمكنك تحديد الطابعة لإرسال التقرير إليها، ويمكنك أيضًا ضبط خيارات الطباعة.

## <a name="export-a-financial-report"></a>تصدير تقرير مالي
لتصدير تقرير مالي، في "جزء الإجراءات"، انقر فوق **تصدير**. تم تصدير التقرير إلى Microsoft Excel، ويطالبك المستعرض الخاص بك بفتح أو حفظ الملف الذي تم تصديره. يتم تطبيق إعدادات التصدير التي تم تحديدها في تصميم التقرير على التقرير الذي تم تصديره.    

<a name="see-also"></a>راجع أيضًا
--------

[التقارير المالية في Microsoft Dynamics AX](/dynamics365/unified-operations/dev-itpro/analytics/financial-reporting-intro)




