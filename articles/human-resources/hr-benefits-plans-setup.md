---
title: إنشاء خطة المزايا
description: إعداد خطط المزايا في Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitPlanListPage, BenefitWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6e3822a1071023898e459a82c14ff648d8cdebed
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/06/2020
ms.locfileid: "3230098"
---
# <a name="create-a-benefits-plan"></a>إنشاء خطة المزايا

يوضح هذا المقال كيفية إعداد خطط المزايا في Dynamics 365 Human Resources.

1. في مساحة العمل **إدارة المزايا** ، ضمن **الخطط**، حدد **خطط المزايا**.

2. حدد **جديد**.

3. في علامة التبويب **عام** ، حدد قيمًا للحقول التالية:

   | الحقل | ‏‏الوصف |
   | --- | --- |
   | **الخطة** | المعرف الفريد للخطة. |
   | **‏‏الوصف** | وصف الخطة. |
   | **نوع الخطة** | عندما تُنشئ خطة جديدة، فإنك تحتاج إلى تحديد نوع الخطة. ويعد نوع الخطة تجميعًا عالي المستوي لأنواع معينة من المزايا. يحدد كل نوع خطة ما إذا كان يمكن للموظف التسجيل في خطط متعددة من هذا النوع، ويحدد ما إذا كانت جهات الاتصال مستفيدة أو تابعة، ويحدد خيارات التغطية. يمكنك إنشاء أنواع خطط مخصصة جديدة لتلبية احتياجات عروض المزايا الخاصة بك. وفيما يلي أنواع المزايا الرئيسية: <ul><li>401 ألف</li><li>ADD</li><li>الأسنان</li><li>ملائم</li><li>FSA</li><li>الحياة</li><li>LTD</li><li>طبي</li><li>PTO</li><li>STD</li><li>الرؤية</li></ul> |
   | **كود نوع الخطة** | كود نوع الخطة الخاص بنوع الخطة. |
   | **البرنامج** | تحديد برنامج لتعيين الخطة اختياريًا إليه. |
   | **مجموعة** | تحديد ‏‫مجموعة لتعيين الخطة اختياريًا إليها. |
   | **الرئيسية** | تحديد ما إذا كانت الخطة هي الخطة الرئيسية داخل المجموعة التي تم تعيينها إليها. |
   | **الحالة** | يشير إلى الوضع الحالي لخطة المزايا. القيمة الافتراضية نشط. إذا قمت بتغيير الحالة إلى غير نشط، فلن تكون الخطة متاحة كاختيار أثناء التسجيل. |
   | **صالح من التاريخ والوقت** | تاريخ ووقت بدء الخطة. والقيمة الافتراضية هي تاريخ النظام الحالي. |
   | **صالح إلى التاريخ والوقت** | تاريخ ووقت انتهاء الخطة (تم تعيين الحالة إلى غير نشط). القيمة الافتراضية هي 12/31/2154، والتي تشير إلى ابدًا. |

4. في علامة التبويب **تكوين** ، حدد قيمًا للحقول التالية استنادًا إلى نوع الخطة التي تقوم بإنشاءها:

   | نوع الخطة | الحقل | ‏‏الوصف |
   | --- | --- | --- |
   | الطبية (طبي، أسنان، عيون، HMO) | COBRA | يحدد ما إذا كانت الخطة مؤهلة لـ COBRA (قانون تسوية الموازنة الموحدة الشامل). |
   | الطبية (طبي، أسنان، عيون، HMO) | HIPAA | يحدد ما إذا كانت الخطة مؤهلة لـ HIPAA (قانون قابلية التأمين الصحي وقابلية المساءلة). |
   | <ul><li>الطبية (طبي، أسنان، عيون، HMO)</li><li>أخرى (PTO، ملائم)</li><li>‏‏غير ذلك</li><li>الإعاقة طويلة الأجل</li><li>ADD (تأمين الحياة الأساسي، تأمين الحياة الاختياري)</li><li>المدخرات (على سبيل المثال، 401 (ألف))</li><li>FSA</li></ul> | الضريبة المسبقة المستحقة | يحدد ما إذا كان يمكن دفع مساهمات في الخطة قبل تطبيق الضرائب أم لا. |
   | <ul><li>الطبية (طبي، أسنان، عيون، HMO)</li><li>أخرى (PTO، ملائم)</li><li>الإعاقة طويلة الأجل</li><li>ADD (تأمين الحياة الأساسي، تأمين الحياة الاختياري)</li><li>المدخرات (على سبيل المثال، 401 (ألف))</li><li>FSA</li></ul> | ترحيل الضريبة المستحقة | يحدد ما إذا كان يمكن إجراء المساهمات في الخطة بعد تطبيق الضرائب أم لا. |
   | <ul><li>الطبية (طبي، أسنان، عيون، HMO)</li><li>أخرى (PTO، ملائم)</li><li>الإعاقة طويلة الأجل</li><li>ADD (تأمين الحياة الأساسي، تأمين الحياة الاختياري)</li><li>المدخرات (على سبيل المثال، 401 (ألف))</li><li>FSA</li></ul> | المساهم | يحدد من يساهم في الخطة – الموظف، صاحب العمل أو كليهما. |
   | <ul><li>الإعاقة طويلة الأجل</li><li>ADD (تأمين الحياة الأساسي، تأمين الحياة الاختياري)</li></ul> | التغطية الدنيا | الحد الأدنى لمبلغ التغطية التأمينية المطلوب للخطة. |
   | <ul><li>الإعاقة طويلة الأجل</li><li>ADD (تأمين الحياة الأساسي، تأمين الحياة الاختياري)</li></ul> | التغطية القصوى | الحد الأقصى لمبلغ التغطية التأمينية المطلوب للخطة. |
   | <ul><li>الإعاقة طويلة الأجل</li><li>ADD (تأمين الحياة الأساسي، تأمين الحياة الاختياري)</li></ul> | استخدام زيادات التغطية | يحدد ما إذا كان يجب التحقق من أن مبلغ التغطية يطابق مبلغًا تزايديًا صالحًا. |
   | <ul><li>الإعاقة طويلة الأجل</li><li>ADD (تأمين الحياة الأساسي، تأمين الحياة الاختياري)</li></ul> | المبلغ التزايدي | المبلغ التزايدي للتغطية التأمينية المطلوب للخطة. على سبيل المثال، إذا كان المبلغ التزايدي هو 1,000، فلا يمكن أن يكون لأحد الموظفين 200,500 دولار للتأمين، سيحتاجون إلى التقريب إلى 201,000 دولار أو إلى 200,000 دولار. |
   | <ul><li>الإعاقة طويلة الأجل</li><li>ADD (تأمين الحياة الأساسي، تأمين الحياة الاختياري)</li></ul> | الاتجاه التزايدي | لتحديد اتجاه التقريب – سواء لأعلى أو لأسفل-عندما لا يحقق مبلغ التغطية قيمة المبلغ التزايدي. |
   | ADD (تأمين الحياة الأساسي، تأمين الحياة الاختياري) | دليل القابلية للتأمين | يحدد ما إذا كان يجب علي الموظف توفير دليل القابلية للتأمين. |
   | ADD (تأمين الحياة الأساسي، تأمين الحياة الاختياري) | ‏‏المقدار | المبلغ بالعملة المحاسبية. يكون هذا الحقل نشطًا فقط إذا تم تحديد خانة الاختيار دليل القابلية للتأمين. |
   | <ul><li>المدخرات (على سبيل المثال، 401 (ألف))</li><li>FSA</li></ul> | المساهمة الدنيا السنوية | الحد الأدنى لمبلغ المساهمة المطلوب للخطة. |
   | <ul><li>المدخرات (على سبيل المثال، 401 (ألف))</li><li>FSA</li></ul> | المساهمة القصوى السنوية | الحد الأقصى لمبلغ المساهمة المطلوب للخطة. |
   | المدخرات (على سبيل المثال، 401 (ألف)) | أقصى مبلغ سنوي لصاحب العمل | الحد الأقصى للمبلغ المسموح به لصاحب العمل للمساهمة في خطة مدخرات الموظفين خلال فترة الميزة. ينبغي عليك تحديد خانة اختيار مطابقة لصاحب العمل لاستخدام هذا الحقل. |
   | المدخرات (على سبيل المثال، 401 (ألف)) | مطابقة صاحب العمل | يحدد ما إذا كان صاحب العمل يساهم في خطة ادخار الموظف. |
   | المدخرات (على سبيل المثال، 401 (ألف)) | النسبة المئوية لمطابقة صاحب العمل | النسبة المئوية لمساهمة الموظف التي سيطابقها صاحب العمل. |
   | المدخرات (على سبيل المثال، 401 (ألف)) | سقف مطابقة صاحب العمل | الحد الأقصى للنسبة التي سيتوافق معها صاحب العمل. على سبيل المثال، إذا كان صاحب العمل سوف يطابق 100٪ من مساهمات الموظفين حتى 6٪ من أجر الموظف، فإن الحد الأقصى لمطابقة صاحب العمل هو 6٪. |

5. في علامة التبويب **إعداد** ، حدد قيمًا للحقول التالية:

   | الحقل | ‏‏الوصف |
   | --- | --- |
   | **إتاحة/متابعة التسجيل** | يحدد ما إذا كان بإمكان الموظفين التسجيل في الخطة إذا استوفوا متطلبات الأهلية.</br></br>وفي حالة تعيين ذلك إلى "لا"، فلن تكون الخطة متاحة للموظفين عند معالجة الأهلية. |
   | **التسجيل التلقائي من السنة السابقة** | لتحديد ما إذا كان سيتم تلقائيًا تسجيل موظف مستحق في الخطة إذا تم تسجيله أثناء السنة السابقة. |
   | **التسجيل التلقائي افتراضيًا** | تحديد ما إذا كان سيتم تحديد خطة التسجيل افتراضيًا. الخطة ليست إلزامية، لذلك يمكن للموظف تغيير التحديد الافتراضي. |
   | **تم الإغلاق للتسجيلات الجديدة** | تحديد ما إذا كان سيتم تقييد الخطة على الموظفين المؤهلين فقط الذين تم تسجيلهم في الخطة في السنة السابقة. |
   | **خطة إلزامية** | تحديد ما إذا كان سيتم تسجيل الموظفين تلقائيًا في الخطة أم لا. لا يمكن للموظفين تغيير اختيار التسجيل. |
   | **تاريخ البدء** | تاريخ إنشاء الخطة في الشركة. |
   | **حساب المورّد** (مورّد الميزة) | المورد الذي تدفع الشركة له أقساط التأمين مقابل الخطة. |
   | **الاسم** (مورّد الميزة) | اسم المورد. |
   | **مرجع المورّد** (مورّد الميزة) | مرجع المورد للخطة. على سبيل المثال، رقم خطة المجموعة الخاصة بالشركة. |
   | **مرجع بديل** (مورّد الميزة) | مرجع المورد البديل للخطة. على سبيل المثال، رقم حساب الشركة. |
   | **العملة** (مورّد الميزة) | العملة المستخدمة لدفع أقساط التأمين إلى المورد. |
   | **حساب المصاريف** (مورّد الميزة) | حساب دفتر الأستاذ العام الذي يتم استخدامه كحساب المصاريف لأقساط الخطة. |
   | **حساب المورّد** (مسؤول الميزة) | المورد الذي تدفع له الشركة لإدارة الخطة. إذا كانت الخطة ذاتية الإدارة، فاترك هذا الحقل فارغًا. |
   | **الاسم** (مسؤول الميزة) | اسم المورد مسؤول الميزة. |
   | **مرجع المورّد** (مسؤول الميزة) | مرجع المورد المسؤول للخطة. |
   | **مرجع بديل** (مسؤول الميزة) | مرجع بديل للمورد المسؤول عن الخطة. |
   | **العملة** (مسؤول الميزة) | العملة المستخدمة للدفع إلى مسؤول المزايا. |
   | **حساب المصاريف** (مسؤول الميزة) | حساب دفتر الأستاذ العام الذي يتم استخدامه كحساب مصروفات للتكاليف المرتبطة بإدارة الخطة. |

6. في علامة التبويب **عوامل التصفية** ، قم بالتصفية حسب الضرورة. يمكنك التصفية حسب الحقول التالية:

   - **وحدة الأعمال**
   - **قسم**
   - **كيان قانوني**
   - **الموقع**
   - **المهنة**

7. في علامة التبويب **قواعد الأهلية** ، حدد قيمًا للحقول التالية:

   | الحقل | ‏‏الوصف |
   | --- | --- |
   | **رقم البند** | رقم بند قاعدة الأهلية. |
   | **قاعدة الاستحقاق** | قاعدة الأهلية المطلوب تطبيقها علي خطة الميزة. تُطبق قاعدة الأهلية هذه على نوع الإجراء المقابل وترتبط بفترة انتظار التغطية المحددة والخصومات. |
   | **نوع الإجراء** | الإجراء الذي يُطبق قاعدة الأهلية على: تسجيل المزايا أو انتهاء صلاحية المزايا. |
   | **فترة انتظار التغطية** | قيمة من نموذج فترات الانتظار. تدفع فترة انتظار التغطية عدد الأيام أو الأشهر التي ينتظرها الموظف لتغطية الميزة أو انتهاء صلاحية الميزة وفقًا للمعايير الموجودة في قاعدة الأهلية ونوع الإجراء. |
   | **فترة انتظار الخصم** | قيمة من نموذج فترات الانتظار. توفر فترة انتظار الخصوم عدد الأيام أو الأشهر التي ينتظرها الموظف لخصومات الميزة من شيك راتبه بناءً على المعايير الموجودة في قاعدة الأهلية ونوع الإجراء. |

8. حدد **حفظ**.

## <a name="view-enrolled-workers"></a>عرض العمال المسجلين

يمكنك عرض العمال المسجلين في خطة المزايا المحددة.

1. في مساحة العمل **إدارة المزايا** ، ضمن **الخطط**، حدد **خطط المزايا**.

2. حدد **العمال المسجلين**.

## <a name="attach-coverage-options"></a>إرفاق خيارات التغطية

يمكنك إضافة خيارات التغطية لخطة المزايا المحددة. يؤدي إرفاق خيارات التغطية إلى جمع إعداد المعدل والخصم معًا لخيار التغطية.  مثال: بالنسبة للخطة الطبية، سيختار المستخدم خيار التغطية العائلية.  سيحتاجون بعد ذلك إلى تحديد معدل العائلة للخطة المرتبطة (المُعين في إعداد المعدل) وخصم الخطة المرتبطة (المُعين في إعداد المعدل). ويوفر ذلك تكلفة صاحب العمل والموظف لتغطيه محددة. ثم يمكنك تكرار العملية لتغطية موظف + 1 أو تغطية الموظف.

1. في مساحة العمل **إدارة المزايا** ، ضمن **الخطط**، حدد **خطط المزايا**.

2. حدد **إرفاق خيارات التغطية**.

## <a name="override-eligibility-rules"></a>تجاوز قواعد الأهلية

يمكنك إضافة عمال إلى خطة كاستثناءات لقواعد الأهلية. يكون كل عامل يتم إضافته مؤهلاً لخطة المزايا.

1. في مساحة العمل **إدارة المزايا** ، ضمن **الخطط**، حدد **خطط المزايا**.

2. حدد **تجاوز قواعد الأهلية**.

## <a name="view-attached-periods"></a>عرض فترات مرفقة

يمكنك الاطلاع على قائمة بفترات المزايا المتاحة.

1. في مساحة العمل **إدارة المزايا** ، ضمن **الخطط**، حدد **خطط المزايا**.

2. حدد **فترات**.

## <a name="view-plan-information"></a>عرض معلومات الخطة

يمكنك تقديم وصف للخطة لمساعدة الموظفين في تحديد مزاياهم. يتم عرض معلومات الخطة التي تقوم بإدخالها هنا في الخدمة الذاتية للموظفين عند تمرير الماوس علي الخطة في قائمة خيارات التغطية.

1. في مساحة العمل **إدارة المزايا** ، ضمن **الخطط**، حدد **خطط المزايا**.

2. حدد **معلومات الخطة**.

## <a name="view-flex-credit-programs"></a>عرض برامج الائتمان المرنة

1. في مساحة العمل **إدارة المزايا** ، ضمن **الخطط**، حدد **خطط المزايا**.

2. حدد **برامج الائتمان المرنة**.