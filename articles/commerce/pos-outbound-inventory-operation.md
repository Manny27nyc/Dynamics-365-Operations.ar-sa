---
title: عملية المخزون الخارجية في نقطه البيع
description: يصف هذا الموضوع إمكانيات عمليه المخزون الخارجية لنقطه البيع (POS).
author: hhaines
manager: annbe
ms.date: 05/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 22f057c20898bb4b4c34e38d62313d2634a33511
ms.sourcegitcommit: 3b6fc5845ea2a0de3db19305c03d61fc74f4e0d4
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/18/2020
ms.locfileid: "3384119"
---
# <a name="outbound-inventory-operation-in-pos"></a>عملية المخزون الخارجية في نقطه البيع

[!include [banner](includes/banner.md)]


في Microsoft Dynamics 365 Commerce الإصدار 10.0.10 والإصدارات الأحدث، تقوم العمليات الداخلية والخارجية في نقطه البيع (POS) باستبدال عملية الانتقاء والاستلام.

> [!NOTE]
> في الإصدار 10.0.10 والإصدارات الأحدث، ستتم إضافة أية ميزات جديدة في تطبيق نقطه البيع المرتبطة باستلام مخزن المتجر مقابل أوامر الشراء وأوامر التحويل إلى عمليه العمليات الخارجية. إذا كنت تستخدم حاليًا عمليه الانتقاء والاستلام في في نقطة البيع، فاننا نوصي بتطوير استراتيجية للانتقال من هذه العملية إلى العمليات الخارجية والداخلية الجديدة. على الرغم من ان عمليه الانتقاء والاستلام لن تتم ازالتها من المنتج، إلا أنه لن تكون هناك إيه استثمارات إضافية فيه، من منظور الوظيفة أو الأداء، بعد إصدار 10.0.9.

## <a name="prerequisite-configure-an-asynchronous-document-framework"></a>المتطلب الأساسي: تكوين إطار عمل غير متزامن للمستند

تتضمن العملية الخارجية تحسينات في الأداء لضمان أن المستخدمين الذين لديهم كميات كبيرة من ترحيلات إيصالات الاستلام عبر العديد من المتاجر أو الشركات، ومستندات المخزون الكبيرة، يمكنهم معالجه هذه المستندات في مركز Commerce دون مواجهة مشكلات تتعلق بانتهاء المهلة أو أعطال. تتطلب هذه التحسينات استخدام إطار عمل مستند غير متزامن.

عند استخدام إطار عمل مستند غير متزامن، يمكنك إجراء تغييرات على المستندات الخارجية من نقطه البيع إلى مركز Commerce ثم الانتقال إلى المهام الأخرى بينما تحدث المعالجة لمركز Commerce في الخلفية. يمكنك فحص حاله المستند من خلال صفحة قائمة المستندات **العملية الخارجية** في نقطة البيع للتأكد من نجاح عمليه الترحيل. في تطبيق نقطه البيع، يمكنك أيضا استخدام قائمة  المستندات النشطة للعملية الخارجية للاطلاع على أية مستندات تعذر ترحيلها إلى مركز Commerce. في حالة فشل مستند، يمكن لمستخدمي نقاط البيع إجراء تصحيحات عليه ثم المحاولة مرة أخرى لمعالجته في مركز Commerce.

> [!IMPORTANT]
> ويجب تكوين إطار عمل المستند غير المتزامن قبل محاولة شركة ما استخدام العملية الخارجية في نقطه البيع.

لتكوين إطار عمل مستند غير متزامن، أكمل الإجراءات التالية.

### <a name="create-and-configure-a-number-sequence"></a>إنشاء تسلسل رقمي وتكوينه

1. انتقل إلى **إدارة المؤسسة العامة \> التسلسلات الرقمية \> التسلسلات الرقمية**.
2. في صفحة **التسلسلات الرقمية**، قم بإنشاء تسلسل رقمي.
3. في حقل **كود التسلسل الرقمي** وحقل **الاسم**، أدخل القيم المعرفة من قبل المستخدم.
4. على علامة التبويب السريعة **المراجع** ، حدد **إضافة**.
5. في حقل **المنطقة** ، حدد **معلمات Commerce**.
6. في حقل **المرجع**، حدد **معرف عملية مستند البيع بالتجزئة**.
7. في علامة التبويب السريعة **عام**، في قسم **الإعداد**، قم بتعيين خيار **مستمر** على **لا** للتاكد من عدم وجود أية مشكلات في الأداء.

### <a name="create-and-schedule-two-batch-jobs-for-the-document-processing-and-monitoring-tasks"></a>إنشاء وظيفتين دفعتين وجدولتهما لمهام معالجة ومراقبة المستندات

سيتم استخدام الوظائف الدفعية لمعالجة المستندات التي فشلت أو انتهت مهلتها. كما سيتم استخدامها عندما يتجاوز عدد مستندات المخزون النشطة التي تتم معالجتها من نقطه البيع قيمه تم تكوينها بواسطة النظام.

1. انتقل إلى **إدارة النظام \> الاستعلامات \> الوظائف الدفعية**.
2. في صفحة **وظيفة دفعية**، قم بإنشاء وظيفتين دفعيتين:

    - قم بتكوين وظيفة واحدة لتشغيل درجة **RetailDocumentOperationMonitorBatch**.
    - قم بتكوين الوظيفة الأخرى لتشغيل درجة **RetailDocumentOperationProcessingBatch**.

3. قم بجدولة الوظائف الدفعية الجديدة ليتم تشغيلها على أساس متكرر. على سبيل المثال، قم بتعيين الجدول بحيث يتم تشغيل الوظائف كل خمس دقائق.

## <a name="prerequisite-add-outbound-operation-to-the-pos-screen-layout"></a>المتطلب الأساسي: إضافة عملية خارجية إلى تخطيط شاشة نقطة البيع

قبل أن تتمكن مؤسستك من استخدام وظيفة العملية الخارجية، قبل أن تكوّن عملية نقطة البيع **العملية الخارجية** على تخطيط واحد أو أكثر من [‏‫تخطيطات شاشة POS‬](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-screen-layouts). قبل نشر العملية الجديدة في بيئة إنتاج، تأكد من اختبارها بدقه ودّرب المستخدمين لديك على استخدامها.

## <a name="overview"></a>نظرة عامة

تتيح العملية الخارجية لمستخدمي نقطة البيع القيام بالمهام التالية:

- ترحيل الشحنات لمستندات أمر التحويل في الحالات التي يكون فيها متجر المستخدم هو المستودع الخارجي المعين.
- عرض معلومات حول الشحنات التاريخية لأمر التحويل التي تم ترحيلها بواسطة المتجر.
- إنشاء طلبات أوامر التحويل الخارجي الجديدة.

عند بدء تشغيل العملية الخارجية من تطبيق نقطة البيع، تظهر طريقة عرض صفحة القائمة. تعرض طريقة العرض هذه مستندات أوامر التحويل المفتوحة التي لها بنود مخزون يجب شحنها أو تنفيذها للمتجر الحالي للمستخدم. للعثور على مستند محدد، يمكن للمستخدمين التمرير في القائمة أو استخدام ميزة البحث.

تحتوي قائمة مستندات المخزون الخارجي على ثلاث علامات تبويب.

- **نشط** -تعرض علامة التبويب هذه أوامر التحويل التي حالتها إما **مطلوب‬** أو **‬‏‫مشحون جزئيًا**. تشتمل الأوامر على البنود أو الكميات الموجودة بالبنود التي يجب شحنها بواسطة المتجر الحالي للمستخدم. تعرض علامة التبويب هذه أيضا الأوامر التي حالتها **قيد المعالجة في المركز الرئيسي‎** (أي أنها في انتظار تأكيد نجاح الترحيل من مركز Commerce) أو **فشلت المعالجة** (بسبب عدم نجاح الترحيل إلى مركز ‏‫Commerce، ويجب ان يقوم المستخدم بتصحيح البيانات ومحاولة إرسال الأوامر مرة أخرى).
- **مسودة** – تعرض علامة التبويب هذه طلبات أوامر التحويل الخارجية الجديدة التي قام مخزن المستخدم بإنشاءها. ومع ذلك، تم حفظ المستندات محليا فقط. لم يتم إرسالها حتى الآن إلى مركز Commerce للمعالجة.
- **مكتمل** -تعرض علامة التبويب هذه قائمة بمستندات أمر التحويل التي قام المتجر بشحنها بالكامل خلال السبعة أيام الماضية. علامة التبويب هذه لأغراض معلوماتية فقط. كافة المعلومات حول المستندات هي بيانات للقراءة فقط للمتجر.

عندما تقوم بعرض المستندات في أي من علامات التبويب، يمكن أن يساعدك الحقل **الحالة** في فهم المرحلة التي يوجد بها المستند.

- **مسودة** – تم حفظ مستند أمر التحويل محليا فقط إلى قاعده بيانات قناه المتجر. لم يتم إرسال إيه معلومات حول طلب أمر التحويل إلى مركز Commerce.
- **مطلوب** – تم إنشاء أمر الشراء أو أمر التحويل في مركز Commerce ويتم فتحه بالكامل. لم يقم المتجر الحالي للمستخدم بمعالجه أية شحنات مقابل المستند حتى الآن.
- **‏‫تم الشحن جزئيًا‬** – يحتوي مستند أمر التحويل على بند واحد أو أكثر أو كميات جزئية للبند تم ترحيلها كشحنه بواسطة المستودع الخارجي. وتتوفر هذه البنود التي تم شحنها للاستلام من خلال العملية الداخلية.
- **‏‫تم الشحن بالكامل‬** – تم ترحيل جميع بنود أمر التحويل وكمياته الكاملة كشحنة بواسطة المستودع الخارجي.
- **قيد التقدم** – تستخدم هذه الحالة لإعلام مستخدمي الجهاز بأن المستند يعمل بشكل نشط من قبل مستخدم آخر.
- **‏‫متوقف مؤقتًا‬** – تظهر هذه الحالة بعد تحديد **توقف الاستلام مؤقتًا** لإيقاف عملية الاستلام مؤقتا.
- **قيد المعالجة في المركز الرئيسي** – تم إرسال المستند إلى مركز Commerce من تطبيق نقطه البيع، ولكن لم يتم ترحيله بعد بنجاح إلى مركز Commerce. يقوم المستند باجراء عملية ترحيل المستندات غير المتزامنة. بعد ترحيل المستند بنجاح إلى مركز Commerce، يجب تحديدث حالته إلى **‏‫تم الاستلام بالكامل‬** أو **مستلم جزئيًا‬**.
- **‏‫فشلت المعالجة** – تم ترحيل المستند إلى مركز Commerce ورفض. يعرض جزء **التفاصيل** سبب فشل الترحيل. يجب تحرير المستند لإصلاح مشكلات البيانات، ومن ثم يجب إعادة إرساله إلى مركز Commerce للمعالجة.

عند تحديد بند مستند في القائمة، يظهر جزء **التفاصيل**. يعرض هذا الجزء معلومات إضافية حول المستند، مثل معلومات الشحنة والتاريخ. يظهر شريط التقدم عدد العناصر التي يجب معالجتها. إذا لم تتم معالجة المستند بنجاح في إدارة Commerce، فإن جزء **التفاصيل** أيضا يعرض رسائل الخطأ المتعلقة بالفشل.

في طريقة عرض صفحة قائمة المستندات، يمكنك تحديد **تفاصيل الأمر** على شريط التطبيقات لعرض تفاصيل المستند. يمكنك أيضا تنشيط معالجه الإيصال في بنود المستندات المؤهلة.

في طريقة عرض صفحة قائمة المستندات، يمكنك أيضا إنشاء أمر تحويل خارجي جديد لأحد المتاجر.

## <a name="transfer-order-shipping-process"></a>عملية شحن أمر التحويل

بعد تحديد مستند أمر تحويل في علامة التبويب **نشط** يمكنك تحديد **تفاصيل الأمر** لبدء عملية الاستيفاء. تظهر طريقة العرض **قائمة الطلبات الكاملة**. تعرض هذه الصفحة كافة بنود المستند التي تحتوي على الصنف. كما تعرض تفاصيل الكمية المطلوبة.

يعمل كل مسح للكود الشريطي على تحديث الكمية في حقل **الشحن الآن** بمقدار وحدة واحدة. وبدلاً من ذلك، يمكنك إدخال كمية شحن عن طريق تحديد **شحن منتج** على شريط التطبيق، وإدخال معرف صنف، ثم إدخال الكمية. إذا كان الصنف متحكمًا في موقعه، فيمكنك تأكيد موقع الشحن أو تعيينه لبند المستند.

في طريقة العرض **قائمة الطلبات الكاملة‬‏‫** يمكنك تحديد بند يدويًا في القائمة ثم تحديث الكمية **شحن الآن** للبند المحدد في جزء **التفاصيل**.

### <a name="over-delivery-shipping-validations"></a>عمليات التحقق من صحة الشحن الزائد

يحدث التحقق من الصحة أثناء عملية الاستلام لبنود المستند. وتتضمن عمليات التحقق من الصحة التسليم بالزيادة. إذا حاول مستخدم استلام المزيد من المخزون أكثر من الذي تم طلبه في أمر شراء، ولكن لم يتم تكوين التسليم بالزيادة أو أن الكمية التي تم استلامها تجاوزت حد التسامح في التسليم بالزيادة الذي تم تكوينه لبند أمر الشراء، فسيستلم المستخدم خطًا ولن يُسمح له باستلام الكمية الزائدة.

### <a name="underdelivery-close-lines"></a>البنود المغلقة في التسليم بالأقل

في الإصدار 10.0.12 من Commerce، تمت إضافة وظيفة تتيح لمستخدمي نقطة البيع إغلاق أو إلغاء الكميات المتبقية أثناء شحن الأمر الصادر إذا حدد المستودع الصادر أنه لا يمكنه شحن الكمية الكاملة التي تم طلبها. يمكن أيضًا إغلاق الكميات أو إلغاؤها فيما بعد. لاستخدام هذه القدرة، يجب تكوين الشركة للسماح بالتسليم الأقل لأوامر التحويل. بالإضافة إلى ذلك، يجب تحديد نسبة مئوية للتسليم بالأقل لسطر أمر التحويل.

لتكوين الشركة بحيث تسمح بالتسليم الأقل لأوامر التحويل، في Commerce Headquarters، انتقل إلى **إدارة المخزون \> الإعداد \> معلمات إدارة المخزون والمستودعات**. في صفحة **معلمات إدارة المخزون والمستودعات**، في علامة التبويب **أوامر التحويل**، قم بتشغيل معلمة **قبول التسليم بالأقل**. ثم قم بتشغيل مهمة مجدول التوزيع **1070** لمزامنة تغييرات المعلمات مع قناة المتجر.

يمكن تحديد النسب المئوية للتسليم بالأقل لسطر أمر التحويل مسبقًا على المنتجات كجزء من تكوين المنتج في Commerce Headquarters. وبدلا من، يمكن تعيينها أو استبدالها بسطر أمر تحويل محدد من خلال Commerce Headquarters.

بعد انتهاء المؤسسة من تكوين تسليم أمر التحويل بالأقل، سيرى المستخدمون خيار **إغلاق الكمية المتبقية** الجديد في جزء **التفاصيل** عند قيامهم بتحديد سطر أمر تحويل صادر من خلال **العملية الصادرة**في نقطة البيع. بعد ذلك عندما يقوم المستخدمون بإكمال الشحنة باستخدام عملية **إنهاء الاستيفاء**، يمكنهم إرسال طلب إلى Commerce Headquarters لإلغاء الكمية المتبقية غير المشحونة. في حالة اختيار مستخدم لإغلاق الكمية المتبقية، فإن Commerce يجري عملية تحقق الصحة للتأكد من أن الكمية التي يتم إلغاؤها تقع ضمن تفاوت النسبة المئوية للتسليم بالأقل الذي تم تحديده في سطر أمر التحويل. وفي حالة تجاوز الحد المسموح به للتسليم بالأقل، يتلقى المستخدم رسالة خطأ ولا يمكنه إغلاق الكمية المتبقية حتى تستوفي الكمية التي تم شحنها وتسليمها الآن أو تتجاوز حد التسليم بالأقل.

بعد مزامنة الشحنة مع Commerce Headquarters، يتم تحديث الكميات المحددة في حقل **الشحن الآن** لسطر أمر التحويل في نقطة البيع إلى حالة مشحونة في Commerce Headquarters. وتعتبر أي كميات غير مشحونة والتي كان يتم اعتبارها في السابق كميات "الشحن المتبقي" (أي الكميات التي سيتم شحنها لاحقا) كميات ملغاة بدلا من ذلك. يتم تعيين كمية "الشحن المتبقي" الخاصة بسطر أمر التحويل إلى **0** (صفر)، ويعتبر السطر مشحون بالكامل.

### <a name="shipping-location-controlled-items"></a>شحن الأصناف المتحكم في موقعها

إذا كانت الأصناف التي يجري شحنها مُتحكم في موقعها، فيمكن للمستخدمين اختيار الموقع الذي يرغبون في إصدار المخزون منه خلال عملية الشحن. نوصي بأن تقوم بتكوين موقع إصدار افتراضي لمستودع المتجر، لجعل هذه العملية أكثر كفاءه. حتى في حالة تكوين موقع افتراضي، يمكن للمستخدمين تجاوز موقع الإصدار في البنود المحددة كما هو مطلوب.

تراعي العملية تكوين **‏‫مسموح بالإيصال الفارغ‬** على بعد التخزين **الموقع** ولا تتطلب إدخال بعد موقع في حالة تكوين إيصال فارغ. إذا كانت مواقع الاستلام الفارغة غير مسموح بها لأحد الأصناف، فسيُظهر تطبيق نقطة البيع خطأً ويتطلب إدخال موقع قبل ترحيل الإيصال.

### <a name="ship-all"></a>شحن الكل

كما يمكنك حسب حاجتك تحديد **شحن الكل** على شريط التطبيق لسرعة تحديث كمية **شحن الآن** بسرعة لكافة بنود المستند إلى القيمة القصوى المتاحة للاستيفاء لهذه البنود.

### <a name="cancel-fulfillment"></a>إلغاء الاستيفاء

يجب عليك استخدام وظيفة **إلغاء التنفيذ‬** على شريط التطبيق فقط إذا كنت ترغب في التراجع عن المستند ولا ترغب في حفظ إيه تغييرات. على سبيل المثال، قمت في البداية بتحديد المستند الخطًا ولا تريد حفظ أي من بيانات الشحن السابقة.

### <a name="pause-fulfillment"></a>إيقاف الاستيفاء مؤقتًا

إذا كنت تنفذ أمر التحويل، يمكنك استخدام وظيفة **وقف التنفيذ مؤقتًا** إذا كنت ترغب في الحصول على راحة قصيرة من العملية. على سبيل المثال، قد ترغب في إجراء عملية أخرى من نقطه البيع، كتسجيل عملية بيع عميل، أو تأخير ترحيل الشحنة إلى مركز Commerce.

عند تحديد **وقف التنفيذ مؤقتًا**، تتغير حالة المستند إلى **متوقف مؤقتا**. لذلك، سيعرف المستخدم بأنه قد تم إدخال البيانات في المستند، ولكن لم يتم بعد تنفيذ المستند. عندما تكون مستعدًا لاستئناف عملية التنفيذ، حدد المستند المتوقف مؤقتا، ثم حدد **تفاصيل الأمر**. سيتم الاحتفاظ بأي كميات **شحن الآن** تم حفظها مسبقا ويمكن عرضها من طريقة العرض **قائمة الطلبات الكاملة**.

### <a name="finish-fulfillment"></a>إنهاء الاستيفاء

عند انتهائك من إدخال جميع كميات **شحن الآن** للمنتجات، يجب عليك تحديد **إنهاء التنفيذ** في شريط التطبيقات.

عند استخدام معالجة مستند غير متزامن، يتم إرسال الإيصال عبر إطار عمل مستند غير متزامن. يعتمد الوقت المستغرق في ترحيل المستند على حجم المستند (عدد الأسطر) وحركة المعالجة العامة التي تحدث على الخادم. بشكل عام، تحدث هذه العملية بالثواني. في حالة فشل عملية ترحيل المستند، يتم إعلام المستخدم من خلال قائمة مستندات **العملية الخارجية** على علامة التبويب **نشط** حيث سيتم تحديث حالة المستند إلى **‏‫فشلت المعالجة**. ويمكن للمستخدم بعد ذلك تحديد المستند الذي تعرض للفشل في نقطة البيع لعرض رسائل الخطأ وسبب الفشل في جزء **التفاصيل**. ويظل المستند الفاشل غير مرحل ويلزم المستخدم الرجوع إلى بنود المستند عن طريق تحديد **تفاصيل الأمر** في نقطة البيع. ويجب على المستخدم تحديث المستند بالتصحيحات استنادا إلى الأخطاء. بعد تصحيح مستند، يمكن للمستخدم القيام بذلك مرة أخرى من خلال تحديد **إنهاء التنفيذ** على شريط التطبيق.

## <a name="create-an-outbound-transfer-order"></a>إنشاءأمر تحويل خارجي

من نقطة البيع، يمكن للمستخدمين إنشاء مستندات أوامر تحويل جديدة. لبدء العملية، حدد **جديد** في شريط التطبيقات أثناء وجودك في قائمة المستندات **العملية الخارجية**. ستتم مطالبتك بعد ذلك بتحديد **تحويل إلى** المستودع أو المتجر الذي سيقوم المتجر الحالي بإرسال المخزون إليه. وتقتصر القيم على التحديد الذي يتم تحديده في تكوين مجموعة تنفيذ المتجر. في طلب تحويل خارجي، سيكون المتجر الحالي الخاص بك دائمًا **تحويل من** المستودع الخاص بأمر التحويل. لا يمكن تغيير القيمة.

يمكنك إدخال القيم في الحول **تاريخ الشحن** و **‏‫تاريخ الاستلام‬**و **‏‫وضع التسليم‬** كما هو مطلوب. يمكنك أيضا إضافة ملاحظة سيتم تخزينها مع رأس أمر التحويل، كمرفق بالمستند في مركز Commerce.

بعد إنشاء معلومات الرأس، يمكنك إضافة منتجات إلى أمر التحويل. لبدء عملية إضافة الأصناف والكميات المطلوبة، قم بمسح الأكواد الشريطية أو حدد **إضافة منتج**.

بعد إدخال البنود في أمر التحويل الخارجي، يجب عليك تحديد **حفظ** لحفظ تغييرات المستند محليا أو **‏‫إرسال الطلب‬** لإرسال تفاصيل الأمر إلى مركز Commerce لمزيد من المعالجة. إذا حددت **حفظ**، سيتم تخزين مستند المسودة في قاعدة بيانات القناة، ولا يمكن للمستودع الخارجي تشغيل المستند حتى تتم معالجته بنجاح من خلال **إرسال الطلب**. يجب تحديد **حفظ** فقط إذا لم تكن مستعدا لإرسال الطلب إلى مركز Commerce للمعالجة.

إذا تم حفظ مستند محليا، فيمكن العثور عليه على علامة التبويب **مسوادات** في قائمة مستندات **العملية الداخلية**. وعندما يكون المستند في حالة **مسودة**، يمكنك تحريره عن طريق تحديد **تحرير** يمكنك تحديث البنود أو إضافتها أو حذفها كما هو مطلوب. يمكنك أيضا حذف المستند بالكامل عندما يكون في حالة **مسودة** عن طريق تحديد **حذف** في علامة التبويب **مسودات**.

وبعد إرسال مستند المسودة بنجاح إلى مركز Commerce، يظهر في علامة التبويب **نشط** وتكون حالته **مطلوب**. وفي هذه المرحلة، يمكن للمستخدمين في المستودع الخارجي وحدهم تحرير المستند، وذلك بتحديد **العملية الخارجية** في تطبيق نقطه البيع. يمكن للمستخدمين الموجودين في المستودع الداخلي عرض أمر التحويل على علامة التبويب **نشط** في قائمة المستندات **العملية الداخلي** ولكن لا يمكنهم تحريره أو حذفه. ويضمن تأمين التحرير عدم حدوث أية تعارضات لأن الطالب الداخلي بغيّر أمر التحويل في نفس الوقت الذي يقوم فيه الشاحن الخارجي بانتقاء الأمر وشحنه بفعالية. إذا كانت هناك تغييرات مطلوبة من المخزن أو المستودع الداخلي بعدما يتم إرسال أمر التحويل، فانه يجب الاتصال بالشاحن الخارجي ومطالبته بإدخال التغييرات.

وبعد وضع المستند في الحالة **مطلوب** يكون جاهزا لمعالجة التنفيذ بواسطة المستودع الخارجي. وبمجرد معالجة الشحن باستخدام العملية الخارجية، يتم تحديث حالة مستندات أمر التحويل من **مطلوب** إلى **تم الشحن بالكامل‬** أو **‏‫تم الشحن جزئيًا‬**. بعدما تكون المستندات في الحالة **تم الشحن بالكامل** أو **تم الشحن جزئيًا** يمكن للمتجر أو المستودع الداخلي ترحيل الإيصالات مقابلها باستخدام عملية استلام العملية الداخلية

يتم نقل أوامر التحويل المشحونة بالكامل إلى علامة التبويب **إكمال** لقائمة مستندات **العملية الخارجية**. هناك، تظل مرئية للمستخدمين في المخزن أو المستودع الخارجي، في وضع القراءة فقط، لسبعة أيام.

## <a name="related-topics"></a>مواضيع مرتبطة

[عملية المخزون الداخلية في نقطه البيع](pos-inbound-inventory-operation.md)