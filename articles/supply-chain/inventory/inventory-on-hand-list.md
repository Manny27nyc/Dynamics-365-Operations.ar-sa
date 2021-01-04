---
title: قائمة المخزون الفعلي
description: يصف هذا الموضوع كيفية استخدام صفحة قائمة المخزون الفعلي لفحص تفاصيل المخزون الفعلي. وهي تعرض بعض الطرق التي تعمل من خلالها خيارات التصفية والفرز المختلفة معًا، وكيف يمكن لهذه الخيارات أن تنتج في بعض الأحيان نتائج غير متوقعة عند دمجها.
author: sherry-zheng
manager: tfehr
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventOnhandItem, InventOnHandItemListPage, WHSOnHand
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-07-07
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 33e5ccc454191e27e33835a05094b823ec54e891
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 10/16/2020
ms.locfileid: "4421784"
---
# <a name="inventory-on-hand-list"></a>قائمة المخزون الفعلي

[!include [banner](../includes/banner.md)]

يصف هذا الموضوع كيفية استخدام صفحة **قائمة المخزون الفعلي** لفحص تفاصيل المخزون الفعلي. وهي تعرض بعض الطرق التي تعمل من خلالها خيارات التصفية والفرز المختلفة معًا، وكيف يمكن لهذه الخيارات أن تنتج في بعض الأحيان نتائج غير متوقعة عند دمجها.

## <a name="query-your-on-hand-inventory"></a>الاستعلام عن المخزون الفعلي

لفحص توفر المخزون، انتقل إلى **إدارة المخزون \> الاستعلامات والتقارير \> قائمة المخزون الفعلي**.

يتم تحديث صفحة **قائمة المخزون الفعلي** بشكل تلقائي عند إجراء حركات في المخزون. قد تكون هذه الحركات عبارة عن حركات تم التنبؤ بها أو حركات فعلية أو مالية.

استخدم الأدوات التالية للعثور على مجموعة المنتجات التي تبحث عنها:

- في جزء الإجراءات، حدد [**الأبعاد**](#dimensions) لفتح مربع حوار حيث يمكنك إضافة أو إزالة الأعمدة التي تظهر في شبكة **المخزون الفعلي**.
- في جزء [**عوامل التصفية**](#filters-pane)،أدخل قيمًا للحقول المعينة لإظهار فقط السجلات التي تتطابق مع هذه القيم. لاحظ أن عوامل التصفية التي تقوم بتحديدها هنا تنطبق على الجداول المصدر التي قد يتم تجميعها لاحقًا، وفقًا للأبعاد التي حددتها كي تم إظهارها. للحصول على معلومات حول كيفية تأثير هذا السلوك هلة النتائج، راجع [الأمثلة](#examples) لاحقًا في هذا الموضوع.
- في جزء **عوامل التصفية**، حدد **تطبيق** لإنشاء قائمة المخزون الفعلي المطابق في شبكة **المخزون الفعلي**.
- في شبكة **المخزون الفعلي**، حدد أي رأس عمود للفرز أو التصفية حسب القيم الموجودة في هذا العمود. يوفر QuickFilter في أعلى الشبكة خيارات تصفية إضافية. يتم تطبيق عوامل التصفية هذه على النتائج، وليس على الجداول المصدر. للحصول على معلومات حول كيفية تأثير هذا السلوك هلة النتائج، راجع [الأمثلة](#examples) لاحقًا في هذا الموضوع.

بالنسبة لكل صنف مطابق، توفر شبكة **المخزون الفعلي** الأعمدة التالية لمعلومات المخزون.

| العمود | ‏‏الوصف |
|---|---|
| المخزون الفعلي | الكمية الفعلية المتوفرة في المخزون. |
| المحتجز الفعلي | إجمالي الكمية التي تم حجزها فعليًا. |
| الفعلي المتاح | الكمية المتوفرة (غير المحجوزة) المتوفرة في المخزون الفعلي.<p>**الفعلي المتاح** هو حقل محسوب. القيمة تساوي قيمة **المخزون الفعلي** ناقص قيمة **المحجوز الفعلي**.</p> |
| المحجوز الفعلي على الأبعاد الإضافية | الكمية الفعلية المتاحة لكافة الأبعاد المعروضة في الشبكة. |
| الكمية المطلوبة إجمالاً | إجمالي الكمية المضمنة في الأوامر الواردة أو التي لها كمية موجبة في دفاتر يومية المخزون المتعددة. |
| تحت الطلب | إجمالي الكمية المضمنة في الأوامر الصادرة أو التي لها كمية سلبية في دفاتر يومية المخزون المتعددة. |
| الكمية المطلوبة المحجوزة | إجمالي الكمية المحجوزة في عمليات الاستلام المطلوبة. تمثل القيمة الموجودة في هذا الحقل إجمالي كمية الأصناف الموجودة في الحركات الصادرة بالحالة _مطلوبة محجوزة_. الأصناف المحجوزة كأصناف مطلوبة غير متاحة فعليًا في المخزون. وبالتالي، لا يمكن انتقاؤها وتسليمها بشكل مباشر. |
| متوفر للحجز | إجمالي كمية المخزون الفعلي التي يمكن حجزها.<p>**ملاحظة:** إذا تم تحديد خانة الاختيار **حجز الأصناف المطلوبة‬** في صفحة **معلمات إدارة المستودعات والمخزون‬**، تتضمن القيمة في هذا الحقل الإيصالات المتوقعة. إذا تم إلغاء تحديد خانة الاختيار، يتم استبعاد الإيصالات المتوقعة من القيمة.</p> |
| الإجمالي المتاح | إجمالي الكمية المتوفرة.<p>**الإجمالي المتاح** هو حقل محسوب. القيمة تساوي قيمة **الفعلي المتاح** بالإضافة إلى قيمة **الكمية المطلوبة إجمالاً** ناقص قيمة **تحت الطلب**.</p> |

## <a name="apply-filters-to-find-the-records-that-youre-looking-for"></a><a name="filters-pane"></a>تطبيق عوامل التصفية للعثور على السجلات التي تبحث عنها

استخدم جزء **عوامل التصفية** لتصفية قائمة قائمه المخزون الفعلي بحيث تتضمن فقط السجلات حيث تتطابق قيم الحقول مع معايير التصفية. لتعريف عامل تصفية، اتبع هذه الخطوات.

1. في جزء **عوامل التصفية**، ابحث عن الحقل الذي تريد استخدامه لإجراء التصفية.
2. في الحقل الموجود أسفل اسم الحقل الهدف، حدد عامل التشغيل المنطقي (على سبيل المثال، *يبدأ بـ* أو *يساوي* أو *أكبر من*).
3. ادخل القيمة التي تريد البحث عنها أو حددها.

> [!IMPORTANT]
> يتم تجميع صفحة **قائمة المخزون الفعلي** من جدول المخزون الفعلي الذي يتضمن جميع الأبعاد المتوفرة. ومع ذلك، القائمة الموجودة في هذه الصفحة هي ملخص. وبالتالي، فقد تجمع الصفوف من الجدول المصدر عن طريق تجميع القيم وفقًا للأبعاد المعروضة.
>
> تنطبق عوامل التصفية التي تقوم بتعريفها في جزء **عوامل التصفية** على الجدول المصدر ، وليس على القائمة المجمعة. قد يُنتج هذا السلوك في بعض الأحيان نتائج غير متوقعة. للحصول على معلومات حول كيفية تأثير هذا السلوك هلة النتائج، راجع [الأمثلة](#examples) لاحقًا في هذا الموضوع.
> 
> ومع ذلك، فإن [عوامل التصفية المتوفرة في الشبكة](#grid-filters) *تنطبق* على القائمة المجمعة. تتضمن عوامل التصفية هذه QuickFilter في الجزء العلوي من الشبكة بالإضافة إلى عامل التصفية لكل عنوان عمود.

يمكنك تعديل مجموعة عوامل التصفية المتوفرة في جزء **عوامل التصفية** باتباع الخطوات التالية.

- لإزالة عامل تصفية من الجزء، حدد الزر **إغلاق** التابع له (**X**).
- لإضافة عامل تصفية، حدد **إضافة** في أعلى جزء **عوامل التصفية**. يعرض مربع الحوار **إضافة حقول التصفية** الذي يظهر قائمة بالحقول المتوفرة. ويعرض أيضًا معلومات حول نوع البيانات والجدول لكل حقل. استخدم عناوين الأعمدة لتصفية القائمة وفرزها كما هو مطلوب، ثم حدد خانة الاختيار لكل حقل تريد إضافته إلى جزء **عامل التصفية**. عند الانتهاء، حدد **إدراج** لتطبيق التغييرات.

## <a name="select-which-dimensions-to-show"></a><a name="dimensions"></a>حدد الأبعاد المطلوب عرضها

تخبرك الأبعاد بالمزيد حول كل صنف في قائمة المخزون الفعلي، وتمنحك المزيد من الطرق لفرز القائمة وتصفيتها. تؤثر أيضًا الأبعاد التي تحددها لعرضها على كيفية تجميع الصفوف في صفحة **قائمة المخزون الفعلي**. وبإمكان هذا التجميع، بدوره، أن يؤثر على كيفية دمج الصفوف من الجداول المصدر في النتائج التي تراها. للحصول على معلومات حول كيفية تأثير هذا السلوك هلة النتائج، راجع [الأمثلة](#examples) لاحقًا في هذا الموضوع.

لتخصيص التحديد الخاص بأبعاد المخزون المعروضة، اتبع الخطوات التالية.

1. في جزء الإجراءات، حدد **الأبعاد**.

    يعرض مربع الحوار **عرض البُعد** الذي يظهر كل بُعد.

2. حدد خانة الاختيار لكل بُعد تريد تضمينه في الشبكة.
3. إذا أردت أن يتم استخدام تحديدك بشكل افتراضي في المرة التالية التي تقوم فيها بفتح صفحة **قائمة المخزون الفعلي**، عيّن الخيار **حفظ الإعداد** إلى **نعم**. إذا قمت بتعيين هذا الخيار إلى **لا**، سيتم استخدام تحديدها فقط خلال جلسة العمل الحالية. وبالتالي، في المرة التالية التي تقوم فيها بفتح الصفحة، سيتم استخدام التحديد الافتراضي الحالي.
4. حدد **موافق** لإغلاق مربع الحوار وتطبيق تغييراتك.

## <a name="filter-on-the-output-of-the-inventory-on-hand-list"></a><a name="grid-filters"></a>التصفية على مخرجات قائمة المخزون الفعلي

يمكنك تحديد أي عنوان عمود في شبكة **المخزون الفعلي** للفرز أو التصفية حسب القيم الموجودة في هذا العمود. يوفر QuickFilter في أعلى الشبكة خيارات تصفية إضافية. يتم تطبيق عوامل التصفية هذه على النتائج، وليس على الجداول المصدر. للحصول على معلومات حول كيفية تأثير هذا السلوك هلة النتائج، راجع [الأمثلة](#examples) لاحقًا في هذا الموضوع.

> [!NOTE]
> لا يمكنك التصفية والفرز حسب كافة الأعمدة. لا تتضمن معظم أعمدة الكمية عناصر تحكم الفرز والتصفية، لأنها عبارة عن حقول محتسبة. العمود **حسب الطلب** هو استثناء.

## <a name="examples"></a><a name="examples"></a>أمثلة

يتضمن النظام جدولاً مفصلاً (غير مجمع) للمخزون يعرض المخزون الفعلي التالي.

| رقم الصنف | الموقع | المستودع | المخزون الفعلي | الفعلي المتاح |
|---|---|---|---|---|
| IA0001 | 1 | 1 | 1 | 1 |
| IA0001 | 1 | 2 | 2 | 2 |
| IA0001 | 1 | 3 | 1 | 1 |

### <a name="scenario-1"></a>السيناريو 1

يتم إعداد صفحة **قائمة المخزون الفعلي** لإظهار الأبعاد النهائية التالية:

- رقم العنصر
- الموقع
- المستودع

في جزء **عوامل التصفية**، تم إعداد معايير التصفية التالية:

- **رقم الصنف** \| **هو تمامًا** \| _IA0001_
- **الفعلي المتاح** \| **أقل من أو يساوي** \| _1_

فيما يلي الإخراج الناتج.

| رقم الصنف | الموقع | المستودع | المخزون الفعلي | الفعلي المتاح |
|---|---|---|---|---|
| IA0001 | 1 | 1 | 1 | 1 |
| IA0001 | 1 | 3 | 1 | 1 |

### <a name="scenario-2"></a>السيناريو 2

يتم إعداد صفحة **قائمة المخزون الفعلي** لإظهار الأبعاد النهائية التالية:

- رقم العنصر
- الموقع

في جزء **عوامل التصفية**، تم إعداد معايير التصفية التالية:

- **رقم الصنف** \| **هو تمامًا** \| _IA0001_
- **الفعلي المتاح** \| **أقل من أو يساوي** \| _1_

فيما يلي الإخراج الناتج.

| رقم الصنف | الموقع | المخزون الفعلي | الفعلي المتاح |
|---|---|---|---|
| IA0001 | 1 | 2 | 2 |

لاحظ أن الإعدادات الموجودة في جزء **عوامل التصفية** تنطبق على الجدول المفصل (غير المجمع) للمخزون الذي يظهر في بداية هذا القسم. وبالتالي، فإن المعيار **الفعلي المتاح** \| **أقل من أو يساوي** \| _1_ يبحث عن صفين من الجدول (الصف الأول والثالث، يعرض كل واحد منهما قيمة **الفعلي المتاح** من _1_). ومع ذلك، في هذا السيناريو ، لم يتم إعداد صفحة **قائمة المخزون الفعلي** لإظهار **بُعد المستودع**. وهي بالتالي تقوم بتجميع الصفين الأصليين في صف ناتج واحد، لأن الصفين لهما قيم مماثلة في جميع الأبعاد التي تظهر. يبدو هذا الصف وكأنه يخرق معيار التصفية، لأن قيمة **الفعلي المتاح** تظهر على أنها _2_. ومع ذلك، فالنتيجة صحيحة، لأن الإعدادات الموجودة في جزء **عوامل التصفية** تنطبق على الجدول المصدر، وليس على الجدول المجمع الذي يظهر في صفحة **قائمة المخزون الفعلي**.