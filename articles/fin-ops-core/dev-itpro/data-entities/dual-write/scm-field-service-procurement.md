---
title: تكامل التدبير بين Supply Chain Management وField Service
description: يصف هذا الموضوع كيف يدعم تكامل الكتابة الثنائية إنشاء أمر شراء وتحديثات من كل من Supply Chain Management وField Service.
author: RichardLuan
manager: tfehr
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: rhaertle
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2020-11-11
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: c2b0d5be38425b5ceebb38b7964f5ec600b1c838
ms.sourcegitcommit: ca05440ee503bf15fe98fe138d317c1cdf21ad16
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/09/2021
ms.locfileid: "5141894"
---
# <a name="integrate-procurement-between-supply-chain-management-and-field-service"></a>تكامل التدبير بين Supply Chain Management وField Service

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

توفر Microsoft Dynamics 365 Supply Chain Management وظيفة تدبير قويه. يقدم Dynamics 365 Field Service وظيفة مشابهه تدعم عمليات الشراء المرتبطة بعمليه الخدمة. يتم دمج الوظيفة الموجودة في هذين التطبيقين من خلال الكتابة المزدوجة ، ويتم تمكين حالات الاستخدام المتداخلة الناتجة من خلال تعيينات الجداول ومنطق الحلول وطرق العرض والنماذج.

يدعم هذا التكامل إنشاء أمر الشراء، وفي معظم الحالات، تحديثات من كلا التطبيقين. ومع ذلك ، فان Supply Chain Management تتحكم في التسعير والعناوين وإيصال استلام المنتجات. يتم تمكين العديد من حالات الاستخدام الفعالة الفعالة للمؤسسات التي تستخدم Field Service وSupply Chain Management. وتمكن حالات الاستخدام هذه بدء عمليات التدبير وتعقبها عبر كلا النظامين.

يبين الرسم التوضيحي التالي الجداول الموجودة في كلا النظامين وكيفيه تعيينها لبعضها البعض. أوامر الشراء في Field Service تشير إلى صف *حساب*، في حين ان أوامر الشراء في Supply Chain Management تشير إلى صف *مورد*. لحل التكامل، يستخدم الكتابة الثنائية مرجعا لربط صفوف *المورد* بصفوف *الحساب*. لمزيد من المعلومات، راجع [الرئيسي المتكامل للمورد](vendor-mapping.md).

![تعيينات التدبير](media/scm-field-service-tables.png)

## <a name="prerequisites"></a>المتطلبات الأساسية

لتكامل Supply Chain Management مع Field Service، يجب تثبيت المكونات التالية:

- إصدار 8.8.31.60 Field Service أو إصدار لاحق، لتكامل أمر الشراء الشامل
- الإصدار 10.0.14 أو أحدث من Supply Chain Management
- الكتابة الثنائية، لتشغيل حل OneFSSCM

## <a name="installation-guidelines"></a>إرشادات التثبيت

### <a name="prerequisites"></a>المتطلبات الأساسية

+ **الكتابة الثنائية** – لمزيد من المعلومات، راجع [الصفحة الرئيسية ثنائيه الكتابة](dual-write-home-page.md#dual-write-setup).
+ **Dynamics 365 Field Service** – لمزيد من المعلومات، راجع [كيفية تثبيت Dynamics 365 Field Service](https://docs.microsoft.com/dynamics365/field-service/install-field-service#step-1-install-dynamics-365-field-service)

عند تمكينها في Microsoft Dataverse، تقوم الكتابة الثنائية وField Service بتقديم عده طبقات حل تعمل علي توسيع البيئة مع بيانات التعريف الجديدة والنماذج وطرق العرض والمنطق. يمكن تمكين هذه الحلول بأي ترتيب، بالرغم من انك عاده ما تقوم بالتثبيت بالترتيب المحدد هنا:

1. **Field Service Common** - يتم تثبيت Field Service Common عند تثبيت Field Service في البيئة.
2. **Field Service (Anchor)** - يتم تثبيت Field Service (Anchor) عند تثبيت Field Service في البيئة. 
3. **Supply Chain Management الموسعة** - Supply Chain Management الموسعة يتم تثبيتها تلقائيا عند تمكين الكتابة الثنائية في البيئة. 
4. **حل OneFSSCM** – يتم تثبيت OneFSSCM تلقائيا بواسطة اي الحلول (Field Service أو Supply Chain Management) التي تم تثبيتها مؤخرا.

    + إذا كانت Field Service مثبته بالفعل في البيئة، وكانت تقوم بتمكين الكتابة الثنائية، التي تقوم بتثبيت Supply Chain Management الموسعة، سيتم تثبيت OneFSSCM.
    + إذا كانت Supply Chain Management الموسعة مثبته بالفعل في البيئة، وكانت تقوم بتمكين الكتابة الثنائية، التي تقوم بتثبيت Field Service، سيتم تثبيت OneFSSCM.

## <a name="initial-synchronization"></a>مزامنة أولية

لإنشاء أوامر شراء جديده والعمل مع أوامر الشراء الموجودة، يجب عليك مزامنة البيانات المرجعية بين Supply Chain Management وDataverse. يمكنك استخدام وظيفة الكتابة الاوليه للكشف عن علاقات الجداول والبحث عن الجداول التي يجب تمكينها لخريطة معينه.

يجب مزامنة الجداول التالية:

- قوالب المنتجات

    عندما تقوم بتشغيل الكتابة الاوليه، تحصل علي قائمه كامله بالجداول المطلوبة. فيما يلي بعض الأمثلة عن هذه القوالب:

    - كل المنتجات
    - المنتجات الصادرة V2
    - المنتجات المميزة الصادرة لـ Dataverse

- المواقع
- المستودعات
- قوالب فئات التدبير

    فيما يلي بعض الأمثلة عن هذه القوالب:

    - فئات التدبير
    - أساس
    - التدرج الهرمي لفئات المنتجات
    - تعيينات فئات المنتج

- قوالب الموردين ، مثل المورد الإصدار 2
- قوالب الشخص المسؤول عن الاتصال، مثل جهات اتصال Dataverse الإصدار 2
- قوالب العاملين، مثل العامل

تضمن مزامنة الجداول ان كافة المستندات (أوامر الشراء وإيصالات استلام المنتجات) في Supply Chain Management متاحه في Dataverse.

### <a name="account-and-vendor-tables"></a>جداول الحساب والمورّد

تعتمد أوامر الشراء في Field Service علي جدول الحساب لتعقب الموردين. التالي، تستخدم جداول Dataverse لأوامر الشراء الحسابات لتعقب الموردين. لاحتواء هذا الاختلاف في المفتاح، يجب تنشيط مهام سير العمل الأربع التالية للاحتفاظ بالحسابات والموردين في عمليه المزامنة: 

- إنشاء الموردين في جدول الحسابات
- إنشاء الموردين في جدول الموردين
- تحديث الموردين في جدول الحسابات
- تحديث الموردين في جدول الموردين

إذا تم تثبيت OneFSSCM، لأنه يتم تثبيت كل من Field Service وSupply Chain Management الموسعة، يتم تنشيط مهام سير العمل تلقائيا. إذا لم تكن Field Service مثبته، وكانت ترغب في دمج جداول أوامر الشراء مع Dataverse، فيجب تنشيط مهام سير العمل هذه. وفي كلتا الحالتين، الا إذا قمت بالبدء من البداية، فقد تحتاج إلى التاكد من ان كافة الموردين قد تم إنشاؤهم كحسابات في Dataverse قبل إنشاء أوامر الشراء. والا، قد تحدث أخطاء.

### <a name="initial-synchronization"></a>مزامنة أولية

بعد ان تكون كافة المتطلبات المسبقة في مكانها، إذا كنت ترغب في ان تكون أوامر الشراء وإيصالات استلام المنتجات الموجودة متاحه في كلا النظامين، فيجب عليك القيام بمزامنة أوليه للقوالب التالية:

- رأس أمر الشراء الإصدار 2
- سطر أمر الشراء CDS
- حذف مبدئي لسطر أمر الشراء CDS
- عملية استلام أوامر الشراء
- منتج عملية استلام أمر الشراء

## <a name="mappings-with-logic"></a>تعيينات ذات منطق

ويقوم تكامل التدبير بتوسيع تعيين المنتج بالمنطق التالي لضمان تعيين عمود **نوع منتج Field Service** بشكل صحيح في الجدول المنتجات في Dataverse:

- إذا تم تعيين **نوع المنتج** إلى *منتج*، وتعيين **مجموعه نماذج صنف، المنتج المخزن** علي *صحيح*، يتم تعيين **نوع منتج Field Service** علي *المخزون*.
- إذا تم تعيين **نوع المنتج** إلى *منتج*، وتعيين **مجموعه نماذج صنف، المنتج المخزن** علي *خطأ*، يتم تعيين **نوع منتج Field Service** علي *غير مخزون*.
- إذا تم تعيين **نوع المنتج** على *الخدمة*، فيتم تعيين **نوع منتج Field Service** علي *الخدمة*.

بالاضافه إلى ذلك، يتضمن Dataverse المنطق الذي يقوم بتعيين الموردين مع الحسابات المرتبطة بهم. يقوم هذا المنطق بتعيين حساب مورد الفاتورة الافتراضي. عند الإنشاء ، يقوم منطق المكون الإضافي من جانب الخادم بتعيين حساب مورد الفاتورة الافتراضي من المورد المرتبط بالحساب. يكون للمورد مرجع لحساب الفاتورة المستخدم لتعيين هذه القيمة.

## <a name="supported-scenarios"></a>السيناريوهات المدعومة

+ يمكن إنشاء أوامر الشراء وتحديثها بواسطة Dataverse المستخدمين. ومع ذلك، يتم التحكم في العملية والبيانات بواسطة Supply Chain Management. يتم تطبيق قيود علي تحديثات أعمده أمر الشراء في Supply Chain Management عندما تاتي التحديثات من Field Service. علي سبيل المثال، لا يمكنك تحديث أمر شراء إذا كان قد تم إنهاؤه. 
+ إذا تم التحكم في أمر الشراء بواسطة أداره التغيير في Supply Chain Management، فيمكن لمستخدم Field Service تحديث أمر الشراء فقط عندما تكون حاله موافقه Supply Chain Management هي *مسودة*.
+ تتم أداره العديد من الاعمده فقط بواسطة Supply Chain Management ولا يمكن تحديثها في Field Service. لمعرفه الاعمده التي لا يمكن تحديثها ، راجع جداول التعيين في المنتج. لأغراض البساطة، يتم تعيين معظم هذه الاعمده للقراءة فقط علي صفحات Dataverse. 

    علي سبيل المثال، تتم أداره أعمده معلومات السعر بواسطة Supply Chain Management. تشتمل Supply Chain Management علي اتفاقيات تجاره يمكن ان تستفيد منها Field Service. تاتي الاعمده مثل **سعر الوحدة** و **الخصم** و **المبلغ الصافي** من Supply Chain Management فقط. للتاكد من مزامنة السعر مع Field Service، يجب استخدام ميزه **المزامنة** في صفحات **أمر الشراء** و **المنتجات الخاصة بامر الشراء** في Dataverse عند إدخال بيانات أمر الشراء. لمزيد من المعلومات، راجع [المزامنة مع بيانات التدبير عند الطلب Dynamics 365 Supply Chain Management](#sync-procurement).

+ لا يتوفر عمود **الإجماليات** الا في Field Service، نظرا لعدم وجود إجماليات محدثه لأمر الشراء في Supply Chain Management. يتم حساب الإجماليات في Supply Chain Management استنادا إلى معلمات متعددة غير متوفرة في Field Service.
+ بنود أمر الشراء التي يتم فيها تحديد فئة تدبير فقط، أو حيث يكون المنتج الذي تم تحديده هو أحد أصناف نوع منتج *الخدمة* أو نوع منتج Field Service، يمكن البدء فقط في Supply Chain Management. ثم تتم مزامنة البنود مع Dataverse وتكون مرئية في Field Service.
+ إذا تم تثبيت Field Service فقط، وليست Supply Chain Management، فان عمود **المستودع** يكون إلزاميا في أمر الشراء. ومع ذلك ، في حاله تثبيت Supply Chain Management، يتم إيقاف هذا المتطلب، وذلك لان Supply Chain Management تسمح ببنود أمر الشراء حيث لم يتم تحديد اي مستودع في مواقف معينه.
+ تتم أداره إيصالات استلام المنتجات (عمليات استلام طلبات شراء الشراء Dataverse) من قبل Supply Chain Management ولا يمكن إنشاؤها من Dataverse حاله تثبيت Supply Chain Management. تتم مزامنة إيصالات استلام المنتجات من Supply Chain Management من Supply Chain Management إلى Dataverse.
+ يتم السماح بالتسليم بالنقص في Supply Chain Management. يضيف الحل OneFSSCM المنطق بحيث يتم إنشاء أو تحديث بند إيصال استلام المنتجات (أو منتج استلام أمر شراء في Dataverse)، ويتم إنشاء صف دفتر يوميه المخزون في Dataverse لتعديل الكمية المتبقية التي يتم ترتيبها في سيناريوهات التسليم.

## <a name="unsupported-scenarios"></a>السيناريوهات غير المدعومة

+ تمنع Field Service أضافه البنود إلى أمر شراء ملغي في Supply Chain Management. وكحل بديل، يمكنك تغيير حاله النظام الخاصة بامر الشراء في Field Service، ثم أضافه البند الجديد في اما Field Service أو Supply Chain Management.
+ علي الرغم من ان صفوف التدبير تؤثر علي مستويات المخزون في كلا النظامين، فان هذا التكامل لا يضمن محاذاة المخزون عبر Supply Chain Management وField Service. تشتمل كلا من Field Service وSupply Chain Management علي عمليات أخرى تقوم بتحديث مستويات المخزون. وتكون هذه العمليات خارج نطاق التدبير.

## <a name="status-management"></a>أداره الحالة

تختلف حالات أوامر الشراء في Field Service عن الحالات الخاصة بـ Supply Chain Management.

### <a name="field-service-purchase-order-and-purchase-order-product-statuses"></a>حالات منتجات أمر الشراء وأمر الشراء لـ Field Service

| الراس – حاله النظام | الرأس - حالة الموافقة | حالة الصنف |
|---|---|---|
| <ul><li>مبدئي‬</li><li>‏‫مُرسل</li><li>مُلغاة</li><li>تم استلام المنتج</li><li>تمت فوترته</li></ul> | <ul><li>قيمة خالية</li><li>تمت الموافقة عليها</li><li>مرفوض</li></ul> | <ul><li>معلّق</li><li>تم الاستلام</li><li>مُلغاة</li></ul> |

### <a name="supply-chain-management-purchase-order-and-purchase-order-line-statuses"></a>Supply Chain Management أوامر الشراء وحالات سطر أمر الشراء

تكون حالات اعتماد البنود نشطه فقط عندما يكون هناك سير عمل بند.

| الراس – حاله المستندات | الرأس - حالة الموافقة | حالة السطر | حالة موافقة البند |
|---|---|---|---|
| <ul><li>أمر مفتوح (أمر متاخر)</li><li>تم الاستلام</li><li>مفوتر</li><li>مُلغاة</li></ul> | <ul><li>مبدئي‬</li><li>قيد المراجعة</li><li>تمت الموافقة عليها</li><li>مرفوض</li><li>في مراجعة خارجية</li><li>تاريخ التأكيد</li><li>تم الانتهاء</li></ul> | <ul><li>أمر مفتوح (أمر متاخر)</li><li>تم الاستلام</li><li>مفوتر</li><li>مُلغاة</li></ul> | <ul><li>غير مرسل</li><li>قيد المراجعة</li><li>تمت الموافقة عليها</li><li>مرفوض</li></ul> |

يتم تطبيق القواعد التالية علي أعمده الحالة:

+ لا يمكن تحديث الحالة في Supply Chain Management من Field Service. ومع ذلك، في بعض الحالات، سيتم تحديث الحالة في Field Service عند تغيير حاله أمر الشراء في Supply Chain Management.
+ إذا كان أمر الشراء في Supply Chain Management ضمن أداره التغييرات، وكان هناك تغيير تتم معالجته، تكون حاله الاعتماد هي *مسودة* أو *قيد المراجعة*. في هذه الحالة، سيتم تعيين حاله الموافقة الخاصة بـ Field Service إلى *قيمه خاليه*.
+ في حاله تعيين حاله الموافقة علي أمر الشراء في Supply Chain Management إلى *معتمد*، *في المراجعة الخارجية* أو *المؤكدة* أو *المنتهية*، سيتم تعيين حاله الموافقة علي أمر شراء Field Service إلى *معتمد*.
+ في حاله تعيين حاله الموافقة علي أمر الشراء في Supply Chain Management إلى *مرفوض*، سيتم تعيين حاله الموافقة علي أمر شراء Field Service إلى *مرفوض*.
+ إذا تم تغيير حاله راس المستند في Supply Chain Management إلى *أمر مفتوح (أمر متاخر)*، وكانت حاله أمر الشراء لـ Field Service هي *مسودة* أو *ملغي*، سيتم تغيير حاله أمر الشراء الخاص بـ Field Service إلى تم *الإرسال*.
+ إذا تم تغيير حاله راس المستند في Supply Chain Management إلى تم *إلغاء*، وكانت إيه منتجات إيصال أمر شراء في Field Service مرتبطة بامر الشراء (بالاضافه إلى منتجات أوامر الشراء)، يتم تعيين حاله نظام Field Service علي *ملغي*.
+ إذا تم إلغاء حاله سطر أمر الشراء في *Supply Chain Management*، يتم تعيين حاله منتج أمر الشراء في Field Service علي القيمة *الملغية*. بالاضافه إلى ذلك ، إذا تم تغيير حاله سطر أمر الشراء في Supply Chain Management من *ملغى* إلى *الأمر المتأخر*، يتم تعيين حاله صنف منتج أمر الشراء في Field Service علي *معلق*.

## <a name="sync-with-the-supply-chain-management-procurement-data-on-demand"></a><a id="sync-procurement"></a>مزامنة بيانات التدبير لـ Supply Chain Management حسب الطلب

تشتمل Supply Chain Management علي بيانات التدبير التي تعالج الاتفاقيات التجارية والخصومات والسيناريوهات الأخرى التي تعتمد علي العمليات الثانوية في Supply Chain Management. يستخدم محرك التدبير قواعد معقدة لتحديد أفضل سعر لأمر شراء معين. عند استخدام الكتابة الثنائية، لا يتم دائما الاحتفاظ بالبيانات متزامنة خلال البيئتين ، وخاصه في السيناريوهات التي تم فيها إنشاء الصف أو Dataverse تحديثه من ويمكنه تشغيل عمليات التتبع في Supply Chain Management

## <a name="sync-the-procurement-data-from-supply-chain-management"></a>مزامنة بيانات التدبير من Supply Chain Management

1. في Dataverse، انتقل إلى **المخزون \> أمر الشراء**.
2. حدد **جديد** لإنشاء أمر شراء جديد، أو حدد صفًا لأمر شراء موجود.
3. من أمر الشراء أو بند أمر الشراء.
4. في جزء الإجراءات، حدد **مزامنة**.

تتم مزامنة كافة الاعمده من Dataverse وField Service التي تتم مشاركتها من خلال Supply Chain Management.

فيما يلي المواقف التي قد تستخدم فيها وظيفة **المزامنة**:

- إذا قمت باجراء عده تغييرات متتابعة في نفس الصف من Dataverse، قم بتشغيل وظيفة **المزامنة**.
- إذا لم تكن متاكدا مما إذا كان التغيير قد يكون هو التغيير المتتالي الثاني من Dataverse، فقد يكون من المنطقي تشغيل وظيفة **المزامنة**.
- في حاله ظهور رسالة خطا حول تحديث قيمه من Supply Chain Management، قم بتشغيل وظيفة **المزامنة**، ثم أعد محاولة اجراء التحديث في Dataverse.

## <a name="cancelling-the-posting-process"></a>إلغاء عمليه الترحيل

في حاله إلغاء عمليه ترحيل إيصال استلام المنتجات اثناء المعالجة، فقد يؤدي الكتابة المزدوجة إلى إنشاء صف إيصال استلام المنتجات في  Dataverse، ولكن لا يتم إنشاء صف إيصال استلام المنتجات في Supply Chain Management. يحدث هذا الموقف نظرا لان الكتابة الثنائية لا تدعم المعاملات الموزعة.

## <a name="templates"></a>القوالب

تتوفر القوالب التالية لتكامل المستندات ذات الصلة بالتدبير.

| Supply Chain Management | Field Service | الوصف |
|---|---|---|
| رأس أمر الشراء الإصدار 2 | msdyn\_Purchaseorders | يحتوي هذا الجدول علي الاعمده التي تمثل البيانات الرئيسية لأمر الشراء. |
| كيان بند أمر شراء | msdyn\_PurchaseOrderProducts | يحتوي هذا الجدول علي الصفوف التي تمثل سطور أمر الشراء. يتم استخدام رقم المنتج للمزامنة. وهذا يعرف المنتج علي انه وحده احتفاظ بالمخزون (SKU) ، بما في ذلك ابعاد المنتج. لمزيد من المعلومات حول تكامل المنتج مع Dataverse، راجع [تجربه المنتج الموحدة](product-mapping.md). |
| رأس إيصال استلام المنتج | msdyn\_purchaseorderreceipts | يحتوي هذا الجدول علي رؤوس إيصال استلام المنتجات التي يتم إنشاؤها عند ترحيل إيصال استلام المنتجات في Supply Chain Management. |
| سطر إيصال استلام المنتج | msdyn\_purchaseorderreceiptproducts | يحتوي هذا الجدول علي سطور إيصال استلام المنتجات التي يتم إنشاؤها عند ترحيل إيصال استلام المنتجات في Supply Chain Management. |
| الكيان المحذوف المبدئي لبند أمر الشراء | msdyn\_purchaseorderproducts | يحتوي هذا الجدول علي معلومات حول بنود أمر الشراء التي تم حذفها بالحالات المبدئية. يمكن حذف بند أمر شراء في Supply Chain Management فقط عند تاكيد أمر الشراء أو اعتماده ، في حاله تشغيل أداره التغييرات. الصف موجود في قاعده بيانات Supply Chain Management وتم وضع علامة عليه علي انه **IsDeleted**. وبسبب Dataverse عدم وجود مفهوم للحذف السهل، فمن المهم ان تتم مزامنة هذه المعلومات مع Dataverse. وبهذه الطريقة، يمكن حذف البنود التي تم حذفها بشكل تلقائي في Supply Chain Management من Dataverse. في هذه الحالة، يتم وضع المنطق الخاص بحذف أحد البنود في Dataverse في Supply Chain Management الموسعة. |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Currency](includes/productreceiptheader-msdyn-purchaseorderreceipts.md)]

[!include [Currency](includes/productreceiptline-msdyn-purchaseorderreceiptproducts.md)]

[!include [Currency](includes/purchaseorderheadersv2-msdyn-purchaseorders.md)]

[!include [Currency](includes/purchaseorderlinesoftdeletedtable-msdyn-purchaseorderproducts.md)]

[!include [Currency](includes/purchaseorderlinetable-msdyn-purchaseorderproducts.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]