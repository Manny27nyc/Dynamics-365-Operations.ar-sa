---
title: إنشاء خطط التعويض الثابت
description: يشير التعويض الثابت إلى الأجر أو الراتب الإجمالي المنتظم للموظف. توضح هذه المقالة المكونات التي يجب إعدادها قبل أن تتمكن من إنشاء خطة التعويض الثابت وتسجيل الموظفين.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HRCCompGrid, HRCCompRefPointSetup, HRMCompEligibility, HRMCompEvent, HRMFixedCompPlanTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 15991
ms.assetid: ef8cf992-176c-4c98-9dff-6510e1eb9f1c
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 05eea520c656619d72d4601991e255ae887ffe9c
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008012"
---
# <a name="create-a-fixed-compensation-plans"></a>إنشاء خطط التعويض الثابت

يشير التعويض الثابت إلى الأجر أو الراتب الإجمالي المنتظم للموظف. توضح هذه المقالة المكونات التي يجب إعدادها قبل أن تتمكن من إنشاء خطة التعويض الثابت وتسجيل الموظفين.

يمكن حساب مبالغ التعويض الثابت للموظفين، على أساس عوامل مثل الأداء والمنطقة وزيادات الموازنة. يدعم Dynamics 365 Human Resources أنواع تعويضات الخطوة والدرجة والنطاق.

## <a name="fixed-compensation-components"></a>مكونات التعويض الثابت
### <a name="compensation-levels"></a>مستويات التعويض

‏‫يمكنك استخدام **‬‏‫مستويات التعويض** لتعيين التعويض لمهن مختلفة، وللمساعدة في ضمان دفع الأجور للموظفين الذين يشغلون الوظائف بشكل عادل. وفي صفحة **مستويات التعويض‬‏‫**، يمكنك إعداد مستويات التعويض المطلوبة لكل خطوة ودرجة وخطة نطاق.‬ واستخدام الزرين **لأعلى** و**لأسفل** لوضع المستويات بالترتيب الصحيح، وفقًا لنوعها. ومن خلال تعيين مستويات التعويض في وظيفة، تساعد على ضمان دفع الأجور لجميع الموظفين الذين يشغلون منصب في تلك الوظيفة بنفس المستوى.

### <a name="reference-points"></a>النقاط المرجعية

**النقاط المرجعية** هي الأعمدة الموجودة في الشبكة والتي تحدد نطاقات التعويض لكل مستوى. مستوى التعويض هو الصف في الشبكة. ‏‫النقاط المرجعية النموذجية لخطة نوع الدرجة هي الحد الأدنى والنقطة الوسط والحد الأقصى. ويمكنك إنشاء نقاط مرجعية في صفحة **‬‏‫إعدادات النقاط المرجعية**.

### <a name="compensation-grids"></a>شبكات التعويض

بعد تعيين المستويات والنقاط المرجعية، يمكن دمجها لإنشاء **شبكة التعويض**. وفي صفحة **شبكات التعويض**، حدد المعلومات المتعلقة بالشبكة. على سبيل المثال، حدد الشبكة المصممة المراد استخدامها ونوع الخطة التي سيتم استخدامها في الشبكة والنقاط المرجعية أو الأعمدة المطلوبة في الشبكة. وبعد الانتهاء من إدخال هذه المعلومات، انقر فوق **بنية التعويض** لإضافة المستويات والمبالغ إلى الشبكة. 

**تلميح:** استخدم وظيفة **التغييرات الجماعية** في بنية التعويض لتحديد المبالغ الأولية، ثم قم بزيادة المبالغ أو النسب المئوية عبر المستويات أو النقاط المرجعية الخاصة بك.

### <a name="pay-frequencies"></a>تكرارات الدفع

**تكرارات الدفع** يتم استخدامها لتحديد الطريقة التي يتم بها تحديد أجر أو مرتب الموظف (على سبيل المثال 10 دولارات في الساعة مقابل 50,000 دولار في السنة)، والتحويل بين المعدلات بالساعة والأسبوع والشهر (12 شهرًا) والسنة. على سبيل المثال، تثوم إحدى الشركات التي تستخدم أسبوع العمل المشتمل على 38 ساعة لموظفيها العاملين بالساعة بإعداد تكرار الدفع بمعدل 1، ومعدل أسبوعي 38، ومعدل شهري 164.6666666667، ومعدل سنوي يبلغ 1,976. يتم استخدام هذه التحويلات لحساب معدلات الدفع المختلفة التي تظهر في سجل التعويض الثابت للموظف.

## <a name="fixed-compensation-plans"></a>خطط التعويض الثابت
يمكنك تصميم خطة التعويض الثابت لضم كافة المكونات التي قمت بتكوينها. ولإنشاء خطة تعويض ثابتة، افتح صفحة **خطط التعويض الثابت**. وهنا، يمكنك إعطاء الخطة الخاصة بك اسمًا ووصفًا، وتحديد نوع الخطة (الخطوة أو الدرجة أو النطاق)، وتحديد تكرار الدفع الذي ستستخدمه لمعدل دفع الموظف (المبلغ في الساعة، والمبلغ كل سنة، وهكذا)، وتعيين بعض الخيارات التي تتحكم في كيفية معالجة التعويض. 

يتيح لك إعداد **التفاوت الخارج عن النطاق‬** تحديد مدى الصرامة التي تريد أن تكون عليها عن التأكد من أن هناك مبالغ تعويض بين الحد الأدنى والحد الأقصى للمبالغ. ويتطلب التفاوت **الثابت** أن يكون التعويض ضمن النطاق المحدد لمستوى معين. وينبهك التفاوت **المرن** عندما يكون مبلغ التعويض خارج النطاق ولكنه يسمح لك بالمتابعة. وفي حالة تعيين التفاوت إلى **لا شيء**، يمكنك إدخال أي مبلغ تعويض لموظف دون تلقي رسائل خطأ أو تحذير. 

تتيح لك **قاعدة التوظيف** تحديد ما إذا كان يجب أن يتلقى جميع الموظفين نفس الزيادة، بغض النظر عن التاريخ الذي تم تعيينهم فيه (**قاعدة التوظيف** = **لا شيء**)، أو ما إذا كان ينبغي أن يتلقى الموظفون نسبة مئوية من المكافأة، استناداً إلى المدة التي كانوا يعملون خلالها أثناء الدورة (**قاعدة التوظيف** = **في المائة**). 

وتفيد **مصفوفة استخدام النطاق** إذا كنت تريد إما لتقليل الوقت اللازم للموظفين للوصول إلى نقطة الوسط في نطاقها، أو زيادة الوقت اللازم للموظفين للوصول إلى نقطة مرجعية قصوى في النطاق. على سبيل المثال، تحتاج إلى إعطاء الموظفين الموجودين في أسفل من 25 في المائة من النطاق الخاص بهم نسبة 110 لنطاقهم هذه المنحة المستهدفة الخاصة بهم، ولكن تحتاج إلى إعطاء الموظفين الموجودين في أعلى من 25 بالمائة من النطاق الخاص بهم فقط 80 في المائة من هذه المنحة المستهدفة، لمنعهم من الوصول إلى الحد الأقصى بأسرع وقت. 

وبعد تحديد أساسيات خطة التعويض الثابتة، يمكنك إعداد بنية تعويض للخطة. انقر فوق **إعداد التعويض**. يتم فتح شريط تمرير حوار يوفر ثلاثة خيارات:‬

-   إنشاء شبكة تعويض جديدة عن طريق تحديد إعداد نقطة مرجعية وإعطاء اسم للشبكة.
-   إنشاء شبكة تعويض جديدة بعمل نسخة من شبكة موجودة يمكنك استخدامها كنقطة بداية.
-   استخدام شبكة تعويض موجودة تم تحديدها مسبقاً. تتلقي كافة خطط التعويض التي تستخدم الشبكة نفس التحديثات إذا تم تغيير هذه الشبكة.

بعد تحديد خيار، يتم فتح صفحة **بنية التعويض**، ويمكنك إجراء تغييرات على شبكة التعويض الجديدة أو شبكة التعويض الموجودة.

## <a name="fixed-compensation-enrollment"></a>تسجيل التعويض الثابت
### <a name="determine-who-is-eligible-for-the-plan"></a>تحديد الشخص المؤهل للخطة

الخطوة الأولى في تسجيل الموظفين في خطة تعويض ثابت هي تحديد الشخص المؤهل للتعويض المحدد في الخطة. وحتى يمكنك تحديد الأهلية، لن تتمكن من تعيين الخطة لأي موظفين. ‏‫ولإعداد الأهلية، افتح صفحة **قواعد الأهلية**. وهنا، يمكنك إنشاء قاعدة أهلية جديدة لخطة التعويض وتحديد المعايير التي يجب أن يستوفيها موظف ليكون مؤهلاً لخطة.‬ يمكنك تقييد الأهلية استنادًا إلى القسم أو اتحاد العمال منطقة التعويض (الموقع) أو المهمة أو الوظيفة أو نوع الوظيفة أو مستوى التعويض. ولا يمكن تسجيل الموظفين في خطة تعويض إلا إذا كانوا يستوفون كافة الشروط التي تم تعيينها في قاعدة الأهلية. 

**ملاحظة** يتم استخدام قواعد الأهلية لتحديد الأهلية لكلٍّ من خطط التعويض الثابت والمتغير. 

وتراعي قاعدة الأهلية قيمة حقول محددة في سجلات الوظيفة والمنصب والموظف لتحديد ما إذا كان موظف مؤهلاً لخطة تعويض.

-   في صفحة **الوظيفة**، تراعي قاعدة الأهلية الحقول التالية:
    -   حقل **الوظيفة**
    -   في علامة التبويب **تصنيف وظيفة**، في حقلي **المهمة** و**نوع الوظيفة**
    -   في علامة التبويب **التعويض**، في حقل **المستوى**
-   في صفحة **المناصب**، تراعي قاعدة الأهلية حقلي **الإدارة** و**منطقة التعويض**.

كما تراعي قاعدة الأهلية اتحادات العمال المرتبطة بالموظف (في صفحة **الموظفين**، في علامة التبويب **العامل**، انقر فوق **المعلومات الشخصية** &gt; **اتحادات العمال**).

### <a name="define-fixed-compensation-actions"></a>تحديد إجراءات التعويض الثابت

يتم استخدام **إجراءات التعويض الثابت** عندما تقوم بتعيين أو تطبيق تغييرات على التعويض الثابت لموظف. وتتيح لك إجراءات التعويض الثابت توفير أسماء وصفية لأنواع الإجراءات التي يمكن لمدير التعويضات والاستحقاقات تنفيذها. وتشتمل أنواع الإجراءات المختلفة على منطق خاص بها بحيث يمكن استخدامها في أوقات معينة. 

على سبيل المثال، عند إعداد التعويض الثابت لموظف، لا يمكن استخدام سوى الإجراءات التي تحتوي على نوع **تعيين/إعادة التعيين**. وفي هذه الحالة، قد تحتاج إلى إنشاء ثلاثة إجراءات مختلفة من نوع **التعيين/إعادة التعيين**، وأطلق عليها أسماء **التعيين**، و**إعادة التعيين**، و**النقل**. ويتوفر لك فيما بعد شرح أكثر تفصيلاً لسبب إعطاء التعويض لموظف أو تغييره.

### <a name="enroll-the-employee"></a>تسجيل الموظف

يمكنك الآن تعيين موظف جديد لخطة تعويض ثابت. افتح صفحة **الموظفين**، وقم بتحديد الموظف لتسجيله في خطة التعويض. في جزء الإجراءات، انقر فوق **التعويض** &gt; **‬‏‫الخطة الثابتة**. ويمكنك الآن إنشاء إجراء تعويض ثابت جديد لهذا الموظف.‬ 

**ملاحظة:** لا يُظهر حقل خطة التعويض سوى الخطط التي يكون الموظف مؤهلاً لها بموجب قواعد الأهلية التي تم إعدادها لكل خطة. وإذا لم يتم إعداد أي قاعدة أهلية لخطة، لن يكون أي موظف مؤهلاً لتلك الخطة. 

ويتحقق النظام من وجود مبلغ التعويض المحدد لخطة تعويض من نوع الدرجة أو النطاق ضمن الحد الأدنى والحد الأقصى للنقاط المرجعية لمستوى التعويض المحدد في وظيفة الموظف. إذا كان مبلغ التعويض خارج النطاق المسموح به، فإنه يتم عرض رسالة تحذير أو رسالة خطأ، تبعاً لمستوى التفاوت الذي يتم تعيينه في خطة التعويض الثابت.
