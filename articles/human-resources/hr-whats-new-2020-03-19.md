---
title: ما الجديد أو المتغير في Dynamics 365 Human Resources (19 مارس 2020)
description: يصف هذا المقال الميزات الجديدة أو المتغيرة في Microsoft Dynamics 365 Human Resources.
author: Darinkramer
manager: AnnBe
ms.date: 03/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-03-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d6988bb95cf2ffe8146434f4b194d97491952915
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/21/2020
ms.locfileid: "3157356"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-19-2020"></a>ما الجديد أو المتغير في Dynamics 365 Human Resources (19 مارس 2020)

تصف هذه المقالة الميزات الجديدة أو المتغيرة في Dynamics 365 Human Resources. يتم تطبيق التغييرات على رقم الإصدار 8.1.3014. تشير الأرقام الموجودة بين أقواس في بعض العناوين إلى أرقام دعم المرجع في  Lifecycle Services (LCS).

## <a name="human-resources-environment-limits-are-now-based-on-updated-licensing-394595"></a>تعتمد حدود بيئة Human Resources الآن على الترخيص الذي تم تحديثه (394595)

تم تغيير الحد المعين لعدد البيئات لكل مشروع في Lifecycle Services (LCS). الحد السابق هو اثنين من البيئات. يتم الآن تحديد عدد بيئات الإنتاج وآلية تحديد الصلاحيات التي يمكنك إنشاؤها لـ Human Resources في LCS الآن استنادًا إلى الترخيص الذي تم تحديثه. يمكنك الآن إنشاء العديد من البيئات حسب الحاجة لمشروع LCS، استنادًا إلى عدد التراخيص التي تم شراؤها. يسمح الترخيص الجديد، الذي تم تحديثه في 1 فبراير 2020، للعملاء بشراء بيئات إضافيه. لمزيد من المعلومات حول متطلبات الترخيص للبيئات الإضافية، راجع [دليل ترخيص Dynamics 365](https://dynamics.microsoft.com/pricing/#HumanResources).

## <a name="provide-cross-company-viewing-of-compensation-data-for-employees-and-managers-403904"></a>توفير العرض المشترك بين الشركات لبيانات التعويض للموظفين والمديرين (403904)

قم بتشغيل هذه الميزة في مساحة عمل **إدارة الميزات**. لمزيد من المعلومات، راجع [تمكين أو تعطيل ميزات المعاينة](hr-admin-manage-features.md#enable-or-disable-preview-features).

عند تمكين هذه الميزة، يمكن للمديرين الاطلاع على تعويض التقارير المباشرة والموسعة دون الحاجة إلى تسجيل الدخول إلى شركة التوظيف. تتوفر محفوظات التعويض الكامل من أي شركة مسجلة يمكن للمدير الوصول إليها. لمزيد من المعلومات، راجع [نظرة عامة على الخدمة الذاتية للموظف والمدير](hr-employee-manager-self-service-overview.md).

## <a name="enable-global-address-book-merge-functionality-427189"></a>تمكين وظيفة دمج دفاتر العناوين العمومية (427189)

يمكنك الآن دمج إدخالات دفاتر عناوين مكررة وذلك بتحديد السجلات المكررة واختيار **دمج** من صفحة **دفتر العناوين العمومي**.

## <a name="unable-to-adjust-leave-balance-for-a-plan-with-no-accruals-that-was-created-with-the-multiple-leave-type-feature-on-419635"></a>يتعذر تعديل رصيد الإجازات لإحدى الخطط دون استحقاقات تم إنشاؤها باستخدام ميزة "نوع الإجازة المتعددة" في (419635)

يمكنك الآن تعديل الأرصدة للحصول على خطط الإجازات التي تم إنشاؤها في ميزة معاينة **نوع الإجازة المتعددة** الممكّنة في إدارة الميزات.

## <a name="primary-position-field-in-the-workerpositionassignmententity-when-an-employee-is-terminated-420774"></a>حقل المنصب الأساسي في WorkerPositionAssignmentEntity عند إنهاء عمل الموظف (420774)

بالنسبة للموظفين الذين تم إنهاء توظيفهم، يتم عرض المنصب الأساسي الذي كان نشطًا في وقت الإنهاء في الكيان. بالنسبة لعمليات التكامل، لن يتم بعد ذلك إنشاء سجل مكرر لتعيين منصب العامل الخاص بالموظف. 

## <a name="common-data-service-solution-is-now-available-with-the-following-changes"></a>يتوفر حل Common Data Service الآن مع التغييرات التالية:

| ‏‏الوصف | تغيير |
| --- | --- |
| تغييرات كيان **الوظيفة/المنصب** | <ul><li>تم إضافة **منطقة التعويض**</li>|
| تمت إضافة كيان **بُعد منصب الوظيفة** | <ul><li>تمت إضافة **الأبعاد المالية**</li>
| تغييرات كيان **العامل** | <ul><li>تمت إضافة **تسلسل الاسم**</li><li>تم إضافة **الأعمال من الصفحة الرئيسية**</li><li>تمت إضافة **اللغة**</li><li>تمت إضافة **تاريخ الأقدمية**</li><li>تمت إضاف **تاريخ التفعيل السنوي**</li><li>تمت إضافة **تاريخ التوظيف الأصلي**</li></ul> |
| تغييرات كيان **التوظيف** | <ul><li>تمت إضافة **الأبعاد المالية**</li><li>تمت إضافة **سبب الإنهاء**</li><li>تمت إعادة تسمية **تاريخ الإنهاء** من **تاريخ الانتقال**</li><li>تمت إضافة **تاريخ فترة الاختبار**</li></ul> |
| تغييرات كيان **عنوان العامل** | <ul><li>تمت إضافة **عنوان الشارع**</li><li>**سطر العنوان 1**، و**سطر العنوان 2**، و**سطر العنوان 3** المميز للإهلاك</li></ul> |
| كيانات إعداد التعويض المتغيرة الجديدة | <ul><li>**نوع خطة التعويض المتغير**</li><li>**خطة التعويض المتغيرة**</li><li>**قواعد الاستحقاق**</li><li>**مستوى خطة التعويض المتغير**</li></ul> |
| كيان **توظيف تقويم العامل** الجديد | <ul><li>تمت إضافة **كيان تقويم العمل**</li></ul> |
| كيان **تفاصيل المنصب في كشف الرواتب** الجديد | <ul><li>تمت إضافة **تفاصيل المنصب في كشف الرواتب**</li></ul> |
| كيان **العنوان** الجديد | <ul><li>تمت إضافة **العنوان**</li></ul>تم تضمين كيان **العنوان** الجديد في Common Data Service ولكن لا تتم الإشارة إليها من الكيانين **منصب الوظيفة‬** أو **الوظيفة‬‏‎** في هذا الوقت. |

> [!NOTE]
> توفر الأبعاد المالية لكل من المنصب والتوظيف تكاملاً أحادي الاتجاه للتحديثات من Human Resources إلى Common Data Service. في الوقت الحالي، لا تتم مزامنة تحديثات الأبعاد المالية من Common Data Service إلى Human Resources.

خلال الأسابيع القليلة التالية، ستتوفر هذه التغييرات الخاصة بالكيانات في كافة البيئات. لتثبيت حل Common Data Service الأحدث لـ Human Resources:

1.  انتقل إلى [مركز إدارة Power Platform](https://admin.powerplatform.microsoft.com).

2.  حدد **بيئات**.

3.  ابحث عن البيئة التي تريد ترقيتها. يجب أن تتطابق البيئة مع **اسم البيئة** في قسم **Common Data Service المعلومات** في النموذج **حول** في Human Resources.

4.  حدد البيئة لعرض تفاصيل البيئة.

5.  حدد **إدارة الحلول** في شريط الإجراءات في الجزء العلوي. ستفتح نافذة مستعرض جديدة وتنتقل إلى **مركز إدارة Dynamics 365** في سياق بيئتك.

6.  في قائمة **الحل**، حدد **ارتساء Dynamics 365 Human Resources**.

7.  حدد **ترقية** لتطبيق الحل الأخير.

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a>معاينة SharePoint لا تعمل في بعض البيئات

إذا كانت معاينة المستندات للمستندات المخزنة في SharePoint لا تعمل، جرب الإجراء التالي:

1. تحقق من وجود بريد إلكتروني مقترن بحساب المستخدم المسؤول. يمكنك عرض هذه المعلومات في صفحة **المستخدم**. إذا لم يتم إعداد البريد الإلكتروني، فأنت بحاجة إلى إضافة البريد الإلكتروني والموفر مع وظيفة Excel في OData. افتراضيًا، لا يكون عنوان البريد الإلكتروني موجودًا في تصميم Excel. ستحتاج إلى تحرير تصميم Excel، وإضافة جميع الحقول والتطبيق والتحديث. بمجرد إكمال هذه الخطوات، يمكنك تحديث حساب المسؤول.

2. بعد أن يحتوي حساب المسؤول على حساب بريد إلكتروني مقترن، قم بتسجيل الدخول إلى Human Resources باستخدام بيانات اعتماد المسؤول.

3. يمكنك الوصول إلى مرفق في SharePoint لبدء معاينة المستند.

4. قم بتسجيل الدخول باستخدام حساب مستخدم آخر له حق الوصول إلى المرفقات وتحقق من أن المعاينة تعمل كما هو متوقع.

## <a name="coming-soon"></a>قريبًا

### <a name="platform-update-33"></a>update 33 للنظام الأساسي

- تطبيقات الصفحة الكاملة (معاينة) - تسمح ميزة المعاينة هذه، التي تتطلب منك تمكين ميزة طرق العرض المحفوظة، بإضافة تطبيقات Power Apps وتطبيقات من جهة خارجية كتجارب صفحة كاملة عبر لوحة المعلومات.

- طرق العرض المحفوظة (معاينة) - تمكّن ميزة المعاينة طرق العرض المحفوظة، والتي توفر تحسينًا ملحوظًا للنظام الفرعي للتخصيص. تسمح هذه الميزة للمستخدمين بالحصول على عدة مجموعات مسماة من التخصيصات لكل صفحة. يمكنك أيضًا نشر طرق العرض لأدوار الأمان.

- تحسين تجربة التصفية "أحد مما يلي" - تمكن هذه الميزة ‏‫تحسين تجربة التصفية "أحد ما يلي"‬ التي تسهل إدخال قيم عوامل تصفية متعددة، وتشتمل على آلية أبسط لإزالة القيم الفردية أو جميع قيم عامل التصفية، كما تشتمل على مؤثرات عرض لقيم عامل التصفية أكثر بساطة وأصغر حجمًا.

- الحقول المخصصة - يحتاج المستخدمون في أغلب الأحيان إلى إضافة حقول إلى شبكة أو صفحة. قد يكون هذا الأمر صعبًا مع وجود عدد كبير من الحقول المتوفرة. بدلاً من البحث عبر قائمة كبيرة، تسمح هذه الميزة للنظام بإظهار مجموعة من الحقول الموصى بها استنادًا إلى ما يضيفه المستخدمون الآخرون في أغلب الأحيان في سيناريوهات مماثلة.‬

- الإجراءات الافتراضية الثابتة في الشبكات‬ - تضمن هذه الميزة أن الإجراء الافتراضي في إحدى الشبكات مرتبط بعمود معين في شبكة، بغض النظر عما إذا كان قد تم نقل هذا العمود أو إخفاؤه.

## <a name="new-production-release-cadence"></a>وتيرة إصدار الإنتاج الجديدة

اعتبارًا من شهر أبريل، سيتم تبديل الإصدار التالي لـ Human Resources من تحديث أسبوعي إلى تحديث كل أسبوعين. سيتم التأكد من المحاذاة باستخدام الممارسات الآمنة للتوزيع والاحتفاظ بمقاييس عالية لمستوى الاستقرار والموثوقية في الخدمة. نقوم بإجراء اختبارات إضافية وأجهزة عرض للتحقق من النشر الناجح في كل مرحلة من العملية. لمزيد من المعلومات حول وتيرة الإصدار، راجع [عملية التحديث](hr-admin-setup-update-process.md).

## <a name="in-preview"></a>قيد المعاينة

تتوفر ميزات المعاينة التالية في 3 فبراير، 2020:

- **ميزات معاينة الغياب والإجازات** - لمزيد من المعلومات، راجع [ميزات معاينة الإجازات والغياب](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **ميزة معاينة إدارة الميزات** - لمزيد من المعلومات، بما في ذلك المشكلات المعروفة، راجع [نظرة عامة على إدارة الميزات](hr-benefits-management-overview.md).
