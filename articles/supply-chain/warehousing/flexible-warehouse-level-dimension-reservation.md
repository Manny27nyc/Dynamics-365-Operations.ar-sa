---
title: سياسة مرنة لحجز البعد على مستوى المستودع
description: يصف هذا الموضوع نهج حجز المخزون الذي يجب علي الشركات التي تقوم ببيع المنتجات التي تتبع المجموعات وتشغيل التجهيزات الخاصة به كعمليات ممكنة ل WMS-بحجز مجموعات محدده لأوامر توريد العميل ، حتى وان كان التدرج الهرمي للحجز الذي يتم المرتبطة بالمنتجات لا تسمح بحجز الدفعات الخاصة.
author: omulvad
manager: tfehr
ms.date: 02/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2020-01-15
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 6c462a87494c434a6047542d448a85b3bce9f769
ms.sourcegitcommit: ffd845d4230646499b6f074cb43e69ab95787671
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/07/2020
ms.locfileid: "3346458"
---
# <a name="flexible-warehouse-level-dimension-reservation-policy"></a>سياسة مرنة لحجز البعد على مستوى المستودع

[!include [banner](../includes/banner.md)]

عندما يكون نوع التسلسل الهرمي الخاص بحجز\[المخزون للنوع "الدفعة تحت الموقع\]" مقترنا بالمنتجات، لا يمكن للشركات التي تقوم Microsoft Dynamics 365ببيع المنتجات التي تتبع المجموعات وتشغيل التجهيزات الخاصة بها لنظام أداره المستودعات (WMS) حجز دفعات محدده لأوامر توريد العميل. يصف هذا الموضوع نهج حجز المخزون الذي يتيح لهذه الشركات حجز مجموعات محدده ، حتى عندما تكون المنتجات\[مقترنة بالتدرج الهرمي للحجز الخاص بالمجموعة\].

## <a name="inventory-reservation-hierarchy"></a>التدرجات الهرمية لحجز المخزون

يلخص هذا المقطع التدرج الهرمي لحجز المخزون الموجود. فهو يركز علي الطريقة التي يتم بها معالجه الأصناف التي يتم تتبعها من قبل التجميع والأصناف التي تتبع التسلسل.

يفرض التدرج الهرمي لحجز المخزون علي المدى القلق لابعاد التخزين ، والتي تكون فيها الابعاد إلزاميه الموقع ، والمستودع ، وحالة المخزون ، حيث يكون منطق المستودع مسؤولا عن تعيين موقع إلى الكميات المطلوبة وحجز الموقع. بمعني آخر، في التفاعلات بين أمر الطلب وعمليات المستودع، من المتوقع أن يشير أمر الطلب إلى المكان الذي يجب أن يتم فيه شحن الأمر من (أي الموقع والمستودع). وبعد ذلك يعتمد المستودع علي المنطق الخاص به للعثور علي الكمية المطلوبة في المستودع المحلي.

ومع ذلك ، لكي تعكس نموذج التشغيل الخاص بالاعمال ، يتم عرض ابعاد التعقب (المجموعة والأرقام المسلسلة) لمزيد من المرونة. يمكن للتسلسل الهرمي لحجز المخزون استيعاب السيناريوهات التي تنطبق فيها الشروط التالية:

- يعتمد العمل علي عمليات المستودع الخاصة به لأداره انتقاء الكميات التي تحتوي علي المجموعة أو الأرقام المسلسلة بعد العثور علي الكميات في مساحة التخزين التي يتم تخزينها. عاده ما يشار إلى هذا النموذج *\[بالموقع\]* الدفعي. ويستخدم عاده عندما لا يكون تعريف مجموعة المنتجات أو الرقم المسلسل مهما للعملاء الذين يقومون بتقديم الطلب مع الشركة الموردة.
- إذا كانت المجموعة أو الأرقام المسلسلة جزءا من مواصفات أمر العميل ، وتم تسجيلها في أمر الطلب ، يتم تقييد عمليات المستودع التي تقوم بالبحث عن الكميات في المستودع بواسطة الأرقام المطلوبة المحددة ولا يسمح بتغييرها. يشار إلى هذا النموذج *\[بالموقع\]* الدفعي.

في هذه السيناريوهات ، يكون التحدي هو انه يمكن تعيين تسلسل هرمي واحد فقط لحجز المخزون لكل منتج تم إصداره. التالي ، بالنسبة إلى WMS لمعالجة الأصناف المتتبعة، بعد أن يحدد تعيين التدرج الهرمي متى يتم حجز المجموعة أو الرقم المسلسل (أما عند أخذ أمر الطلب أو أثناء عمل الانتقاء الخاص بالمستودع)، لا يمكن تغيير هذا التوقيت على أساس المؤقت.

## <a name="flexible-reservation-for-batch-tracked-items"></a>حجز مرن للأصناف التي يتم تعقبها للدفعة

### <a name="business-scenario"></a>سيناريو الأعمال

في هذا السيناريو، تستخدم إحدى الشركات استراتيجية مخزون حيث يتم تعقب البضائع المنتهية حسب أرقام المجموعات. تستخدم هذه الشركة أيضا حمل العمل WMS. نظرا لأن حمل العمل هذا يستخدم منطق مجهز بشكل جيد لتخطيط عمليات الشحن والشحن وتشغيلها للأصناف التي تم تمكين المجموعة بها\[،\]يتم إقران معظم الأصناف المنتهية بالتسلسل الهرمي الخاص بحجز المخزون الخاص بالمجموعة. تعد ميزة هذا النوع من الإعداد التشغيلي بأن القرارات (التي تعتبر قرارات حجز فاعلية) حول المجموعات التي سيتم انتقاؤها ومكان وضعها في المستودع يتم تأجيلها حتى تبدأ عمليات انتقاء المستودع. ولا يتم اجراؤها عند وضع أمر العميل.

علي الرغم من أن التسلسل الهرمي للحجز "الدفعة تحت\[الشركة\]" يعمل بشكل جيد، يتطلب العديد من العملاء الذين تم تأسيسهم للشركة وجود نفس المجموعة التي تم شراؤها مسبقا عند قيامهم بإعادة ترتيب المنتجات. التالي، فإن الشركة تبحث عن مرونة في الطريقة التي تتم بها معالجة قواعد الحجز، وذلك وفقا لطلب العملاء لنفس الصنف، تحدث السلوكيات التالية:

- يمكن تسجيل رقم المجموعة وحجزها عند أخذ الطلب بواسطة معالج المبيعات، ولا يمكن تغييره أثناء عمليات المستودع و/أو القيام بذلك من قبل طلبات أخرى. ويضمن هذا السلوك شحن رقم المجموعة التي تم طلبها إلى العميل.
- إذا كان رقم المجموعة غير هام للعميل، يمكن أن تحدد عمليات المستودع رقم مجموعة أثناء العمل التصنيعي، بعد إجراء تسجيل أمر التوريد والحجز.

### <a name="allowing-reservation-of-a-specific-batch-on-the-sales-order"></a>السماح بحجز مجموعة محددة في أمر المبيعات

لاستيعاب المرونة المطلوبة في سلوك حجز الدفعات للأصناف المقترنة بالتسلسل\[الهرمي لحجز المخزون\]"الدفعة" ، **يجب أن يقوم مديرو** المخزون بتحديد **خانة الاختيار السماح بالحجز حسب الطلب لمستوي رقم** المجموعة في **صفحة التدرجات الهرمية لحجز المخزون**.

![صيانة جدول التدرج الهرمي لحجز المخزون](media/Flexible-inventory-reservation-hierarchy.png)

عند تحديد **مستوى رقم** المجموعة في التدرج الهرمي، يتم تحديد كافة الأبعاد الموجودة **أعلى** هذا المستوى والمستوى المحدد تلقائيا. (بشكل افتراضي، يتم تحديد **كافة الأبعاد فوق مستوى الموقع** بشكل مسبق.) ويعكس هذا السلوك المنطق الذي يتم فيه أيضا حجز كافة الأبعاد الموجودة في النطاق بين رقم المجموعة والموقع تلقائيا بعد حجز رقم مجموعة محدد في بند الأمر.

> [!NOTE]
> يتم **تطبيق خانة الاختيار السماح بالحجز حسب طلب** الطلب فقط على مستويات التدرج الهرمي للحجز الموجودة أسفل بعد موقع المستودع.
>
> **رقم** المجموعة هو المستوى الوحيد في التدرج الهرمي المفتوح لنهج الحجز المرن. بمعنى آخر ، لا يمكنك تحديد خانه الاختيار **السماح بالحجز حسب الطلب** **للموقع** أو **لوح الترخيص** أو مستوى **الرقم المسلسل**.
>
> إذا تضمن التدرج الهرمي للحجز بعد الرقم المسلسل (والذي **يجب** أن يكون أقل من مستوى رقم المجموعة)، وإذا قمت بتشغيل الحجز الخاص بالمجموعة لرقم المجموعة، سيتابع النظام معالجة حجز الرقم المسلسل وعمليات الانتقاء\[، وذلك استنادا إلى القواعد التي تنطبق علي نهج الحجز\]

عند أي نقطة، يمكنك السماح بالحجز الخاص بالدفعة للتسلسل\[الهرمي للحجز الموجود ضمن المجموعة\]"في عملية التوزيع الخاصة بك. لن يؤثر هذا التغيير على أية عمليات حجز وعمل مستودع مفتوح تم إنشاؤه قبل حدوث التغيير. ومع ذلك **، لا يمكن إلغاء تحديد** خانة الاختيار السماح بالحجز حسب أمر **الطلب**إذا **كانت**حركات **المخزون الخاصة بنوع المشكلة الفعلية المحجوزة أو المحجوزة أو المطلوبة** موجودة لصنف واحد أو أكثر من الأصناف المرتبطة بتسلسل الحجز هذا.

> [!NOTE]
> إذا لم يسمح التدرج الهرمي للحجز الموجود بالصنف بمواصفات التشغيلة في الأمر، فيمكنك إعادة تعيينه إلى تدرج الحجز الذي يسمح بمواصفات المجموعة، بشرط أن تكون بنية مستوى التدرج الهرمي هي نفسها في كلا التدرجات الهرمية. استخدم وظيفة **تغيير التدرج الهرمي** للحجز للأصناف لإجراء إعادة التعيين. قد يكون هذا التغيير متعلقا عندما ترغب في منع حجز المجموعات المرنة لمجموعة فرعية من الأصناف التي تتبع المجموعة ولكن مع السماح لها بالحفاظ علي بقية قائمة مشاريع المنتج.

بغض النظر عما إذا كنت قد قمت بتحديد **خانة الاختيار السماح بالحجز حسب أمر** الطلب ، فاذا كنت لا ترغب في حجز رقم مجموعة معين للصنف في بند أمر، سيظل\[بالإمكان تطبيق منطق عمليات المستودع الافتراضي الذي يعد صالحا للتسلسل الهرمي للحجز الخاص بالمجموعة\].

### <a name="reserve-a-specific-batch-number-for-a-customer-order"></a>حجز رقم مجموعة محدد لأمر عميل

بعد إعداد الصنف "الدفعات الموجودة\[في\]أسفل الصنف الذي تم تتبعه" للسماح بحجز أرقام مجموعات معينة في أوامر التوريد، يمكن أن تتخذ معالجات أوامر التوريد طلبات العميل لنفس الصنف بأحدي الطرق التالية، وذلك وفقا لطلب العميل:

- **ادخل تفاصيل الأمر بدون تحديد رقم** المجموعة - يجب استخدام هذه الطريقة عندما لا تكون مواصفات المجموعة الخاصة بالمنتج مهمة للعميل. كافة العمليات الموجودة المقترنة بمعالجة أمر من هذا النوع يظل النظام بدون تغيير. لا توجد اعتبارات إضافية مطلوبة في جزء المستخدمين.
- **ادخل تفاصيل الأمر وقم بحجز رقم مجموعة معين** - يجب استخدام هذا الأسلوب عندما يطلب العميل مجموعة معينة. وعادة ما يقوم العملاء بطلب مجموعة محددة عند إعاده طلب المنتج الذي تم شراؤه سابقا. ويشار إلى هذا النوع من الحجز الخاص بالدفعة *بالحجز المرتبط بالأمر*.

وتكون المجموعة التالية من القواعد صالحة عند معالجة الكميات، ويتم تخصيص رقم مجموعة لأمر محدد:

- للسماح بحجز رقم مجموعة محدد لصنف ضمن نهج الحجز "المجموعة الموجودة أسفل\[المجموعة\]" ، يجب أن يقوم النظام بحجز كافة الأبعاد خلال الموقع. يتضمن هذا النطاق عادة بُعد لوح الترخيص.
- لا يتم استخدام توجيهات المواقع عند إنشاء انتقاء العمل لبند المبيعات الذي يستخدم حجز المجموعات المرتبطة بالأمر.
- وأثناء معالجة المستودع للعمل بالنسبة للدفعات المرتبطة بالأمر، لا يسمح للمستخدم أو النظام بتغيير رقم المجموعة. (تتضمن هذه المعالجة معالجة الاستثناء.)

يوضح المثال التالي تدفق نهاية إلى نهاية.

## <a name="example-scenario"></a>سيناريو كمثال

بالنسبة إلى هذا العرض التوضيحي، يجب تثبيت بيانات العرض التوضيحي، ويجب استخدام شركة بيانات العرض التوضيحي **USMF‎**.

### <a name="set-up-an-inventory-reservation-hierarchy-to-allow-batch-specific-reservation"></a>إعداد تدرج هرمي لحجز مخزون للسماح بحجز خاص بمجموعة

1. الانتقال إلى **إدارة المخزون** \> **إعداد** \> **المخزون \> ‏‫التدرج الهرمي للحجز‬**.
2. حدد **جديد**.
3. في حقل **الاسم** أدخل اسمًا (على سبيل المثال، **BatchFlex**).
4. في الحقل **الوصف**، ادخل وصفا (على سبيل المثال، **المجموعة الموجودة أسفل المرونة**).
5. في الحقل **المحدد**، حدد **الرقم المسلسل** و**المالك**، ثم حدد زر السهم الأيسر لنقلهم إلى الحقل **المتوفر**.
6. حدد **موافق**.
7. في الصف الخاص بمستوى بعد **رقم المجموعة**، حدد خانة الاختيار **السماح بالحجز عند الطلب**. يتم تحديد **لوحة الترخيص**ومستويات **الموقع** تلقائيا، ولا يمكنك إلغاء تحديد خانات الاختيار الخاصة بها.
8. حدد **حفظ**.

### <a name="create-a-new-released-product"></a>إنشاء منتج جديد صادر

1. قم بتعيين معلمات البيانات الرئيسية الثلاثة الخاصة بالمنتج باستخدام هذه القيم:

    - وفي الحقل **مجموعة أبعاد التخزين**، حدد **مستودع**.
    - في الحقل **تتبع مجموعة الأبعاد**، حدد **الدفعة المادية**.
    - في حقل **تدرج الحجز**، حدد **BatchFlex**.

2. قم بإنشاء رقمين للمجموعة مثل **B11** و**B22**.
3. أضافه كميات الأصناف إلى المخزون الفعلي من خلال استخدام القيم التالية.

    | المستودع | رقم الدُفعة | الموقع | لوحة الترخيص | الكمية |
    |-----------|--------------|----------|---------------|----------|
    | 24        | B11          | BULK-001 | لا‬‬ شيء          | 10       |
    | 24        | B11          | FL-001   | LP11          | 10       |
    | 24        | B22          | FL-002   | LP22          | 10       |

### <a name="enter-sales-order-details"></a>إدخال تفاصيل أمر المبيعات

1. انتقل إلى **المبيعات والتسويق** \> **أوامر المبيعات** \> **كافة أوامر المبيعات**.
2. حدد **جديد**.
3. في البيانات الرئيسية لأمر التوريد ، في الحقل **حساب العميل**، أدخل **US-003**.
4. أضف سطرًا لمنتج مُنتهِ، وادخل **10** ككمية. تأكد من تعيين الحقل **الكمية** على **24**.
5. في علامة التبويب السريعة **بنود أمر التوريد**، حدد **المخزون**، ثم في المجموعة **الصيانة**، حدد **حجز المجموعة**. تقوم **صفحه حجز** المجموعات بعرض قائمة بالمجموعات المتوفرة للحجز الخاص ببند الأمر. بالنسبة لهذا المثال، فإنه يعرض كمية بمقدار **20** لرقم المجموعة **B11** وكمية **10** لرقم المجموعة **B22** . لاحظ أنه لا يمكن الوصول إلى صفحة **حجز الدفعة** من بند إذا كان الصنف الموجود في هذا السطر مقترنا بالتدرج الهرمي للحجز الموجود\[بالبند "الدفعة\]" ما لم يتم إعداده للسماح بالحجز الخاص بالدفعة.

    > [!NOTE]
    > لحجز مجموعة محددة لأمر توريد، يجب استخدام الصفحة **حجز المجموعة**.
    >
    > إذا قمت بإدخال رقم المجموعة مباشره في بند أمر التوريد ، سيعمل النظام كما لو قمت بإدخال قيمه مجموعة محدده لأحد الأصناف الذي يخضع لنهج الحجز "المجموعة ضمن\[الموقع\]". عند حفظ البند، ستتلقى رسالة تحذير. إذا قمت بالتاكيد علي انه يجب تحديد رقم المجموعة مباشره علي سطر الأمر، فلن تتم معالجه البند بواسطة منطق إدارة المستودع العادي.
    >
    > إذا قمت بحجز الكمية من صفحة **الحجز**، فلن يتم حجز مجموعة محددة، سيتبع تنفيذ عمليات المستودع للبند القواعد التي تنطبق عليها نهج الحجز\["الدفعات الموجودة في أسفل\]".

    بشكل عام ، تعمل هذه الصفحة ويتم التفاعل معها بنفس الطريقة التي تعمل بها ويتم التفاعل مع الأصناف التي تحتوي علي تسلسل هرمي مقترن لنوع "المجموعة الموجودة أعلى \[الموقع\]". ومع ذلك، يتم تطبيق الاستثناءات التالية:

    - تعرض علامة التبويب السريعة **أرقام المجموعات التي تم تنفيذها لبند المصدر** أرقام المجموعات التي تم حجزها لبند الأمر. ستظهر قيم المجموعات في الشبكة خلال دورة الاستيفاء لسطر الأمر، بما في ذلك مراحل معالجة المستودع. وعلي النقيض، في علامة التبويب السريعة **النظرة العامة**، يتم عرض حجز بند الأمر العادي (أي ، الحجز الذي يتم إنجازه للابعاد الموجودة اعلي مستوي **الموقع**) في الشبكة حتى النقطة التي يتم فيها إنشاء عمل المستودع. ثم يقوم كيان العمل بعد ذلك بالحفاظ علي حجز البند ، ولا يظهر حجز البند بعد ذلك في الصفحة. تساعد علامة التبويب السريعة **أرقام المجموعات التي تم تنفيذها علي بند المصدر** على التأكد من أن معالج أمر التوريد يمكنه عرض أرقام المجموعات التي تم تنفيذها لأمر العميل في أي مرحلة أثناء الفوترة.
    - بالإضافة إلى القيام بحجز مجموعة محدده، يمكن للمستخدم تحديد الموقع الخاص بالمجموعة ولوحه الترخيص يدويا بدلا من السماح للنظام بتحديدها تلقائيا. ترتبط هذه الامكانيه بتصميم آلية حجز المجموعة الملتزم بها الأمر. للسماح بحجز رقم مجموعة محدد لصنف ضمن نهج الحجز "المجموعة الموجودة أسفل\[الموقع\]" ، يجب أن يقوم النظام بحجز كافة الأبعاد خلال الموقع. التالي، سيحمل عمل المستودع نفس أبعاد التخزين التي تم حجزها بواسطة المستخدمين الذين قاموا بالعمل مع الأوامر، وقد لا يمثلون دائما موضع تخزين الأصناف الملائم ، أو حتى الممكن ، لعمليات الانتقاء. إذا كانت معالجه الأمر علي علم بقيود المستودع ، فقد يرغبون في تحديد المواقع المحددة ولوحات الترخيص يدويا عند حجزها لأحدي المجموعات. في هذه الحالة ، يجب أن يستخدم المستخدم وظيفة **ابعاد العرض** في راس الصفحة ، ويجب أن يضيف لوحه الموقع والترخيص الشبكة في على علامة التبويب السريعة **النظرة العامة**.

6. في الصفحة **حجز المجموعة**، حدد بندا لمجموعة **B11**، ثم حدد **حجز البند**. لا يوجد منطق مخصص لتعيين المواقع ولوحات الترخيص اثناء الحجز التلقائي. يمكنك إدخال الكمية يدويا في حقل **الحجز**. لاحظ انه يتم في علامة التبويب السريعة **الأرقام الدفعيه التي تم تنفيذها لبند المصدر** عرض مجموعة **B11** بالحالة **منفذ.**

    ![تنفيذ رقم دفعه معين لبند أمر التوريد في صفحه حجز الدفعات](media/Batch-reservation-form-with-order-committed-reservation.png)

    > [!NOTE]
    > يمكن القيام بحجز الكمية في بند أمر التوريد عبر مجموعات متعددة. المثل ، يمكن القيام بحجز نفس الدفعة مقابل المواقع المتعددة ولوحات الترخيص (في حالة تمكين لوحات الترخيص للمواقع).
    >
    > يمكن أيضا أن يكون حجز مجموعة محدده للكمية في بند أمر التوريد جزئيا. على سبيل المثال ، يمكن حجز إجمالي الكمية 100 من الوحدات بحيث يتم التزام بمجموعة معينه إلى 20 وحده ، بينما يتم حجز 80 وحده في مستويات الموقع والمستودع لآيه مجموعة متاحه. في هذه الحالة ، سيقوم WMS بمعالجه عمليات الانتقاء باستخدام بندين منفصلين من أسطر العمل.

7. انتقل إلى **إدارة معلومات المنتج** \> **المنتجات** \> **المنتجات الصادرة**. حدد الصنف، ثم حدد **إدارة المخزون**\>**عرض**\>**الحركات**.

    ![الحجز المرتبط بالأمر كنوع حركه مخزون](media/Inventory-transactions-for-order-committed-reservation.png)

8. مراجعه حركات المخزون الخاصة بالصنف والمرتبطة بحجز بند أمر التوريد.

    - حركه يتم تعيين الحقل**المرجع** بها إلى **أمر المبيعات** ويتم تعيين حقل **الإصدار** على القيمة **الفعلية المحجوزة** تمثل حجز بند الأمر لابعاد المخزون فوق مستوى **الموقع**. ووفقا للتسلسل الهرمي لحجز مخزون الصنف ، فان هذه الابعاد هي الموقع والمستودع وحالة المخزون.
    - حركه يتم تعيين الحقل **المرجع** بها إلى **الحجز بواسطة الأمر** ويتم تعيين حقل **الإصدار** على القيمة **الفعلية المحجوزة** تمثل حجز بند الأمر لدفعة معينة وجميع أبعاد المخزون فوقها. ووفقا للتسلسل الهرمي لحجز مخزون الصنف، فان هذه الابعاد هي الموقع ورقم الدفعة. في هذا المثال، يكون **Bulk-001.**

9. في رأس أمر المبيعات، حدد **المستودع** \> **الإجراءات‏‎** \> **إصدار إلى المستودع**. يتم الآن إرسال بند الأمر، ويتم إنشاء تحميل وعمل.

### <a name="review-and-process-warehouse-work-that-has-order-committed-batch-numbers"></a>مراجعه عمل المستودع الذي يحتوي على أرقام الدفعات المخصصة للأمر ومعالجتها

1. في علامة التبويب السريعة **بنود أمر المبيعات**، حدد **المستودع**\>**تفاصيل العمل**.

    يحتوي العمل الذي يقوم بمعالجه عمليه الانتقاء لكميات الدفعة التي يتم تنفيذها علي بند أمر التوريد علي الخصائص التالية:

    - لإنشاء العمل ، يستخدم النظام قوالب العمل وليس توجيهات المواقع. سيتم تطبيق كافة الإعدادات القياسية التي تم تحديدها لقوالب العمل ، مثل العدد الأقصى لبنود الانتقاء أو وحده قياس معينه ، لتحديد الوقت الذي ينبغي فيه إنشاء عمل جديد. ومع ذلك ، لا يتم التعامل مع القواعد المقترنة بتوجيهات المواقع لتعريف مواقع الانتقاء ، نظرا لان الحجز المرتبط بالأمر يحدد بالفعل كافة ابعاد المخزون. وتتضمن ابعاد المخزون هذه الابعاد علي مستوي تخزين المستودع. التالي ، يرث العمل تلك الابعاد دون الحاجة إلى استشاره توجيهات المواقع.
    - لا يتم إظهار رقم المجموعة في بند الانتقاء (كما هو الحال بالنسبة لبند العمل الذي تم إنشاؤه للصنف الذي يشتمل على تسلسل الحجز "الدفعة أعلى \[الموقع\]".) بدلا من ذلك ، يتم عرض رقم المجموعة "من" وكافة ابعاد التخزين الأخرى في حركه مخزون العمل الخاصة ببند العمل المشار اليها من حركات المخزون المرتبطة.

        ![حركه مخزون المستودع للعمل الذي ينتج عن الحجز المرتبط بالطلبات](media/Work-inventory-transactions-for-order-committed-reservation.png)

    - بعد إنشاء العمل، تتم إزالة حركة المخزون الخاصة بالصنف التي تم تعيين حقل **المرجع**فيها إلى **الحجز المرتبط بالأمر**. حركة المخزون التي تم تعيين الحقل**المرجع** بها على **عمل** تحتفظ الآن بالحجز الفعلي علي كافة ابعاد المخزون الخاصة بالكمية.

        يمكن أن تتابع عمليات المستودع معالجه تنفيذ العمل بالطريقة المعتادة. ومع ذلك، ستقوم الإرشادات الموجودة علي الجهاز المحمول بإرشاد العامل لانتقاء رقم مجموعة معين. في بيئات المستودعات حيث تكون المواقع عبارة عن لوحه ترخيص – يتم التحكم بها ، بعد وصول أحد العاملين إلى موقع يقوم بتخزين نفس المجموعة علي ألواح ترخيص متعددة ، فانه يمكنه الانتقاء من اي لوحه ترخيص غير محجوزه بالفعل (على سبيل المثال ، بواسطة آخر الحجز أو الاعمال المرتبطة بالطلبات التي تنشا من حجز من هذا النوع.)

        وفي حالة تشغيله للانتقاء من الموقع المحدد في بند العمل ، يمكن لمشغلي المستودع استخدام أحد الإجراءات التالية لأعاده توجيه انتقاء المجموعة المحددة من موقع أكثر ملاءمة:

        - إجراء **تجاوز الموقع** القياسي علي جهاز محمول (شريطة تمكين الإعداد الخاص بالعامل الخاص بالمستودع **السماح بتجاوز موقع الالتقاط**)
        - إجراء **تغيير الموقع** في الصفحة **تفاصيل قائمة العمل**. 

2. علي الجهاز المحمول ، قم بإنهاء الانتقاء ووضع العمل.

    يتم الآن انتقاء الكمية **10** لرقم الدفعة **B11** لبند أمر المبيعات ووضعها في موقع **باب تحميل البضائع**. في هذه المرحلة، يكون جاهزا ليتم تحميله علي الشاحنة وإرساله إلى عنوان العميل.

## <a name="exception-handling-of-warehouse-work-thas-has-order-committed-batch-numbers"></a>معالجة استثنائية لعمل المستودع الذي يحتوي علي أرقام الدفعات المخصصة للأمر

يعمل المستودع الخاص بأرقام أمر الانتقاء-المخصصة إلى نفس معالجه استثناء المستودع القياسي والإجراءات الخاصة به كعمل عادي. بشكل عام ، يمكن إلغاء العمل المفتوح أو سطر العمل، حيث يمكن مقاطعته لان موقع المستخدم ممتلئ، ويمكن أن يتم انتقاؤه بشكل قصير، ويمكن تحديثه بسبب الحركة. بالمثل ، يمكن تقليل الكمية المنتقاة للعمل التي تم إكمالها بالفعل، أو يمكن عكس العمل.

يتم تطبيق قاعده المفتاح التالية علي كافة إجراءات معالجه الاستثناءات هذه: لا يمكن استبدال رقم المجموعة التي تم حجزها للعميل برقم مجموعة مختلف ، ولكن لا يمكن تغيير ابعاد التخزين الخاصة به (لوحه الموقع والترخيص) من خلال اي منهما التحديث اليدوي بواسطة المستخدم أو التحديث التلقائي بواسطة النظام. ويعتمد التحديث التلقائي علي نفس التعيين العشوائي لابعاد التخزين التي يتم تطبيقها عند حجز مجموعة معينه تلقائيا ولكن لم يتم تحديد أية ابعاد للتخزين.

### <a name="example-scenario"></a>سيناريو كمثال

مثال عن هذا السيناريو هو موقف حيث تم إكمال العمل سابقا يتم إلغاء انتقائها باستخدام وظيفة **تقليل الكمية المنتقاة**. ويستمر هذا المثال في المثال السابق في هذا الموضوع.

1. انتقال إلى **إدارة المستودعات**\>**أحمال**\>**جميع الأحمال**.
2. حدد الحمل الذي تم إنشاؤه فيما يتعلق بشحنه أمر التوريد الخاص بك.
3. من بنود علامة التبويب السريعة **سطور أمر التحميل**، حدد **تقليل الكمية المنتقاة**.
4. في الصفحة **تقليل الكمية المنتقاة** في الحقل **نقل إلى الموقع** ، حدد **FL-001**.
5. في الحقل **الانتقال إلى لوحة الترخيص**، حدد **LP33**.
6. في الشبكة، في الحقل **كميه المخزون التي سيتم إلغاء انتقائها**، أدخل **10.**
7. حدد **موافق**.

وفيما يلي نتائج إجراء إلغاء الانتقاء:

- تم تعيين حالة العمل الذي تم إغلاقه مسبقا إلى **ملغى**.
- يتم إنشاء العمل الجديد لنوع**حركه المخزون** للكمية التي تم إلغاء انتقاؤها والتي تبلغ **10** بالنسبة لرقم الدفعة **B11**. يمثل هذا العمل الانتقال من موقع**باب تحميل البضائع** إلى لوحه الترخيص **LP33** في الموقع **FL-001**. تم تعيين الحقل إلى الحالة **مغلق**.
- قام النظام باعاده حجز رقم المجموعة الذي تم طلبه في الأصل، ويقوم بتعيين معرفات لوحات الترخيص والموقع. (هذه العملية مكافئه لتشغيل وظيفة **البند الاحتياطي** لسطر الأمر الخاص برقم دفعه معين). ونتيجة لذلك، يتم عرض الدفعة**B11** كما تم تنفيذها في علامة التبويب السريعة **أرقام المجموعات التي تم التزام بها علي الخط المصدر**في صفحة  **حجز الدفعة** ويحتوي الحقل **الحجز** على الكمية **10** لرقم الدفعة **B11**. بالإضافة إلى ذلك يتم تعيين حقل**الموقع** على **FL-001** ويتم تعيين**لوحة الترخيص** على **LP11**. (يمكنك أضافه هذه الحقول إلى الشبكة إذا لم تكن مرئية.)

توفر الجداول التالية نظره عامه توضح كيفيه قيام النظام بمعالجه حجز المجموعات المرتبطة بالأمر لإجراءات مستودع معينه. لتفسير المحتوي في الجداول ، افترض انه يتم تشغيل كل إجراء للمستودع في سياق عمل المستودع الموجود الذي ينتج عن حجز المجموعة المرتبطة بالأمر ، أو أن تنفيذ كل إجراء مستودع يؤثر علي العمل من هذا النوع.

> [!NOTE]
> في هذه الجداول ، يشير العمود "الكمية المجمعة" إلى ما إذا كانت كميه المجموعة متوفرة بالإضافة إلى الكمية التي تم حجزها بالفعل بالنسبة لعمليات الحجز المرتبطة بالأمر أو المحجوزة بالفعل بواسطة عمل المستودع الذي تنشا من عمليات الحجز لذلك النوع.

#### <a name="override-the-pick-location-on-the-open-work"></a>تجاوز موقع الانتقاء في العمل المفتوح

<table>
<thead>
<tr>
<th>معلمة الإعداد الرئيسية</th>
<th>كمية الدفعة متاحة</th>
<th>خطوات المستخدم الاساسيه</th>
<th>عمل المستودع</th>
<th>حجز المجموعة المرتبطة بالأمر</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>تم تمكين خيار <strong>السماح بتجاوز موقع الانتقاء</strong> علي العامل.</td>
<td>‏‏نعم</td>
<td>
<ol>
<li>حدد عنصر القائمة <strong>تجاوز الموقع</strong> في تطبيق المستودع عند بدء عمل الانتقاء.</li>
<li>حدد <strong>اقتراح</strong>.</li>
<li>قم بتاكيد الموقع الجديد المقترح بناء علي توفر كميه الدفعة.</li>
</ol>
</td>
<td>تحدث الإجراءات التالية في العمل الحالي:
<ul>
<li>ويتم تحديث الموقع الموجود في بند الانتقاء في الموقع الجديد. (إذا كان الموقع لوحه ترخيص – يتم التحكم به ، يتم تعيين لوحه ترخيص عشوائية لحركه مخزون العمل ، ويمكن للعامل الانتقاء من اي لوحه ترخيص بالكمية المتاحة.)</li>
<li>في حالة العثور علي الكمية في أكثر من لوحه ترخيص واحده في الموقع الجديد ، يتم تقسيم بند الانتقاء الأصلي إلى بنود متعددة لمطابقه كل لوحه ترخيص.</li>
</ul>
</td>
<td>غير قابل للتطبيق</td>
</tr>
<tr>
<td>لا</td>
<td>
<ol>
<li>حدد عنصر القائمة <strong>تجاوز الموقع</strong> في تطبيق المستودع عند بدء عمل الانتقاء.</li>
<li>ادخل موقعا يدويا.</li>
</ol>
</td>
<td>إجراء <strong>تجاوز الموقع</strong> غير ممكن. وهو يفشل ويتم عرض خطا.</td>
<td>غير قابل للتطبيق</td>
</tr>
</tbody>
</table>

#### <a name="full-button--split-a-work-line-because-of-overflow-on-the-user-location"></a>الزر الكامل – تقسيم بند العمل نظرا لتجاوز الحد الأقصى لموقع المستخدم

<table>
<thead>
<tr>
<th>معلمة الإعداد الرئيسية</th>
<th>كمية الدفعة متاحة</th>
<th>خطوات المستخدم الاساسيه</th>
<th>عمل المستودع</th>
<th>حجز المجموعة المرتبطة بالأمر</th>
</tr>
</thead>
<tbody>
<tr>
<td>يتم <strong>تمكين خيار السماح</strong> بتقسيم العمل في عنصر القائمة جهاز المحمول.</td>
<td>غير قابل للتطبيق</td>
<td>
<ol>
<li>حدد عنصر القائمة <strong>كامل</strong> في تطبيق المستودع عند معالجة عمل الانتقاء.</li>
<li>في الحقل <strong>كميه الانتقاء</strong>، ادخل كميه جزئيه من الانتقاء المطلوب للاشاره إلى القدرة الكاملة.</li>
</ol>
</td>
<td>
<ul>
<li>وفي العمل الحالي ، يتم تحديث الكمية إلى الكمية المتبقية التي يجب انتقاؤها.</li>
<li>يتم إنشاء العمل الجديد للكمية المنتقية وإغلاقه.</li>
</ul></td>
<td>غير قابل للتطبيق</td>
</tr>
</tbody>
</table>

#### <a name="reduce-the-picked-quantity-of-completed-work-from-a-load"></a>تقليل الكمية المنتقاة للعمل المكتمل (من التحميل)

<table>
<thead>
<tr>
<th>معلمة الإعداد الرئيسية</th>
<th>كمية الدفعة متاحة</th>
<th>خطوات المستخدم الاساسيه</th>
<th>عمل المستودع</th>
<th>حجز المجموعة المرتبطة بالأمر</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>غير قابل للتطبيق</td>
<td>‏‏نعم</td>
<td>
<ol>
<li>افتح صفحه <strong>تقليل الكمية المنتقاة</strong> من بند التحميل.</li>
<li>إدخال الكمية الكاملة المراد انتقاؤها.</li>
<li>حدد لوحة الترخيص/الموقع "تحريك إلى".</li>
</ol>
</td>
<td>
<ul> 
<li>تم إلغاء العمل المرتبط ببند التحميل.</li>
<li>يتم إنشاء العمل الجديد لحركة المخزون وإغلاقه.</li>
</ul>
</td>
<td>تمت إعاده حجز الكمية لنفس المجموعة. يقوم النظام بتعيين الموقع ولوحه الترخيص عشوائيا (إذا كان الموقع لوحه ترخيص – يتم التحكم به) حيث تكون الكمية متاحه.</td>
</tr>
<tr>
<td>لا</td>
<td>راجع الصف السابق.</td>
<td>راجع الصف السابق.</td>
<td>يتم أعاده حجز الكمية لنفس المجموعة، ولنفس الموقع ولوحه الترخيص (إذا كان الموقع عبارة عن لوحه ترخيص – يتم التحكم به) والتي تم إدخالها اثناء إلغاء الانتقاء.</td>
</tr>
</tbody>
</table>

#### <a name="move-an-item-within-a-warehouse"></a>نقل صنف داخل مستودع

> [!NOTE]
> لا ينطبق إجراء المستودع الا علي حركه نوع **عمليه إنشاء العمل**، وليس للحركة بواسطة القالب.

<table>
<thead>
<tr>
<th>معلمة الإعداد الرئيسية</th>
<th>كمية الدفعة متاحة</th>
<th>خطوات المستخدم الاساسيه</th>
<th>عمل المستودع</th>
<th>حجز المجموعة المرتبطة بالأمر</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>يتم تمكين خيار <strong>السماح بنقل المخزون مع العمل المقترن</strong> علي العامل.</td>
<td>‏‏نعم</td>
<td>
<ol>
<li>بدء حركه في تطبيق المستودع.</li>
<li>أدخل موقعي البداية والنهاية.</li>
</ol></td>
<td>
<ul>
<li>وفي كل العمل الموجود الذي يتاثر بالنقل ، يتم تحديث موقع الانتقاء إلى الموقع "إلى" الجديد.</li>
<li>يتم إنشاء العمل الجديد لحركة المخزون وإغلاقه.</li>
</ul>
</td>
<td>تتم أعاده حجز كافة عمليات الحجز الموجودة التي تاثرت بحركة الكمية من الموقع المحدد لنفس المجموعة. يقوم النظام بتعيين الموقع ولوحه الترخيص عشوائيا (إذا كان الموقع لوحه ترخيص – يتم التحكم به) حيث تكون الكمية متاحه.</td>
</tr>
<tr>
<td>لا</td>
<td>راجع الصف السابق.</td>
<td>راجع الصف السابق.</td>
<td>يتم أعاده حجز كافة عمليات الحجز الموجودة التي تاثرت بحركة الكمية من الموقع المحدد لنفس المجموعة ، وللموقع الجديد "إلى" ولوحه الترخيص (إذا كان الموقع لوحه الترخيص-التي يتم التحكم بها).</td>
</tr>
</tbody>
</table>

#### <a name="reverse-the-picked-quantity-of-completed-work-from-a-load-or-a-wave"></a>حجز الكمية المنتقاة للعمل المكتمل (من التحميل أو الموجة)

<table>
<thead>
<tr>
<th>معلمة الإعداد الرئيسية</th>
<th>كمية الدفعة متاحة</th>
<th>خطوات المستخدم الاساسيه</th>
<th>عمل المستودع</th>
<th>حجز المجموعة المرتبطة بالأمر</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='6'>غير قابل للتطبيق</td>
<td>‏‏نعم</td>
<td>
<ol>
<li>افتح صفحه <strong>العمل العكسي</strong>.</li>
<li>في الصفحة طلب ، حدد الخيار <strong>ترك العناصر في الموقع الحالي</strong>.</li>
</ol>
</td>
<td>تم إلغاء العمل المرتبط بالتحميل.</td>
<td>تمت إعاده حجز الكمية لنفس المجموعة. يقوم النظام بتعيين الموقع ولوحه الترخيص عشوائيا (إذا كان الموقع لوحه ترخيص – يتم التحكم به) حيث تكون الكمية متاحه.</td>
</tr>
<tr>
<td>لا</td>
<td>راجع الصف السابق.</td>
<td>راجع الصف السابق.</td>
<td>يتم أعاده حجز الكمية لنفس المجموعة ، وللوح الموقع والترخيص الذي تم فيه ترك الكمية عند إلغاء.</td>
</tr>
<tr>
<td>‏‏نعم</td>
<td>
<ol>
<li>افتح صفحه <strong>العمل العكسي</strong>.</li>
<li>في الصفحة طلب ، حدد الخيار <strong>تعيين العناصر للموقع الحالي</strong>.</li>
</ol>
</td>
<td>
<ul>
<li>تم إلغاء العمل الحالي.</li>
<li>يتم إنشاء العمل الجديد لحركة المخزون وإغلاقه.</li>
</ul>
</td>
<td>تمت إعاده حجز الكمية لنفس المجموعة. يقوم النظام بتعيين الموقع ولوحه الترخيص عشوائيا (إذا كان الموقع لوحه ترخيص – يتم التحكم به) حيث تكون الكمية متاحه.</td>
</tr>
<tr>
<td>لا</td>
<td>راجع الصف السابق.</td>
<td>راجع الصف السابق.</td>
<td>يتم أعاده حجز الكمية لنفس المجموعة ، وللوح الموقع والترخيص الذي تم فيه تعيين الكمية عند إلغاء.</td>
</tr>
<tr>
<td>نعم/لا</td>
<td>
<ol>
<li>افتح صفحه <strong>العمل العكسي</strong>.</li>
<li>في الصفحة طلب ، حدد الخيار <strong>نقل العناصر إلى هذا الموقع</strong>.</li>
</ol>
</td>
<td>العكس غير معتمد.</td>
<td>غير قابل للتطبيق</td>
</tr>
<tr>
<td>نعم/لا</td>
<td>
<ol>
<li>افتح صفحه <strong>العمل العكسي</strong>.</li>
<li>في الصفحة طلب ، حدد الخيار <strong>نقل العناصر على أساس موجهات الموقع</strong>.</li>
</ol>
</td>
<td>العكس غير معتمد. </td>
<td>غير قابل للتطبيق</td>
</tr>
</tbody>
</table>

#### <a name="short-pick-a-quantity--register-the-quantity-as-physically-not-found-at-the-locationlicense-plate-while-you-perform-picking-work"></a>قصور انتقاء الكمية – تسجيل الكمية بأنها لم يتم العثور عليها فعليا في لوحه الترخيص/الموقع اثناء إجراء عمل الانتقاء

<table>
<thead>
<tr>
<th>معلمة الإعداد الرئيسية</th>
<th>كمية الدفعة متاحة</th>
<th>خطوات المستخدم الاساسيه</th>
<th>عمل المستودع</th>
<th>حجز المجموعة المرتبطة بالأمر</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>تم إعداد استثناء عمل لنوع <strong>الانتقاء القصير</strong> حيث <strong>إعادة توزيع الصنف</strong> = <strong>لا شيء</strong> و <strong>وتسوية المخزون</strong> = <strong>نعم</strong> و <strong>إزالة عمليات الحجز</strong> = <strong>لا</strong>.</td>
<td>‏‏نعم</td>
<td>
<ol>
<li>حدد عنصر القائمة <strong>انتقاء قصير</strong> في تطبيق المستودع عند معالجة عمل الانتقاء.</li>
<li>في حقل <strong>كمية الانتقاء</strong>، أدخل <strong>0</strong> (صفرًا).</li>
<li>في حقل <strong>السبب</strong>، أدخل <strong>لا توجد إعادة توزيع</strong>.</li>
</ol>
</td>
<td>
<ul>
<li>يتم إغلاق العمل الحالي، وتكون الكمية المنتقاة هي 0 (صفر).</li>
<li>يتم إنشاء حركه مخزون لنوع <strong>الجرد</strong>  ونوع الإصدار <strong>مباع</strong> ليمثل التعديل.</li>
</ul>
</td>
<td>تمت إعاده حجز الكمية لنفس المجموعة. يقوم النظام بتعيين الموقع ولوحه الترخيص عشوائيا (إذا كان الموقع لوحه ترخيص – يتم التحكم به) حيث تكون الكمية متاحه.</td>
</tr>
<tr>
<td>لا</td>
<td>راجع الصف السابق.</td>
<td>
<ul>
<li>فشل إجراء الانتقاء القصير، ويتم عرض خطأ.</li>
<li>يظل العمل الحالي مفتوحا.</li>
</ul>
</td>
<td>غير قابل للتطبيق</td>
</tr>
<tr>
<td rowspan='2'>تم إعداد استثناء عمل لنوع <strong>الانتقاء القصير</strong> حيث <strong>إعادة توزيع الصنف</strong> = <strong>‎لا شيء</strong>، و <strong>تسوية المخزون</strong> = <strong>نعم</strong>، و <strong>‎إزالة عمليات الحجوزات</strong> = <strong>نعم</strong>.</td>
<td>‏‏نعم</td>
<td>
<ol>
<li>حدد عنصر القائمة <strong>انتقاء قصير</strong> في تطبيق المستودع عند معالجة عمل الانتقاء.</li>
<li>في حقل <strong>كمية الانتقاء</strong>، أدخل <strong>0</strong> (صفرًا).</li>
<li>في حقل <strong>السبب</strong>، أدخل <strong>لا توجد إعادة توزيع</strong>.</li>
</ol>
</td>
<td>
<ul>
<li>يتم إغلاق العمل الحالي، وتكون الكمية المنتقاة هي 0 (صفر).</li>
<li>يتم إنشاء حركه مخزون لنوع <strong>الجرد</strong>  ونوع الإصدار <strong>مباع</strong> ليمثل التعديل.</li>
</ul>
</td>
<td>تتم أعاده حجز كافة عمليات الحجز الموجودة التي تاثرت بتسوية الكمية في موقع الانتقاء القصير المعاد حجزه لنفس المجموعة. يقوم النظام بتعيين الموقع ولوحه الترخيص عشوائيا (إذا كان الموقع لوحه ترخيص – يتم التحكم به) حيث تكون الكمية متاحه.</td>
</tr>
<tr>
<td>لا</td>
<td>راجع الصف السابق.</td>
<td>راجع الصف السابق.</td>
<td>تمت إزالة جميع الحجوزات الحالية المتأثرة بتسوية الكمية في موقع الانتقاء القصير.</td>
</tr>
<tr>
<td>تم إعداد استثناء عمل لنوع <strong>الانتقاء القصير</strong> حيث <strong>إعادة توزيع الصنف</strong> = <strong>يدوي</strong>، و <strong>تسوية المخزون</strong> = <strong>نعم</strong>, و <strong>‎إزالة عمليات الحجوزات</strong> = <strong>لا/نعم</strong>. بالإضافة إلى ذلك ، يتم تمكين الخيار <strong>السماح بإعادة توزيع العناصر اليدوية</strong> علي العامل.</td>
<td>‏‏نعم</td>
<td>
<ol>
<li>حدد عنصر القائمة <strong>انتقاء قصير</strong> في تطبيق المستودع عند معالجة عمل الانتقاء.</li>
<li>في حقل <strong>كمية الانتقاء القصير</strong>، أدخل <strong>0</strong> (صفرًا).</li>
<li>في الحقل <strong>السبب</strong>، حدد<strong>الانتقاء القصير مع إعادة التوزيع اليدوية</strong>.</li>
<li>حدد لوحه الترخيص/الموقع في القائمة.</li>
</ol>
</td>
<td>
<ul>
<li>تحدث الإجراءات التالية في العمل الحالي:
<ul>
<li>يتم إغلاق بند الانتقاء، وتكون الكمية المنتقاة هي 0 (صفر).</li>
<li>تم إلغاء بند الإدخال.</li>
<li>يتم إنشاء بند انتقاء جديد. ويستخدم الموقع/لوحه الترخيص التي قام المستخدم بتحديدها.</li>
<li>يتم إنشاء بند إدخال جديد.</li>
</ul>
</li>
<li>يتم إنشاء حركه مخزون لنوع <strong>الجرد</strong>  ونوع الإصدار <strong>مباع</strong> ليمثل التعديل.</li>
</ul>
</td>
<td>غير قابل للتطبيق</td>
</tr>
<tr>
<td>تم إعداد استثناء عمل لنوع <strong>الانتقاء القصير</strong> حيث <strong>إعادة توزيع الصنف</strong> = <strong>يدوي</strong> و <strong>تسوية المخزون</strong> = <strong>نعم</strong> و <strong>إزالة عمليات الحجوزات</strong> = <strong>لا</strong>. بالإضافة إلى ذلك ، يتم تمكين الخيار <strong>السماح بإعادة توزيع العناصر اليدوية</strong> علي العامل.</td>
<td>لا</td>
<td>
<ol>
<li>حدد عنصر القائمة <strong>انتقاء قصير</strong> في تطبيق المستودع عند معالجة عمل الانتقاء.</li>
<li>في حقل <strong>كمية الانتقاء القصير</strong>، أدخل <strong>0</strong> (صفرًا).</li>
<li>في الحقل <strong>السبب</strong>، حدد<strong>الانتقاء القصير مع إعادة التوزيع اليدوية</strong>.</li>
</ol>
</td>
<td>فشل إجراء الانتقاء القصير، ويتم عرض خطأ.</td>
<td>غير قابل للتطبيق</td>
</tr>
<tr>
<td>تم إعداد استثناء عمل لنوع <strong>الانتقاء القصير</strong> حيث <strong>إعادة توزيع الصنف</strong> = <strong>يدوي</strong> و <strong>تسوية المخزون</strong> = <strong>نعم</strong> و <strong>إزالة عمليات الحجوزات</strong> = <strong>نعم</strong>. بالإضافة إلى ذلك ، يتم تمكين الخيار <strong>السماح بإعادة توزيع العناصر اليدوية</strong> علي العامل.</td>
<td>لا</td>
<td>
<ol>
<li>حدد عنصر القائمة <strong>انتقاء قصير</strong> في تطبيق المستودع عند معالجة عمل الانتقاء.</li>
<li>في حقل <strong>كمية الانتقاء القصير</strong>، أدخل <strong>0</strong> (صفرًا).</li>
<li>في الحقل <strong>السبب</strong>، حدد<strong>الانتقاء القصير مع إعادة التوزيع اليدوية</strong>.</li>
<li>حدد لوحه الترخيص/الموقع في القائمة.</li>
</ol>
</td>
<td>
<ul>
<li>تحدث الإجراءات التالية في العمل الحالي:
<ul>
<li>يتم إغلاق بند الانتقاء، وتكون الكمية المنتقاة هي 0 (صفر).</li>
<li>تم إلغاء بند الإدخال.</li>
</ul>
</li>
<li>يتم إنشاء حركه مخزون لنوع <strong>الجرد</strong>  ونوع الإصدار <strong>مباع</strong> ليمثل التعديل.</li>
</ul>
</td>
<td>تمت إزالة جميع الحجوزات الحالية المتأثرة بتسوية الكمية في موقع/لوحة ترخيص الانتقاء القصير.</td>
</tr>
<tr>
<td>تم إعداد استثناء عمل لنوع <strong>الانتقاء القصير</strong> حيث <strong>إعادة توزيع الصنف</strong> = <strong>تلقائي</strong> و <strong>تسوية المخزون</strong> = <strong>نعم/لا</strong> و <strong>‎إزالة عمليات الحجوزات</strong> = <strong>نعم/لا</strong>.</td>
<td>غير قابل للتطبيق</td>
<td>
<ol>
<li>حدد عنصر القائمة <strong>انتقاء قصير</strong> في تطبيق المستودع عند معالجة عمل الانتقاء.</li>
<li>في حقل <strong>كمية الانتقاء القصير</strong>، أدخل <strong>0</strong> (صفرًا).</li>
<li>في الحقل <strong>السبب</strong>، حدد<strong>الانتقاء القصير مع إعادة التوزيع التلقائية</strong>.</li>
</ol>
</td>
<td>الانتقاء القصير الذي يتضمن إعادة التوزيع تلقائيا غير مدعوم.</td>
<td>الانتقاء القصير الذي يتضمن إعادة التوزيع تلقائيا غير مدعوم.</td>
</tr>
</tbody>
</table>

#### <a name="change-the-inventory-status"></a>تغيير حالة المخزون

> [!NOTE]
> يمكن تنفيذ إجراء المستودع هذا من نقاط إدخال متعددة. يستخدم المثال الموضح هنا إجراء **تغيير حالة المخزون** في الصفحة **الفعلية حسب الموقع**

<table>
<thead>
<tr>
<th>معلمة الإعداد الرئيسية</th>
<th>كمية الدفعة متاحة</th>
<th>خطوات المستخدم الاساسيه</th>
<th>عمل المستودع</th>
<th>حجز المجموعة المرتبطة بالأمر</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>في علامة التبويب<strong> المستودع</strong>، في سجل <strong> المستودع</strong> ، يتم تعيين الحقل<strong> حجوزات الازاله والعلامات</strong> إلى <strong>عمليات الحجز</strong> أو <strong>العلامات والحجوزات.</strong></td>
<td>‏‏نعم</td>
<td>
<ol>
<li>حدد موقعًا معينًا.</li>
<li>حدد البند الذي يحتوي علي أحد الأصناف والمواقع والتراخيص المحددة (إذا كان الموقع لوحه ترخيص – يتم التحكم به).</li>
<li>حدد <strong>تغيير حالة المخزون</strong>.</li>
<li>قم بتعيين حقل <strong>حالة المخزون</strong> إلى <strong>"تجميد</strong>".</li>
</ol>
</td>
<td>لا يسمح بإجراء تغييرات علي حالة المخزون للكميات المحجوزة للعمل.</td>
<td>
<ul>
<li>تمت إعاده حجز الكمية لنفس المجموعة. يقوم النظام بتعيين الموقع ولوحه الترخيص عشوائيا (إذا كان الموقع لوحه ترخيص – يتم التحكم به) حيث تكون الكمية متاحه.</li>
<li>يتم إنشاء حركتي مخزون بنوع <strong>تغيير حالة المخزون</strong> لتمثيل التغيير في بعد حالة المخزون.</li>
<li>يتم إنشاء حركه مخزون لنوع <strong>تامين المخزون</strong> ونوع الإصدار <strong>الفعلي المحجوز</strong> لتمثيل حجز الكمية المحظورة.</li>
</ul>
</td>
</tr>
<tr>
<td>لا</td>
<td>راجع الصف السابق.</td>
<td>لا يسمح بإجراء تغييرات علي حالة المخزون للكميات المحجوزة للعمل.</td>
<td>
<ul>
<li>تمت إزاله الحجز.</li>
<li>يتم إنشاء حركتي مخزون بنوع <strong>تغيير حالة المخزون</strong> لتمثيل التغيير في بعد حالة المخزون.</li>
<li>يتم إنشاء حركه مخزون لنوع <strong>تامين المخزون</strong> ونوع الإصدار <strong>الفعلي المحجوز</strong> لتمثيل حجز الكمية المحظورة.</li>
</ul>
</td>
</tr>
<tr>
<td rowspan='2'>في علامة التبويب <strong>المستودع</strong>، في سجل <strong>المستودع</strong>، يتم تعيين الحقل <strong>حجوزات الازاله والعلامات</strong> إلى <strong>لا شيء</strong>.</td>
<td>‏‏نعم</td>
<td>
<ol>
<li>حدد موقعًا معينًا.</li>
<li>حدد البند الذي يحتوي علي أحد الأصناف والمواقع والتراخيص المحددة (إذا كان الموقع لوحه ترخيص – يتم التحكم به).</li>
<li>حدد <strong>تغيير حالة المخزون</strong>.</li>
<li>قم بتعيين حقل <strong>حالة المخزون</strong> إلى <strong>"تجميد</strong>".</li>
</ol>
</td>
<td>لا يسمح بإجراء تغييرات علي حالة المخزون للكميات المحجوزة للعمل.</td>
<td>تمت إعاده حجز الكمية لنفس المجموعة. يقوم النظام بتعيين الموقع ولوحه الترخيص عشوائيا (إذا كان الموقع لوحه ترخيص – يتم التحكم به) حيث تكون الكمية متاحه.</td>
</tr>
<tr>
<td>لا</td>
<td>راجع الصف السابق.</td>
<td>لا يسمح بإجراء تغييرات علي حالة المخزون للكميات المحجوزة للعمل.</td>
<td>لا يسمح بتغييرات حالة المخزون.</td>
</tr>
</tbody>
</table>

## <a name="limitations"></a>قيود

- لا تدعم وظيفة حجز بعد علي مستوي المستودع المرن الميزات التالية:

    - أداره وزن التقاط
    - مخزون سالب مادي
    - الحجز مقابل التوريد المطلوب
    - أوامر التحويل وانتقاء المادة الخام

- تشتمل قاعده دمج الحاوية للتعبئة حسب الوحدة الموجهة عليها علي قيود. بالنسبة لعمليات الحجز المرتبطة بالطلبات ، نوصي بعدم استخدام قوالب بنيه الحاوية حيث تم تمكين الحزم حسب حقل **الوحدة الموجهة**. في التصميم الحالي ، لا يتم استخدام توجيهات المواقع عند إنشاء عمل المستودع. وبالتالي، يتم تطبيق أدنى وحدة في مجموعة تسلسل الوحدة (وحدة المخزون) اثناء خطوة الموجة التعبئة في الحاويات.