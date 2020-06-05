---
title: تطوير بنية التعويض
description: تنقلك هذه المقالة عبر عملية إنشاء خطة تعويض ثابت وتسجيل الموظفين بالخطة من خلال قواعد الأهلية.
author: andreabichsel
manager: AnnBe
ms.date: 02/10/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: DefaultDashboard, HcmCompensationWorkspace, HcmCompFixedPlansPart, HRMCompFixedPlanTable, HRMCompCreateGridDialog, HRCCompGridView, HRMCompEligibility,  HRCCompGrid
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 124d0f7f83feebabf622f00732c25bfa0f6eccdd
ms.sourcegitcommit: de715b7fda2f1548f2f443b9e0f6d09f5b881d61
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/10/2020
ms.locfileid: "3034253"
---
# <a name="develop-a-compensation-structure"></a>تطوير بنية التعويض

تنقلك هذه المقالة عبر عملية إنشاء خطة تعويض ثابت وتسجيل الموظفين بالخطة من خلال قواعد الأهلية. تستخدم هذه المقالة بيانات العرض التوضيحي USMF ويتم تطبيقها على مدراء التعويضات والميزات.

## <a name="create-a-fixed-compensation-plan"></a>إنشاء خطة تعويض ثابتة

1. حدد **إدارة التعويض**.

2. حدد **خطط التعويض الثابت**.

3. حدد **جديد**.

4. في الحقل **خطة**، أدخل قيمة.

5. في حقل **الوصف**، أدخل قيمة.

6. في حقل **تاريخ السريان**، أدخل تاريخًا.

7. في الحقل **النوع**، حدد ما إذا كانت خطة التعويض الثابت عبارة عن خطة **نطاق** أو **درجة** أو **خطوة**.

8. تعمل خانة الاختيار **التوصيات المسموحة** بمثابة قيمة افتراضية لأي إجراءات تتم إضافتها إلى هذه الخطة في حدث عملية. تمكّنك خانة الاختيار "التوصيات المسموحة" من تجاوز مبلغ الإرشاد المحسوب عند معالجة التعويض.

9. يسمح لك **التفاوت الخارج عن النطاق** بتحديد كيفية التعامل مع مبالغ التعويض التي تقع خارج نطاق بنية التعويض المحددة للمستوى المعين. يتيح لك تعيين الحقل **‏‫التفاوت الخارج عن النطاق‬** إلى **لا شيء** لاستخدام أي مبلغ تعويض. سيقوم **التفاوت الناعم** بتحذير المستخدم إذا كان مبلغ التعويض أقل من الحد الأدنى أو أكبر الحد الأقصى لمبالغ النقطة المرجعية لهذا المستوى. يمكن للمستخدمين تجاهل التحذير والمتابعة. سيؤدي **التفاوت الثابت** إلى توليد رسالة خطأ إذا كان تعويض الموظف خارج الحد الأدنى والحد الأقصى للنقاط لمرجعية للمستوى، وسيقوم بشكل تلقائي بضبط تعويض الموظف لكي يقع ضمن النطاق.

10. يقوم الحقل **قاعدة التوظيف** بحساب تعويض الموظف أثناء حدث العملية. تحسب **قاعدة التوظيف** بـ **النسبة المئوية** الزيادة التي تم حساب تناسبها لفترة الوقت التي تم خلالها توظيف العامل في الدورة.

11. في الحقل **العملة**، اكتب قيمة.

12. في الحقل **تحويل معدل الدفع**، أدخل قيمة أو حددها.

13. قم بتوسيع القسم **مصفوفة مقياس معدل استخدام النطاق**. بشكل اختياري، يمكنك إضافة سجلات استخدام النطاق لتمكين الموظفين من الوصول إلى نقطة الوسط الخاصة بهم بشكل أسرع وإبطاء وصولهم إلى الحد الأقصى للنطاق.

14. حدد **حفظ**. وهذا يمكن الزر **إعداد التعويض** ويستمر في تعريف بنية التعويض للخطة.

15. حدد **إعداد التعويض**. يمكنك إنشاء بنية التعويض باستخدام أحد الأساليب الثلاثة هذه:

    - إنشاء هيكل جديد تمامًا عن طريق تحديد مجموعة من النقاط المرجعية وإضافة المستويات اللازمة لإنشاء الهيكل الخاص بك.
    - نسخ بنية تعويض من إحدى الخطط الموجودة كنقطة انطلاق وتعديلها للخطة الجديدة.
    - تحديد شبكة تعويض موجودة. إذا كانت خطة أخرى تستخدم شبكة التعويض بالفعل، فستعمل الخطة الأخرى كذلك على عكس أية تغييرات تقوم بإدخالها على الشبكة.

16. حدد **إنشاء مصفوفة جديدة من مصفوفة تعويض موجودة**.

17. في الحقل **نسخ من الشبكة**، أدخل قيمة أو حددها. بشكل اختياري، يمكنك تغيير اسم شبكة التعويض الجديدة التي ستقوم بإنشائها عن طريق نسخ الشبكة المحددة.

18. حدد **موافق**.

19. حدد **تغيير شامل**. يسمح لك **التغيير الشامل** بالاحتفاظ بمبالغ مصفوفة التعويض عن طريق تطبيق زيادة في النسبة المئوية أو المبلغ الأساسي إلى واحد أو أكثر من المستويات أو النقاط المرجعية.

20. في الحقل **مبلغ التسوية**، أدخل رقمًا.

21. في القائمة، قم بوضع علامة أو إلغاء علامة كل الصفوف.

22. انقر فوق **تطبيق على الشبكة**.

23. قم بإغلاق الصفحة. بمجرد أن تقوم بإنشاء بنية تعويض، فإنه يمكنك تحديد النقاط المرجعية التي يجب استخدامها كنقطة التحكم لخطة التعويض الثابت. يتم استخدام نقطة التحكم لحساب نسبة التعويض للموظف.

24. في الحقل **نقطة التحكم**، أدخل قيمة أو حددها.

25. قم بإغلاق الصفحة.

## <a name="create-an-eligibility-rule-for-the-fixed-compensation-plan"></a>إنشاء قاعدة أهلية لخطة التعويض الثابت

يتعذر عليك تعيين خطة التعويض الثابت الجديدة إلى موظف حتى تقوم بتعريف قواعد الأهلية للخطة.  

1. حدد **قواعد الأهلية**.

2. حدد **جديد**.

3. في الحقل **الأهلية**، أدخل أو حدد قيمة.

4. في حقل **الوصف**، أدخل قيمة.

5. في حقل **تاريخ السريان**، أدخل تاريخًا. تستخدم كلاً من خطط التعويض الثابت والمتغير قواعد الأهلية. في الحقل **النوع**، حدد نوع الخطة.

6. في حقل **الخطة**، أدخل قيمة أو حددها. حدد المعايير التي يجب أن يفي بها الموظف لكي يتأهل لخطة التعويض. يمكن أن تتضمن المعايير ما يلي:

    - **قسم**
    - **اتحاد العمال**
    - **الموقع** (**منطقة التعويض**)
    - **الوظيفة**
    - **الوظيفة**
    - **نوع الوظيفة**
    - **مستوى التعويض**
    
    يجب أن يفي الموظف بكل المعايير المحددة لكي يتأهل لخطة التعويض. إذا لم تقم بتحديد أية معايير، فسيتأهل جميع الموظفين لخطة التعويض. إذا لم يتمكن الموظف من استيفاء المعايير المحددة في قاعدة الأهلية، أو لم يتم تحديد قاعدة أهلية لخطة تعويض، فلن تظهر خطة التعويض في البحث عندما تقوم بإنشاء سجل تعويض ثابت لموظف.

7. قم بإغلاق الصفحة.

8. قم بإغلاق الصفحة.
