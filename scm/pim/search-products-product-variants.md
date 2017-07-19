---
title: "البحث عن المنتجات ومتغيرات المنتجات أثناء إدخال الأمر"
description: "استخدم حقل <strong>رقم الصنف </strong> للبحث عن المنتجات ومتغيرات المنتجات عندما تقوم بإنشاء بند أمر مبيعات أو بند أمر شراء يدويًا.  يسمح لك ذلك بالعثور بسرعة على متغيرات المنتجات إذا توفرت لديك سلسلة التكوين أو أحد أبعاد المنتح فقط."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: MCRFullTextIndexField, MCRFullTextParameters, PurchTable, SalesTable
audience: Application User
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 248534
ms.assetid: 99dd5ce1-0029-4f06-90e7-865e6d46d86e
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 3960cc3eb9b8d488973d258db45aa0ab9f1dd988
ms.contentlocale: ar-sa
ms.lasthandoff: 05/25/2017


---

# <a name="search-for-products-and-product-variants-during-order-entry"></a>البحث عن المنتجات ومتغيرات المنتجات أثناء إدخال الأمر

[!include[banner](../includes/banner.md)]

[!include[Retail name](../includes/retail-name.md)]

استخدم حقل <strong>رقم الصنف </strong> للبحث عن المنتجات ومتغيرات المنتجات عندما تقوم بإنشاء بند أمر مبيعات أو بند أمر شراء يدويًا.  يسمح لك ذلك بالعثور بسرعة على متغيرات المنتجات إذا توفرت لديك سلسلة التكوين أو أحد أبعاد المنتح فقط.

في بعض الأحيان، قد لا تجد نفسك في وضع مثالي عندما تمتلك كمية كبيرة من منتج ما، وهذا يصح تحديدًا إذا كنت تبيع عددًا من المنتجات المتشابهة، وكنت تحاول أن تتذكر أرقام الأصناف أو البحث عن أسماء المنتجات للعثور على المنتج المناسب لوضعه في أمر المبيعات. يمكنك استخدام حقل **رقم الصنف** على بند أمر مبيعات أو أمر شراء كحقل بحث. يمكنك إدخال أي جزء من اسم المنتج أو الرقم أو البُعد والحصول على بحث يعرض كافة الأصناف التي تطابق كلمة البحث.

## <a name="how-search-works"></a>كيفية تعمل ميزة البحث
عندما تبحث عن منتجات أو متغيرات منتجات، من الضروري فهم كيف تعثر ميزة البحث عن المنتجات التي تطابق النص الذي أدخلته. قواعد البحث الرئيسية في تقديم نتائج البحث هي:

-   تُرجع نتائج البحث أي سجل مطابق، بصرف النظر عن الحقل الذي تم إدخال نص البحث فيه.
-   يجب أن يكون نص البحث موجودًا في السجل المطابق بطوله الكامل.
-   سوف تحدث المطابقة حتى لو تم العثور على نص البحث في وسط سلسلة نصية في السجل المطابق. ومن غير الضروري أن يظهر في بداية سلسلة نصية.
-   يتم التعامل مع نص البحث كسلسلة نصية واحدة حتى لو احتوى على مسافة بيضاء.

### <a name="examples"></a>أمثلة

تستخدم الأمثلة التالية المنتجات ومتغيرات المنتجات لتوضيح كيفية التعامل مع البحث في سيناريوهات متعددة. **المتطلب الأساسي:** ضمن **المبيعات والتسويق &gt; الإعداد &gt; البحث &gt; معلمات البحث** &gt; **نوع البحث**، حدد الخيار **تطابق كامل**.

| نوع المنتج     | اسم المنتج    | رقم عرض المنتج | رقم الصنف | التكوين |
|------------------|-----------------|------------------------|-------------|---------------|
| منتج مميز | SpeakerMidRange | D0001                  | D0001       | غير متوفر            |
| متغير المنتج  | مكبر صوت النشط  | D0010:::أسود:         | D0010       | 000005        |
| متغير المنتج  | مكبر صوت النشط  | D0010:::أبيض:         | D0010       | أبيض         |

إذا قمت بكتابة "كلام" في حقل **رقم الصنف**، فستحصل على كافة المنتجات المذكورة أعلاه كنتيجة في البحث. إذا قمت بكتابة "أسود" في حقل **رقم الصنف**، فستحصل على المنتج الثاني كنتيجة، لأنه يحتوي على النص "أسود" في رقم عرض المنتج. يوضح هذان المثالان أن البحث ليس فقط في بداية الحقل، بل أن التطابق يحدث حتى لو تم العثور على نص البحث في وسط سلسلة نصية في السجل المطابق.  

إذا قمت بكتابة "05"، فستحصل فقط على متغير المنتج الثاني كنتيجة، لأنه يحتوي على "05" في التكوين. وهذا يوضح أن البحث يتم عبر كافة الحقول الممكّنة في صفحة **معايير البحث**.  

إذا قمت بكتابة "كلام 05"، لن تحصل على أية نتائج. وسبب ذلك أن ميزة البحث تبحث عن كامل النص الذي تم إدخاله. ولن تحاول ميزة البحث العثور على "كلام" ثم تضييق النتائج إلى تلك التي تحتوي على "05".  

يمكنك تحديد عدد نتائج البحث باستخدام حقل **عدد النتائج** في صفحة **المبيعات والتسويق &gt; الإعداد &gt; البحث &gt; معلمات البحث**. إذا قمت بتعيين هذا الحقل إلى 0، يتم إرجاع كافة نتائج البحث. إذا قمت بتعيينه إلى 10، على سبيل المثال، فسيُرجع 10 نتائج بحث كحد أقصى.

## <a name="configure-the-product-search"></a>تكوين البحث عن المنتج
قبل استخدام ميزة البحث عن المنتجات ومتغيرات المنتجات، اتبع هذه الخطوات لتكوين البحث عن المنتج. [![3 خطوات لتكوين بحث المنتجات\_AXAppFall](./media/3-steps-to-configure-product-search_axappfall.png)](./media/3-steps-to-configure-product-search_axappfall.png)

### <a name="step-1-include-all-the-relevant-product-and-product-variant-identifiers-and-dimensions-in-the-search-criteria"></a>الخطوة 1: تضمين كل معرفات وأبعاد المنتجات ومعرفات المنتجات ذات الصلة في معايير البحث

أمثلة معرفات وأبعاد المنتجات ومعرفات المنتجات التي يمكنك البحث فيها هي **اسم المنتج ورقم الصنف**, **رقم عرض المنتج، التكوين، اللون، الحجم، النمط، اسم البحث، إلخ**.  

انتقل إلى **المبيعات والتسويق &gt; الإعداد &gt; البحث &gt; معايير البحث**. تسمح لك صفحة **معايير البحث** بتعريف المعايير الخاصة بالعملاء والعملاء المتوقعين والبحث عن المنتج. تأكد من تصفية الصفحة باستخدام معايير البحث عن المنتج. يمكنك القيام بذلك عن طريق التبديل إلى **المنتج** في قائمة الصفحة.  

‏‫لإضافة رقم عرض المنتج إلى معايير البحث، انقر فوق **جديد** في قائمة الصفحة. سيؤدي ذلك إلى إضافة سجل جديد في شبكة **معايير البحث**. افتح عمود البحث **اسم الحقل** واختر **DisplayProductNumber**. لإضافة تكوين المنتج إلى معايير البحث، قم بإنشاء سجل جديد في شبكة **معايير البحث** واختر **configId** في عمود **اسم الحقل**. بطريقة ماثلة، قم بإنشاء سجل مع **اسم الحقل** **InventColorId** لبُعد اللون و**InventSizeId** لبُعد الحجم و**InventStyleId** لبُعد النمط.

### <a name="step-2-populate-the-database-table-that-is-used-for-product-search"></a>الخطوة 2: تعبئة جدول قاعدة البيانات المستخدمة للبحث عن المنتج

في صفحة **معايير البحث**، انقر فوق الزر **تحديث بيانات البحث**. في مربع الحوار **تحديث بيانات البحث**، تأكد من تعيين **المصدر** إلى **المنتج**، ثم انقر فوق **موافق**. ‏‫سيقوم النظام بتجميع كافة معايير البحث المحددة المحدد في الخطوة 1 في جدول واحد. إذا كان لديك كثير من المنتجات ومتغيرات المنتجات، فقد تستغرق هذه العملية وقتًا طويلاً وقد تتلقى رسالة تحذير.‬ نوصي بأن تقوم بجدولة تعبئة جدول البحث على خادم الدُفعة‬ عندما لا يكون الخادم كثير الانشغالات.  

لن يوفر البحث عن المنتج النتائج الصحيحة إلا بعد تعبئة الجدول. إذا لم تحصل على أية نتائج بحث، فتأكد من تعبئة هذا الجدول.  

يجب تعبئة الجدول فقط عند تعديل معايير البحث. تُضاف بشكل تلقائي إلى الجدول المنتجات ومتغيرات المنتجات التي تم إصدارها حديثًا. وتُزال بشكل تلقائي من الجدول المنتجات ومتغيرات المنتجات المحذوفة.

### <a name="step-3-enable-the-lookup-for-product-search-on-sales-and-purchase-order-lines"></a>الخطوة 3: تمكين البحث للبحث عن المنتج على بنود أوامر المبيعات وأوامر الشراء

يمكنك تمكين هذه الوظيفة عن طريق الانتقال إلى **المبيعات والتسويق &gt; الإعداد &gt; البحث &gt; معلمات البحث** وتعيين الخيار **تمكين البحث للبحث** إلى **نعم** في علامة التبويب **عام**.  

بالنسبة إلى إدخالات بنود أمر المبيعات، السلوك الافتراضي هو فتح صفحة  **البحث عن منتج** عند بدء الكتابة في حقل **رقم الصنف**، ثم الضغط على المفتاح **Tab**. تقو صفحة **البحث عن منتج** بتغيير السياق أثناء إنشاء بند أمر، ويمكن اعتبار ذلك بمثابة تدخل لا داعي له. إذا كنت تفضل الحصول على نتائج البحث في عملية بحث دون فقدان السياق أثناء إدخال بند الأمر، يمكنك استخدام البحث في البحث بدلاً من ذلك. إذا كنت تبحث عن منتج أو متغير منتج، ولكنك لم تحدد أي شيء في البحث وقمت بالضغط على المفتاح **Tab**، فستظهر صفحة **البحث عن منتج**.



