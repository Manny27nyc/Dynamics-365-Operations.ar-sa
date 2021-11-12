---
title: تكوين رؤية المخزون
description: يصف هذا الموضوع كيفية تكوين رؤية المخزون.
author: yufeihuang
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 53cc457c788d24adfe3c523719ccffc6d445fb61
ms.sourcegitcommit: 1e5a46271bf7fae2f958d2b1b666a8d2583e04a8
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 10/25/2021
ms.locfileid: "7678461"
---
# <a name="configure-inventory-visibility"></a>تكوين رؤية المخزون

[!include [banner](../includes/banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

يوضح هذا الموضوع كيفية تكوين رؤية المخزون باستخدام تطبيق رؤية المخزون في Power Apps.

## <a name="introduction"></a><a name="introduction"></a>مقدمة

قبل البدء في العمل مع "رؤية المخزون"، يجب إكمال التكوين التالي كما هو موضح في هذا الموضوع:

- [تكوين مصدر البيانات](#data-source-configuration)
- [تكوين التقسيم](#partition-configuration)
- [تكوين التسلسل الهرمي لمؤشر المنتج](#index-configuration)
- [تكوين الحجز (اختياري)](#reservation-configuration)
- [نموذج التكوين الافتراضي](#default-configuration-sample)

## <a name="prerequisites"></a>المتطلبات الأساسية

قبل البدء، قم بتثبيت وإعداد الوظيفة الإضافية لرؤية المخزون كما هو موضح في [تثبيت وإعداد رؤية المخزون](inventory-visibility-setup.md).

## <a name="enable-inventory-visibility-features-in-power-apps-feature-management"></a><a name="feature-switch"></a>تمكين ميزات رؤية المخزون في إدارة ميزات Power Apps

تضيف الوظيفة الإضافية لرؤية المخزون العديد من الميزات الجديدة إلى تثبيت Power Apps الخاص بك. بشكل افتراضي، تكون هذه الميزات متوقفة عن التشغيل. لاستخدامها، افتح صفحة **التكوين** في Power Apps، ثم في علامة التبويب **إدارة الميزات**، قم بتشغيل الميزات التالية.

- *OnHandReservation*
- *OnHandMostSpecificBackgroundService*

## <a name="find-the-service-endpoint"></a><a name="get-service-endpoint"></a>البحث عن نقطة نهاية الخدمة

إذا لم تكن تعرف نقطة نهاية خدمة رؤية المخزون الصحيحة، فافتح صفحة **التكوين** في Power Apps، ثم حدد **إظهار نقطة نهاية الخدمة** في الزاوية العلوية اليمنى. ستظهر الصفحة نقطة نهاية الخدمة الصحيحة.

## <a name="the-configuration-page-of-the-inventory-visibility-app"></a><a name="configuration"></a>صفحة تكوين تطبيق رؤية المخزون

في Power Apps، تساعدك صفحة **التكوين** في [تطبيق رؤية المخزون](inventory-visibility-power-platform.md) في إعداد التكوين الحالي وتكوين الحجز المرن. بعد تثبيت الوظيفة الإضافية، يتضمن التكوين الافتراضي القيمة من Microsoft Dynamics 365 Supply Chain Management (مصدر بيانات `fno`). يمكنك مراجعة الإعدادات الافتراضية. بالإضافة إلى ذلك، استنادا إلى متطلبات العمل ومتطلبات ترحيل المخزون للنظام الخارجي، يمكنك تعديل التكوين لتوحيد الطريقة التي يمكن بها ترحيل تغييرات المخزون وتنظيمها والاستعلام عنها عبر الأنظمة المتعددة. توضح الأقسام المتبقية من هذا الموضوع كيفية استخدام كل جزء من صفحة **التكوين**.

بعد اكتمال التكوين، تأكد من تحديد **تحديث التكوين** في التطبيق.

## <a name="data-source-configuration"></a>تكوين مصدر البيانات

يمثل كل مصدر بيانات نظامًا تأتي منه بياناتك. ويتضمن مثال أسماء مصادر البيانات `fno` (وهو ما يعني "تطبيقات Dynamics 365 Finance and Operations") و`pos` (وتعني "نقطة البيع"). افتراضيًا، يتم إعداد Supply Chain Management كمصدر بيانات افتراضي ( `fno`) في رؤية المخزون.

> [!NOTE]
> مصدر بيانات `fno` محجوز لـ Dynamics 365 Supply Chain Management.

لإضافة مصدر بيانات، اتبع هذه الخطوات.

1. قم بتسجيل الدخول إلى بيئة Power Apps الخاصة بك، وافتح **رؤية المخزون**.
1. افتح صفحة **التكوين**.
1. في علامة التبويب **مصدر البيانات**، حدد **مصدر بيانات جديد** لإضافة مصدر بيانات.

> [!NOTE]
> عند إضافة مصدر بيانات، تأكد من التحقق من صحة اسم مصدر البيانات ومقاييسه الفعلية وتعيينات الأبعاد قبل تحديث التكوين لخدمة "رؤية المخزون". لن تتمكن من تعديل هذه الإعدادات بعد تحديد **تحديث التكوين**.

يتضمن تكوين مصدر البيانات الأجزاء التالية:

- الأبعاد (تعيين البعد)
- القياسات المادية
- القياسات المحسوبة

### <a name="dimensions-dimension-mapping"></a><a name="data-source-configuration-dimension"></a>الأبعاد (تعيين البعد)

الغرض من تكوين الأبعاد هو توحيد التكامل متعدد الأنظمة لترحيل الأحداث والاستعلامات، بناءً على مجموعات الأبعاد. توفر رؤية المخزون قائمة بالأبعاد الأساسية التي يمكن تعيينها من أبعاد مصدر البيانات. ثلاثة وثلاثون بعدًا متاحًا للتعيين.

- بشكل افتراضي، إذا كنت تستخدم Supply Chain Management كأحد مصادر البيانات الخاصة بك، فسيتم تعيين 13 بُعدًا إلى أبعاد Supply Chain Management القياسية. يتم تعيين اثني عشر بُعدًا آخر (`inventDimension1` حتى `inventDimension12`) إلى أبعاد مخصصة في Supply Chain Management. أما الأبعاد الثمانية المتبقية فهي أبعاد ممتدة يمكنك تعيينها إلى مصادر بيانات خارجية.
- إذا لم تستخدم Supply Chain Management كأحد مصادر البيانات، يمكنك تعيين الأبعاد بحرية. يعرض الجدول التالي القائمة الكاملة للأبعاد المتوفرة.

> [!NOTE]
> إذا لم يكن البعد في قائمة الأبعاد الافتراضية، وكنت تستخدم مصدر بيانات خارجي، نوصيك باستخدام `ExtendedDimension1` حتى `ExtendedDimension8` للقيام بالتعيين.

| نوع البعد | البُعد الأساسي |
|---|---|
| منتج | `ColorId` |
| منتج | `SizeId` |
| منتج | `StyleId` |
| منتج | `ConfigId` |
| التعقب | `BatchId` |
| التعقب | `SerialId` |
|  الموق | `LocationId` |
|  الموق | `SiteId` |
| حالة المخزون | `StatusId` |
| خاص بالمستودع | `WMSLocationId` |
| خاص بالمستودع | `WMSPalletId` |
| خاص بالمستودع | `LicensePlateId` |
| غير ذلك | `VersionId` |
| المخزون (مخصص) | `InventDimension1` حتى `InventDimension12` |
| ملحق | `ExtendedDimension1` حتى `ExtendedDimension8` |
| النظام | `Empty` |

> [!NOTE]
> أنواع الأبعاد المسردة في الجدول السابق هي للإشارة فقط. ليس عليك تعريفها في "رؤية المخزون".
>
> قد يتم حجز أبعاد المخزون (المخصصة) لـ Supply Chain Management. في هذه الحالة، يمكنك استخدام الأبعاد الموسعة بدلا من ذلك.

يمكن للأنظمة الخارجية الوصول إلى رؤية المخزون من خلال واجهات برمجة التطبيقات RESTful الخاصة بها. بالنسبة للتكامل، تتيح لك رؤية المخزون تكوين _مصدر البيانات الخارجي_ وتعيين من _الأبعاد الخارجية_ إلى _الأبعاد الأساسية_. فيما يلي مثال على جدول تعيين الأبعاد.

| البعد الخارجي | البُعد الأساسي |
|---|---|
| `MyColorId` | `ColorId` |
| `MySizeId` | `SizeId` |
| `MyStyleId` | `StyleId` |
| `MyDimension1` | `ExtendedDimension1` |
| `MyDimension2` | `ExtendedDimension2` |

عن طريق تكوين تعيين البعد، يمكنك إرسال الأبعاد الخارجية مباشرة إلى "رؤية المخزون". ستقوم رؤية المخزون بعد ذلك بتحويل الأبعاد الخارجية تلقائيا إلى أبعاد أساسية.

لإضافة تعيينات الأبعاد، اتبع هذه الخطوات.

1. قم بتسجيل الدخول إلى بيئة Power Apps الخاصة بك، وافتح **رؤية المخزون**.
1. افتح صفحة **التكوين**.
1. في علامة التبويب **مصدر البيانات**، في قسم **تعيينات الأبعاد**، حدد **إضافة** لإضافة تعيينات الأبعاد.
    ![إضافة تعيينات الأبعاد](media/inventory-visibility-dimension-mapping.png "إضافة تعيينات الأبعاد")

1. في حقل **اسم البعد**، حدد بعد المصدر.
1. في حقل **إلى البعد الأساسي**، حدد البعد في رؤية المخزون الذي تريد تعيينه.
1. حدد **حفظ**.

على سبيل المثال، إذا كان مصدر البيانات يتضمن بعد لون منتج، يمكنك تعيينه إلى بعد أساس `ColorId` لإضافة بعد مخصص `ProductColor` في مصدر بيانات `exterchannel`. بعد ذلك، يتم تعيينها إلى بعد أساس `ColorId`.

### <a name="physical-measures"></a>القياسات المادية

عندما يقوم مصدر بيانات بنشر تغيير المخزون إلى "رؤية المخزون"، فإنه يقوم بنشر هذا التغيير باستخدام *مقاييس فعلية*. تقوم المقاييس الفعلية بتعديل الكمية وتعكس حالة المخزون. يمكنك تحديد التدابير المادية الخاصة بك، استنادا إلى الاحتياجات الخاصة بك. يمكن أن تستند الاستعلامات إلى التدابير الفعلية.

توفر رؤية المخزون قائمة بالمقاييس المادية الافتراضية المرتبطة بـ Supply Chain Management (مصدر بيانات `fno`). يتم أخذ هذه التدابير الفعلية الافتراضية من حالات حركة المخزون في صفحة **القائمة المتاحة**  في Supply Chain Management (**إدارة المخزون \> الاستعلامات والتقرير \> القائمة المتاحة**). يقدم الجدول التالي مثالا للمقاييس المادية.

| اسم القياس المادي | الوصف |
|---|---|
| `NotSpecified` | غير محدد |
| `Arrived` | الوصول |
| `AvailOrdered` | متوفر ومطلوب |
| `AvailPhysical` | الفعلي المتاح |
| `Deducted` | مخفض |
| `OnOrder` | OnOrder |
| `Ordered` | مطلوبة |
| `PhysicalInvent` | المخزون الفعلي |
| `Picked` | المستلَم |
| `PostedQty` | الكمية التي تم ترحيلها |
| `QuotationIssue` | إصدار عرض الأسعار |
| `QuotationReceipt` | إيصال عرض الأسعار |
| `Received` | مستلَم‬ |
| `Registered` | مسجّل |
| `ReservOrdered` | الكمية المطلوبة المحجوزة |
| `ReservPhysical` | المحتجز الفعلي |

إذا كان مصدر البيانات هو Supply Chain Management، فلن تضطر إلى إعادة إنشاء المقاييس المادية الافتراضية. ومع ذلك، بالنسبة لمصادر البيانات الخارجية، يمكنك إنشاء مقاييس فعلية جديدة باتباع الخطوات التالية.

1. قم بتسجيل الدخول إلى بيئة Power Apps الخاصة بك، وافتح **رؤية المخزون**.
1. افتح صفحة **التكوين**.
1. في علامة التبويب **مصدر البيانات**، في قسم **المقاييس الفعلية**، حدد **إضافة**، حدد اسم مقياس مصدر، واحفظ التغييرات.

### <a name="calculated-measures"></a>القياسات المحسوبة

يمكنك استخدام "رؤية المخزون" للاستعلام عن كل من المقاييس الفعلية للمخزون و *المقاييس المحسوبة المخصصة*. توفر المقاييس المحسوبة صيغة حساب مخصصة تتكون من مجموعة من التدابير المادية. تتيح لك هذه الوظيفة تحديد مجموعة من المقاييس المادية التي سيتم إضافتها، و/أو مجموعة من المقاييس المادية التي سيتم طرحها، لتشكيل القياس المخصص.

يتيح لك التكوين تحديد مجموعة من المعدلات التي تمت إضافتها أو طرحها للحصول على إجمالي كمية الإخراج المجمعة.

لإعداد مقياس محسوب مخصص، اتبع هذه الخطوات.

1. قم بتسجيل الدخول إلى بيئة Power Apps الخاصة بك، وافتح **رؤية المخزون**.
1. افتح صفحة **التكوين**.
1. في علامة التبويب **القياس المحسوب**، حدد **قياس حساب جديد** لإضافة قياس محسوب. ثم قم بتعيين الحقول كما هو موضح في الجدول التالي.

    | الحقل | قيمة |
    |---|---|
    | اسم قياس محسوب جديد | أدخل اسم القياس المحسوب. |
    | مصدر البيانات | نظام الاستعلام هو مصدر بيانات. |
    | مصدر بيانات المعدّل | أدخل مصدر البيانات للمعدِّل. |
    | المعدّل | أدخل اسم المعدل. |
    | نوع المعدّل | حدد نوع المعدل (*الجمع* أو *الطرح*). |

على سبيل المثال، لديك نتيجة الاستعلام التالية.

```json
[
    {
        "productId": "T-shirt",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red"
        },
        "quantities": {
            "pos": {
                "inbound": 80.0,
                "outbound": 20.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "externalchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            }
        }
    }
]
```

يمكنك بعد ذلك تكوين مقياس محسوب يسمى `MyCustomAvailableforReservation`، كما هو موضح في الجدول التالي. وسيستهلك نظام الاستهلاك هذا التدبير المحسوب.

| نظام الاستهلاك | القياس المحسوب | مصدر البيانات | القياس المادي | نوع الحساب |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `pos` | `inbound` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `pos` | `outbound` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `received` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `scheduled` | `Addition` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `issued` | `Subtraction` |
| `CustomChannel` | `MyCustomAvailableforReservation` | `externalchannel` | `reserved` | `Subtraction` |

عند استخدام صيغة الحساب هذه، ستتضمن نتيجة الاستعلام الجديدة القياس المخصص.

```json
[
    {
        "productId": "T-shirt",
        "dimensions": {
            "SiteId": "1",
            "LocationId": "11",
            "ColorId": "Red"
        },
        "quantities": {
            "pos": {
                "inbound": 80.0,
                "outbound": 20.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "externalchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

إخراج `MyCustomAvailableforReservation`، بناءً على إعداد الحساب في القياسات المخصصة، هو 100 + 50 – 10 + 80 – 20 + 90 + 30 – 60 – 40 = 220.

## <a name="partition-configuration"></a><a name="partition-configuration"></a>تكوين التقسيم

يتكون تكوين القسم من مجموعة من الأبعاد الأساسية. وهو يحدد نمط توزيع البيانات. تدعم عمليات البيانات في نفس القسم الأداء العالي ولا تكلف الكثير. لذلك، يمكن أن تساهم أنماط التقسيم الجيدة في فوائد كبيرة.

توفر رؤية المخزون تكوين القسم الافتراضي التالي.

| البُعد الأساسي | التدرج الهرمي |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |

> [!NOTE]
> تكوين القسم الافتراضي هو للرجوع إليه فقط. ليس عليك تعريفها في "رؤية المخزون". حاليا، ترقية تكوين القسم غير مدعومة.

## <a name="product-index-hierarchy-configuration"></a><a name="index-configuration"></a>تكوين التسلسل الهرمي لمؤشر المنتج

في معظم الأحيان، لن يكون الاستعلام الفعلي للمخزون فقط عند أعلى مستوى "إجمالي". بدلا من ذلك، قد ترغب أيضا في مشاهدة النتائج التي يتم تجميعها استنادا إلى أبعاد المخزون.

توفر رؤية المخزون المرونة من خلال السماح لك بإعداد _الفهارس_. تستند هذه الفهارس إلى بعد أو مجموعة أبعاد. يتكون الفهرس من *تعيين رقم*، و *بعد*، و *تدرج هرمي*، كما هو محدد في الجدول التالي.

| الاسم | الوصف |
|---|---|
| تعيين الرقم | سيتم تجميع الأبعاد التي تنتمي إلى نفس المجموعة (الفهرس) معًا، وسيتم تخصيص نفس الرقم المحدد لها. |
| البعد | الأبعاد الأساسية التي يتم تجميع نتيجة الاستعلام عليها. |
| التدرج الهرمي | يتم استخدام التدرج الهرمي لتحديد مجموعات الأبعاد المدعومة التي يمكن الاستعلام عنها. على سبيل المثال، يمكنك إعداد مجموعة أبعاد لها تسلسل هرمي لـ `(ColorId, SizeId, StyleId)`. في هذه الحالة، يدعم النظام الاستعلامات على تركيبات الأبعاد الأربعة. المجموعة الأولى فارغة، والثانية هي `(ColorId)`، والثالثة هي `(ColorId, SizeId)`، والرابعة هي `(ColorId, SizeId, StyleId)`. المجموعات الأخرى غير مدعومة. لمزيد من المعلومات، راجع المثال التالي. |

لإعداد فهرس التسلسل الهرمي للمنتج، اتبع هذه الخطوات.

1. قم بتسجيل الدخول إلى بيئة Power Apps الخاصة بك، وافتح **رؤية المخزون**.
1. افتح صفحة **التكوين**.
1. في علامة التبويب **فهرس التدرج الهرمي للمنتج**، في قسم **تعيينات الأبعاد**، حدد **إضافة** لإضافة تعيينات الأبعاد.
1. بشكل افتراضي، يتم توفير قائمة الفهارس. لتعديل فهرس موجود، حدد **تحرير** أو **إضافة** في القسم للفهرس ذي الصلة. لإنشاء مجموعة فهرس جديدة، حدد **مجموعة فهرس جديدة**. لكل صف في كل مجموعة فهرس، في حقل **البعد**، حدد من قائمة الأبعاد الأساسية. يتم إنشاء قيم الحقول التالية تلقائيا:

    - **تعيين رقم** – سيتم تجميع الأبعاد التي تنتمي إلى نفس المجموعة (الفهرس) معا، وسيتم تخصيص نفس رقم المجموعة لها.
    - **التسلسل الهرمي** – يتم استخدام التدرج الهرمي لتعريف مجموعات الأبعاد المدعومة التي يمكن الاستعلام عنها في مجموعة أبعاد (فهرس). على سبيل المثال، إذا قمت بإعداد مجموعة أبعاد لها تسلسل هرمي *للنمط* و *اللون* و *الحجم*، فإن النظام يدعم نتيجة مجموعات الاستعلام الثلاث. المجموعة الأولى هي النمط فقط. المجموعة الثانية هي مزيج من نمط واللون. والمجموعة الثالثة هي مزيج من النمط واللون والحجم. المجموعات الأخرى غير مدعومة.

### <a name="example"></a>مثال

يقدم هذا القسم مثالا يوضح كيفية عمل التسلسل الهرمي.

يوفر الجدول التالي قائمة بالمخزون المتوفر لهذا المثال.

| الصنف | ColorId | SizeId | StyleId | الكمية |
|---|---|---|---|---|
| القميص | أسود | صغير | عريض | 1 |
| القميص | أسود | صغير | عادي | 2 |
| القميص | أسود | كبير | عريض | 3 |
| القميص | أسود | كبير | عادي | 4 |
| القميص | أحمر | صغير | عريض | 5 |
| القميص | أحمر | صغير | عادي | 6 |
| القميص | أحمر | كبير | عادي | 7 |

يوضح الجدول التالي كيفية إعداد التسلسل الهرمي للفهرس.

| تعيين الرقم | البعد | التدرج الهرمي |
|---|---|---|
| 1 | `ColorId` | 1 |
| 1 | `SizeId` | 2 |
| 1 | `StyleId` | 3 |

يتيح الفهرس الاستعلام عن المخزون الفعلي بالطرق التالية:

- `()` – مجمعة من قبل الجميع

    - قميص، 28

- `(ColorId)` – مجمعة بواسطة `ColorId`

    - قيمص، أسود، 10
    - قميص، أحمر، 18

- `(ColorId, SizeId)` – مجمعة حسب مزيج من `ColorId` و`SizeId`

    - قيمص، أسود، صغير، 3
    - قيمص، أسود، كبير، 7
    - قيمص، أحمر، صغير، 11
    - قيمص، أحمر، كبير، 7

- `(ColorId, SizeId, StyleId)` – مجمعة حسب مزيج من `ColorId`، و`SizeId`، و`StyleId`

    - قيمص، أسود، صغير، عريض، 1
    - قيمص، أسود، صغير، عادي، 2
    - قيمص، أسود، كبير، عريض، 3
    - قيمص، أسود، كبير، عادي، 4
    - قيمص، أحمر، صغير، عريض، 5
    - قيمص، أحمر، صغير، عادي، 6
    - قيمص، أحمر، كبير، عادي، 7

> [!NOTE]
> يجب عدم تعريف الأبعاد الأساسية التي تم تعريفها في تكوين القسم في تكوينات الفهرس.
> 
> إذا كان من الضروري الاستعلام فقط عن المخزون الذي تم تجميعه بواسطة كافة مجموعات الأبعاد، فيمكنك إعداد فهرس مفرد يحتوي على البعد الأساسي `Empty`.

## <a name="reservation-configuration-optional"></a><a name="reservation-configuration"></a>تكوين الحجز (اختياري)

يلزم تكوين الحجز إذا كنت ترغب في استخدام ميزة الحجز الناعمة. يتكون التكوين من جزأين أساسيين:

- تعيين حجز مرن
- تدرج هرمي للحجز المرن

### <a name="soft-reservation-mapping"></a>تعيين حجز مرن

عند إجراء الحجز، قد ترغب في معرفة ما إذا كان المخزون الفعلي متاحا حاليا للحجز. يتم ربط التحقق من الصحة إلى مقياس محسوب يمثل صيغة حساب مجموعة من التدابير الفعلية.

من خلال إعداد التعيين من المقياس الفعلي إلى المقياس المحسوب، يمكنك تمكين خدمة "رؤية المخزون" من التحقق تلقائيا من توفر الحجز، استنادا إلى المقياس الفعلي.

قبل إعداد هذا التعيين، يجب تعريف المقاييس الفعلية والمقاييس المحسوبة ومصادر البيانات الخاصة بها في علامات التبويب **مصدر البيانات** و **القياس المحسوب** لصفحة **التكوين** في Power Apps (كما هو موضح سابقا في هذا الموضوع).

لتعريف تعيين الحجز ناعمة اتبع الخطوات التالية.

1. تعريف المقياس المادي الذي يعمل كمقياس حجز مرن (على سبيل المثال، `SoftReservOrdered`).
1. في علامة التبويب **قياس محسوب** من صفحة **التكوين**، حدد المقياس المحسوب *المتاح للحجز* (AFR) الذي يحتوي على صيغة حساب AFR التي تريد تعيينها إلى المقياس الفعلي. على سبيل المثال، قد تقوم بإعداد `AvailableToReserve` (متوفر للحجز) بحيث يتم تعيينه إلى المقياس الفعلي `SoftReservOrdered` المعرف مسبقا. وبهذه الطريقة، يمكنك العثور على الكميات التي ستكون حالة مخزون `SoftReservOrdered` متوفرة للحجز. يوضح الجدول التالي صيغة حساب AFR.

    | نوع الحساب | مصدر البيانات | القياس المادي |
    |---|---|---|
    | الجمع | `fno` | `AvailPhysical` |
    | الجمع | `pos` | `Inbound` |
    | الطرح | `pos` | `Outbound` |
    | الطرح | `iv` | `SoftReservOrdered` |

    نوصي بإعداد القياس المحسوب بحيث يحتوي على المقياس الفعلي الذي يستند إليه مقياس الحجز. وبهذه الطريقة، ستتاثر كمية القياس المحسوب بكمية مقياس الحجز. بالتالي، في هذا المثال، يجب أن يحتوي مقياس `AvailableToReserve` المحسوب لمصدر البيانات `iv` على مقياس `SoftReservOrdered` الفعلي من `iv` كمكون.

1. افتح صفحة **التكوين**.
1. في علامة التبويب **تعيين الحجز المرن**، قم بإعداد التعيين من المقياس الفعلي إلى المقياس المحسوب. بالنسبة للمثال السابق، قد تستخدم الإعدادات التالية لتعيين `AvailableToReserve` إلى المقياس الفعلي `SoftReservOrdered` المعرف مسبقا.

    | مصدر بيانات القياسات الفعلية | القياس المادي | متاح لمصدر بيانات الحجز | متاح للقياس المحسوب للحجز |
    |---|---|---|---|
    | `iv` | `SoftReservOrdered` | `iv` | `AvailableToReserve` |

    > [!NOTE]
    > إذا لم تتمكن من تحرير علامة التبويب **تعيين الحجز المرن**، فقد يلزمك تشغيل ميزة *OnHandReservation* في علامة التبويب **إدارة الميزات**.

الآن، عند إجراء حجز على `SoftReservOrdered`، ستعثر رؤية المخزون تلقائيًا على `AvailableToReserve` وصيغة الحساب المرتبطة بها لإجراء التحقق من صحة الحجز.

على سبيل المثال، لديك المخزون الفعلي التالي في "رؤية المخزون".

```json
{
    "productId": "T-shirt",
    "dimensions": {
        "SiteId": "1",
        "LocationId": "11",
        "ColorId": "Red"
    },
    "quantities": {
        "iv": {
            "SoftReservOrdered": 90
        },
        "fno": {
            "availphysical": 70.0,
        },
        "pos": {
            "inbound": 50.0,
            "outbound": 20.0
        }
    }
}
```

في هذه الحالة، يتم تطبيق الحساب التالي:

`AvailableToReserve` = `fno.availphysical` + `pos.inbound` – `pos.outbound` – `iv.SoftReservOrdered`  
= 70 + 50 – 20 – 90  
= 10

لذلك، إذا حاولت إجراء حجوزات على `iv.SoftReservOrdered`، وكانت الكمية أقل من أو تساوي `AvailableToReserve` (10)، يمكنك إجراء الحجز.

> [!NOTE]
> عند استدعاء API للحجز، يمكنك التحكم في التحقق من صحة الحجز عن طريق تحديد المعلمة المنطقية `ifCheckAvailForReserv` في النص الأساسي للطلب. تعني القيمة `True` أن التحقق من الصحة مطلوب، بينما تعني القيمة `False` أن التحقق من الصحة غير مطلوب. القيمة الافتراضية هي `True`.

### <a name="soft-reservation-hierarchy"></a>تدرج هرمي للحجز المرن

يصف التسلسل الهرمي للحجز تسلسل الأبعاد التي يجب تحديدها عند إجراء الحجوزات. إنه يعمل بنفس الطريقة التي يعمل بها التسلسل الهرمي لفهرس المنتج للاستعلامات الفعلية.

التسلسل الهرمي للحجز مستقل عن التسلسل الهرمي لمؤشر المنتج. يتيح لك هذا الاستقلال تنفيذ إدارة الفئات حيث يمكن للمستخدمين تقسيم الأبعاد إلى تفاصيل لتحديد متطلبات إجراء حجوزات أكثر دقة. يجب أن يحتوي التدرج الهرمي للحجز المرن على `SiteId` و`LocationId` كمكونات، لأنه يقوم بإنشاء تكوين التقسيم. عند إجراء الحجز، يجب تحديد تقسيم للمنتج.

فيما يلي مثال على التسلسل الهرمي للحجز المرن.

| البُعد الأساسي | التدرج الهرمي |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |
| `ColorId` | 3 |
| `SizeId` | 4 |
| `StyleId` | 5 |

في هذا المثال، يمكنك الحجز في تسلسلات الأبعاد التالية. يجب تحديد تقسيم للمنتج عند الحجز. بالتالي، فان التدرج الهرمي الأساسي الذي يمكنك استخدامه هو `(SiteId, LocationId)`.

- `(SiteId, LocationId)`
- `(SiteId, LocationId, ColorId)`
- `(SiteId, LocationId, ColorId, SizeId)`
- `(SiteId, LocationId, ColorId, SizeId, StyleId)`

يجب أن يتبع تسلسل الأبعاد الصالح بدقة التسلسل الهرمي للحجز، البعد حسب البعد. على سبيل المثال، التسلسل الهرمي `(SiteId, LocationId, SizeId)` غير صالح، لأن `ColorId` مفقود.

## <a name="complete-and-update-the-configuration"></a>إكمال التكوين وتحديثه

بعد الانتهاء من التكوين، يجب عليك تنفيذ جميع التغييرات على رؤية المخزون. للقيام بالتغييرات، حدد **تحديث التكوين** في الزاوية العلوية اليسرى من صفحة **التكوين** في Power Apps.

في المرة الأولى التي تحدد فيها **تحديث التكوين**، يطلب النظام بيانات الاعتماد الخاصة بك.

- **معرف العميل** - معرف تطبيق Azure الذي قمت بإنشائه من أجل رؤية المخزون.
- **معرف المستأجر** - معرف مستأجر Azure الخاص بك.
- **سر العميل** - سر تطبيق Azure الذي قمت بإنشائه من أجل رؤية المخزون.

بعد تسجيل الدخول، يتم تحديث التكوين في خدمة "رؤية المخزون".

> [!NOTE]
> تأكد من التحقق من صحة اسم مصدر البيانات ومقاييسه الفعلية وتعيينات الأبعاد قبل تحديث التكوين لخدمة "رؤية المخزون". لن تتمكن من تعديل هذه الإعدادات بعد تحديد **تحديث التكوين**.

## <a name="default-configuration-sample"></a><a name="default-configuration-sample"></a>نموذج التكوين الافتراضي

أثناء مرحلة التهيئة الخاصة به، تقوم رؤية المخزون بإعداد تكوين افتراضي، والذي يتم توضيحه بالتفصيل هنا. يمكنك تعديل هذا التكوين كما تشاء.

### <a name="data-source-configuration"></a>تكوين مصدر البيانات

#### <a name="configuration-of-the-iv-data-source"></a>تكوين مصدر البيانات iv

يصف هذا القسم كيفية تكوين مصدر بيانات `iv`.

##### <a name="physical-measures-configured-for-the-iv-data-source"></a>القياسات الفعلية التي تم تكوينها لمصدر البيانات iv

يتم تكوين القياسات الفعلية التالية لمصدر بيانات `iv`:

- `Ordered`
- `SoftReservPhysical`
- `SoftReservOrdered`
- `ReservOrdered`
- `ReservPhysical`

##### <a name="orderedtotal-calculated-measure"></a>القياس المحسوب لـ OrderedTotal

يمكنك تكوين المقياس المحسوب لـ `OrderedTotal` لمصدر بيانات `iv` كما هو موضح في الجدول التالي.

| نوع الحساب | مصدر البيانات | القياس المادي |
|---|---|---|
| الجمع | `fno` | `Ordered` |
| الجمع | `fno` | `Arrived` |
| الجمع | `iv` | `Ordered` |

##### <a name="onhand-calculated-measure"></a>القياس المحسوب المتاح

يمكنك تكوين المقياس المحسوب لـ `OnHand` لمصدر بيانات `iv` كما هو موضح في الجدول التالي.

| نوع الحساب | مصدر البيانات | القياس المادي |
|---|---|---|
| الجمع | `fno` | `PhysicalInvent` |
| الجمع | `iom` | `OnHand` |
| الجمع | `erp` | `Unrestricted` |
| الجمع | `erp` | `QualityInspection` |
| الجمع | `pos` | `PosInbound` |
| الطرح | `pos` | `PosOutbound` |

##### <a name="reservedtotal-calculated-measure"></a>القياس المحسوب لـ ReservedTotal

يمكنك تكوين المقياس المحسوب لـ `ReservedTotal` لمصدر بيانات `iv` كما هو موضح في الجدول التالي.

| نوع الحساب | مصدر البيانات | القياس المادي |
|---|---|---|
| الجمع | `fno` | `ReservPhysical` |
| الجمع | `fno` | `ReservOrdered` |
| الجمع | `iv` | `SoftReservPhysical` |
| الجمع | `iv` | `SoftReservOrdered` |
| الجمع | `iv` | `ReservPhysical` |
| الجمع | `iv` | `ReservOrdered` |

##### <a name="softreserved-calculated-measure"></a>القياس المحسوب لـ SoftReserved

يمكنك تكوين المقياس المحسوب لـ `SoftReserved` لمصدر بيانات `iv` كما هو موضح في الجدول التالي.

| نوع الحساب | مصدر البيانات | القياس المادي |
|---|---|---|
| الجمع | `iv` | `SoftReservPhysical` |
| الجمع | `iv` | `SoftReservOrdered` |

##### <a name="hardreserved-calculated-measure"></a>القياس المحسوب لـ HardReserved

يمكنك تكوين المقياس المحسوب لـ `HardReserved` لمصدر بيانات `iv` كما هو موضح في الجدول التالي.

| نوع الحساب | مصدر البيانات | القياس المادي |
|---|---|---|
| الجمع | `fno` | `ReservPhysical` |
| الجمع | `fno` | `ReservOrdered` |
| الجمع | `iv` | `ReservPhysical` |
| الجمع | `iv` | `ReservOrdered` |

##### <a name="openorder-calculated-measure"></a>القياس المحسوب لـ OpenOrder

يمكنك تكوين المقياس المحسوب لـ `OpenOrder` لمصدر بيانات `iv` كما هو موضح في الجدول التالي.

| نوع الحساب | مصدر البيانات | القياس المادي |
|---|---|---|
| الجمع | `fno` | `OnOrder` |
| الجمع | `iom` | `OnOrder` |

##### <a name="onhandavailable-calculated-measure"></a>المقياس المحسوب لـ OnHandAvailable

يمكنك تكوين المقياس المحسوب لـ `OnHandAvailable` لمصدر بيانات `iv` كما هو موضح في الجدول التالي.

| نوع الحساب | مصدر البيانات | القياس المادي |
|---|---|---|
| الجمع | `fno` | `PhysicalInvent` |
| الجمع | `iom` | `OnHand` |
| الجمع | `erp` | `Unrestricted` |
| الجمع | `erp` | `QualityInspection` |
| الجمع | `pos` | `PosInbound` |
| الطرح | `fno` | `ReservPhysical` |
| الطرح | `iv` | `SoftReservPhysical` |
| الطرح | `pos` | `PosOutbound` |

##### <a name="availabletoreserve-calculated-measure"></a>المقياس المحسوب لـ AvailableToReserve

يمكنك تكوين المقياس المحسوب لـ `AvailableToReserve` لمصدر بيانات `iv` كما هو موضح في الجدول التالي.

| نوع الحساب | مصدر البيانات | القياس المادي |
|---|---|---|
| الجمع | `fno` | `PhysicalInvent` |
| الجمع | `iom` | `OnHand` |
| الجمع | `erp` | `Unrestricted` |
| الجمع | `erp` | `QualityInspection` |
| الجمع | `pos` | `PosInbound` |
| الجمع | `fno` | `Ordered` |
| الجمع | `fno` | `Arrived` |
| الجمع | `iv` | `Ordered` |
| الطرح | `fno` | `ReservPhysical` |
| الطرح | `fno` | `ReservOrdered` |
| الطرح | `iv` | `SoftReservPhysical` |
| الطرح | `iv` | `SoftReservOrdered` |
| الطرح | `iv` | `ReservPhysical` |
| الطرح | `iv` | `ReservOrdered` |
| الطرح | `pos` | `PosOutbound` |

##### <a name="inventorysupply-calculated-measure"></a>المقياس المحسوب لـ InventorySupply

يمكنك تكوين المقياس المحسوب لـ `InventorySupply` لمصدر بيانات `iv` كما هو موضح في الجدول التالي.

| نوع الحساب | مصدر البيانات | القياس المادي |
|---|---|---|
| الجمع | `fno` | `Ordered` |
| الجمع | `fno` | `Arrived` |
| الجمع | `iv` | `Ordered` |
| الجمع | `fno` | `PhysicalInvent` |
| الجمع | `iom` | `OnHand` |
| الجمع | `erp` | `Unrestricted` |
| الجمع | `erp` | `QualityInspection` |
| الجمع | `pos` | `PosInbound` |
| الطرح | `pos` | `PosOutbound` |

##### <a name="inventorydemand-calculated-measure"></a>المقياس المحسوب لـ InventoryDemand

يمكنك تكوين المقياس المحسوب لـ `InventoryDemand` لمصدر بيانات `iv` كما هو موضح في الجدول التالي.

| نوع الحساب | مصدر البيانات | القياس المادي |
|---|---|---|
| الجمع | `fno` | `OnOrder` |
| الجمع | `iom` | `OnOrder` |
| الجمع | `iv` | `SoftReservPhysical` |
| الجمع | `iv` | `SoftReservOrdered` |
| الجمع | `fno` | `ReservPhysical` |
| الجمع | `fno` | `ReservOrdered` |
| الجمع | `iv` | `ReservPhysical` |
| الجمع | `iv` | `ReservOrdered` |

#### <a name="configuration-of-the-fno-data-source"></a>تكوين مصدر بيانات fno

يصف هذا القسم كيفية تكوين مصدر بيانات `fno`.

##### <a name="dimension-mappings-for-the-fno-data-source"></a>تعيينات الأبعاد لمصدر بيانات fno

يتم تكوين تعيينات الأبعاد المسردة في الجدول التالي لمصدر بيانات `fno`.

| البعد الخارجي | البُعد الأساسي |
|---|---|
| `InventBatchId` | `BatchId` |
| `InventColorId` | `ColorId` |
| `InventLocationId` | `LocationId` |
| `InventSerialId` | `SerialId` |
| `InventSiteId` | `SiteId` |
| `InventSizeId` | `SizeId` |
| `InventStatusId` | `StatusId` |
| `InventStyleId` | `StyleId` |
| `LicensePlateId` | `LicensePlateId` |
| `WMSLocationId` | `WMSLocationId` |
| `WMSPalletId` | `WMSPalletId` |
| `ConfigId` | `ConfigId` |
| `InventVersionId` | `VersionId` |
| `InventDimension1` | `CustomDimension1` |
| `InventDimension2` | `CustomDimension2` |
| `InventDimension3` | `CustomDimension3` |
| `InventDimension4` | `CustomDimension4` |
| `InventDimension5` | `CustomDimension5` |
| `InventDimension6` | `CustomDimension6` |
| `InventDimension7` | `CustomDimension7` |
| `InventDimension8` | `CustomDimension8` |
| `InventDimension9` | `CustomDimension9` |
| `InventDimension10` | `CustomDimension10` |
| `InventDimension11` | `CustomDimension11` |
| `InventDimension12` | `CustomDimension12` |

##### <a name="physical-measures-configured-for-the-fno-data-source"></a>القياسات الفعلية التي تم تكوينها لمصدر بيانات fno

يتم تكوين القياسات الفعلية التالية لمصدر بيانات `fno`:

- `Ordered`
- `Arrived`
- `AvailPhysical`
- `PhysicalInvent`
- `ReservPhysical`
- `ReservOrdered`
- `OnOrder`

#### <a name="configuration-of-the-pos-data-source"></a>تكوين مصدر بيانات pos

يصف هذا القسم كيفية تكوين مصدر بيانات `pos`.

##### <a name="physical-measures-for-the-pos-data-source"></a>القياسات الفعلية لمصدر بيانات pos

يتم تكوين القياسات الفعلية التالية لمصدر بيانات `pos`:

- `PosInbound`
- `PosOutbound`

##### <a name="availquantity-calculated-measure"></a>المقياس المحسوب لـ AvailQuantity

يمكنك تكوين المقياس المحسوب لـ `AvailQuantity` لمصدر بيانات `pos` كما هو موضح في الجدول التالي.

| نوع الحساب | مصدر البيانات | القياس المادي |
|---|---|---|
| الجمع | `fno` | `AvailPhysical` |
| الجمع | `pos` | `PosInbound` |
| الطرح | `pos` | `PosOutbound` |

#### <a name="configuration-of-the-iom-data-source"></a>تكوين مصدر بيانات iom

يتم تكوين القياسات الفعلية التالية لمصدر بيانات `iom` (إدارة الأمر الذكي):

- `OnOrder`
- `OnHand`

#### <a name="configuration-of-the-erp-data-source"></a>تكوين مصدر بيانات erp

يتم تكوين القياسات الفعلية التالية لمصدر بيانات `erp` (تخطيط مورد المؤسسة):

- `Unrestricted`
- `QualityInspection`

### <a name="partition-configuration"></a>تكوين التقسيم

يعرض الجدول التالي تكوين التقسيم الافتراضي.

| البُعد الأساسي | التدرج الهرمي |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |

### <a name="index-configuration"></a>تكوين الفهرس

يعرض الجدول التالي تكوين الفهرس الافتراضي.

| تعيين الرقم | البعد | التدرج الهرمي |
|---|---|---|
| 1 | `ColorId` | 1 |
| 1 | `SizeId` | 2 |
| 1 | `StyleId` | 3 |

### <a name="reservation-configuration"></a>تكوين الحجز

يصف هذا القسم تكوين الحجز الافتراضي.

#### <a name="reservation-mapping"></a>تعيين الحجز

يعرض الجدول التالي تعيين الحجز الافتراضي.

| مصدر بيانات القياسات الفعلية | القياس المادي | متاح لمصدر بيانات الحجز | متاح للقياس المحسوب للحجز |
|---|---|---|---|
| `iv` | `SoftReservOrdered` | `iv` | `AvailableToReserve` |

#### <a name="reservation-hierarchy"></a>التدرج الهرمي للحجز

يعرض الجدول التالي التدرج الهرمي للحجز الافتراضي.

| البُعد الأساسي | التدرج الهرمي |
|---|---|
| `SiteId` | 1 |
| `LocationId` | 2 |
| `ColorId` | 3 |
| `SizeId` | 4 |
| `StyleId` | 5 |
| `BatchId` | 6 |
| `SerialId` | 7 |
| `StatusId` | 8 |
| `LicensePlateId` | 9 |
| `WMSLocationId` | 10 |
| `WMSPalletId` | 11 |
| `ConfigId` | 12 |
| `VersionId` | 13 |
| `CustomDimension1` | 14 |
| `CustomDimension2` | 15 |
| `CustomDimension3` | 16 |
| `CustomDimension4` | 17 |
| `CustomDimension5` | 18 |
| `CustomDimension6` | 19 |
| `CustomDimension7` | 20 |
| `CustomDimension8` | 21 |
| `CustomDimension9` | 22 |
| `CustomDimension10` | 23 |
| `CustomDimension11` | 24 |
| `CustomDimension12` | 25 |
| `ExtendedDimension1` | 26 |
| `ExtendedDimension2` | 27 |
| `ExtendedDimension3` | 28 |
| `ExtendedDimension4` | 29 |
| `ExtendedDimension5` | 30 |
| `ExtendedDimension6` | 31 |
| `ExtendedDimension7` | 32 |
| `ExtendedDimension8` | 33 |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]