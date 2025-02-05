---
title: نظرة عامة حول مهام استيراد البيانات وتصديرها
description: استخدم مساحة عمل إدارة البيانات لإنشاء وإدارة وظائف استيراد البيانات وتصديرها.
author: peakerbl
ms.date: 08/26/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a03f8fd0fa05a1400c69a2da8867dee135ad06a1
ms.sourcegitcommit: 7bcaf00a3ae7e7794d55356085e46f65a6109176
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/26/2022
ms.locfileid: "9357580"
---
# <a name="data-import-and-export-jobs-overview"></a>نظرة عامة حول مهام استيراد البيانات وتصديرها

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

لإنشاء وإدارة وظائف استيراد البيانات وتصديرها، استخدم مساحة عمل **إدارة البيانات**. بشكل افتراضي، تنشئ عملية استيراد البيانات وتصديرها جدولاً مرحليًا لكل كيان في قاعدة البيانات الهدف. تسمح لك الجداول المرحلية بالتحقق من البيانات أو تنظيمها أو تحويلها قبل قبل أن تقوم بنقلها.

> [!NOTE]
> تفترض هذه المقالة أنك على دراية بـ [كيانات البيانات](data-entities.md).

## <a name="data-importexport-process"></a>عملية استيراد/تصدير البيانات
فيما يلي الخطوات اللازمة لاستيراد أو تصدير البيانات.

1. أنشئ وظيفة استيراد وتصدير حيث يمكنك إتمام المهام التالية:

    - تعريف فئة المشروع.
    - تحديد الكيانات لاستيرادها أو تصديرها.
    - تعيين تنسيق البيانات للوظيفة.
    - إجراء تسلسل للكيانات، لكي تتم معالجتها في مجموعات منطقية، وبترتيب ملائم.
    - تحديد ما إذا كان يجب استخدام جداول مرحلية.

2. تحقق من تعيين البيانات المصدر والبيانات الهدف بشكل صحيح.
3. تحقق من أمان وظيفة الاستيراد أو التصدير.
4. شغُل وظيفة الاستيراد أو التصدير.
5. تحقق من تشغيل الوظيفة كما هو متوقع من خلال مراجعة سجل الوظائف.
6. نظف الجداول المرحلية.

توفر المقاطع المتبقية من هذه المقالة تفاصيل إضافية عن كل خطوة من خطوات العملية.

> [!NOTE]
> لكي يتم تحديث نموذج استيراد/تصدير البيانات للاطلاع على التقدم الأخير الذي حصل، استخدم أيقونة تحديث النموذج. من غير المستحسن إجراء التحديث على مستوى المستعرض لأنه سوف يقاطع أي وظائف استيراد/تصدير لا يتم تشغيلها على دُفعات.

## <a name="create-an-import-or-export-job"></a>إنشاء وظيفة استيراد أو تصدير
يمكن تشغيل وظيفة استيراد البيانات أو تصديرها مرة واحدة أو مرات كثيرة.

### <a name="define-the-project-category"></a>تعريف فئة المشروع
إننا ننصحك بأن تخصص بعض الوقت لتحديد فئة مشروع مناسبة لمهمة الاستيراد أو التصدير. بإمكان فئات المشروع أن تساعدك في إدارة الوظائف ذات الصلة.

### <a name="identify-the-entities-to-import-or-export"></a>تحديد الكيانات لاستيرادها أو تصديرها
يمكنك إضافة كيانات محددة إلى وظيفة استيراد أو تصدير أو تحديد قالب لتطبيقه. تقوم القوالب بتعبئة وظيفة ما بقائمة وحدات. يتوفر الخيار **تطبيق قالب** بعد أن تقوم بتسمية الوظيفة وحفظها.

### <a name="set-the-data-format-for-the-job"></a>تعيين تنسيق البيانات للوظيفة
عندما تقوم بتحديد كيان ما، يجب تحديد تنسيق البيانات التي سيتم تصديرها أو استيرادها. يمكنك تحديد التنسيقات باستخدام اللوحة **إعداد مصادر البيانات**. تنسيق بيانات مصدر عبارة عن مجموعة من **النوع**، و **تنسيق الملف**، و **محدد الصف**، و **محدد العمود**. هناك أيضًا سمات أخرى، ولكن هذه هي الأساسية للفهم. يسرد الجدول التالي المجموعات الصالحة.

| تنسيق الملف            | محدد الأعمدة/الصفوف                       | نمط XML                 |
|------------------------|--------------------------------------------|---------------------------|
| Excel                  | Excel                                      | \-غير متوفر                     |
| XML                    | \-غير متوفر                                      | سمة XML لعنصر XML |
| عرض ثابت، محدد | الفاصلة، الفاصلة المنقوطة، علامة التبويب، خط عمودي، الفاصلة المنقوطة | \-غير متوفر                     |

> [!NOTE]
> من المهم تحديد القيمة الصحيحة **لمحدد الصف**، و **محدد العمود**، و **مؤهل النص** ، في حاله تعيين خيار **تنسيق الملف** إلى **محدد**. تاكد من ان بياناتك لا تحتوي علي الحرف المستخدم كمحدد أو مؤهل ، لان هذا قد يؤدي إلى حدوث أخطاء اثناء الاستيراد والتصدير.

> [!NOTE]
> بالنسبة لتنسيقات الملفات المستندة إلى XML، تأكد من استخدام الأحرف القانونية فقط. لمزيد من التفاصيل حول الأحرف الصالحة، راجع [الأحرف الصالحة في XML 1.0](https://www.w3.org/TR/2006/REC-xml-20060816/Overview.html#charsets/). لا يسمح XML 1.0 بأي من أحرف التحكم فيما عدا علامات التبويب وإرجاع الأسطر وتغذية الأسطر. من الأمثلة عن الأحرف غير القانونية الأقواس المربعة والأقواس المتعرجة والخطوط المائلة العكسية. 

استخدم Unicode بدلا من صفحه ترميز لغوي معينه لاستيراد البيانات أو تصديرها. سيساعد هذا في توفير أكثر النتائج توافقا والتخلص من مهام أداره البيانات لأنها تشتمل علي أحرف Unicode. تحتوي تنسيقات البيانات المصدر المحددة بواسطة النظام والتي تستخدم Unicode علي **unicode** في اسم المصدر. يتم تطبيق تنسيق Unicode عن طريق تحديد مخطط شفره ترميز Unicode كصفحه **رموز** في علامة التبويب الإعدادات **الاقليميه** . حدد أحدي صفحات الرموز التالية الخاصة ب Unicode:

| صفحة تشفير لغوي | الاسم المعروض                |
|-----------|-----------------------------|
| 1200      | Unicode                     |
| 12000     | Unicode (UTF-32)            |
| 12001     | Unicode (32 UTF-8 انديان) |
| 1201      | Unicode (Big-Endian)        |
| 65000     | Unicode (UTF-7)             |
| 65001     | Unicode (UTF-8)             |

للحصول علي مزيد من التفاصيل حول صفحات الترميز اللغوي ، راجع [معرفات](/windows/win32/intl/code-page-identifiers/)صفحات التعليمات البرمجية.

### <a name="sequence-the-entities"></a>إجراء تسلسل للكيانات
يمكن إجراء تسلسل للكيانات في قالب بيانات أو في وظائف الاستيراد والتصدير. عندما تقوم بتشغيل وظيفة تحتوي على أكثر من كيان بيانات واحد، يجب أن تتأكد من التسلسل الصحيح لكيانات البيانات. إنك تجري تسلسلاً للكيانات بشكل أساسي لكي تتمكن من معالجة أي تبعيات وظيفية بين الكيانات. وإذا لم يكن هناك أي تبعيات وظيفية لدى الكيانات، فيمكن جدولتها للاستيراد أو التصدير المتوازي. 

#### <a name="execution-units-levels-and-sequences"></a>وحدات التنفيذ والمستويات والتسلسلات
تساعد وحدة التنفيذ والمستوى في وحدة التنفيذ وتسلسل الكيان في التحكم في الترتيب الذي يتم فيه تصدير البيانات أو استيرادها.

- تتم معالجة الكيانات في وحدات تنفيذ مختلفة في نفس الوقت.
- في كل وحدة التنفيذ، تتم معالجة الكيانات في نفس الوقت إذا كانت ذات مستوى مماثل.
- في كل مستوى، تتم معالجة الكيانات وفقًا لرقمها التسلسلي في هذا المستوى.
- بعد أن تمت معالجة أحد المستويات، تتم معالجة المستوى التالي.

#### <a name="resequencing"></a>إعادة إجراء التسلسل
قد تحتاج إلى إعادة إجراء تسلسل للكيانات في الحالات التالية:

- إذا تم استخدام وظيفة بيانات واحدة فقط لكافة تغييراتك، فيمكنك استخدام خيارات إعادة إجراء التسلسل لتحسين وقت التنفيذ للوظيفة الكاملة. في هذه الحالات، يمكنك استخدام وحدة التنفيذ لتمثيل الوحدة النمطية، ومستوى لتمثيل منطقة الميزات في الوحدة النمطية، والتسلسل لتمثيل الكيان. باستخدام هذه الطريقة، يمكنك العمل عبر الوحدات النمطية في نفس الوقت، ولكن مع ذلك يمكنك العمل بشكل متسلسل في وحدة نمطية. للمساعدة في ضمان نجاح العمليات المتزامنة، يجب مراعاة كافة التبعيات.
- إذا كنت تستخدم وظائف بيانات متعددة (على سبيل المثال، وظيفة واحدة لكل وحدة نمطية)، يمكنك استخدام التسلسل للتأثير على مستوى الكيانات وتسلسلها لتمكين التنفيذ الأمثل.
- في حال عدم وجود تبعيات، يمكنك إجراء تسلسل للكيانات عند وحدات تنفيذ مختلفة لتمكين الحد الأقصى للتحسين.

تتوفر قائمة **إعادة إجراء التسلسل** عند تحديد كيانات متعددة. يمكنك إعادة إجراء التسلسل استنادًا إلى خيارات وحدة التنفيذ أو المستوى أو التسلسل. ويمكنك تعيين تزايد لإجراء إعادة تسلسل للكيانات التي تم تحديدها. يتم تحديث الوحدة و/أو المستوى و/أو الرقم التسلسلي المحدد لكل كيان بواسطة التزايد المحدد.

#### <a name="sorting"></a>الفرز
يمكنك استخدام الخيار **فرز حسب** لعرض قائمة الكيانات بترتيب متسلسل.

### <a name="truncating"></a>الاقتطاع
لاستيراد المشروعات، فإنه يمكنك اختيار اقتطاع السجلات في الكيانات قبل الاستيراد. هذا مفيد في حالة وجوب استيراد سجلاتك إلى مجموعة جداول خالية. يكون هذا الخيار متوقفًا عن التشغيل بشكل افتراضي.

## <a name="validate-that-the-source-data-and-target-data-are-mapped-correctly"></a>التحقق من تعيين البيانات المصدر والبيانات الهدف بشكل صحيح
إن التعيين عبارة عن وظيفة تنطبق على وظائف الاستيراد والتصدير على حد سواء.

- في سياق وظيفة استيراد، يصف التعيين الأعمدة في الملف المصدر التي تتحوّل إلى أعمدة في الجدول المرحلي. وبالتالي، باستطاعة النظام تحديد بيانات العمود في الملف المصدر التي يجب نسخها والعمود في الجدول المرحلي الذي يجب نسخ البيانات إليه.
- في سياق وظيفة تصدير، يصف التعيين الأعمدة في الجدول المرحلي (أي، المصدر) التي تتحوّل إلى أعمدة في الملف الهدف.

إذا تطابقت أسماء الأعمدة في الجدول المرحلي والملف، فسيقوم النظام تلقائيًا بإنشاء التعيين، استنادًا إلى الأسماء. ولكن لن يتم تعيين الأعمدة تلقائيًا إذا كانت الأسماء مختلفة. في هذه الحالات، يجب عليك إكمال التعيين من خلال تحديد الخيار **عرض التعيين** على الكيان في وظيفة البيانات.

هناك طريقتا عرض للتعيين: **مؤثرات عرض التعيين**، وهي طريقة العرض الافتراضية، و **تفاصيل التعيين**. تحدد علامة نجمية حمراء (\*) أي حقول مطلوبة في الكيان. يجب تعيين هذه الحقول قبل أن تتمكن من العمل مع الكيان. يمكن إلغاء تعيين حقول أخرى كما تقتضي الحاجة عندما تعمل مع الكيان. لإلغاء تعيين حقل، حدد الحقل في عمود **الكيان** أو عمود **المصدر**، ثم حدد **حذف التحديد**. حدد **حفظ** لحفظ التغييرات التي أجريتها، ثم قم بإغلاق الصفحة للعودة إلى المشروع. يمكنك استخدام العملية نفسها لتحرير تعيين الحقول من المصدر إلى الجدول المرحلي بعد استيرادها.

يمكنك إنشاء تعيين على الصفحة عن طريق تحديد **إنشاء تعيين للمصدر**. يعمل التعيين المُنشأ كتعيين تلقائي. وبالتالي، يجب تعيين أي حقول غير معينة يدويًا.

![تعيين البيانات.](./media/dixf-map.png)

## <a name="verify-the-security-for-your-import-or-export-job"></a>التحقق من أمان وظيفة الاستيراد أو التصدير
قد يكون الوصول إلى مساحة عمل **إدارة البيانات** مقيدًا، بهدف تمكين المستخدمين من غير المسؤولين من الوصول فقط إلى وظائف بيانات معينة. يشتمل الوصول إلى وظيفة بيانات حق الوصول الكامل إلى سجل التنفيذ لتلك الوظيفة والوصول إلى الجداول المرحلية. وبالتالي، يجب أن تتأكد من وضع عناصر التحكم بالوصول المناسبة عند إنشاء وظيفة بيانات.

### <a name="secure-a-job-by-roles-and-users"></a>حماية وظيفة بواسطة الأدوار والمستخدمين
استخدم قائمة **الأدوار القابلة للتطبيق** لتقييد الوظيفة بحيث تقتصر على دور أمان واحد أو أكثر. سيتمكن فقط المستخدمون الذين لديهم هذه الأدوار من الوصول إلى الوظيفة.

يمكنك أيضًا تقييد وظيفة بحيث تقتصر على مستخدمين معينين. عندما تقوم بحماية وظيفة بواسطة المستخدمين بدلاً من الأدوار، سيكون هناك المزيد من التحكم في حالة تعيين عدة مستخدمين إلى دور ما.

### <a name="secure-a-job-by-legal-entity"></a>حماية وظيفة بواسطة الكيان القانوني
تعتبر وظائف البيانات عمومية بطبيعتها. لذلك، إذا تم إنشاء وظيفة بيانات واستخدامها في كيان قانوني، فستكون الوظيفة مرئية في كيانات قانونية أخرى في النظام. قد يكون هذا السلوك الافتراضي مفضلاً في بعض سيناريوهات التطبيق. على سبيل المثال، قد تقوم مؤسسة تستورد الفواتير باستخدام كيانات بيانات بتوفير فريق لمعالجة الفواتير المركزية يكون مسؤولاً عن إدارة أخطاء الفواتير لكافة الأقسام في المؤسسة. في هذا السيناريو، من المفيد أن يتوفر لفريق معالجة الفواتير المركزية حق الوصول إلى وظائف استيراد الفواتير من كافة الكيانات القانونية. نتيجة لذلك، يلبي السلوك الافتراضي المتطلبات من وجهة نظر كيان قانوني.

ومع ذلك، قد تحتاج المؤسسة إلى وجود فرق عمل لمعالجة الفواتير في كل كيان قانوني. في هذه الحالة، يجب أن يتوفر لدى الفريق في الكيان القانوني حق الوصول فقط إلى وظيفة استيراد الفواتير في كيانه القانوني الخاص. لتلبية هذه المتطلبات، يمكنك تكوين التحكم بالوصول الذي يستند إلى الكيان القانوني على وظائف البيانات باستخدام قائمة **الكيانات القانونية القابلة للتطبيق** داخل وظيفة البيانات. بعد تنفيذ عملية التكوين، يستطيع المستخدمون رؤية فقط الوظائف المتوفرة في الكيان القانوني الذي سجلوا دخولهم إليه حاليًا. لرؤية الوظائف من كيان قانوني آخر، يجب على المستخدمين التبديل إلى هذا الكيان القانوني.

يمكن حماية وظيفة بواسطة الأدوار والمستخدمين والكيان القانوني في نفس الوقت.

## <a name="run-the-import-or-export-job"></a>تشغيل وظيفة الاستيراد أو التصدير
يمكنك تشغيل وظيفة مرة واحدة عن طريق تحديد الزر **استيراد** أو **تصدير** بعد تعريف الوظيفة. لإعداد وظيفة متكررة، حدد **إنشاء وظيفة بيانات متكررة**.

> [!NOTE]
> يمكن تشغيل وظيفة استيراد أو تصدير عن طريق تحديد الزر **استيراد** أو **تصدير**. سيؤدي هذا إلى جدولة وظيفة الدفعة للتشغيل مرة واحدة فقط. قد لا يتم تنفيذ المهمة على الفور إذا كانت خدمة الدُفعات قيد التقييد بسبب الحمل على خدمة الدُفعات. يمكن أيضًا تشغيل الوظائف بشكل متزامن عن طريق تحديد **استيراد الآن** أو **تصدير الآن**. ويؤدي ذلك إلى تشغيل الوظيفة على الفور، ويكون مفيدًا إذا تعذر بدء عمل الدُفعة بسبب التقييد. ويمكن أيضًا جدولة الوظائف لتنفيذها في وقت لاحق. يمكن القيام بذلك باختيار خيار **تشغيل في دفعة**. تخضع موارد الدُفعة للتقييد، وبالتالي قد لا تبدأ الوظيفة الدفعية على الفور. يعد استخدام الدُفعة هو الخيار الموصى به لأنه سيساعد أيضًا مع كميات كبيرة من البيانات التي يجب استيرادها أو تصديرها. يمكن جدولة الوظائف الدفعية بحيث تعمل على مجموعة دفعات محددة، مما يسمح بمزيد من التحكم من منظور موازنة الأحمال.

## <a name="validate-that-the-job-ran-as-expected"></a>التحقق من تشغيل الوظيفة كما هو متوقع
يتوف سجل الوظائف لاستكشاف الأخطاء وإصلاحها ولعمليات الاستقصاء على وظائف الاستيراد والتصدير على حدٍ سواء. يتم تنظيم عمليات التشغيل التاريخية حسب نطاقات الوقت.

![نطاقات سجل الوظائف.](./media/dixf-job-history.md.png)

توفر كل عملية تشغيل للوظيفة التفاصيل التالية:

- تفاصيل التنفيذ
- سجل التنفيذ

تُظهر تفاصيل التنفيذ حالة كل كيان بيانات قامت الوظيفة بمعالجته. وبالتالي، يمكنك العثور بسرعة على المعلومات التالية:

- الكيانات التي تمت معالجتها.
- بالنسبة إلى كيان ما، عدد السجلات التي تمت معالجتها بنجاح وعدد السجلات التي فشلت معالجتها.
- السجلات المرحلية لكل كيان.

يمكنك تنزيل البيانات المرحلية في ملف لوظائف التصدير، أو يمكن تحميلها كحزمة لوظائف الاستيراد والتصدير.

من تفاصيل التنفيذ، يمكنك أيضًا فتح سجل التنفيذ.

## <a name="parallel-imports"></a>عمليات الاستيراد المتوازية
لتسريع استيراد البيانات، يمكن تمكين المعالجة المتوازية لاستيراد الملف إذا كان الكيان يدعم عمليات الاستيراد المتوازية. لتكوين المعالجة المتوازية لأحد الكيانات، يجب اتباع الخطوات التالية.

1. اذهب إلى **إدارة النظام \> مساحات العمل \> إدارة البيانات**.
2. في قسم **الاستيراد/التصدير**، حدد تجانب **معلمات إطار العمل** لفتح صفحة **معلمات إطار العمل لاستيراد/تصدير البيانات**.
3. في علامة تبويب **إعدادات الكيان**، حدد **تكوين معلمات تنفيذ الكيان** لفتح صفحة **معلمات تنفيذ استيراد الكيان**.
4. قم بتعيين الحقول التالية لتكوين الاستيراد المتوازي للكيان:

    - في حقل **الكيان**، حدد الكيان.
    - في حقل **عدد السجلات لحد الاستيراد** أدخل عدد سجلات الحد الخاصة بالاستيراد. هذا يحدد عدد السجلات المراد معالجتها بواسطة أحد السلاسل. إذا كان أحد الملفات يتضمن 10K سجل، فإن عدد السجلات 2500 مع عدد مهام 4 سيعني أن كل سلسلة ستعالج 2500 سجل.
    - في حقل **عدد مهام الاستيراد** أدخل عدد مهام الاستيراد. وهذا يجب ألا يتجاوز الحد الأقصى لسلاسل المجموعة المخصص لكل معالجة مجمعة في **إدارة النظام \>تكوين الخادم**.

## <a name="job-history-clean-up"></a>تنظيف محفوظات الوظائف 
يجب استخدام وظيفة تنظيف محفوظات الوظائف في إدارة البيانات لجدولة تنظيف دوري لمحفوظات التنفيذ. تحل هذه الوظيفة محل وظيفة تنظيف الجداول المرحلية السابقة، التي أصبحت الآن مهملة. سيتم تنظيف الجداول التالية بواسطة عملية التنظيف.

-   جميع الجداول المرحلية

-   DMFSTAGINGVALIDATIONLOG

-   DMFSTAGINGEXECUTIONERRORS

-   DMFSTAGINGLOGDETAIL

-   DMFSTAGINGLOG

-   DMFDEFINITIONGROUPEXECUTIONHISTORY

-   DMFEXECUTION

-   DMFDEFINITIONGROUPEXECUTION

يجب تمكين ميزة **تنظيف محفوظات التنفيذ** في إدارة الميزات، ثم يمكن الوصول إليها من **إدارة البيانات \> تنظيف محفوظات الوظائف**.

### <a name="scheduling-parameters"></a>محددات الجدولة

عند جدولة عملية التنظيف، يجب تحديد المعلمات التالية لتحديد معايير التنظيف.

-   **عدد أيام الاحتفاظ بالمحفوظات** – يتم استخدام هذا الإعداد للتحكم في مقدار محفوظات التنفيذ التي سيتم الاحتفاظ بها. يتم تحديد هذا الخيار بعدد الأيام. عند جدولة وظيفة التنظيف كوظيفة دفعية متكررة، سيعمل هذا الإعداد كإطار متحرك باستمرار، مما يؤدي دائمًا إلى ترك المحفوظات سليمة لعدد الأيام المحدد مع حذف الباقي. الإعداد الافتراضي هو 7 أيام.

-   **عدد الساعات المطلوبة لتنفيذ الوظيفة** – بحسب مقدار المحفوظات التي سيتم تنظيفها، قد يختلف إجمالي وقت تنفيذ وظيفة التنظيف من دقائق قليلة إلى ساعات قليلة. يجب تعيين هذه المعلمة على عدد الساعات التي سيتم تنفيذ الوظيفة فيها. بعد تنفيذ وظيفة التنظيف لعدد محدد من الساعات، فسيتم إنهاء الوظيفة وستستأنف عملية التنظيف في المرة التالية التي يتم تشغيلها استنادًا إلى جدول التكرار.

    يمكن تحديد الحد الأقصى لوقت التنفيذ عن طريق تعيين حد أقصى لعدد الساعات التي يجب خلالها تشغيل هذه الوظيفة باستخدام هذا الإعداد. يمر منطق التنظيف عبر معرف تنفيذ وظيفة واحدة في كل مرة بتسلسل ترتيب زمني، حيث يأتي الأقدم أولاً في عملية تنظيف محفوظات التنفيذ ذات الصلة. ستتوقف العملية عن انتقاء معرفات تنفيذ جديدة للتنظيف عندما تكون مدة التنفيذ المتبقية ضمن آخر 10% من المدة المحددة. وفي بعض الحالات، من المتوقع أن تستمر وظيفة التنظيف ما بعد الوقت الأقصى المحدد. يعتمد هذا إلى حد كبير على عدد السجلات التي سيتم حذفها لمعرف التنفيذ الحالي الذي بدأ قبل الوصول إلى حد 10%. يجب إكمال عملية التنظيف التي بدأت لضمان تكامل البيانات، مما يعني أن التنظيف سيستمر على الرغم من تجاوز الحد المحدد. عند اكتمال هذه العمية، لا يتم انتقاء معرفات تنفيذ جديدة وتكتمل مهمة التنظيف. سيتم انتقاء محفوظات التنفيذ المتبقية التي لم يتم تنظيفها بسبب عدم وجود وقت تنفيذ كافٍ في المرة التالية التي يتم فيها تحديد موعد وظيفة التنظيف. تم تعيين ساعتين كقيمة افتراضية وحد أدنى لهذا الإعداد.

-   **الدُفعة المتكررة** – يمكن تشغيل وظيفة التنظيف كتنفيذ يدوي لمرة واحدة، أو يمكن أيضًا جدولتها للتنفيذ المتكرر على دُفعات. يمكن جدولة الدُفعة باستخدام إعدادات **التشغيل في الخلفية**، وهو إعداد الدُفعات القياسي.

> [!NOTE]
> في حالة عدم تنظيف الجداول المرحلية بالكامل، فتأكد من جدولة وظيفة التنظيف ليتم تشغيلها في التكرار. وكما هو موضح أعلاه، في أي تنفيذ عملية نظيف ستكون الوظيفة تنظيف أكبر قدر ممكن من معرفات التنفيذ فقط خلال الحد الأقصى المتوفر من الساعات. ولمتابعة التنظيف لأي سجلات مرحلية متبقية، فإنه يجب جدولة الوظيفة لتعمل بشكل دوري.

## <a name="job-history-clean-up-and-archival"></a>تنظيف محفوظات المهمة وأرشفتها 
تحل وظيفة تنظيف محفوظات الوظيفة والأرشفة محل الإصدارات السابقة من وظيفة التنظيف. سيشرح هذا القسم هذه الإمكانات الجديدة.

أحد التغييرات الرئيسية لوظيفة التنظيف هو استخدام وظيفة مجموعة النظام لتنظيف المحفوظات. يسمح استخدام الوظيفة الدفعية للنظام لتطبيقات التمويل والعمليات بجدولة مهمة دفعة التنظيف وتشغيلها تلقائيًا بمجرد أن يكون النظام جاهزًا. لم يعد مطلوبًا جدولة وظيفة الدفعة يدويًا. في وضع التنفيذ الافتراضي هذا، سيتم تنفيذ المهمة المجمعة كل ساعة بدءًا من الساعة 12 منتصف الليل وستحتفظ بمحفوظات التنفيذ لآخر 7 أيام. تتم أرشفة المحفوظات التي تم حذفها لاسترجاعها في المستقبل. بدءا من 10.0.20 الإصدار ، فان هذه الميزة في التشغيل دائما.

التغيير الثاني في عملية التنظيف هو أرشفة محفوظات التنفيذ الذي تمت إزالتها. ستعمل مهمة التنظيف على أرشفة السجلات المحذوفة إلى وحدة تخزين البيانات الثنائية الكبيرة التي يستخدمها DIXF لعمليات التكامل المنتظمة. سيكون الملف المؤرشف بتنسيق حزمة DIXF وسيكون متاحًا لمدة 7 أيام في الكائن الثنائي يمكن خلالها تنزيله. يمكن تغيير طول العمر الافتراضي البالغ 7 أيام للملف المؤرشف إلى 90 يومًا كحد أقصى في المعلمات.

### <a name="changing-the-default-settings"></a>تغيير الإعدادات الافتراضية
هذه الوظيفة قيد المعاينة حاليًا ويجب تشغيلها بشكل صريح عن طريق تمكين الرحلة DMFEnableExecutionHistoryCleanupSystemJob. يجب أيضًا تشغيل ميزة تنظيف التدريج في إدارة الميزات.

لتغيير الإعداد الافتراضي لطول عمر الملف المؤرشف، انتقل إلى مساحة عمل إدارة البيانات وحدد **تنظيف محفوظات الوظائف**. قم بتعيين **الأيام للاحتفاظ بالحزمة في الكائن الثنائي** لقيمة بين 7 و90 (شاملاً الرقمين). سيسري هذا على الأرشيفات التي تم إنشاؤها بعد إجراء هذا التغيير.

### <a name="downloading-the-archived-package"></a>يتم الآن تنزيل الحزمة المؤرشفة
هذه الوظيفة قيد المعاينة حاليًا ويجب تشغيلها بشكل صريح عن طريق تمكين الرحلة DMFEnableExecutionHistoryCleanupSystemJob. يجب أيضًا تشغيل ميزة تنظيف التدريج في إدارة الميزات.

لتنزيل محفوظات التنفيذ المؤرشفة، انتقل إلى مساحة عمل إدارة البيانات وحدد **تنظيف محفوظات الوظائف**. حدد **محفوظات النسخ الاحتياطي للحزمة** لفتح نموذج المحفوظات. يعرض هذا النموذج قائمة بجميع الحزم المؤرشفة. يمكن تحديد أرشيف وتنزيله من خلال تحديد **تنزيل حزمة**. ستكون الحزمة التي تم تنزيلها بتنسيق حزمة DIXF وستحتوي على الملفات التالية:

-   ملف الجدول المرحلي للكيان
-   DMFDEFINITIONGROUPEXECUTION
-   DMFDEFINITIONGROUPEXECUTIONHISTORY
-   DMFEXECUTION
-   DMFSTAGINGEXECUTIONERRORS
-   DMFSTAGINGLOG
-   DMFSTAGINGLOGDETAILS
-   DMFSTAGINGVALIDATIONLOG



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

