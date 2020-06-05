---
title: تكوين نُهج دمج الشحنات
description: يوضح هذا الموضوع كيفية إعداد نُهج دمج الشحنات الافتراضية والمخصصة.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: v-olbara
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: e879ec53a88e5e30257608cba7604b404ac2368a
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383704"
---
# <a name="configure-shipment-consolidation-policies"></a>تكوين نُهج دمج الشحنات

[!include [banner](../includes/banner.md)]

تسمح عملية دمج الشحنات التي تستخدم نُهج دمج الشحنات بالدمج التلقائي للشحنات أثناء الإصدار التلقائي واليدوي إلى المستودع. بعد تشغيل هذه الميزة، يجب تكوين النهج الأولي الخاص بك. إذا لم يتم تكوين أي نهج، سيقوم كل بند مبيعات بإنشاء شحنة منفصلة تحتوي على بند تحميل واحد.

توضح السيناريوهات الواردة في هذا الموضوع كيفية إعداد نُهج دمج الشحنات الافتراضية والمخصصة.

## <a name="turn-on-the-shipment-consolidation-policies-feature"></a>تشغيل ميزة نُهج دمج الشحنات

> [!IMPORTANT]
> في [السيناريو الأول](#scenario-1) الموضح في هذا الموضوع، ستقوم أولا بإعداد مستودع بحيث يستخدم ميزة دمج الشحنات السابقة. وبعد ذلك ستقوم بإتاحة نُهج دمج الشحنات. بهذه الطريقة، يمكنك تجربة كيف يعمل سيناريو الترقية. إذا كنت تخطط لاستخدام بيئة بيانات العرض التوضيحي للانتقال عبر السيناريو الأول، فلا تقم بتشغيل الميزة قبل تنفيذ السيناريو.

قبل أن تتمكن من استخدام ميزة *نُهج دمج الشحنات*، يجب تشغيلها في النظام لديك. بإمكان المسؤولين استخدام إعدادات [دارة الميزات](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) للتحقق من حالة الميزة وتشغيلها. في مساحة عمل **إدارة الميزات**، تكون هذه الميزة مدرجة بالطريقة التالية:

- **الوحدة:** *إدارة المستودعات*
- **اسم الميزة:** *دمج الشحنات*

## <a name="make-demo-data-available"></a>جعل بيانات العرض التوضيحي متاحة

يشير كل سيناريو في هذا الموضوع إلى قيم وسجلات مضمنة في بيانات العرض التوضيحي القياسية المتوفرة لـ Microsoft Dynamics 365 Supply Chain Management. إذا كنت ترغب في استخدام القيم الواردة هنا أثناء تنفيذ التمرينات، فتأكد من العمل في بيئة تم فيها تثبيت بيانات العرض التوضيحي، وقم بتعيين الكيان القانوني إلى **USMF**قبل أن تبدأ.

## <a name="scenario-1-configure-default-shipment-consolidation-policies"></a><a name="scenario-1">السيناريو 1: تكوين نهج دمج الشحنات الافتراضي</a>

يوجد حالتان يجب فيهما أن تقوم بتكوين عدد أدنى من النهج الافتراضية بعد تشغيل ميزة *نُهج دمج الشحنات*:

- أنت تقوم بترقية بيئة تحتوي بالفعل على البيانات.
- أن تقوم بإعداد بيئة جديدة تمامًا.

### <a name="upgrade-an-environment-where-warehouses-are-already-configured-for-cross-order-consolidation"></a>ترقيه بيئة تم بالفعل تكوين المستودعات لها للدمج عبر الأوامر

عند بدء هذا الإجراء، يجب إيقاف تشغيل ميزة *نهج دمج الشحنات*، لمحاكاة بيئة تم فيها بالفعل استخدام ميزة الدمج الأساسي عبر الأوامر. ستستخدم بعد ذلك إدارة الميزات لتشغيل الميزة، لكي تتمكن من معرفة كيفية إعداد نُهج دمج الشحنات بعد الترقية.

اتبع هذه الخطوات لإعداد نُهج دمج الشحنات الافتراضية في بيئة تم فيها بالفعل تكوين المستودعات للدمج عبر الأوامر.

1. انتقل إلى **إدارة المستودعات \> الإعداد \> المستودع \> المستودعات**.
1. في القائمة، ابحث عن سجل المستودع المطلوب وافتحه (على سبيل المثال، المستودع *24* في بيانات العرض التوضيحي **USMF**).
1. في جزء الإجراءات، حدد **تحرير**.
1. في علامة التبويب السريعة **المستودع**، قم بتعيين خيار **دمج الشحنات عند الإصدار إلى المستودع** إلى *نعم*.
1. كرر الخطوات من 2 إلى 4 لكافة المستودعات الأخرى التي يكون الدمج مطلوبًا فيها.
1. قم بإغلاق الصفحة.
1. استخدم [إدارة الميزات](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) لتشغيل ميزة *نُهج دمج الشحنات*. في مساحة عمل **إدارة الميزات**، يتم تسمية الميزة باسم *الشحنة المدمجة*.
1. انتقل إلى **إدارة المستودعات \> الإعداد \> الإصدار إلى المستودع \> نُهج دمج الشحنات**. قد تضطر إلى تحديث المستعرض الخاص بك لرؤية عنصر قائمة **نُهج دمج الشحنات** الجديدة بعد تشغيل الميزة.
1. في جزء الإجراءات، حدد **إنشاء إعداد افتراضي** لإنشاء النُهج التالية:

    - نهج **CrossOrder** لنوع نهج *أوامر المبيعات* (بشرط أن يكون لديك على الأقل مستودع واحد تم إعداده لاستخدام ميزة الدمج السابقة)
    - نهج **افتراضي** لنوع نهج *أوامر المبيعات*
    - نهج **افتراضي** لنوع نهج *إصدار التحويل*
    - نهج **CrossOrder** لنوع نهج *إصدار التحويل* (بشرط أن يكون لديك على الأقل مستودع واحد تم إعداده لاستخدام ميزة الدمج السابقة)

    > [!NOTE]
    > - يأخذ كل من نهجي **CrossOrder** في الاعتبار نفس مجموعة الحقول مثل المنطق السابق، باستثناء الحقل الخاص برقم الأمر. (يتم استخدام هذا الحقل لدمج البنود في الشحنات استنادا إلى عوامل مثل المستودع ووضع نقل التسليم والعنوان.)
    > - يأخذ كل من نهجي **الافتراضي** في الاعتبار نفس مجموعة الحقول مثل المنطق السابق، مع تضمين الحقل الخاص برقم الأمر. (يتم استخدام هذا الحقل لدمج البنود في الشحنات استنادا إلى عوامل مثل رقم الأمر والمستودع ووضع نقل التسليم والعنوان.)

1. حدد نهج **CrossOrder** لـ *أوامر المبيعات*، ثم في جزء الإجراءات، حدد **تحرير الاستعلام**.
1. في مربع الحوار محرر الاستعلام ، لاحظ أين تم تعيين خيار **دمج الشحنة عند الإصدار إلى المستودع** إلى *نعم*. بالتالي، يتم تضمينها في الاستعلام.

### <a name="create-default-policies-for-a-new-environment"></a>إنشاء نُهج افتراضية لبيئة جديدة

اتبع هذه الخطوات لإعداد نُهج دمج الشحنات الافتراضية في بيئة جديدة تمامًا.

1. استخدم [إدارة الميزات](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) لتشغيل ميزة *نُهج دمج الشحنات* إذا لم يكن قد تم تشغيلها بالفعل. في مساحة عمل **إدارة الميزات**، يتم تسمية الميزة باسم *الشحنة المدمجة*.
1. انتقل إلى **إدارة المستودعات \> الإعداد \> الإصدار إلى المستودع \> نُهج دمج الشحنات**.
1. في جزء الإجراءات، حدد **إنشاء إعداد افتراضي** لإنشاء النُهج التالية:

    - نهج **افتراضي** لنوع نهج *أوامر المبيعات*
    - نهج **افتراضي** لنوع نهج *إصدار التحويل*

    > [!NOTE]
    > يأخذ كل من نهجي **الافتراضي** في الاعتبار نفس مجموعة الحقول مثل المنطق السابق، مع تضمين الحقل الخاص برقم الأمر. (يتم استخدام هذا الحقل لدمج البنود في الشحنات استنادا إلى عوامل مثل رقم الأمر والمستودع ووضع نقل التسليم والعنوان.)

## <a name="scenario-2-configure-custom-shipment-consolidation-policies"></a>السيناريو 2: تكوين نهج دمج الشحنات المخصصة

يوضح هذا السيناريو كيفية إعداد نُهج دمج الشحنات المخصصة. يمكن للنهج المخصصة دعم متطلبات الأعمال المعقدة حيث تعتمد عملية دمج الشحنات على العديد من الشروط. ويوجد مع كل مثال نهج سيرد لاحقا في هذا السيناريو وصفًا مختصرًا لحالة العمل. يجب إعداد هذه الأمثلة بشكل متسلسل يضمن تقييم الاستعلامات بشكل يشبه الهرم. (بمعنى آخر، يجب تقييم النُهج التي تتضمن معظم الشروط على أنها صاحبة الأولوية الأعلى.)

### <a name="turn-on-the-feature-and-prepare-master-data-for-this-scenario"></a>تشغيل الميزة وتحضير البيانات الرئيسية لهذا السيناريو

قبل أن تتمكن من التنقل عبر التمرينات في هذا السيناريو، يجب عليك تشغيل الميزة وإعداد البيانات الرئيسية المطلوبة لإجراء التصفية، كما هو موضح في الأقسام الفرعية التالية. (يتم تطبيق هذه المتطلبات الأساسية أيضًا على السيناريوهات المدرجة في [أمثلة سيناريوهات لكيفية استخدام نُهج دمج الشحنات](#example-scenarios).)

#### <a name="turn-on-the-feature-and-create-the-default-policies"></a>تشغيل الميزة وإنشاء النُهج الافتراضية.

استخدم إدارة الميزات لتشغيل الميزة، إذا لم تكن قد قمت بتشغيلها بالفعل، وقم بإنشاء نُهج الدمج الافتراضية الموضحة في [السيناريو 1](#scenario-1).

#### <a name="create-two-new-product-filter-codes"></a>إنشاء ترميزين جديدين لتصفية المنتج

1. انتقل إلى **إدارة المستودعات \> إعداد \> عوامل تصفية المنتج \> عوامل تصفية المنتج**، ثم أضف اثنين من عوامل تصفية المنتجات:

    - عامل تصفية المنتج 1:

        - **ترميز عامل التصفية:** *قابل للاشتعال*
        - **عنوان عامل التصفية:** *الرمز 4*

    - عامل تصفية المنتج 2:

        - **ترميز عام التصفية:** *متفجر*
        - **عنوان عامل التصفية:** *الرمز 4*

1. انتقل إلى **إدارة معلومات المنتج‬ \> المنتجات \> المنتجات الصادرة**.
1. افتح المنتج الذي يحتوي على رقم الصنف *M9200*. (يجب تمكين المنتج الذي قمت بتحديده لعمليات \[WMS\] للمستودع المتقدم، وتم تمكين هذا المنتج مسبقًا لعمليات WMS في بيانات العرض التوضيحي **USMF**.)
1. في علامة التبويب السريعة **المستودع**، قم بتعيين حقل **الرمز 4** إلى *قابل للاشتعال*.
1. قم بإغلاق الصفحة.
1. افتح المنتج الذي يحتوي على رقم الصنف *M9201*. (تم تمكين هذا المنتج أيضًا بشكل مسبق لعمليات WMS في بيانات العرض التوضيحي **USMF**.)
1. في علامة التبويب السريعة **المستودع**، قم بتعيين حقل **الرمز 4** إلى *متفجر*.
1. قم بإغلاق الصفحة.

#### <a name="create-a-new-transportation-mode-of-delivery"></a>قم بإنشاء وضع نقل جديد للتسليم.

1. انتقل إلى **إدارة النقل \> الإعداد \> شركات النقل \> الوضع**.
1. قم بإنشاء وضع النقل الذي سيتم استخدامه في استعلامات الدمج، وقم بتسميته *Airways*.
1. انتقل إلى **إدارة النقل \> إعداد \> شركات النقل‬‬ \> شركات الشحن‬‬**.
1. قم بإنشاء شركة نقل تتضمن الإعدادات التالية:

    - **شركه الشحن:** *Airways*
    - **الاسم:** *Airways*
    - **الوضع:** *Airways*

1. في علامة التبويب السريعة **الخدمات** لشركه النقل الجديدة، قم بإضافة صف يحتوي على الإعدادات التالية:

    - **خدمة شركة النقل:** *Air*
    - **وسيلة النقل:** *Air*

1. في جزء الإجراءات، حدد **حفظ**.

    > [!NOTE]
    > عند حفظ شركة النقل الجديدة، يتم تعيين حقل **وضع التسليم** للصف الجديد في شبكة **الخدمات** تلقائيا إلى *Airwa-Air*. عند استخدام وضع التسليم *Airwa-Air* لأمر المبيعات، سيتم استخدام وضع النقل *Airways* للشحنات ذات الصلة.

#### <a name="create-an-order-pool"></a>إنشاء وعاء أوامر

1. انتقل إلى **المبيعات والتسويق \> الإعداد \> أوامر المبيعات \> أوعية الأوامر**.
1. قم بإنشاء وعاء أوامر سيتم استخدامه مع استعلام الدمج. يجب أن يتضمن وعاء الأوامر هذا الإعدادات التالية:

    - **الوعاء:** أدخل عددًا صحيحًا غير مستخدم بالفعل من قبل أي وعاء آخر.
    - **الاسم:** *ShipCons*

1. انتقل إلى **المبيعات والتسويق \> العملاء \> جميع العملاء‬**.
1. افتح العميل الذي يتضمن رقم الحساب *US-003*.
1. في علامة التبويب السريعة **‬‏‫إعدادات أوامر المبيعات الافتراضية‬‏‫**، قم بتعيين حقل **وعاء أوامر المبيعات** إلى وعاء الأوامر الذي قمت بإنشائه لتوك.
1. قم بإغلاق الصفحة، ثم قم بتكرار الخطوتين 4 و 5 للعميل الذي له رقم حساب *004*.

### <a name="create-example-policy-1"></a>إنشاء مثال للنهج 1

في هذا المثال، ستقوم بإنشاء نهج *العميل + الوضع* الذي يمكن استخدامه لحالة الأعمال التالية:

- سيقوم النهج بالاستعلام عن حساب عميل محدد (*US-001*) ووضع تسليم محدد (*Airwa-Air*).
- يتم إيقاف تشغيل الدمج مع الشحنات المفتوحة.
- ويتم إجراء الدمج حسب معرف الأمر. (بمعنى آخر، ستكون هناك شحنات منفصلة لكل أمر، ومستودع، وهكذا.)

اتبع الخطوات التالية لإنشاء نهج دمج الشحنات لحالة الأعمال هذه.

1. انتقل إلى **إدارة المستودعات \> الإعداد \> الإصدار إلى المستودع \> نُهج دمج الشحنات**.
1. قم بتعيين حقل **نوع النهج** إلى *أوامر المبيعات*.
1. في جزء الإجراءات، حدد **جديد** لإنشاء نهج بالإعدادات التالية:

    - **اسم النهج:** *CustomerMode*
    - **وصف النهج:** *حساب العميل ووضع التسليم*

1. اترك خيار **دمج مع الشحنات المفتوحة** معينًا إلى *لا*.
1. في جزء الإجراءات، حدد **حفظ**.
1. في علامة التبويب السريعة **حقول الدمج**، في قائمة **الحقول المتبقية**، حدد الصف الذي تم فيه تعيين حقل **اسم الحقل** إلى *وضع التسليم*.
1. حدد زر **إضافة** ![سهم لليمين](media/forward-button.png) لنقل الحقل إلى قائمة **الحقول المحددة**.
1. في جزء الإجراءات، حدد **تحرير استعلام**.
1. في مربع الحوار محرر الاستعلام ، ضمن علامة التبويب **النطاق**، في الشبكة، ابحث عن الصف الذي تم فيه تعيين حقل **الحقل** إلى *حساب العميل*، وقم بتعيين حقل **المعايير** لهذا الصف إلى *US-001*.
1. حدد **إضافة** لإضافة صف يتضمن الإعدادات التالية للشبكة:

    - **الجدول:** *بنود الأمر*
    - **الجدول المشتق:** *بنود الأمر*
    - **الحقل:** *وضع التسليم*
    - **المعايير:** *Airwa-Air*

1. حدد **موافق** لإغلاق مربع الحوار.

> [!NOTE]
> في حالة الأعمال هذه، لن يتم دمج سطور الأوامر الخاصة بالعميل *US-001* التي تستخدم وضع التسليم *Airwa-Air* عبر الأوامر. يتم تخصيص هذا النهج لاستخدامه أولا في التسلسل، في الحالات التي يتم فيها دمج الشحنات لكافة أوضاع التسليم الأخرى لهذا العميل.

### <a name="create-example-policy-2"></a>إنشاء مثال للنهج 2

في هذا المثال، ستقوم بإنشاء نهج *البضائع الخطرة* الذي يمكن استخدامه لحالة الأعمال التالية:

- سيقوم النهج بالاستعلام عن رمز تصفية محدد (*خطر*) ووضع تسليم محدد (*Airwa-Air*).
- يتم تشغيل الدمج مع الشحنات المفتوحة.
- ويتم إجراء الدمج عبر الأوامر المشتركة. (بمعنى آخر، ستكون هناك شحنات منفصلة لكل حساب ومستودع وهكذا، ولكن فقط داخل مجموعة الأصناف المحددة في الاستعلام.)

اتبع الخطوات التالية لإنشاء نهج دمج الشحنات لحالة الأعمال هذه.

1. انتقل إلى **إدارة المستودعات \> الإعداد \> الإصدار إلى المستودع \> نُهج دمج الشحنات**.
1. قم بتعيين حقل **نوع النهج** إلى *أوامر المبيعات*.
1. في جزء الإجراءات، حدد **جديد** لإنشاء نهج بالإعدادات التالية:

    - **اسم النهج:** *نوع الصنف*
    - **وصف النهج:** *دمج نفس نوع الصنف عبر الأوامر*

1. قم بتعيين خيار **دمج مع الشحنات المفتوحة** إلى *نعم*.
1. في جزء الإجراءات، حدد **حفظ**.
1. في علامة التبويب السريعة **حقول الدمج**، في قائمة **الحقول المتبقية**، حدد الصف الذي تم فيه تعيين حقل **اسم الحقل** إلى *وضع التسليم*.
1. حدد زر **إضافة** ![سهم لليمين](media/forward-button.png) لنقل الحقل إلى قائمة **الحقول المحددة**.
1. في جزء الإجراءات، حدد **تحرير استعلام**.
1. في مربع الحوار محرر الاستعلام، في علامة تبويب **عمليات الانضمام**، قم بتوسيع وتحديد **الجداول \> تحميل التفاصيل** في الشجرة.
1. حدد **إضافة انضمام جدول**.
1. في شبكة العلاقات التي تظهر، ابحث عن وحدد الصف الذي تم فيه تعيين حقل **العلاقة** إلى *رقم صنف المستودع (رقم الصنف)*، ثم حدد **تحديد**. 
1. في علامة تبويب **النطاق**، حدد **إضافة** لإضافة صف يتضمن الإعدادات التالية للشبكة:

    - **الجدول:** *رقم صنف المستودع*
    - **الجدول المشتق:** *رقم صنف المستودع*
    - **الحقل:** *الرمز 4*
    - **المعايير:** *قابل للاشتعال*

1. حدد **موافق** لإغلاق مربع الحوار.

> [!NOTE]
> في حالة الأعمال هذه، سيتم دمج كافة بنود الأوامر التي تحتوي الأصناف فيها على رمز تصفية محدد (أي، رمز التصفية الذي تم تعيين حقل **الرمز 4** فيه إلى *قابل للاشتعال*) مع الأصناف الأخرى بنفس نوع عبر الأوامر. إذا كان هناك شحنة مفتوحة لنفس الحساب والمستودع ومجموعة الأصناف، فسيتم إلحاق البنود الجديدة بها.

### <a name="create-example-policy-3"></a>إنشاء مثال للنهج 3

في هذا المثال، ستقوم بإنشاء نهج *متطلبات العملاء* الذي يمكن استخدامه لحالة الأعمال التالية:

- سيقوم النهج بالاستعلام عن حساب عميل محدد.
- يتم تشغيل الدمج مع الشحنات المفتوحة.
- ويتم إجراء الدمج عبر الأوامر ولكنه يستند إلى طلبات العميل. (بمعنى آخر، سيتم تجميع الأوامر المتعددة إلى شحنات، استنادًا إلى نفس رقم طلب العميل والمستودع.)

اتبع الخطوات التالية لإنشاء نهج دمج الشحنات لحالة الأعمال هذه.

1. انتقل إلى **إدارة المستودعات \> الإعداد \> الإصدار إلى المستودع \> نُهج دمج الشحنات**.
1. قم بتعيين حقل **نوع النهج** إلى *أوامر المبيعات*.
1. في جزء الإجراءات، حدد **جديد** لإنشاء نهج بالإعدادات التالية:

    - **اسم النهج:** *CustomerOrderNo*
    - **وصف النهج:** *دمج البنود استنادا إلى أمر شراء العميل*

1. قم بتعيين خيار **دمج مع الشحنات المفتوحة** إلى *نعم*.
1. في جزء الإجراءات، حدد **حفظ**.
1. في علامة التبويب السريعة **حقول الدمج**، في قائمة **الحقول المتبقية**، حدد الصف الذي تم فيه تعيين حقل **اسم الحقل** إلى *طلب العميل*.
1. حدد زر **إضافة** ![سهم لليمين](media/forward-button.png) لنقل الحقل إلى قائمة **الحقول المحددة**.
1. في قائمة **الحقول المتبقية**، حدد الصف الذي تم فيه تعيين حقل **اسم الحقل** إلى *وضع التسليم*.
1. حدد زر **إضافة** ![سهم لليمين](media/forward-button.png) لنقل الحقل إلى قائمة **الحقول المحددة**.
1. في جزء الإجراءات، حدد **تحرير استعلام**.
1. في مربع الحوار محرر الاستعلام ، ضمن علامة التبويب **النطاق**، ابحث عن الصف الذي تم فيه تعيين حقل **الحقل** إلى *حساب العميل*، وقم بتعيين حقل **المعايير** لهذا الصف إلى *US-001*.
1. حدد **موافق** لإغلاق مربع الحوار.

> [!NOTE]
> في حالة الأعمال هذه، سيتم دمج كافة بنود الأوامر التي يكون لأوامر المبيعات فيها نفس رقم طلب العميل في شحنة واحدة، بغض النظر عن رقم أمر المبيعات. (يتم استخدام رقم طلب العميل كرقم \[PO\] لأمر شراء العميل.) إذا كان هناك شحنة مفتوحة لنفس الحساب والمستودع وطلب العميل، فسيتم إلحاق البنود الجديدة بها. يمكن استخدام هذا النهج إذا كان العميل يقوم بإرسال بنود أوامر إضافية لها نفس رقم أمر الشراء عدة مرات خلال يوم معين ويرغب في تجميع كافة البنود في شحنة واحدة. (بمعنى آخر، سيكون هناك بوليصة شحن واحدة وإيصال تعبئة واحد.)

### <a name="create-example-policy-4"></a>إنشاء مثال للنهج 4

في هذا المثال، ستقوم بإنشاء نهج *سماح العملاء بالدمج* الذي يمكن استخدامه لحالة الأعمال التالية:

- سيقوم النهج بالاستعلام عن وعاء أوامر محدد لتحديد العملاء الذين يقبلون الشحنات المدمجة.
- يتم إيقاف تشغيل الدمج مع الشحنات المفتوحة.
- يتم إجراء الدمج عبر الأوامر باستخدام الحقول المحددة بواسطة نهج CrossOrder الافتراضي (لاستنساخ خانة اختيار **المستودع** السابقة).

- يمكنك تجاوز القاعدة في أمر المبيعات من خلال تحديد وعاء أوامر مختلف.

اتبع الخطوات التالية لإنشاء نهج دمج الشحنات لحالة الأعمال هذه.

1. انتقل إلى **إدارة المستودعات \> الإعداد \> الإصدار إلى المستودع \> نُهج دمج الشحنات**.
1. قم بتعيين حقل **نوع النهج** إلى *أوامر المبيعات*.
1. في جزء الإجراءات، حدد **جديد** لإنشاء نهج بالإعدادات التالية:

    - **اسم النهج:** *وعاء الأوامر*
    - **وصف النهج:** *دمج عبر الأوامر استنادًا إلى وعاء الأوامر*

1. اترك خيار **دمج مع الشحنات المفتوحة** معينًا إلى *لا*.
1. في جزء الإجراءات، حدد **حفظ**.
1. في علامة التبويب السريعة **حقول الدمج**، في قائمة **الحقول المتبقية**، حدد الصف الذي تم فيه تعيين حقل **اسم الحقل** إلى *وضع التسليم*.
1. حدد زر **إضافة** ![سهم لليمين](media/forward-button.png) لنقل الحقل إلى قائمة **الحقول المحددة**.
1. في جزء الإجراءات، حدد **تحرير استعلام**.
1. في مربع حوار محرر الاستعلام، في علامة تبويب **النطاق**، حدد **إضافة** لإضافة صف يتضمن الإعدادات التالية للشبكة:

    - **الجدول:** *أوامر المبيعات*
    - **الجدول المشتق:** *أوامر المبيعات*
    - **الحقل:** *الوعاء*
    - **المعايير:** *ShipCons*

1. حدد **موافق** لإغلاق مربع الحوار.

> [!NOTE]
> في حالة الأعمال هذه، سيتم دمج كافة بنود الأوامر التي تنتمي فيها أوامر المبيعات إلى نفس وعاء الأوامر في شحنة واحدة عبر أوامر المبيعات لنفس الحساب والمستودع ووضع النقل الخاص بالتسليم. وبدلا من وعاء الأوامر، يمكنك استخدام أي حقل آخر لتمييز مجموعة من العملاء واستخدام رأس أمر المبيعات بشكل افتراضي. يمكنك استخدام هذا الأسلوب إذا كان العميل، وليس المستودع، يقوم بتوجيه الحاجة إلى الدمج. (في منطق الدمج السابق، ساهم المستودع في توجيه الحاجة إلى الدمج.)

### <a name="create-example-policy-5"></a>إنشاء مثال للنهج 5

في هذا المثال، ستقوم بإنشاء نهج *سماح المستودعات بالدمج* الذي يمكن استخدامه لحالة الأعمال التالية:

- سيقوم النهج بالاستعلام عن وعاء أوامر محدد لتحديد المستودعات التي يمكنها دمج الشحنات.
- يتم إيقاف تشغيل الدمج مع الشحنات المفتوحة.
- يتم إجراء الدمج عبر الأوامر باستخدام الحقول المحددة بواسطة نهج CrossOrder الافتراضي (لاستنساخ خانة اختيار **المستودع** السابقة).

عادة، يمكن معالجة حالة الأعمال هذه باستخدام النُهج الافتراضية التي قمت بإنشائها في [السيناريو 1](#scenario-1). ومع ذلك، يمكنك أيضًا إنشاء سياسات مشابهة يدويًا باتباع الخطوات التالية.

1. انتقل إلى **إدارة المستودعات \> الإعداد \> الإصدار إلى المستودع \> نُهج دمج الشحنات**.
1. قم بتعيين حقل **نوع النهج** إلى *أوامر المبيعات*.
1. في جزء الإجراءات، حدد **جديد** لإنشاء نهج بالإعدادات التالية:

    - **اسم النهج:** *عبر الأوامر*
    - **وصف النهج:** *دمج عبر الأوامر لمستودعات محددة*

1. اترك خيار **دمج مع الشحنات المفتوحة** معينًا إلى *لا*.
1. في جزء الإجراءات، حدد **حفظ**.
1. في علامة التبويب السريعة **حقول الدمج**، في حقل **الحقول المتبقية**، حدد الصف الذي تم فيه تعيين حقل **اسم الحقل** إلى *وضع التسليم*.
1. حدد زر **إضافة** ![سهم لليمين](media/forward-button.png) لنقل الحقل إلى قائمة **الحقول المحددة**.
1. في جزء الإجراءات، حدد **تحرير استعلام**.
1. في مربع الحوار محرر الاستعلام ، ضمن علامة التبويب **النطاق**، ابحث عن الصف الذي تم فيه تعيين حقل **الحقل** إلى *المستودع*، وقم بتعيين حقل **المعايير** لهذا الصف إلى *61, 63*.
1. حدد **موافق** لإغلاق مربع الحوار.

### <a name="set-the-order"></a>تعيين الأمر

والآن بعد إنشاء كافة النُهج، يجب عليك إنشاء الأمر الذي سيتم تطبيقها فيه. لاستخدام أسلوب يشبه الهرم، بحيث يتم تقييم النهج التي تتضمن معظم الشروط باعتبارها صاحبة أعلى أولوية، اتبع الخطوات التالية.

1. انتقل إلى **إدارة المستودعات \> الإعداد \> الإصدار إلى المستودع \> نُهج دمج الشحنات**.
1. قم بتعيين حقل **نوع النهج** إلى *أوامر المبيعات*.
1. حدد كل نهج مسرود في العمود الأيمن، ثم استخدم الزرين **تحريك لأعلى** و **تحريك لأسفل** في جزء الإجراءات لترتيب النهج بالترتيب التالي:

    1. CustomerMode
    1. نوع الصنف
    1. CustomerOrderNo
    1. وعاء الأوامر
    1. عبر الأوامر
    1. الإعداد الافتراضي

## <a name="example-scenarios-of-how-to-use-shipment-consolidation-policies"></a><a name="example-scenarios"></a>سيناريوهات أمثلة لكيفية استخدام نُهج دمج الشحنات

توضح السيناريوهات التالية كيفية استخدام نُهج دمج الشحنات التي قمت بإنشائها أثناء قراءة هذا الموضوع. يتناول معك كل سيناريو عملية دمج الشحنات التي تستخدم نُهج دمج الشحنات أثناء الإصدار التلقائي واليدوي إلى المستودع:

- السيناريو 1: [دمج الشحنات عند إصدارها إلى المستودع باستخدام الإصدار التلقائي لأوامر المبيعات](../warehousing/consolidate-shipments-automatic.md)
- السيناريو 2: [دمج الشحنات عند تجاوز نهج دمج الشحنات من صفحة الإصدار إلى المستودع](../warehousing/consolidate-shipments-release-to-warehouse-override.md)
- السيناريو 3: [دمج الشحنات باستخدام الإصدار إلى المستودع من منضدة عمل تخطيط الحمل](../warehousing/consolidate-shipments-load-planning-workbench.md)
- السيناريو 4: [دمج الشحنات باستخدام منضدة عمل دمج الشحنات](../warehousing/consolidate-shipments-manual-workbench.md)
- السيناريو 5: [دمج الشحنات يدويًا باستخدام صفحة دمج الشحنات](../warehousing/consolidate-shipments-manual-form.md)


## <a name="additional-resources"></a>الموارد الإضافية

- [سياسات دمج الشحنات](about-shipment-consolidation-policies.md)