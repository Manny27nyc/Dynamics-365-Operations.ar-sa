---
title: إعداد التكامل المالي لقنوات Commerce
description: يوفر هذا المقال إرشادات لإعداد وظيفة التكامل المالي لقنوات Commerce.
author: EvgenyPopovMBS
ms.date: 04/28/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 9fd801395f2ba04c703734a1de7998d6a53b6462
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276119"
---
# <a name="set-up-the-fiscal-integration-for-commerce-channels"></a>إعداد التكامل المالي لقنوات Commerce

[!include [banner](../includes/banner.md)]

يوفر هذا المقال إرشادات لإعداد وظيفة التكامل المالي لقنوات Commerce. للحصول على مزيد من المعلومات حول التكامل المالي، راجع [نظرة عامة على التكامل المالي لقنوات Commerce](fiscal-integration-for-retail-channel.md).

## <a name="enable-features-in-commerce-headquarters"></a>تمكين الميزات في Commerce Headquarters

لتمكين الميزات المرتبطة بوظيفة التكامل المالي لقنوات Commerce، اتبع الخطوات التالية.

1. في Commerce headquarters، انتقل إلى **إدارة النظام \> مساحات العمل \> إدارة الميزات**.
1. البحث عن الميزات التالية وتمكينها:

    - **التكامل المالي المباشر من سجلات نقطة البيع‬** – تعمل هذه الميزة على توسيع إطار عمل التكامل المالي عن طريق إضافة القدرة على إنشاء موصلات مالية سيتم تشغيلها في نقطة البيع (POS). يتصل هذا النوع من الموصلات بجهاز أو خدمة مالية توفر واجهة برمجة تطبيقات (API) لـ HTTP ولا يتطلب جهازًا فعليًا مخصصًا في المتجر. على سبيل المثال، تتيح هذه الوظيفة التكامل المالي للأجهزة المحمولة دون الحاجة إلى محطة أجهزة مشتركة.
    - **تجاوزات ملف التعريف الفني للتكامل المالي‬** – تتيح هذه الميزة توسيع تكوين التكامل المالي وتضيف القدرة على التحقق من معلمات الاتصال في صفحة الإعدادات لسجل نقطة البيع. عند تمكين هذه الميزة، يمكنك تجاوز معلمات ملف التعريف الفني.
    - **حالة التسجيل المالي لسجلات نقطة البيع‬** – عند تمكين هذه الميزة، يمكنك تعطيل عملية التسجيل المالي لسجلات نقاط بيع محددة. إذا تم تعطيل التسجيل المالي لسجل نقطة بيع، فلا يمكن إكمال حركات المبيعات في هذا السجل.
    - **نسخ احتياطي للتخزين المحلي للتكامل المالي‬** – تعمل هذه الميزة على توسيع إمكانيات معالجة الأخطاء لإطار عمل التكامل المالي. وتمكّن هذه الميزة أيضًا إجراء نسخ احتياطي تلقائي لبيانات التسجيل المالي في حالة فقدان البيانات، بحيث تتم استعادة البيانات الموجودة في التخزين المحلي أثناء تنشيط الجهاز.

## <a name="set-up-commerce-parameters"></a>إعداد معلمات Commerce

لإعداد معلمات Commerce، اتبع هذه الخطوات.

1. في صفحة **معلمات Commerce المشتركة‬**، على علامة التبويب **عام**، عيّن الخيار **تمكين التكامل المالي** إلى **نعم**.
1. على علامة التبويب **التسلسلات الرقمية‬‬**، حدد التسلسلات الرقمية‬ للمراجع التالية:

    - رقم ملف التعريف التقني المالي
    - رقم مجموعة الموصل المالي
    - رقم عملية التسجيل

1. في صفحة **معلمات Commerce‬**، حدد التسلسل الرقمي لرقم ملف تعريف الوظائف المالية.

> [!NOTE]
> التسلسلات الرقمية اختيارية. يمكن إنشاء أرقام كافة الكيانات التكامل المالي من التسلسلات الرقمية أو يدويًا.

## <a name="set-up-a-fiscal-registration-process"></a>إعداد عملية التسجيل المالي

تتضمن عملية إعداد التكامل المالي المهام التالية:

- تكوين الموصلات المالية التي تمثل أجهزة أو خدمات مالية يتم استخدامها لأغراض التسجيل المالي، مثل طابعات الضرائب المحصلة .
- تكوين موفري المستندات الذين يعملون على إنشاء المستندات المالية التي سيتم تسجيلها في الأجهزة أو الخدمات المالية بواسطة الموصلات المالية.
- تكوين عملية التسجيل المالي التي تحدد يعرف تسلسل خطوات التسجيل المالي والموصلات المالية وموفري المستندات المالية المستخدمة لكل خطوة.
- عيّن عملية التسجيل المالي إلى ملفات تعريف وظائف نقطة البيع.
- تعيين ملفات التعريف التقنية للموصلات إلى ملفات تعريف الأجهزة.
- قم بتعيين ملفات التعريف الفنية للموصل لأجهزة نقاط البيع أو ملفات تعريف الوظائف.

### <a name="upload-configurations-of-fiscal-document-providers"></a>تحميل تكوينات موفري المستندات المالية

يعتبر موفر المستندات المالية مسؤولاً عن إنشاء المستندات المالية التي تمثل أحداث وحركات والأحداث المسجلة في نقطة البيع بتنسيق يُستخدم أيضًا للتفاعل مع جهاز أو خدمة مالية. على سبيل المثال، بإمكان موفر المستندات المالية إنشاء تمثيل لإيصال مالي بتنسيق XML.

لتحميل تكوينات موفري المستندات المالية، اتبع هذه الخطوات.

1. في Commerce Headquarters، انتقل إلى صفحة **موفرو المستندات المالية** (**البيع بالتجزئة والتجارة \> إعداد القناة \> التكامل المالي \> موفرو المستندات المالية**).
1. قم بتحميل تكوين XML لكل جهاز أو خدمة تخطط لاستخدامها.

> [!TIP]
> عن طريق تحديد **عرض**، يمكنك عرض كافة ملفات التعريف الوظيفية والتقنية التي ترتبط بموفر المستندات المالية الحالي.

> [!NOTE]
> يعتبر تعيين البيانات جزءًا من موفر المستندات المالية. لإعداد تعيينات بيانات مختلفة للموصل نفسه (على سبيل المثال، القواعد الخاصة بالولاية)، يجب عليك إنشاء موفرين مختلفين للمستندات المالية.

### <a name="upload-configurations-of-fiscal-connectors"></a>تحميل تكوينات الموصلات المالية

يعتبر الموصل المالي مسؤولاً عن الاتصال بجهاز مالي أو خدمة مالية. على سبيل المثال، بإمكان الموصل المالي إرسال إيصال مالي أنشأه موفر المستندات المالية بتنسيق XML إلى طابعة الضرائب المحصلة. لمزيد من التفاصيل حول مكونات التكامل المالي، راجع [عملية التسجيل المالي وعينات التكامل المالي للأجهزة والخدمات المالية](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

لتحميل تكوينات الموصلات المالية، اتبع هذه الخطوات.

1. في Commerce Headquarters، انتقل إلى صفحة **الموصلات المالية** (**البيع بالتجزئة والتجارة \> إعداد القناة \> التكامل المالي \> الموصلات المالية**).
1. قم بتحميل تكوين XML لكل جهاز أو خدمة تخطط لاستخدامها لأغراض تتعلق بالتكامل المالي.

> [!TIP]
> عن طريق تحديد **عرض**، يمكنك عرض كافة ملفات التعريف الوظيفية والتقنية التي ترتبط بالموصل المالي الحالي.

للحصول على أمثلة حول تكوينات الموصلات المالية وموفري المستندات المالية، راجع [نماذج التكامل المالي في Commerce SDK](fiscal-integration-for-retail-channel.md#fiscal-integration-samples-in-the-commerce-sdk).

### <a name="create-connector-functional-profiles"></a>إنشاء ملفات تعريف وظيفية للموصلات

لإنشاء ملفات تعريف وظيفية للموصلات، اتبع الخطوات التالية.

1. في Commerce Headquarters، انتقل إلى صفحة **ملفات التعريف الوظيفية للموصلات** (**البيع بالتجزئة والتجارة \> إعداد القناة \> التكامل المالي \> ملفات التعريف الوظيفية للموصلات**).
1. لكل مجموعة مكونة من موصل مالي وموفر مستندات مالية تتعلق بهذا الموصل المالي، يجب إنشاء ملف تعريف وظيفي للموصل باتباع الخطوات التالية:

    1. حدد اسم موصل.
    1. حدد موفر المستندات.

#### <a name="change-data-mapping-parameters-in-a-connector-functional-profile"></a>تغيير معلمات تعيين البيانات في ملف التعريف الوظيفي للموصل

يمكنك تغيير معلمات تعيين البيانات في ملف التعريف الوظيفي للموصل. يوفر الجدول التالي بعض الأمثلة عن معلمات تعيين البيانات في ملف التعريف الوظيفي للموصل.

| المحددة | التنسيق | مثال |
|-----------|--------|---------|
| إعدادات معدلات ضريبة القيمة المضافة | القيمة: VATrate | 1 : 2000, 2 : 1800 |
| تعيين أكواد ضريبة القيمة المضافة | VATcode : القيمة | vat20 : 1, vat18 : 2 |
| تعيين أنواع طرق الدفع | TenderType: قيمة | النقد : 1، البطاقة : 2 |

لاستعادة المعلمات الافتراضية التي تم تعريفها في تكوين موفر المستندات المالية، حدد **تحديث** في صفحة **ملفات التعريف الوظيفية للموصلات**.

> [!NOTE]
> تعتبر ملفات التعريف الوظيفية للموصلات خاصة بالشركة. إذا كنت تخطط لاستخدام المجموعة نفسها لموصل مالي وموفر مستندات مالية لشركات مختلفة، فيجب إنشاء ملف تعريف وظيفي للموصل لكل شركة.

### <a name="create-connector-technical-profiles"></a>إنشاء ملفات تعريف تقنية للموصلات

لإنشاء ملفات تعريف تقنية للموصلات، اتبع الخطوات التالية.

1. في Commerce Headquarters، انتقل إلى صفحة **ملفات التعريف التقنية للموصلات** (**البيع بالتجزئة والتجارة \> إعداد القناة \> التكامل المالي \> ملفات التعريف التقنية للموصلات**).
1. أنشئ ملف تعريف تقنيًا لكل موصل مالي باتباع الخطوات التالية:

    1. حدد اسم موصل.
    1. حدد نوع موصل:

        - بالنسبة للأجهزة أو الخدمات المتصلة بمحطة أجهزة أو موجودة في الشبكة المحلية، حدد **محلي**.
        - بالنسبة للخدمات الخارجية، حدد **خارجي**.
        - بالنسبة للارتباطات الداخلية في Commerce runtime (CRT)، حدد **Internal**. 

    1. حدد موقعًا للموصل:

        - إذا كان الموصل موجودًا على محطة الأجهزة، فحدد **محطة الأجهزة**.
        - ‏‫إذا كان الموصل موجودًا على سجل نقطة البيع، فحدد **سجل**.

يمكن تغيير المعلمات على علامتي التبويب **الجهاز** و **الإعدادات** في ملف تعريف تقني للموصل. لاستعادة المعلمات الافتراضية التي تم تعريفها في تكوين الموصل المالي، حدد **تحديث**. بينما يتم تحميل إصدار جديد لتكوين XML، ستتلقى رسالة تفيد بأن الموصل المالي الحالي أو موفر المستندات المالية الحالي قيد الاستخدام. لا يتجاوز هذا الإجراء التغييرات اليدوية التي تم إدخالها في وقت سابق على ملفات التعريف الوظيفية أو التقنية للموصلات. لتطبيق المجموعة الافتراضية للمعلمات من تكوين جديد، حدد **تحديث** في صفحة **ملفات التعريف الوظيفية للموصلات‬** أو صفحة **ملفات التعريف التقنية للموصلات‬**.

إذا كان يجب إعداد معلمات محددة إلى سجل نقطة بيع فردية أو متجر فردي، فاتبع الخطوات التالية.

1. حدد عنصر قائمة **تجاوز**.
1. في الصفحة **التجاوز**، قم بإنشاء سجل جديد.
1. حدد متجرًا أو سجل نقطة بيع. يمكنك تجاوز معلمات ملف التعريف التقني المحدد لسجل نقطة بيع فردية أو جميع سجلات نقاط البيع في متجر فردي.
1. في علامة التبويب **الجهاز**، أدخل معلمات سجل نقطة البيع المحددة أو المتجر المحدد.

### <a name="create-fiscal-connector-groups"></a>إنشاء مجموعات موصلات مالية

تضم مجموعة الموصلات المالية ملفات التعريف الوظيفية للموصلات المالية التي تؤدي وظائف مماثلة وتُستخدم في الخطوة نفسها في عملية التسجيل المالي. على سبيل المثال، إذا كان استخدام نماذج متعددة لطابعات الضرائب المحصلة في متجر، فيمكن دمج الموصلات المالية لطابعات الضرائب المحصلة هذه في مجموعة موصلات مالية.

لإنشاء مجموعة موصلات مالية، اتبع الخطوات التالية,

1. انتقل إلى صفحة **مجموعة الموصلات المالية** (**البيع بالتجزئة والمتجر \> إعداد القناة \> التكامل المالي \> مجموعة الموصلات المالية**).
1. أنشئ مجموعات موصلات مالية جديدة.
1. أضف ملفات تعريف وظيفية إلى مجموعة الموصلات. حدد **إضافة** في صفحة **ملفات التعريف الوظيفية** وحدد رقم ملف تعريف. ضمن مجموعة موصلات، يتوفر ملف تعريف وظيفي واحد لكل موصل مالي في مجموعة موصلات.
1. لتعليق استخدام ملف التعريف الوظيفي، عيّن الخيار **تعطيل** إلى **نعم**. يؤثر هذا التغيير على مجموعة الموصلات الحالية فقط. يمكنك متابعة استخدام ملف التعريف الوظيفي نفسه في مجموعات موصلات أخرى.

### <a name="create-a-fiscal-registration-process"></a>إنشاء عملية تسجيل مالي

يتم تعريف عملية التسجيل بواسطة تسلسل خطوات التسجيل ومجموعة الموصلات المستخدمة لكل خطوة.

لإنشاء إنشاء عملية تسجيل مالي، اتبع هذه الخطوات.

1. في Commerce Headquarters، انتقل إلى صفحة **عملية تسجيل مالي** (**البيع بالتجزئة والتجارة \> إعداد القناة \> التكامل المالي \> عمليات التسجيل المالي**).
1. قم بإنشاء سجل جديد لكل عملية تسجيل مالي فريدة.
1. أضف خطوات التسجيل إلى العملية باتباع الخطوات التالية:

    1. حدد **إضافة**.
    1. حدد نوع موصل مالي.
    1. في حقل **رقم المجموعة**، حدد مجموعة الموصلات المالية المناسب.

### <a name="assign-entities-of-the-fiscal-registration-process-to-pos-profiles"></a>تعيين كيانات عملية التسجيل المالي إلى ملفات تعريف نقطة البيع

لتعيين كيانات عملية التسجيل المالي إلى ملفات تعريف نقطة البيع، اتبع الخطوات التالية.

1. في Commerce Headquarters، انتقل إلى الصفحة **ملفات تعريف وظائف نقطة البيع** (**البيع بالتجزئة والتجارة \> إعداد القناة \> إعداد القناة \> ملفات تعريف نقطة البيع \> ملفات تعريف الوظائف**). 
1. عيّن عملية التسجيل المالي إلى ملف تعريف وظائف نقطة البيع.
1. حدد **تحرير**، ثم، على علامة تبويب **عملية التسجيل المالي**، في حقل **رقم العملية**، حدد عملية.
1. في علامة التبويب **الخدمات المالية**، حدد ملفات تعريف تقنية للموصل مع موقع الموصل **سجل**.
1. انتقل إلى الصفحة **ملف تعريف أجهزة نقطة البيع‬‏‫** (**البيع بالتجزئة والتجارة \> إعداد القناة \> إعداد نقطة البيع \> ملفات تعريف نقاط البيع \> ملف تعريف الأجهزة**).
1. عيّن ملفات التعريف التقنية للموصلات إلى ملف تعريف الأجهزة. 
1. حدد **تحرير**، ثم، على علامة التبويب **الأجهزة الطرفية المالية**، أضف سطرًا. 
1. في الحقل **رقم ملف التعريف**، حدد ‏‫ملف التعريف التقني للموصل.
1. في علامة التبويب **الأجهزة الطرفية المالية**، حدد ملفات تعريف تقنية للموصل مع موقع الموصل **محطة الأجهزة**.

> [!NOTE]
> يمكنك إضافة العديد من ملفات التعريف التقنية إلى ملف تعريف الأجهزة نفسه. ومع ذلك، يجب أن يتضمن ملف تعريف الأجهزة أو ملف تعريف وظائف نقطة البيع تقاطعًا واحدًا فقط مع أي مجموعة موصلات مالية.

يتحدد سير عمل التسجيل المالي بواسطة عملية التسجيل المالي وأيضًا بواسطة بعض معلمات مكونات التكامل المالي: ملحق CRT لموفر المستندات المالية وملحق محطة الأجهزة للموصل المالي.

- يتم تعريف اشتراك الأحداث والحركات في التسجيل المالي بواسطة موفر المستندات المالية بشكل مسبق.
- يتحمل موفر المستندات المالية أيضًا مسؤولية تعريف الموصل المالي المستخدم لعملية التسجيل المالي. وهو يعمل على مطابقة ملفات التعريف الوظيفية للموصلات المضمنة في مجموعة الموصلات المالية المحددة للخطوة الحالية في عملية التسجيل المالي مع ملف التعريف التقني للموصل المعيّن إلى ملف تعريف الأجهزة في محطة الأجهزة التي تقترن بها نقطة البيع.
- يستخدم موفر المستندات المالية إعدادات تعيين البيانات من تكوين موفر المستندات المالي لتحويل بيانات الحركة/الحدث مثل الضرائب والدفعات بينما يتم إنشاء مستند مالي.
- عندما ينشئ موفر المستندات المالية مستندًا ماليًا، بإمكان الموصل المالي إرساله إلى الجهاز المالي كما هو، أو تحليله وتحويله إلى تسلسل أوامر لواجهة برمجة التطبيقات (API) في الجهاز، بحسب التعامل مع الاتصال.

### <a name="set-up-registers-with-fiscal-registration-restrictions"></a>إعداد السجلات مع قيود التسجيل المالي

يمكنك تحديد السجلات التي يكون فيها التسجيل المالي محظورًا، على سبيل المثال في الحالات التي تحتاج فيها إلى توفير عمليات غير مالية فقط مثل البحث في كتالوج المنتجات أو البحث عن العملاء أو إنشاء مسودة المعاملة على هذه الأجهزة.

لإعداد السجلات مع قيود التسجيل المالي، اتبع هذه الخطوات.

1. في Commerce headquarters، انتقل إلى **Retail وCommerce \> إعداد القناة \> التكامل المالي \> عمليات التسجيل المالي**.
1. حدد العملية المطلوبة.
1. حدد علامة التبويب **سجلات نقاط البيع مع قيود العملية المالية**.
1. أضف السجلات مع قيود العملية المالية حسب الحاجة.

### <a name="validate-the-fiscal-registration-process"></a>التحقق من صحة عملية التسجيل المالي

من المستحسن أن تتحقق من صحة عملية التسجيل المالي في الحالات التالية:

- أكملت جميع إعدادات عملية تسجيل جديدة. تتضمن هذه الإعدادات تعيين عمليات التسجيل إلى ملفات تعريف وظائف نقطة البيع وملفات تعريف الأجهزة.
- أدخلت تغييرات على عمليه تسجيل مالي موجودة، وقد تؤدي هذه التغييرات إلى تحديد موصل مالي مختلف في وقت التشغيل. (على سبيل المثال، لقد قمت بتغيير مجموعة الموصلات الخاصة بخطوة في عملية التسجيل المالي، وقمت بتمكين ملف التعريف الوظيفي للموصل في مجموعة موصلات أو أضفت ملف تعريف وظيفي لموصل جديد إلى مجموعة موصلات.)
- لقد أدخلت تغييرات في تعيين ملفات التعريف التقنية للموصلات إلى ملفات تعريف الأجهزة.

للتحقق من صحة عملية التسجيل المالي، اتبع هذه الخطوات.

1. في Commerce Headquarters، انتقل إلى صفحة **عملية تسجيل مالي** (**البيع بالتجزئة والتجارة \> إعداد القناة \> التكامل المالي \> عمليات التسجيل المالي**).
1. حدد **التحقق من الصحة** للتحقق من صحة عملية التسجيل المالي.
1. في صفحة **جدول التوزيع**، شغّل المهمتين **1070** و **1090** لنقل البيانات إلى قاعدة بيانات القناة.

## <a name="set-up-fiscal-texts-for-discounts"></a>إعداد النصوص المالية للخصومات

في بعض الحالات، يجب طباعة نص خاص على إيصال مالي عند تطبيق خصم. يمكنك إعداد النصوص المالية للخصومات في صفحة **مجموعة الموصلات المالية** (**البيع بالتجزئة والتجارة \> إعداد القناة \> التكامل المالي \> مجموعة الموصلات المالية**).

- بالنسبة إلى الخصومات اليدوية المطبقة على نقطة البيع، يمكنك تكوين نص مالي لكود المعلومات أو مجموعة أكواد المعلومات المحدد في كود المعلومات **خصم المنتج** في ملف تعريف وظائف نقطة البيع.

    1. في صفحة **مجموعة الموصلات المالية**، حدد **نص للإيصال المالي**.
    1. في صفحة **أكواد المعلومات**، حدد **إضافة**، وحدد كود معلومات أو مجموعة أكواد معلومات.
    1. في **رقم كود المعلومات**، حدد قيمة.
    1. في الحقل **رقم الكود الفرعي‬**، حدد قيمة إذا كان الكود الفرعي مطلوبًا لكود المعلومات المحدد.
    1. في حقل **نص الإيصال المالي**، حدد نصًا ماليًا يجب طباعته على إيصال مالي.
    1. عيّن الخيار **طباعة إدخال المستخدم على الإيصال المالي** إلى **نعم** لتجاوز النص الموجود على إيصال مالي بالمعلومات التي يدخلها المستخدم يدويًا في نقطة البيع. ينطبق هذا الخيار فقط على أكواد المعلومات التي تحتوي على إدخال من نوع **النص**.

    > [!NOTE]
    > يمكنك تحديد نص مالي لعدة أكواد معلومات لدعم السيناريوهات التي يتم فيها استخدام مجموعات أكواد معلومات وأكواد معلومات مرتبطة وأكواد معلومات تم تشغيلها. في هذه السيناريوهات، سوف يحتوي الإيصال المالي على النصوص المالية من جميع أكواد المعلومات المرتبطة ببند الحركة حيث تم تطبيق الخصم.

- بالنسبة إلى الخصومات الخاصة بالقناة، يجب تحديد نص مالي لمعرّف الخصم.

    1. في صفحة **مجموعة الموصلات المالية**، حدد **نص للإيصال المالي**.
    1. على علامة تبويب **الخصومات**، حدد **إضافة**، وحدد معرّف خصم.
    1. في حقل **نص الإيصال المالي**، حدد نصًا ماليًا يجب طباعته على إيصال مالي.

    > [!NOTE]
    > إذا تم تطبيق خصومات متعددة على بند الحركة نفسه، فسيحتوي الإيصال المالي على نصوص مالية من جميع الخصومات المرتبطة ببند الحركة هذا.

## <a name="set-error-handling-settings"></a>تعيين إعدادات معالجة الأخطاء‬

يتم تعيين خيارات معالجة الأخطاء المتوفرة في التكامل المالي في عملية التسجيل المالية. للحصول على مزيد من المعلومات حول معالجة الأخطاء في التكامل المالي، راجع [معالجة الأخطاء](fiscal-integration-for-retail-channel.md#error-handling).

لتعيين إعدادات معالجة الأخطاء، اتبع الخطوات التالية.

1. في صفحة **عملية التسجيل المالي** (**البيع بالتجزئة والتجارة \> إعداد القناة \> التكامل المالي \> عمليات التسجيل المالي**)، يمكنك تعيين المعلمات التالية لكل خطوة في عملية التسجيل المالي.

    - **السماح بالتخطي‬** – هذه المعلمة تمكّن الخيار **تخطي** في مربع حوار معالجة الأخطاء.
    - **السماح بوضع علامة كمسجل** – تمكّن هذه المعلمة الخيار **وضع علامة كمسجل** في مربع حوار معالجة الأخطاء.
    - **السماح بالتأجيل‬** – هذه المعلمة تمكّن الخيار **تأجيل** في مربع حوار معالجة الأخطاء.
    - **المتابعة مع وجود الخطأ‬** - إذا تم تمكين هذه المعلمة، فبإمكان عملية التسجيل المالي المتابعة على سجل نقطة البيع إذا فشل التسجيل المالي لحركة أو حدث. وبخلاف ذلك، لتشغيل التسجيل المالي للحركة التالية أو الحدث التالي، يجب على المشغّل إعادة تجربة التسجيل المالي الفاشل أو تخطيه أو وضع علامة على الحركة أو الحدث كمسجل. للحصول على مزيد من المعلومات، راجع [التسجيل المالي الاختياري](fiscal-integration-for-retail-channel.md#optional-fiscal-registration).

    > [!NOTE]
    > إذا تم تمكين المعلمة **المتابعة مع وجود الخطأ**، فسيتم تعطيل المعلمتين **السماح بالتخطي** و **السماح بوضع علامة كمسجل‬‏‫** بشكل تلقائي.

1. يحتاج الخياران **تخطي** و **وضع علامة كمسجل** في مربع حوار معالجة الأخطاء إلى تمكين الإذن **السماح بتخطي التسجيل أو وضع علامة كمسجل**. لتمكين هذا الإذن، انتقل إلى الصفحة **مجموعات الأذونات** (**البيع بالتجزئة والتجارة \> الموظفون \>مجموعات الأذونات**)، وعيّن الخيار **السماح بتخطي التسجيل أو وضع علامة كمسجل** إلى **نعم**.
1. يتطلب الخيار **تأجيل‬**‎‏‎ في مربع حوار معالجة الأخطاء تمكين الإذن **السماح بالتأجيل**. لتمكين الإذن، انتقل إلى الصفحة **مجموعات الأذونات** (**البيع بالتجزئة والتجارة \> الموظفون \>مجموعات الأذونات**)، وعيّن الخيار **السماح بالتأجيل** إلى **نعم**.
1. تسمح الخيارات **تخطي‏‎** و **وضع علامة كمسجل** و **تأجيل** للعاملين بإدخال معلومات إضافية عند فشل التسجيل المالي. لإتاحة هذه الوظيفة، يجب تحديد أكواد معلومات **تخطي** و **وضع علامة كمسجل** و **تأجيل** على مجموعة موصلات مالية. يتم عندئذٍ حفظ المعلومات التي قام العاملون بإدخالها كحركة أكواد معلومات مرتبطة بالحركة المالية. للحصول على مزيد من التفاصيل حول أكواد المعلومات، راجع [أكواد المعلومات وأكواد مجموعات المعلومات‬](../info-codes-retail.md).

    > [!NOTE]
    > لم تعد وظيفة المشغل **المنتج** مدعومة لأكواد المعلومات المستخدمة للخيارين **تخطي** و **وضع علامة كمسجل** في مجموعات الموصلات المالية.

    - في صفحة **مجموعة الموصلات المالية**، على علامة التبويب **أكواد المعلومات**، حدد أكواد المعلومات أو مجموعات أكواد المعلومات في الحقول **تخطي** و **وضع علامة كمسجل** و **تأجيل**.

    > [!NOTE]
    > يمكن إنشاء مستند مالي ومستند آخر غير مالي في أي خطوة في عملية التسجيل المالي. يحدد ملحق موفر المستندات المالية كل نوع من حركة أو حدث يرتبط بالمستندات المالية أو غير المالية. وتنطبق ميزة معالجة الأخطاء على المستندات المالية فقط.
    >
    > - **مستند مالي** - مستند إلزامي يجب تسجيله بنجاح (على سبيل المثال، إيصال مالي).
    > - **مستند غير مالي** - مستند مكمّل للحركة أو الحدث (على سبيل المثال، قسيمة بطاقة هدايا).

1. إذا كان من الضروري أن يكون المشغّل قادرًا على متابعة معالجة العملية الحالية (على سبيل المثال، إنشاء حركة أو إنجازها) بعد حدوث خطأ في فحص الصحة، يجب تمكين الإذن **السماح بتخطي خطأ فحص الصحة** في صفحة **مجموعات الأذونات** (**البيع بالتجزئة والتجارة \> الموظفون \> مجموعات الأذونات‏‎**). للحصول على مزيد من المعلومات حول إجراء فحص الصحة، راجع [فحص صحة التسجيل المالي](fiscal-integration-for-retail-channel.md#fiscal-registration-health-check).

## <a name="set-up-fiscal-xz-reports-from-the-pos"></a>إعداد التقارير المالية X/Z من نقطة البيع

لتمكين تشغيل التقارير المالية X/Z من نقطة البيع، يجب إضافة أزرار جديدة إلى تخطيط نقطة البيع.

- في صفحة **شبكات الأزرار**، اتبع الإرشادات في [إضافة عمليات نقطة البيع إلى مخططات نقطة البيع باستخدام مصمم شبكة الأزرار](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters) لتثبيت المصمم وتحديث تخطيط نقطة البيع.

    1. حدد التخطيط الذي تريد تحديثه. 
    1. أضف زرًا جديدًا، وعيّن خاصية الزر **طباعة X المالي**.
    1. أضف زرًا جديدًا، وعيّن خاصية الزر **طباعة Z المالي**.
    1. في صفحة **مجدول التوزيع**، شغّل المهمة **1090** لنقل التغييرات إلى قاعدة بيانات القناة.

## <a name="enable-manual-execution-of-postponed-fiscal-registration"></a>تمكين التنفيذ اليدوي للتسجيل المالي المؤجل

لتمكين التنفيذ اليدوي لتسجيل مالي مؤجل، يجب إضافة زر جديد إلى مخطط نقطة البيع.

- في صفحة **شبكات الأزرار**، اتبع الإرشادات في [إضافة عمليات نقطة البيع إلى مخططات نقطة البيع باستخدام مصمم شبكة الأزرار](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters) لتثبيت المصمم وتحديث تخطيط نقطة البيع.

    1. حدد التخطيط الذي تريد تحديثه.
    1. أضف زرًا جديدًا، وعيّن خاصية الزر **إكمال عملية التسجيل المالي**.
    1. في صفحة **جدول التوزيع**، شغّل المهمة **1090** لنقل التغييرات إلى قاعدة بيانات القناة.


## <a name="view-connection-parameters-and-other-information-in-pos"></a>عرض معلمات الاتصال والمعلومات الأخرى في نقطة البيع

لعرض معلمات الاتصال والمعلومات الأخرى في نقطة البيع، اتبع هذه الخطوات.

1. افتح Modern POS (MPOS) أو Cloud POS (CPOS).
1. حدد **الإعدادات**. إذا تم تمكين التكامل المالي، فسيعرض قسم **التكامل المالي** إلى اليسار المعلومات التالية:

    - حالة التسجيل المالي
    - حالة الحركة المالية الأخيرة
    - عدد أحداث التدقيق المعلقة

1. حدد **التفاصيل** لعرض المعلومات التالية:

    - خطوات عملية التسجيل
    - معلمات الاتصال
    - تفاصيل أحداث التدقيق
 
[!INCLUDE[footer-include](../../includes/footer-banner.md)]
