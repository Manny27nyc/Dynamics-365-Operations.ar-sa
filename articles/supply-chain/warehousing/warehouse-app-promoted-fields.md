---
title: تكوين الحقول المروجة للخطوات في Warehouse Management للأجهزة المحمولة
description: يصف هذا المقال كيفية ترويج وتمييز معلومات معينة لأي خطوة في تدفقات المهام الجديدة أو المخصصة لتطبيق الأجهزة المحمولة لـ Warehouse Management.
author: Mirzaab
ms.date: 08/09/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 3451b1aec525cd0738af558b183f8676d20294a0
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336054"
---
# <a name="configure-promoted-fields-for-steps-in-the-warehouse-management-mobile-app"></a>تكوين الحقول المروجة للخطوات في Warehouse Management للأجهزة المحمولة

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> تنطبق الميزات الموضحة في هذا المقال فقط على تطبيق الجوال الجديد لإدارة المستودعات. لا تؤثر على تطبيق المستودع القديم، الذي تم إهماله الآن.

يصف هذا المقال كيفية ترويج وتمييز معلومات معينة لأي خطوة في تدفقات المهام الجديدة أو المخصصة لتطبيق الأجهزة المحمولة لـ Warehouse Management. ويمكن لهذه القدرة ان تساعد علي تركيز العاملين علي الحقول الأكثر اهميه عند العمل من خلال تدفق. بالنسبة لكل خطوه في كل عمليه ، يمكن للمسؤولين تحديد الحقول المراد ترقيتها والحقول المراد تمييزها.

## <a name="enable-promoted-fields-in-your-system"></a>تمكين الحقول التي تمت ترقيتها في النظام

إذا كنت تقوم بتشغيل إصدار Supply Chain Management 10.0.28 أو إصدار أقدم ، فقبل أن تتمكن من إعداد الحقول التي تمت ترقيتها ، يجب عليك إكمال الإجراء التالي لتمكين الميزات المطلوبة وإنشاء أسماء الحقول المطلوبة في تطبيق Warehouse Management للأجهزة المحمولة. إذا كنت تقوم بتشغيل إصدار Supply Chain Management 10.0.29 أو أحدث ، فان الميزات تكون إلزاميه ولا يمكن إيقاف تشغيلها ، بحيث يمكنك تخطي هذا الاجراء.

1. انتقل إلى **إدارة النظام \> مساحات العمل \> إدارة الميزات**. راجع [نظرة عامة على إدارة الميزات](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) لمزيد من المعلومات حول هذه الصفحة.
1. تاكد *من تشغيل ميزه إرشادات* خطوه تطبيق المستودع للنظام الخاص بك. هذه الميزة هي المتطلبات الاساسيه لميزه *الحقول المروجة في تطبيق Warehouse*. اعتبارًا من الإصدار 10.0.29 من Supply Chain Management ، فهو إلزامي ولا يمكن إيقاف تشغيله. لمزيد من المعلومات حول ميزه *إرشادات خطوه تطبيق المستودع* ، راجع [تخصيص العناوين والتعليمات الخاصة بالخطوة لتطبيق الاجهزه المحمولة لـ Warehouse Management](mobile-app-titles-instructions.md).
1. تاكد *روج تطبيق المستودع الحقول* خطوه تطبيق المستودع للنظام الخاص بك. هذه هي الميزة الموضحة في هذه المقالة. اعتبارًا من الإصدار 10.0.29 من Supply Chain Management ، فهو إلزامي ولا يمكن إيقاف تشغيله.
1. قم بتحديث أسماء الحقول في تطبيق الاجهزه المحمولة لـ Warehouse Management بالانتقال إلى **Warehouse Management \> اعداد \> الجهاز المحمول \> أسماء حقول تطبيق مستودع** وتحديد **إنشاء اعداد افتراضي**. كرر هذه الخطوة لكل كيان قانوني (شركة) تستخدم فيه تطبيق Warehouse Management للأجهزة المحمولة. لمزيد من المعلومات، راجع [تكوين الحقول لتطبيق إدارة المستودع للأجهزة المحمولة](configure-app-field-names-priorities-warehouse.md).

## <a name="configure-promoted-fields-from-a-menu-specific-override"></a>تكوين الحقول المروجة من تجاوز خاص بالقائمة

استخدم الإجراء التالي لإعداد الحقول المروجة.

1. قم بإنشاء تجاوز خاص بالقائمة للقائمة والخطوة المناسبة كما هو موضح في [تخصيص عناوين الخطوة والتعليمات لتطبيق الاجهزه المحمولة لـ Warehouse Management](mobile-app-titles-instructions.md).
1. ابحث عن تركيبة قيم  **معرف الخطوة** و **اسم عنصر القائمة** التي تريد تحريرها، وحدد القيمة في عمود **معرف الخطوة**.
1. في الصفحة التي تظهر ، في علامة التبويب السريعة **تحديد الحقول المروجة**، حدد **تحديد الحقول** في شريط الادوات.
1. في مربع الحوار **الحقول المروجة**، حدد الحقول المروجة. يمكنك أيضا تمييز حتى اثنين من الحقول المحددة. ستظهر الحقول المميزة بالأسود العريض في تطبيق الاجهزه المحمولة لـ Warehouse Management. عند تحديد الحقول ، ضع في اعتبارك حقيقة ان بعض الشاشات قد تكون كبيره بما يكفي لعرض الحقل الذي تم ترقيته في الأعلى أو حقلين آخرين. للحصول علي مثال يوضح كيفيه استخدام هذه الإعدادات ، راجع السيناريو لاحقا في هذا المقال.

    > [!NOTE]
    > تقتصر القائمة **الحقول المتوفرة** علي الحقول التي يمكن ان تظهر لعنصر القائمة. ومع ذلك ، تحدد العوامل الأخرى (مثل تكوين الصنف) ما إذا كان الحقل يظهر فعليا في تطبيق الاجهزه المحمولة لـ Warehouse Management. إذا قمت بتكوين حقول تمت ترقيتها ، ستظهر الحقول المحددة فقط في الصفحة الرئيسية لتطبيق الاجهزه المحمولة لـ Warehouse Management. ومع ذلك ، لا يزال بإمكان العاملين عرض الحقول المتبقية عن طريق النقر فوق الصفحة تفاصيل.

1. حدد **موافق** لتطبيق الإعدادات الخاصة بك. الحقول المحددة الآن مسرودة في علامة التبويب السريعة **تحديد الحقول المروجة**.

## <a name="example-scenario"></a>سيناريو كمثال

### <a name="enable-sample-data"></a>تمكين عينة البيانات

لاستخدام سجلات وقيم العينة المحددة للعمل من خلال هذا السيناريو ، يجب أن تستخدم نظامًا حيث تم تثبيت [بيانات العرض](../../fin-ops-core/fin-ops/get-started/demo-data.md) التوضيحي القياسية. كما يجب تحديد الكيان القانوني **USMF** قبل البدء.

### <a name="configure-sales-picking-with-promoted-steps-on-the-license-plate-step"></a>تكوين انتقاء المبيعات بالخطوات التي تمت ترقيتها علي خطوه لوحه الترخيص

في هذا الاجراء، ستقوم بإعداد حقول مروجة ومميزة لعنصر قائمه **انتقاء المبيعات** في خطوة لوحه الترخيص.

1. انتقل إلى **إدارة المستودعات \> إعداد \> جهاز محمول \> خطوات الجهاز المحمول**.
1. ابحث عن معرف الخطوة المسمي *LicensePlateId* وتحديده.
1. في جزء الإجراء، حدد **إضافة تكوين خطوة**.
1. في مربع الحوار المنسدل ، استخدم الحقل **عنصر القائمة** للبحث عن *انتقاء المبيعات* وتحديده.
1. حدد **موافق**.
1. تظهر صفحه التفاصيل للتجاوز الذي قمت بإنشاءه الآن. في علامة التبويب السريعة **تحديد الحقول المروجة**، حدد **تحديد الحقول** في شريط الادوات.
1. في مربع الحوار **الحقول المروجة**، حدد الحقول المروجة وميزها. في القائمة **الحقول المتوفرة** ، ابحث عن الحقول التالية وحددها ، ثم استخدم الأزرار لنقلها إلى القائمة **الحقول المحددة**:

    - الموقع
    - الصنف
    - اسم المنتج
    - حالة المخزون

1. استخدم أزرار سهم لاعلي وسهم لأسفل لتخصيص ترتيب الحقول في القائمة **الحقول المحددة**. في تطبيق الاجهزه المحمولة لـ Warehouse Management، ستظهر الحقول بالترتيب الذي تقوم بتعيينه هنا.
1. حدد حقل **الموقع** ، ثم حدد **تمييز**.
1. حدد **موافق** لحفظ التكوين.

### <a name="view-the-promoted-fields-in-the-warehouse-management-mobile-app"></a>عرض الحقول المروجة للخطوات في Warehouse Management للأجهزة المحمولة

في هذا الاجراء ، ستقوم بفتح تطبيق الاجهزه المحمولة لـ Warehouse Management والانتقال خلال الخطوات لعرض الحقول التي قمت بترقيها وتمييزها في الاجراء السابق.

1. في Microsoft Dynamics 365 Supply Chain Management ، قم بإنشاء أمر توريد سيتطلب خطوه انتقاء لانتقاء أحد المواقع التي تم تعقبها باستخدام لوحه الترخيص. بعد ذلك قم بإصدار أمر المبيعات إلى المستودع. قم بتدوين معرف العمل الذي تم إنشاؤه.
1. سجل الدخول إلى تطبيق Warehouse Management للأجهزة المحمولة وتسجيل الدخول في المستودع 24. (في بيانات العرض التوضيحي القياسية، سجل دخولك باستخدام *24* كمعرف المستخدم و *1* ككلمة مرور.)
1. حدد قائمه **الصادر** ، ثم حدد عنصر قائمه **التقاط المبيعات**.
1. اتبع إرشادات إدخال البيانات الموجودة علي الشاشة لإدخال معرف العمل الذي تم إنشاؤه في الخطوة 1.
1. في الخطوة التي تحتوي علي النص الذي **فحص لوحه الترخيص** ، يجب ان تشاهد التغييرات التي قمت بها في صفحه التفاصيل. تظهر الحقول بالترتيب الذي قمت بتعيينه للحقول التي تمت ترقيتها ، ويتم عرض حقل **الموقع** بالأسود العريض.
