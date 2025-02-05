---
title: إدارة الرحلات البحرية
description: يصف هذا المقال كيفيه العمل مع الرحلات. عادة ما تمثل الرحلة سفينة. ومع ذلك، بناءً على ممارساتك وإجراءاتك، يمكن أن يمثل موردًا أو أمر شراء أو عنصرًا آخر يكون منطقيًا لمؤسستك.
author: Weijiesa
ms.date: 12/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMTableListPage, ITMTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 43f28a7e30dbbe15bb02d26483289f25515fcfca
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905852"
---
# <a name="manage-voyages"></a>إدارة الرحلات البحرية

[!include [banner](../../includes/banner.md)]

عادة ما تمثل الرحلة سفينة. ومع ذلك، بناءً على ممارساتك وإجراءاتك، يمكن أن يمثل موردًا أو أمر شراء أو عنصرًا آخر يكون منطقيًا لمؤسستك.

توفر صفحة **جميع الرحلات** تفاصيل الرحلة ومعلومات التسليم والتكلفة ومعلومات حول الأصناف وأوامر الشراء وأوامر التحويل. لفتح صفحة **جميع الرحلات**، انتقل إلى **التكلفة المستلمة \> الرحلات \> جميع الرحلات**. تعرض هذه الصفحة قائمة بكل الرحلات الحالية. يمكنك استخدام الأزرار الموجودة في جزء الإجراءات لإنشاء الرحلات وحذفها والعمل معها. حدد أي رحلة في القائمة لعرض تفاصيلها.

> [!NOTE]
> حاويات الشحن والسجلات مرتبطة برحلة. بنود الشراء مرتبطة بحاوية شحن. إذا تم إيقاف تشغيل حاويات الشحن والسجلات، فيمكن أيضًا ربطها مباشرةً برحلة ما. بالإضافة إلى ذلك، يتم تقسيم التكاليف التي يتم إدخالها هنا على جميع بنود الشراء المرفقة.

## <a name="action-pane"></a>جزء الإجراءات

يوفر جزء الإجراءات الموجود في صفحة **الرحلات** الأزرار التي تتيح لك العمل مع رحلة محددة. يقوم كل زر بتنفيذ إجراء واحد. يتضمن جزء الإجراءات أيضًا علامات تبويب، يوفر كل منها بدوره مجموعة من الأزرار ذات الصلة. باستثناء ما تمت ملاحظته، تتوفر جميع الأزرار وعلامات التبويب في عرض القائمة لصفحة **جميع الرحلات** وفي العرض التفصيلي لرحلة واحدة محددة.

### <a name="buttons-that-appear-directly-on-the-action-pane"></a>الأزرار التي تظهر مباشرةً في جزء الإجراءات

يصف الجدول التالي الأزرار المتوفرة مباشرة في جزء الإجراءات.

| زر | الوصف |
|---|---|
| إنشاء جديد | أنشئ رحلة. <!-- KFM: Link to scenario --> |
| Delete | احذف الرحلة الحالية. فقط الرحلات التي لها حالة الرحلة *مؤكدة* يمكن حذفها. بعد مغادرة الرحلة للميناء ومعالجة البضائع أثناء النقل، لم يعد من الممكن حذفها. |
| محرر الرحلة البحرية | افتح صفحة **محرر الرحلة**، حيث يمكنك إضافة أو إزالة بنود الشراء للرحلة وإنشاء حاويات جديدة وتعديل تفاصيل الرحلة نفسها. |
| تكاليف الرحلة البحرية | افتح صفحة **تكاليف الرحلة**، حيث يمكنك عرض تكاليف الرحلة وإضافتها إلى جميع البضائع في الرحلة. عند إضافة تكاليف الرحلة يدويًا إلى الرحل، يتم إضافتها تلقائيًا إلى صفحة **استعلام التكاليف** ويتم تقسيمها على كل سلعة وفقًا للطريقة المحددة في صفحة **تكاليف الرحلة**. |

### <a name="buttons-on-the-voyage-tab"></a>الأزرار الموجودة في علامة التبويب الرحلة

يصف الجدول التالي الأزرار المتوفرة في علامة التبويب **الرحلة** في جزء الإجراءات. تتوفر علامة التبويب هذه فقط عندما تعمل في طريقة عرض القائمة في صفحة **جميع الرحلات**.

| زر | الوصف |
|---|---|
| حاوية الشحن | افتح صفحة تعرض جميع حاويات الشحن المرتبطة بالرحلة المحددة. قد يكون هناك حاوية واحدة أو عدة حاويات. |
| حافظة الأوراق | افتح صفحة تعرض جميع السجلات المرتبطة بالرحلة المحددة. قد يكون هناك سجل واحد أو عدة سجلات. |

### <a name="buttons-on-the-manage-tab"></a>الأزرار الموجودة في علامة التبويب إدارة

يصف الجدول التالي الإجراءات المتوفرة في علامة التبويب **إدارة** في جزء الإجراءات.

| زر | الوصف |
|---|---|
| المستندات المستلمة | قم بتحديث الرحلة حتى يتم تعيين خيار **المستندات المستلمة** إلى *نعم*. يمكنك استخدام هذا الزر لتامين الصنف و/أو بند الشراء بحيث لا يمكن تحديثه بعد ذلك. |
| قيد النقل | قم بتحديث حقل **حالة الرحلة** إلى حالة أثناء النقل التي تم تحديدها في صفحة **[معلمات التكلفة المستلمة](landed-cost-parameters.md)**. لا يوجد أي منطق آخر في هذه العملية. يمكن أيضًا تحديث الرحلة تلقائيًا إلى حالة أثناء النقل، بناءً على الإعدادات الموجودة في [مركز التحكم في التعقب](delivery-information-setup.md).
| جاهزة لاحتساب التكلفة | قم بتحديث حقل **حالة الرحلة** إلى حالة جاهز لحالة التكاليف التي تم تحديدها في صفحة **[معلمات التكلفة المستلمة](landed-cost-parameters.md)**. يمكن احتساب تكلفة الرحلة عند معالجة جميع الفواتير (فواتير المخزون وفواتير تكلفة الرحلة) واستلام البضائع. إذا لم يتم احتساب التكاليف المقدرة المرتبطة برحلة ما، فسيحدث خطأ عندما تحاول معالجة تكلفة الرحلة. |
| التكاليف | قم بتنظيف أي مخالفات في التكاليف بعد وجود فاتورة لجميع أوامر الشراء وتكاليف الرحلة. عند تحديد هذا الزر، يظهر مربع الحوار **تحديث الرحلة - تم تحديد التكلفة**. هناك، يمكنك تحديد الترحيل في التاريخ المالي القياسي أو تحديد تاريخ الترحيل، ثم تشغيل الإجراء. يمكنك إعادة الإجراء عدة مرات كما تريد. يمكنك أيضا استخدام مربع الحوار **تحديث الرحلة - تم تحديد التكلفة** لإنشاء جدول لتشغيل الإجراء كمهمة دورية (وظيفة دفعية). نوصي بتشغيل الإجراء بانتظام من خلال إعداده كوظيفة دفعية. |
| ترحيل قائمة عمليات الاستلام | قم بترحيل قائمة الإيصالات لجميع بنود أوامر الشراء في الرحلة.  |
| ترحيل إيصال استلام المنتجات | قم بترحيل إيصال استلام منتج لجميع بنود أوامر الشراء في الرحلة. سيتم استخدام عملية استلام المنتجات لبنود أمر الشراء المرتبطة برحلة فقط إذا كانت البضائع **لن** تمر عبر معالجة البضائع أثناء النقل. إذا كانت البضائع ستخضع لمعالجة البضائع أثناء النقل، فستتلقى خطأً عند محاولتك ترحيل إيصال استلام المنتج لبند أمر شراء.  |
| ترحيل فاتورة | قم بترحيل فاتورة لجميع بنود أوامر الشراء في الرحلة. إذا كانت البضائع في الرحلة تمر عبر معالجة البضائع أثناء النقل، فسيتم إصدار فاتورة بخطوط أمر الشراء قبل إتمام عملية الاستلام. عندما يتم تحرير فاتورة بأمر الشراء الأصلي، سيتم إنشاء أوامر نقل البضائع المرتبطة بأصناف أمر الشراء الأصلي. يمكن للمستودع بعد ذلك استلام هذه الأوامر.  |
| أمر تحويل الشحنة | قم بترحيل رحلة أمر التحويل لجميع بنود أمر التحويل في الرحلة. عند تحديد هذا الزر، ستتوفر أوامر التحويل فقط للتحديث. |
| استلام أمر التحويل | قم بترحيل إيصال أمر التحويل لجميع بنود أمر التحويل في الرحلة. |
| استلام البضائع قيد النقل | استلم جميع بنود الأمر التي هي قيد النقل في الرحلة. يعد هذا الزر أحد الخيارات الثلاثة المتوفرة لاستلام البضائع أثناء النقل في الرحلة. (الخياران الآخران هما زر **إنشاء دفتر يومية وصول** الموصوف لاحقًا في هذا الجدول، وتطبيق إدارة المستودع للأجهزة المحمولة.) هذا الخيار هو الخيار الأبسط، وسيعالج البضائع التي يتم نقلها من مستودع البضائع أثناء النقل إلى مستودع الوجهة النهائية. إذا كنت تريد مزيدًا من التحكم في العملية، فاستخدم دفتر يومية الوصول أو جهازًا محمولًا لمعالجة استلام البضائع. |
| البحث عن التكاليف التلقائية | ابحث عن أي تكاليف رحلة ذات صلة. إذا تم العثور علي هذه التكاليف أو تحديثها بالفعل، ستتلقى الرسالة التالية: "بنود التكلفة غير المفوتره". هل تريد استبدالها؟" سيتم العثور على أي تكاليف لم تكن مرتبطة بالرحلة في وقت الإنشاء. لن تتم الكتابة فوق تكاليف الرحلة المرتبطة برحلة والتي تمت فوترتها. |
| إنشاء دفتر يومية الوصول | <p>افتح مربع الحوار **إنشاء دفتر يومية الوصول**، حيث يمكنك إنشاء دفتر يومية وصول يحدد موقعًا. يوفر مربع الحوار الخيارات التالية:</p><ul><li>**إنشاء من البضائع أثناء النقل** أو **إنشاء من أمر النقل** – تتغير تسمية هذا الخيار بناءً على ما إذا كنت تستخدم عملية نقل البضائع أم لا. قم بتعيينه إلى *نعم* لفتح صفحة دفتر يومية وصول تتيح لك معالجة دفتر يومية وصول قياسي للبضائع أثناء النقل والمرتبطة بالرحلة. إذا تم استلام الصنف بالفعل في مستودع الوجهة النهائي، فلن تتم إضافته إلى بنود دفتر يومية الوصول.</li><li>**تهيئة الكمية** – قم بتعيين هذا الخيار إلى *نعم* لتهيئه الكمية التي سيتم استلامها، استنادا إلى كميه السلع التي يتم تحديدها في بند الرحلة. في حاله استلام بند الرحلة بشكل جزئي، ستكون هذه الكمية هي الكمية المتبقية. ونوصي بأن تعين هذا الخيار إلى *نعم*.</li><li>**إنشاء من بنود الأمر** – قم بتعيين هذا الخيار إلى *نعم* لإجراء القيمة من بنود الأمر.</li></ul><p>يعد هذا الزر أحد الخيارات الثلاثة المتوفرة لاستلام البضائع في الرحلة. (الخيارات الأخرى هي زر **استلام البضائع أثناء النقل** الذي تم وصفه سابقًا في هذا الجدول، وتطبيق إدارة المستودع للأجهزة المحمولة).</p> |
| تجميع التكاليف | يمكنك العمل على استحقاق التكاليف عندما يكون لنوع التكلفة حساب دفتر أستاذ محدد للمدين. يستخدم هذا الزر عاده عندما يكون المخزون في حاله انتقال، أو عند استلام البضائع وفوترتها. |
| تجميع التكاليف | قم بنقل التكاليف من مستوي حاويه الشحن إلى مستوي الرحلة. يمكنك استخدام هذا الزر في سيناريو الخدمات/الشحن المشتركة، حيث تتشارك كيانات متعددة في حاوية شحن أو مساحة كرتون. على سبيل المثال، تحتوي الرحلة على حاوية شحن بطول 40 قدمًا وحاوية شحن بطول 20 قدمًا، ويتم التوزيع حسب الحجم. وفي هذه الحالة، قد تكون البضائع/الكيانات التي تشترك في المساحة الموجودة في حاويه الشحن 20 قدم بيناليزيده أو تستخدمها. لتوزيع التكاليف بشكل عادل، قد ترغب بعض المنظمات في تحويل التكاليف إلى الرحلة وتوزيعها بناءً على طريقة تقسيم مستوى الرحلة. |
| تغيير قالب الرحلة | افتح مربع حوار حيث يمكنك تغيير قالب الرحلة. وبعد تغيير القالب، سيتم حذف تكاليف الرحلة. ولذلك، قد يلزم تحديد **البحث عن التكاليف التلقائية** (راجع الوصف السابق في هذا الجدول) أو إضافه التكاليف يدويًا مرة أخرى. |

### <a name="buttons-on-the-general-tab"></a>الأزرار الموجودة في علامة التبويب عام

يصف الجدول التالي الأزرار المتوفرة في علامة التبويب **عام** في جزء الإجراءات.

| زر | الوصف |
|---|---|
| قائمة الإيصالات | افتح قائمة إيصالات المنتجات لجميع بنود أوامر الشراء في الرحلة.  إذا لم تتم معالجة قوائم إيصال استلام المنتجات، فلن يكون هذا الزر متاحًا. |
| إيصال استلام المنتج | افتح سجل إيصال استلام المنتجات لبنود أمر الشراء المرتبطة بالرحلة، إذا تم استخدام هذا السجل. إذا لم يتم ترحيل إيصالات استلام المنتج، فلن يكون هذا الزر متاحًا. لن يتم استخدام عملية استلام المنتج إذا كنت تستخدم معالجة البضائع أثناء النقل. |
| وصول الصنف | افتح دفتر يومية وصول العنصر، إذا تم استخدامه. |
| التعقب | افتح صفحة **تعقب الوارد**، حيث يمكنك تحديث تاريخ الوصول المتوقع للبضائع في حاوية شحن ورحلة، ثم تحديث تواريخ التسليم المتوقعة لبنود أوامر الشراء لاحقًا. |
| الاستعلام عن التكاليف | <p>افتح صفحة **استعلام التكاليف**، التي تعرض كافة التكاليف الخاصة برحلة.</p><p>حدد **طريقة عرض** في جزء الإجراءات لضبط طريقة العرض. يمكنك عرض أي من المستويات، بالإضافة إلى رمز نوع العنصر والتكلفة.</p><p>تظهر فقط أكواد نوع التكلفة المرتبطة مباشرة بحركات المخزون في صفحة **استعلام التكاليف**. بإزالة أكواد أنواع التكلفة، يمكنك ضبط الصفحة عن طريق تجميع التكاليف معًا. يمكن أن تكون هذه الإمكانية مفيدة إذا كنت تستخدم الأحجام والألوان.</p><p>تعرض صفحة **استعلام التكاليف** أكواد نوع التكلفة فقط حيث يتم تعيين **الخصم** إلى *العنصر*.</p> |
| أوامر بضائع قيد النقل | افتح صفحة **أوامر البضائع أثناء النقل**، التي تعرض السجلات الخاصة بالبضائع أثناء النقل للرحلة المحددة فقط. |

## <a name="lines-view"></a>طريقة عرض البنود

لفتح طريقة عرض **البنود**، افتح رحلة، ثم حدد علامة التبويب **البنود** في أعلى يمين عنوان الرحلة.

### <a name="information-on-the-voyage-header-fasttab"></a>المعلومات الموجودة في علامة التبويب السريع رأس الرحلة

تحتوي علامة التبويب السريع **رأس الرحلة** في طريقة عرض **البنود** في الرحلة على المعلومات الأساسية التي توضح الرحلة. تظهر أيضًا العديد من الحقول التي تظهر في علامة التبويب السريعة هذه في طريقة عرض **الرأس**، كما هو موضح لاحقًا في هذا المقال.

### <a name="information-on-the-voyage-lines-fasttab"></a>المعلومات الموجودة في علامة التبويب السريع بنود الرحلة

ترتبط علامة التبويب السريع **بنود الرحلة** في طريقة عرض **البنود** بالرحلة بتفاصيل الرحلة ومعلومات التكلفة التي تنطبق على مستوى الرحلة. هنا، يمكنك مراجعة حاويات الشحن والسجلات والعناصر المرفقة بالرحلة. كما يتم عرض سعر وكمية العناصر في الرحلة. يمكنك عرض أي حاوية شحن أو سجل مدرج عن طريق تحديد الارتباط ذي الصلة.

### <a name="information-on-the-line-details-fasttab"></a>المعلومات في علامة التبويب السريع تفاصيل البند

توفر علامة التبويب السريع **تفاصيل البند** في طريقة عرض **البنود** بالرحلة مزيدًا من المعلومات عن البند المحدد حاليًا في علامة التبويب السريع **بنود الرحلة**. لاحظ أن علامة التبويب السريعة هذه تتضمن تفاصيل حول الموضع الذي يشغله كل بند في الحاوية والكمية المعلن عنها.

## <a name="header-view"></a>عرض الرأس

لفتح طريقة عرض **الرأس**، افتح رحلة، ثم حدد علامة التبويب **الرأس** في أعلى يمين عنوان الرحلة.

### <a name="settings-on-the-general-fasttab"></a>الإعدادات في علامة التبويب السريعة عام

يصف الجدول التالي الحقول المتوفرة في علامة التبويب السريع **عام** في طريقة عرض **الرأس** في الرحلة.

| الحقل | الوصف |
|---|---|
| الرحلة البحرية | أدخل رقم الرحلة أو الرحلة. |
| مرجع الحجز | إذا كان الشاحن أو مركز الشحن الخاص بك يوفر رقمًا مرجعيًا لتحديد الرحلة (أي المرجع الداخلي للشاحن أو مركز الشحن)، أدخله هنا. |
| الباخرة | أدخل السفينة أو حددها. إذا لم يتم إدراج السفينة كقيمة، يمكنك إدخال معرف السفينة كنص حر. في هذه الحالة، لا يتم تحديث الجدول الرئيسي بحيث يمكن تحديد معرف السفينة في هذا الحقل لاحقًا. |
| معرف رحلة بحرية خارجية | أدخل المعرّف المتاح للجمهور للرحلة (مثل رقم الرحلة). |
| بوليصة الشحن الجوي/بوليصة الشحن الرئيسية | أدخل بوليصة الشحن الجوي الرئيسية أو رقم بوليصة الشحن. يمكنك تحديد هذه القيمة عند الشحن عن طريق الجو. |
| بوليصة شحن جوي/بوليصة شحن صادرة من وكيل الشحن | أدخل بوليصة الشحن الجوي للمنزل أو بوليصة الشحن لحاوية الشحن. |
| الإيجار | حدد مربع الاختيار هذا للإشارة إلى أن الحاوية عبارة عن حاوية مستأجرة يجب إرجاعها. |
| الوصف | أدخل وصفًا للرحلة لتسهيل التعرف عليها. |
| حالة الرحلة البحرية | حالة الرحلة. تتضمن القيم *تم الإنشاء* و *أثناء النقل* و *تم استلام المستندات* و *تم الإغلاق*. لا يتم حساب هذا الحقل على أساس المنطق. ويتم تحديثها فقط من خلال إجراء الترحيل. تشير القيمة *تم الإغلاق* إلى أنه تم استلام فاتورة للمخزون وجميع تكاليف الرحلات. وإذا لم يتم استلام الفاتورة، لا تتمكن الرحلة من الوصول إلى الحالة *تم الإغلاق*. |
| حالة أمر الشراء | أعلى حالة تم الوصول إليها بين جميع أوامر الشراء المرتبطة بالرحلة. |
| المستندات المستلمة | قيمة تشير إلى ما إذا كانت شركتك قد استلمت جميع المستندات المرتبطة بالرحلة. لتغيير القيمة، حدد **تم استلام المستندات** في مجموعة **تحديث الرحلات** في علامة التبويب **إدارة** بجزء الإجراءات. |
| شركة الشحن | حدد شركة الشحن لهذه الرحلة. يمكن استخدام هذا الحقل لتحديد التكاليف التلقائية. |
| الاسم | اسم الشركة المحددة في حقل **شركة الشحن**. |
| القياس | يتيح هذا الحقل تحديد القياس في التكلفة التلقائية. غالبًا ما تُستخدم القياسات من قبل المؤسسات التي لا تعرف الحجم الفردي للبضائع أو وزنها، ولكنها تتطلب تقسيمًا أكثر دقة مما توفره الكمية أو المبلغ. سيوفر وكيل الشحن الوزن أو القياس المكعب، ويمكنك وضعه على مستوى عنصر أو أمر شراء. يمكن تحديثه تلقائيًا إذا تم تحديد المعلمة، أو يمكن إدخالها يدويًا. |
| وحدة القياس | وحدة القياس التي تنطبق على الرقم الموجود في حقل **القياس**. |
| عدد البالتات | حدد عدد المنصات على خط الرحلة. يتم تحديث هذا الحقل تلقائيًا إذا تم تعيين خيار **تحديث تلقائي لعدد الكراتين** إلى *نعم* في علامة التبويب **عام** في صفحة **معلمات التكلفة المستلمة**. |

### <a name="settings-on-the-delivery-fasttab"></a>الإعدادات في علامة التبويب السريع التسليم

يصف الجدول التالي الحقول المتوفرة في علامة التبويب السريع **التسليم** في طريقة عرض **الرأس** في الرحلة.

| الحقل | الوصف |
|---|---|
| تاريخ  ووقت الإنشاء | التاريخ والوقت الذي تم فيه إنشاء سجل الرحلة. |
| تاريخ تجهيز الشحنة ونقلها من المصنع | يحدد هذا الحقل أقرب تاريخ سابق لمصنع من بين أوامر الشراء المرتبطة بالرحلة. يكون تاريخ التصنيع متاحا في البيانات الرئيسية لأمر الشراء ويتم تحديثه باستخدام ميزه التحكم في التعقب. |
| تاريخ الشحن | التاريخ المقدر عندما تغادر الطائرة أو السفينة نقطة المنشأ. |
| تاريخ المغادرة | عادة ما يكون تاريخ المغادرة هو التاريخ الذي تغادر فيه الطائرة أو السفينة فعليًا الميناء الخارجي. لا يلزم مطابقه تاريخ الشحن وتاريخ المغادرة. حقل **تاريخ المغادرة** هو لغرض المعلومات فقط. لا يتم استخدامه لتقدير تاريخ التسليم المتوقع. تُستخدم ميزة التحكم في التعقب لتقدير تاريخ التسليم المتوقع، ويمكن إعداد هذا الحقل بحيث يتم ملؤه تلقائيًا بواسطة ميزة التحكم في التعقب. |
| تاريخ الدخول إلى المخزن | يحدد هذا الحقل أقرب تاريخ تكون فيه البضائع من أوامر الشراء المرتبطة بالرحلة متاحة للبيع. |
| تاريخ التسليم المقدّر | عادة ما يكون تاريخ التسليم المقدر هو التاريخ الذي يحين فيه وصول البضائع إلى المستودع. هذا الحقل للأغراض المعلوماتية فقط. لا يتم استخدامه للتخطيط الرئيسي للبضائع. يتم استخدام تاريخ التسليم المتوقع في بند أمر الشراء للتخطيط الرئيسي للبضائع في الرحلة ويتم تحديثه باستخدام ميزة التحكم في التعقب. يمكن إعداد هذا الحقل بحيث يتم ملؤه بواسطة ميزة التحكم في التعقب. |
| تاريخ التسليم الفعلي | أقرب تاريخ للتسليم، بناءً على البضائع المرتبطة بالرحلة. |
| وقت الوصول المقدّر في مرفأ الشحن | أدخل التاريخ الذي تتوقع أن تصل فيه الرحلة إلى ميناء الشحن، بناءً على المعلومات التي قدمها وكيل الشحن الخاص بك. |
| تم استلام المستندات الأصلية | أدخل التاريخ الذي تم فيه استلام المستندات الأصلية. |
| موصى به من قِبل الوسيط | أدخل تاريخ إخطار الوسيط. |
| تم إرسال بوليصة الشحن الأصلية | أدخل تاريخ إرسال بوليصة الشحن الأصلية. |
| إصدار البضائع | أدخل التاريخ الذي تم فيه الإفراج عن البضائع من الجمارك. |
| موعد العميل | أدخل تاريخ موعد العميل، وهو التاريخ الذي تتوقع فيه أن يأخذ العميل ملكية البضائع. |
| تم التسليم في المستودع | أدخل التاريخ الذي تم فيه تسليم البضائع إلى المستودع. |
| تاريخ التحقق | أدخل تاريخ التحقق. |
| إرشادات التسليم | أدخل تاريخ استلام تعليمات التسليم. |
| وضع التسليم | يوفر هذا الحقل معلومات حول الطريقة المستخدمة لتسليم الرحلة واختيار تكلفة تكاليف السيارات المرتبطة بطريقة التسليم هذه. |
| مرفأ المغادرة | ميناء الشحن الذي تنطلق منه الرحلة. |
| إلى المرفأ | ميناء الشحن الذي تصل إليه الرحلة. يمكن أن يكون لحاويات الشحن موانئ مختلفة، لأن السفينة قد تتوقف عند موانئ متعددة. من خلال التحقق من منفذ "إلى" على مستوى حاوية الشحن، فإنك تقدم تفاصيل منفذ دقيقة لكل حاوية شحن في رحلة ما. يتم تحديد التكلفة التلقائية المرتبطة بالشحن بناءً على مجموعة من نوع حاوية الشحن والمنفذ "إلى" والمنفذ "من". |
| وكيل شحن محلي | هذا الحقل للأغراض المعلوماتية فقط. يجب أن يكون وكيل الشحن المحلي قابلاً للتحديد من جدول المورد. |
| تاريخ النقل المحلي | التاريخ الذي تم حجز النقل المحلي له. يمكن أن يساعد هذا الحقل المستودع في التخطيط له. |
| وقت النقل المحلي | جزء الوقت الذي تم حجز النقل المحلي له. يمكن أن يساعد هذا الحقل المستودع في التخطيط له. |
| قالب الرحلة | قالب الرحلة المحدد للرحلة. يتم استخدام نموذج الرحلة لإدخال منفذ "إلى" و"من" لحاوية الشحن والرحلة. هذه القيم، بدورها، تساعد في تحديد تكاليف السيارات المرتبطة بالرحلة. |

### <a name="settings-on-the-other-fasttab"></a>الإعدادات في علامة التبويب السريعة أخرى

يصف الجدول التالي الحقول المتوفرة في علامة التبويب السريع **أخرى** في طريقة عرض **الرأس** في الرحلة.

| الحقل | الوصف |
|---|---|
| ملاحظات | أدخل معلومات إضافية تتعلق بالرحلة. |
| تاريخ التقييم | حدد هذا الحقل أقرب تاريخ سابق للتصنيع لأوامر الشراء المرتبطة بالرحلة. |
| رحلة بحرية معلّقة | يمكنك استخدام هذا للإشارة إلى ما إذا كانت شحنتك أو رحلتك قد غادرت بعد. هذا لأغراض معلوماتية فقط.  |
| إعادة تسمية حاويات الشحن | بالنسبة للرحلات التي تحتوي على أكثر من حاوية، عدد الحاويات التي لم يتم استلامها بعد. |

## <a name="voyage-update-periodic-tasks"></a>المهام الدورية لتحديث الرحلة

تشتمل وحدة **التكلفة المستلمة** على العديد من المهام الدورية المتعلقة بالرحلة والتي يمكن تحديثها بشكل مجمع للعديد من جوانب الرحلة. لتشغيل هذه المهام الدورية أو جدولتها، انتقل إلى **التكلفة المستلمة \> المهام الدورية \> تحديثات الرحلة**، ثم حدد أحد أنواع المهام التالية:

- **تم استلام المستندات** – تتيح لك هذه المهمة تعيين **المستندات التي تم استلامها** إلى *نعم* لعدة رحلات في نفس الوقت. استخدم إعدادات **التصفية** لتحديد مجموعه الرحلات التي ترغب في تحديثها.
- **أثناء النقل** – تتيح لك هذه المهمة إمكانية تعيين حقل **حالة الرحلة** إلى حالة أثناء النقل المحددة في صفحة **[معلمات التكلفة المستلمة](landed-cost-parameters.md)** للعديد من الرحلات في الوقت نفسه. استخدم إعدادات **التصفية** لتحديد مجموعه الرحلات التي ترغب في تحديثها.
- **جاهز للتكاليف** – تتيح لك هذه المهمة إمكانية تعيين حقل **حالة الرحلة** إلى حالة جاهز للتكاليف المحددة في صفحة **[معلمات التكلفة المستلمة](landed-cost-parameters.md)** للعديد من الرحلات في الوقت نفسه. ستقوم عادةً بإعداد هذه المهمة للتشغيل وفقًا لجدول زمني منتظم.
- **التكاليف** - تتيح لك هذه المهمة تعيين حقل **حالة الرحلة** إلى الحالة المغلقة التي تم تحديدها في صفحة **[معلمات التكلفة المستلمة](landed-cost-parameters.md)** لعدة رحلات في نفس الوقت، بشرط أن يكون قد تم السجل ولكن لم يتم تحديثها بعد الرحلة. ستقوم عادةً بإعداد هذه المهمة للتشغيل وفقًا لجدول زمني منتظم.
