---
title: "بدائل التسليم"
description: "باستطاعة متلقي أوامر المبيعات استخدام صفحة \"بدائل التسليم‬\" لاكتشاف الخيارات البديلة لتنفيذ الأوامر."
author: ChristianRytt
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesLineDeliveryDetails
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 271623
ms.assetid: 527f6084-44fe-41bb-924f-4386e926358a
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: cbfbdf5f79ef557ea934505285b57562b0b289ba
ms.contentlocale: ar-sa
ms.lasthandoff: 09/29/2017

---

# <a name="delivery-alternatives"></a>بدائل التسليم

[!include[banner](../includes/banner.md)]


باستطاعة متلقي أوامر المبيعات استخدام صفحة "بدائل التسليم‬" لاكتشاف الخيارات البديلة لتنفيذ الأوامر.

في الإصدار 1611 من Microsoft Dynamics 365 for Operations (نوفمبر 2016)، يستطيع متلقي أوامر المبيعات استخدام صفحة **بدائل التسليم** لاكتشاف الخيارات البديلة لتنفيذ الأوامر. يوفر تخطيط الصفحة المعاد تصميمها نظرة عامة أفضل على كافة الخيارات البديلة. ويسمح أيضًا لمتلقي أوامر المبيعات بالنظر إلى ما يتجاوز الشركة الحالية للاطلاع على فرص التنفيذ. فباستطاعتهم الآن عرض الفرص بين الشركات الشقيقة والفرص من مورّدين خارجيين. ومن خلال فرز الخيارات حسب تاريخ التسليم، يستطيع متلقو أوامر المبيعات عرض قائمة ذكية ببدائل التسليم. بالإضافة إلى ذلك، تساعدهم المعلمات على إدارة عمليات التسليم المقترحة بشكل أفضل. نظرًا لإمكانية تأثير وقت النقل على تواريخ التسليم، باستطاعة متلقي أوامر المبيعات استكشاف مختلف اختيارات النقل المختلفة التي تقدمها شركات النقل. ونظرًا لعرض معلومات تفصيلية لكل اقتراح، باستطاعة متلقي أوامر المبيعات اتخاذ قرارات صائبة مباشرة من صفحة **بدائل التسليم**.

## <a name="open-the-delivery-alternatives-page"></a>فتح صفحة "بدائل التسليم"
يمكنك فتح صفحة **بدائل** **التسليم** من بند أمر المبيعات.

1.  انقر فوق **المنتجات والتوريد** &gt; **بدائل التسليم**.
2.  انقر فوق **تفاصيل البنود‬** &gt; **التسليم** &gt; **بدائل التسليم.**

يمكنك أيضًا فتح صفحة **بدائل التسليم** عن طريق فتح مساحة العمل **الاستعلام عن أمر المبيعات ومعالجته**، ثم النقر فوق **الأوامر والمفضلات** &gt; **بنود الأوامر المؤجلة** &gt; **بدائل التسليم** **ملاحظة:** يمكنك فتح صفحة **بدائل التسليم** فقط عند استيفاء الشرطين التاليين:

-   يتم إدخال كافة معلومات بنود المبيعات الإلزامية.
-   يتم تعيين الحقل **التحكم في تاريخ التسليم** إلى قيمة أخرى غير **بلا**.

## <a name="delivery-date-control-methods"></a>أساليب التحكم في تاريخ التسليم
يحدد أسلوب التحكم في تاريخ التسليم كيف يقوم النظام بتأسيس تواريخ التسليم وطريقة حساب بدائل التسليم وما هي المعلومات التي يتم عرضها. لاحظ أن التحكم في تاريخ التسليم يأخذ التقويمات في الاعتبار. لذلك، باستطاعة التقويمات التالية التأثير على تاريح الاستلام المقترح: تقويم المستودع وتقويم النقل وتقويم المورّد وتقويم العميل. يصف الجدول التالي كل أسلوب للتحكم في تاريخ التسليم.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><strong>الأسلوب</strong></td>
<td><strong>الوصف</strong></td>
</tr>
<tr class="even">
<td><strong>بلا</strong></td>
<td><ul>
<li>لا يتم دعم بدائل التسليم لبنود المبيعات. يؤدي تحديد هذا الخيار إلى إيقاف تشغيل التحكم في تاريخ التسليم.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>‏‏الحد الأدنى لوقت المبيعات</strong></td>
<td><ul>
<li>يتم حساب بدائل التسليم استنادًا إلى الحد الأدنى لوقت المبيعات المعرف مسبقًا. يتم حساب أيام النقل بالاستناد إلى وضع التسليم.</li>
<li>تتضمن بدائل التسليم المستودعات التي لها مخزون فعلي وأوامر توريد/طلب.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>ATP</strong></td>
<td><ul>
<li>يتم حساب بدائل التسليم بالاستناد إلى منطق المتوفر حسب التعهد (ATP). يؤخذ في الاعتبار التوافر الحالي والتوافر المستقبلي المتوقع. يتم حساب أيام النقل بالاستناد إلى وضع التسليم.</li>
<li>تتضمن بدائل التسليم المستودعات التي لها مخزون فعلي وأوامر توريد/طلب.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>ATP + هامش الإصدار</strong></td>
<td><ul>
<li>يتم حساب بدائل التسليم كما في طريقة ATP، ولكن يتم تضمين هامش الإصدار في عملية الحسابي=.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>CTP</strong></td>
<td><ul>
<li>يتم حساب بدائل التسليم بالاستناد إلى منطق المتاح للتعهد (CTP). يتم استخدام عملية تحديد إجمالي المكونات المطلوبة MRP لتحديد مدى التوافر. لاحظ أنه بالحد الأدنى، يقوم منطق CTP بإزاحة تواريخ التسليم إلى الحد الأدنى لوقت المبيعات. يتم حساب أيام النقل بالاستناد إلى وضع التسليم.</li>
<li>تتضمن بدائل التسليم اقتراحات للمستودعات التالية:
<ul>
<li>المستودع الحالي</li>
<li>المستودع الافتراضي</li>
<li>كافة المستودعات ذات مخزون فعلي متاح</li>
<li>كافة المستودعات ذات أوامر توريد</li>
<li>كافة المستودعات ذات إصدارات قائمة مكونات صنف نشطة</li>
</ul></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="view-information-about-delivery-alternatives"></a>عرض معلومات حول بدائل التسليم
يصف هذا القسم معلومات حول بدائل التسليم المتوفرة على كل علامة تبويب في صفحة **بدائل التسليم**.

### <a name="products"></a>المنتجات

تعرض علامة التبويب هذه ملخصًا للمنتج وتفاصيل بند المبيعات الحالي.

### <a name="delivery-alternatives"></a>بدائل التسليم

تعرض علامة التبويب هذه قائمة ببدائل التسليم التي يتم فرزها حسب تاريخ الاستلام. في أعلى القائمة، يمكنك تحديد الخيارات التي يجب أن تستند الاقتراحات إليها. يمكنك أيضًا تحديد وضع التسليم، الذي يحدد أيام النقل. يتوفر الخياران التاليان:

-   **تضمين متغيرات منتجات أخرى‬** - يتوفر هذا الخيار للمنتجات التي تحتوي على متغيرات المنتج. وسيتضمن بدائل التسليم لمتغيرات المنتج الأخرى. هذا الخيار غير متوفر في CTP.
-   **تضمين الكمية الجزئية‬** - بشكل افتراضي، يتم تضمين فقط الاقتراحات التي تفي بالكمية الكاملة لبند المبيعات. حدد هذا الخيار لتضمين اقتراحات تفي ببند الأمر جزئيًا فقط. يعتبر هذا الخيار مفيدًا عندما يطلب العميل تاريخ تسليم أقرب ويوافق على التسليم الجزئي.
-   **تضمين تواريخ لاحقة** - بشكل افتراضي، تظهر فقط الاقتراحات التي تعتبر أفضل (أبكر) من التواريخ الحالية في بند المبيعات. حدد هذا الخيار لتضمين تواريخ لاحقة. قد يكون هذا الخيار مفيدًا في الحالات حيث تكون الأولوية لمعلمات أخرى غير التاريخ. على سبيل المثال، قد تكون الأولوية لمورّد أو مستودع معيّن.
-   **وضع التسليم** - حدد وضع التسليم المفضل لتحسين وقت النقل وتكلفته. سوف ترى التأثير مباشرة على بدائل التسليم المقترحة. وبالتالي، من السهل مقارنة البدائل.
-   **تضمين التدبير** - عند تحديد تدبير، تتضمن بدائل التسليم المقترحة خيارات للشراء من الموردين الخارجيين والشركات الأخرى في المؤسسة (بين الشركات الشقيقة). يتم اعتماد خيار **تضمين التدبير** فقط لكل من ATP وATP + التحكم في تاريخ تسليم هامش الإصدار. يتم تضمين خيارات التدبير من مورّد الشراء الافتراضي للمنتج وكافة المورّدين المعتمدين للمنتج.
-   بالنسبة إلى المورّدين الخارجيين، يستند الحساب إلى زمن وصول البضاعة.
-   بالنسبة إلى الشركات الشقيقة، يأخذ الحساب في الاعتبار ما هو متوفر من شركة التوريد، استنادًا إلى التحكم في تاريخ التسليم في شركة التوريد.
-   **نوع التسليم** (ذو صلة بالتدبير)
    -   **المخزون** - يتم شحن المنتجات من مستودع التوريد إلى الموقع/المستودع في بند المبيعات. ثم يتم شحنها من هذا المستودع إلى العميل.
    -   **التسليم المباشر** - يتم شحن المنتجات مباشرة من مستودع التوريد إلى العميل.

### <a name="availability-information"></a>معلومات التوفر

تتعلق المعلومات على علامة التبويب هذه ببند بديل التسليم المحدد. يتم عرض المعلومات التالية، بحسب التحكم في تاريخ التسليم لبند المبيعات:

-   **الحد الأدنى لوقت المبيعات**
    -   **متوفر اليوم‬** - لإظهار المخزون الفعلي الموجود‬ والفعلي المحجوز والفعلي المتوفر.
    -   **معلمات** - عرض وحدة المخزون والحد الأدنى لوقت المبيعات‬.

-   **ATP وATP + هامش الإصدار‬**
    -   **متوفر اليوم‬** - لإظهار المخزون الفعلي الموجود‬ والفعلي المحجوز والفعلي المتوفر.
    -   **معلمات** - عرض وحدة المخزون والحد الأدنى لوقت المبيعات‬.
    -   **التوافر في المستقبل‬** - عرض تمثيل رسومي للتوافر الحالي والمستقبلي الخاص بالموقع والمستودع المحددين تحت **بدائل التسليم**. يمكنك النقر فوق أعمدة المخطط للاطلاع على مزيد من المعلومات التفصيلية حول توفر المنتج في المستقبل. يعرض شريط التمرير قائمة بأوامر التوريد والطلب ذات الصلة ضمن الحد الزمني لـ ATP.

-   **CTP**
    -   **متوفر اليوم‬** - لإظهار المخزون الفعلي الموجود‬ والفعلي المحجوز والفعلي المتوفر.
    -   **معلمات** - عرض وحدة المخزون والحد الأدنى لوقت المبيعات‬.
    -   **تحديد إجمالي المكونات المطلوبة** - عرض تحديد إجمالي المكونات المطلوبة للتوريد فيما يتعلق ببديل التسليم المحدد. يمكنك استخدام **إعداد** لتغيير أبعاد الحقول والمخزون التي تظهر في تحديد إجمالي المكونات المطلوبة.

### <a name="impact-of-selected-alternative"></a>تأثير البديل المحدد

تميز علامة التبويب هذه تأثير بديل التسليم المحدد. إذا قمت بالنقر فوق **موافق**، يتم تحديث بند المبيعات بالقيم المحددة الموجودة في الأعمدة "المحددة". لاحظ أنه إذا كانت الكمية على بديل التسليم المحدد أقل من الكمية في بند المبيعات، يتم إنشاء جدول تسليم، ويتم تقسيم بند الأمر إلى بندين: أحدهما للكمية المحددة والآخر للكمية المتبقية. يمكنك أيضًا تحديث البند التجاري لكي يتطابق مع بنود الجدول ويؤثر على التسعير.

<a name="see-also"></a>راجع أيضًا
--------

[التعهد بالأمر](delivery-dates-available-promise-calculations.md)




