---
title: وحدات مقارنة المنتج
description: يوضح هذا المقال الوحدات النمطية لمقارنه المنتجات وكيفيه تنفيذها بحيث يمكن للعملاء اجراء مقارنات للمنتجات علي مواقع ويب الخاصة Microsoft Dynamics 365 Commerce بالتجارة الكترونيه.
author: ashishmsft
ms.date: 08/09/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-02-28
ms.openlocfilehash: 6fd851ce6b32d0772c3fe23c4d7bd4dae2616fdc
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 09/13/2022
ms.locfileid: "9474116"
---
# <a name="product-comparison-modules"></a>وحدات مقارنة المنتج

[!include [banner](../includes/banner.md)]

يوضح هذا المقال الوحدات النمطية لمقارنه المنتجات وكيفيه تنفيذها بحيث يمكن للعملاء اجراء مقارنات للمنتجات علي مواقع ويب الخاصة Microsoft Dynamics 365 Commerce بالتجارة الكترونيه.

> [!NOTE]
> تتوفر وحدات أزرار مقارنة المنتج ومقارنة المنتج اعتبارا من الإصدار 10.0.29 من Dynamics 365 Commerce. ويمكن استخدامها لكل من الشركات التي تتم بين المستهلك (B2C) ومواقع ويب شركه إلى شركه (B2B).

تتيح وظيفة مقارنه المنتجات الشوبيرس مقارنه تفاصيل المنتج في صفحه مقارنه المنتجات لمساعدتهم في اتخاذ قرارات شراء أفضل. يتم تكوين هذه الوظيفة في منشئ موقع التجارة باستخدام الوحدة النمطية لمقارنه المنتجات. في صفحات قائمه المنتجات (بلبس) ، مثل نتائج الفئات ونتائج البحث وصفحات مجموعات المنتجات ، يمكنك تكوين زر لمقارنه المنتجات التي تتيح شوبيرس أضافه منتجات إلى علبه المقارنة. يتم تكوين هذه الوظيفة في منشئ الموقع باستخدام الوحدة النمطية للزر "مقارنه المنتجات" ، التي تعمل مثل الوحدة النمطية للعرض [السريع](quick-view-module.md).

عندما يقوم مستخدمو الموقع باضافه منتجات للمقارنة بتحديدهم في إطارات المنتج ، يظهر علبه المقارنة في أسفل الصفحة. يعرض درج المقارنة المنتجات التي يقارنها الشوبير حاليا ، مع المعاينات القصيرة للمنتجات. كما يمكن لمستخدمي الموقع أضافه منتجات من صفحات تفاصيل المنتجات (PDPs) ، كما يمكنهم أضافه متغيرات منتجات معينه لمقارنتها بأصول المنتجات.

بعد قيام العملاء باضافه بعض المنتجات إلى علبه الورق المقارنة ، يمكنهم تحديد **المقارنة** لتتم أعاده توجيهها إلى صفحه مقارنه منتجات. تعرض صفحه مقارنه المنتجات تفاصيل المنتجات لكل منتج محدد بحيث يمكن للعملاء مقارنه الصور والأسعار وابعاد المنتجات (الحجم والنمط واللون) ومعلومات التصنيفات المجمعة وسمات المنتجات الأخرى.

يبين الرسم التوضيحي التالي أمثله علي الزر "مقارنه المنتج" و "أزاله من المقارنة" و "علبه المقارنة" و "صفحه مقارنه المنتجات".

![نظرة عامة على مقارنة المنتج تعرض زر مقارنة المنتج ، وزر الإزالة من المقارنة ، ولوحة صينية المقارنة ، وصفحة مقارنة المنتج.](./media/Product-Comparison-Overview.png)

> [!NOTE]
> - تقارن صفحه مقارنه المنتجات مجموعه افتراضيه من خصائص المنتج وكافة السمات التي يمكن عرضها علي بدب لمنتج معين.
> - لا يمكن عرض خصائص مثل وضع التسليم والمخزون الفعلي ووحده القياس في صفحه مقارنه المنتجات.
> - يمكن للعملاء أضافه منتجات من فئات مختلفه إلى علبه الورق المقارنة ، بشرط ان تكون المنتجات من نفس الكتالوج.
> - تكون وظيفة مقارنه المنتجات محدوده حاليا بمقارنه المنتجات في كتالوج فردي. لا يمكن لمستخدمي الموقع اجراء مقارنات عبر الكتالوجات.
> - يجب التاكد من مسح الخاصية "جانب **عميل الوحدة النمطية** للعرض" لكافة الوحدات النمطية لمقارنه المنتجات.
> - يجب التاكد من تعطيل التخزين المؤقت علي مستوي الصفحة لكافة الصفحات التي يتم فيها استخدام الوحدة النمطية لمقارنه المنتجات. تتضمن هذه الصفحات صفحات مقارنه المنتجات بدبس و بلبس والمنتج. لمزيد من المعلومات، راجع [‏‫تكوين ذاكرة التخزين المؤقت للصفحة‬](e-commerce-extensibility/page-caching.md).

يوضح الرسم التوضيحي التالي مثالاً لصفحة مقارنة المنتج.

![صفحة مقارنة المنتج.](./media/Product-Comparison-Page.png)

## <a name="add-the-product-comparison-module-to-a-new-product-comparison-page"></a>أضافه الوحدة النمطية لمقارنه المنتجات إلى صفحه مقارنه منتجات جديده

يمكنك إنشاء صفحه مقارنه منتجات مخصصه عن طريق أضافه وحده نمطيه لمقارنه المنتجات إلى نص الصفحة. بالاضافه إلى تمكين العملاء من مقارنه تفاصيل المنتج لمنتجات مختلفه ، يمكنك تكوين الوحدة النمطية لمقارنه المنتجات لمنح العملاء الخيار بإكمال الشراء الخاص بهم سريعا بعد مقارنه المنتجات. تحتوي الوحدة النمطية لمقارنه المنتجات أيضا علي **فتحه مقارنه** فارغه ، حيث يمكنك أضافه وحده نمطيه لكتله المحتوي تصف الحالة الفارغة (علي سبيل المثال ، "مقارنه المنتج الخاص بك فارغ").

لإضافة وحدة مقارنة منتج إلى صفحة مقارنة منتج جديدة، اتبع هذه الخطوات.

1. انتقل إلى **الصفحات**، ثم حدد **جديد** لإنشاء صفحة جديدة.
1. في مربع الحوار **‎إنشاء صفحة جديدة** ضمن **صفحة الاسم** أدخل اسم صفحة مناسبًا على (سبيل المثال **مقارنة السلعة**), ثم حدد **التالي**.
1. ضمن **اختيار قالب** حدد القالب المناسب (على سبيل المثال ، القالب الذي تستخدمه صفحة الفئة الافتراضية الخاصة بك)، ثم حدد **التالي**.
1. ضمن **اختيار تخطيط**، حدد تخطيط صفحة (على سبيل المثال، **تخطيط مرن**)، ثم حدد **التالي**.
1. ضمن **مراجعة وإنهاء**، راجع تكوين الصفحة. إذا كان يجب عليك تحرير معلومات الصفحة، فحدد **رجوع**. إذا كانت معلومات الصفحة صحيحة، فحدد **إنشاء صفحة**.
1. في الفتحة **الرئيسية‬‬‏‫**، حدد علامة القطع (**...**)، ثم حدد **إضافة وحدة**.
1. في مربع الحوار **تحديد وحدات**، حدد وحدة **الحاوية‬‏‎**، ثم حدد **موافق**.
1. في فتحة **الحاوية‬‬‏‫**، حدد علامة القطع (**...**)، ثم حدد **إضافة وحدة**.
1. في مربع الحوار **تحديد وحدات** ، حدد وحدة **مقارنة المنتج** ، ثم حدد **موافق**.
1. في فتحة **زر العرض السريع** ، حدد علامة الحذف (**...**)، ثم حدد **إضافة وحدة**.
1. في مربع الحوار **تحديد وحدات** ، حدد وحدة **العرض السريع للمنتج** ، ثم حدد **موافق**.
1. في جزء الخصائص على اليسار ، قم بتكوين **عرض المنتج السريع** خصائص الوحدة.
1. في فتحة **مقارنة فارغة** ، حدد علامة القطع (**...**)، ثم حدد **إضافة وحدة‬‏‫**.
1. في مربع الحوار **تحديد وحدات**، حدد وحدة **كتلة المحتوى‬**، ثم حدد **موافق**.
1. في جزء الخصائص على اليسار ، قم بتكوين ملف **وحدة خصائص** كتلة المحتوى. 
1. حدد **حفظ**، ثم حدد **معاينة** لمعاينة الصفحة.
1. حدد **إنهاء التحرير** لإيداع الصفحة، ثم حدد **نشر** لنشرها.

يوضح الرسم التوضيحي التالي مثالاً لصفحة مقارنة فارغة في منشئ الموقع.

![وحدة مقارنة المنتج.](./media/Product-comparison-module.png)

## <a name="add-a-product-comparison-button-to-product-tiles-on-search-and-category-results-pages"></a>أضافه زر مقارنه منتجات إلى لوحات المنتجات في صفحات نتائج البحث والفئات

يتيح الزر "مقارنه المنتجات" للمستخدمين أضافه منتج سريعا إلى علبه المقارنة عند استعراض المنتجات في صفحه قائمه. يمكنهم أضافه واحد أو أكثر من المنتجات إلى علبه الورق المقارنة من صفحه قائمه دون الحاجة إلى الانتقال إلى بدب.

زر مقارنة المنتج مدعوم من قبل مجموعة المنتجات ونتائج البحث ووحدات صندوق الشراء PDP.

لإضافة زر مقارنة منتج إلى مربعات المنتج في صفحات نتائج البحث والفئة ، اتبع هذه الخطوات.

1. في منشئ الموقع ، انتقل إلى **صفحات** ، وافتح صفحه الفئة التي ترغب في أضافه زر مقارنه منتجات اليها.
1. في الفتحة **الرئيسية‬‬‏‫**، حدد علامة القطع (**...**)، ثم حدد **إضافة وحدة**.
1. في مربع الحوار **تحديد وحدات**، حدد وحدة **نتائج البحث**، ثم حدد **موافق**.
1. في الفتحة **زر مقارنة المنتج** الخاص بوحدة **نتائج البحث** حدد زر علامة الحذف (**...**), ثم حدد **إضافة وحدة**.
1. في مربع الحوار **تحديد وحدات** ، حدد وحدة **زر مقارنة المنتج** ، ثم حدد **موافق**.
1. في جزء الخصائص على اليسار ، قم بتكوين خصائص وحدة **زر مقارنة المنتج**.
1. حدد **حفظ**، ثم حدد **معاينة** لمعاينة الصفحة.
1. حدد **إنهاء التحرير** لإيداع الصفحة، ثم حدد **نشر** لنشرها.

## <a name="specify-the-maximum-number-of-products-to-show-in-the-comparison-tray"></a>حدد الحد الأقصى لعدد المنتجات التي سيتم عرضها في علبه الورق المقارنة

يمكنك تحديد الحد الأقصى لعدد المنتجات التي سيتم عرضها في علبه المقارنة من خلال الانتقال إلى **ملحقات \> إعدادات** الموقع في منشئ الموقع. يمكنك تكوين حدود قصوى منفصلة لطرق العرض "سطح المكتب" و "المحمول/اللوحي". افتراضيا ، لا يتم فرض اي حد إذا لم يتم تحديد الحد الأقصى للحد.

> [!NOTE]
> للحصول علي تجربه الاستعراض المثلي ، نوصي بتعيين الحد الأقصى لعدد المنتجات في علبه الورق المقارنة إلى **2** لمنفذ التنقل المحمول و **4** لاطار الكمبيوتر المحمول لمنفذ الويب لتقليل كميه التمرير الأفقي المطلوبة.

لتحديد الحد الأقصى لعدد المنتجات في علبة المقارنة ، اتبع هذه الخطوات.

1. في موقع البناء، انتقل إلى **إعدادات الموقع \> الملحقات**
1. بالنسبة **للمنتجات الموجودة في الخاصية حد المقارنة-أجهزه** سطح المكتب ، ادخل الحد الأقصى لعدد المنتجات التي يجب ان تظهر في علبه المقارنة لفيوبورتس سطح المكتب.
1. بالنسبة **للمنتجات الموجودة في الخاصية حد المقارنة-أجهزه** أجهزة الجوّال والأجهزة اللوحية، ادخل الحد الأقصى لعدد المنتجات التي يجب ان تظهر في علبه المقارنة إطارات العرض أجهزة الجوّال والأجهزة اللوحية.
1. في شريط الأوامر، حدد **حفظ ونشر**.

![إعدادات الموقع لتحديد المنتجات في علبه الورق في المقارنة.](./media/Site-settings-to-limit-products-in-comparison-tray.png)