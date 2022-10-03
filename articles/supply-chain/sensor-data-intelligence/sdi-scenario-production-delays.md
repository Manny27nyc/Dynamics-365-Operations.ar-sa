---
title: سيناريو تاخير الإنتاج
description: يصف هذا المقال سيناريو تأخيرات الإنتاج من خلال إنشاء إخطار والذي يُنشئ إشعارًا إذا انخفض معدل نقل الإنتاج إلى أقل من قيمة حد معينة.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreScenarioManagement, IoTIntCoreScenarioConfigurationWizardV2, IoTIntMfgResourceStatusConfiguration, IoTIntMfgResourceStatus
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 073762581d84646ba12b570e57327b7cab8efd3b
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428273"
---
# <a name="the-production-delays-scenario"></a>سيناريو تاخير الإنتاج

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

يقوم سيناريو *تأخيرات الإنتاج* بإنشاء إخطار إذا كان صافي الإنتاج أقل من قيمة حد معينة. في هذا السيناريو، سيتم إرسال رسالة *خروج* إلى مركز IoT Microsoft Azure لكل صنف تم إنتاجه. في Dynamics 365 Supply Chain Management ، يتم حساب تأخير الأمر استنادًا إلى مقدار الوقت المجدول لتشغيل أمر الإنتاج، وعدد الأصناف التي يجب إنتاجها، ومقدار الوقت الذي تم خلاله تشغيل المهمة وعدد إشارات *الخروج* التي تم استلامها. يتم إنشاء إخطار بالتأخير إذا كان عدد إشارات *الخروج* للمهمة أقل من قيمة الحد.

## <a name="scenario-dependencies"></a>تبعيات السيناريو

يتضمن سيناريو *تأخيرات الإنتاج* التبعيات التالية:

- يمكن تشغيل تنبيه فقط إذا كان أمر الإنتاج قيد التشغيل على جهاز تم تعيينه.
- يجب إرسال إشارة تمثل إشارة *خروج* للجهاز المعين إلى مركز IoT، ويجب تضمين اسم خاصية فريد.
- يجب أن تكون خاصية الطابع الزمني UNIX، حيث يتم التعبير عن القيمة بالمللي ثانية، موجودة في رسالة مركز Azure IoT.

## <a name="prepare-demo-data-for-the-product-delays-scenario"></a>إعداد بيانات العرض التوضيحي لسيناريو تأخير المنتج

إذا كنت ترغب في استخدام نظام العرض التوضيحي لاختبار سيناريو *تأخير الإنتاج* فاستخدم النظام الذي تم تثبيت بيانات [العرض التوضيحي](../../fin-ops-core/fin-ops/get-started/demo-data.md) عليه، وحدد الكيان القانوني *USMF* (الشركة)، ثم قم باعداد بيانات العرض التوضيحي الاضافيه كما هو موضح في هذا القسم. إذا كنت تستخدم أدوات الاستشعار والبيانات الخاصة بك، فيمكنك تخطي هذا القسم.

### <a name="set-up-sensor-simulator"></a>إعداد محاكي ‏‫أداة الاستشعار

إذا كنت ترغب في محاولة تنفيذ هذا السيناريو من دون استخدام أداه استشعار فعليه، فإنه يمكنك إعداد أحد المحاكيين لإنشاء الإشارات المطلوبة. لمزيد من المعلومات، راجع [إعداد أداة استشعار محاكاة للاختبار](sdi-set-up-simulated-sensor.md)

### <a name="verify-that-resource-3118-is-used-for-product-p0111"></a>التحقق من استخدام المورد 3118 للمنتج P0111

سيتم جدوله أمر الإنتاج وإصداره. ومن ثم، يتم إصدار وظيفة إنتاج إلى المورد *3118* (*فوام قطع الجهاز*). اتبع هذه الخطوات للتحقق من استخدام المورد *3118* للمنتج *P0111* في بيانات العرض التوضيحي الخاصة بك.

1. انتقل إلى **إدارة معلومات المنتج‬ \> المنتجات \> المنتجات الصادرة**.
1. ابحث وحدد المنتج الذي يتم فيه تعيين الحقل **رقم الصنف** إلى *P0111*.
1. في جزء الإجراءات، في علامة تبويب **المهندس** في مجموعة **عرض‏‎‬** ، حدد **المسار**.
1. في صفحة **المسار** ، وفي علامة التبويب **نظره عامة** في أسفل الصفحة ، حدد البند الذي فيه **العملية رقم.** يتم تعيين الحقل إلى *30*.
1. في علامة التبويب **متطلبات الموارد** أسفل الصفحة، تاكد من ان المورد *3118* (*فوام قطع الجهاز*) مقترنًا بالعملية.

### <a name="create-and-release-a-production-order-for-product-p0111"></a>قم بإنشاء أمر إنتاج وإصداره للمنتج P0111

اتبع الخطوات التالية لإنشاء أمر إنتاج وإصداره للمنتج *P0111*.

1. انتقل إلى **التحكم بالإنتاج \> أوامر الإنتاج \> كافة أوامر الإنتاج**.
1. في صفحة **جميع أوامر الانتاج** ، في جزء الإجراءات، حدد **أمر مجموعة جديد**.
1. في مربع الحوار **إنشاء دفعة** ، قم بتعيين القيم التالية:

    - **رقم الصنف:** *P0111*
    - **الكمية:** *10*

1. حدد **إنشاء** لإنشاء الأمر والرجوع إلى صفحة **كافة أوامر الإنتاج**.
1. استخدم حقل **عامل التصفية** للبحث عن أوامر الإنتاج التي تم تعيين حقل **رقم الصنف** فيها علي *P0111*. ثم ابحث وحدد أمر الإنتاج الذي قمت بإنشائه للتوّ.
1. في جزء الإجراءات، في علامة تبويب **أمر الإنتاج** في مجموعة **العملية‏‎‬** حدد **تقدير**.
1. في مربع الحوار **التقدير** ، اختر **موافق** لإجراء التقدير.
1. في جزء الإجراءات، في علامة تبويب **أمر الإنتاج** في مجموعة **العملية‏‎‬** ، حدد **إصدار**.
1. في مربع الحوار **إصدار** ، دون رقم أمر المجموعة الذي قمت بإنشاءه.
1. حدد **موافق** لإصدار الأمر.

### <a name="configure-the-production-floor-execution-interface"></a>تكوين واجهة تنفيذ صالة الإنتاج‬

إذا لم تكن قد قمت بذلك بالفعل، فقم بتكوين واجهه تنفيذ صالة للإنتاج لإظهار المهام التي تم تعيينها إلى المورد *3118* (*ماكينة قطع الرغوة*). بالنسبة للتعليمات، راجع الأقسام التالية:

- [تكوين واجهة تنفيذ صالة الإنتاج‬ واستخدامها](sdi-scenario-equipment-downtime.md#config-pfe)
- [تمكين خيار البحث في واجهة تنفيذ صالة الإنتاج](sdi-scenario-equipment-downtime.md#enable-pfe-search)

### <a name="start-the-first-job-in-the-batch-order"></a>بدء الوظيفة الأولي في أمر المجموعة

اتبع هذه الخطوات لبدء المهمة الاولي في أمر الدفعة.

1. انتقل إلى **التحكم بالإنتاج \> تنفيذ التصنيع \> تنفيذ صالة الإنتاج**.
1. في حقل **معرف الشارة** ، أدخل *123*. ثم حدد **تسجيل دخول**.
1. إذا طُلب منك سبب الغياب، فحدد أحدي البطاقات للغياب، ثم حدد **موافق**.
1. في حقل **البحث** ، أدخل رقم أمر المجموعة الذي قمت بالسابق بإنشاء إشعار له. ثم حدد مفتاح **الرجوع**.
1. حدد الأمر، ثم حدد **موافق**.
1. في مربع الحوار **بدء المهمة** ، حدد **بدء**.

## <a name="set-up-the-production-delays-scenario"></a>إعداد سيناريو تاخير الإنتاج

اتبع هذه الخطوات التالية لإعداد سيناريو *تأخير الإنتاج* في Supply Chain Management.

1. انتقل إلى **التحكم بالإنتاج \> الإعداد \> ‏‫الوظيفة الإضافية Sensor Data Intelligence‬ \> السيناريوهات‬‏‫**.
1. في مربع سيناريو **تأخير الإنتاج** حدد **تكوين** لفتح معالج الإعداد الخاص بهذا السيناريو.
1. في صفحة **أدوات الاستشعار** حدد **جديد** لإضافة إداة استشعار إلى الشبكة. ثم قم بتعيين الحقول التالية لها:

    - **معرف أداة الاستشعار**– أدخل معرف أداه الاستشعار الذي تستخدمه. إذا كنت تستخدم وحدة محاكاة Raspberry PI Azure IoT عبر الإنترنت ‬‏‫وقمت بإعداده كما هو موضح في [قم بإعداد أداه استشعار محاكيه للاختبار](sdi-set-up-simulated-sensor.md)ادخل *ProductionDelay*.
    - **وصف أداة الاستشعار** - أدخل وصفًا للأداة الاستشعار.

1. كرر الخطوة السابقة لكل أداة استشعار إضافية يجب إضافتها الآن. يمكنك العودة وإضافة مزيد من أدوات الاستشعار في اي وقت.
1. حدد **التالي**.
1. في صفحة **تعيين سجل الاعمال** في قسم **أدوات الاستشعار** حدد سجلاً لأحدي أدوات الاستشعار التي قمت بإضافتها.
1. في قسم **تعيين سجل الأعمال** حدد **جديد** لإضافة صف إلى الشبكة.
1. على الصف الجديد، قم بعتتين **سجل الأعمال** إلى المورد الذي تستخدم أداه الاستشعار المحددة لمراقبته. (إذا كنت تستخدم بيانات العرض التوضيحي التي قمت بإعدادها سابقًا في هذه المقالة، قم بتعيينه إلى *3118، ماكينة قطع الرغوة*.)
1. حدد **التالي**.
1. في الصفحة **حد تحويل مسار تاخير الإنتاج** ، إذا كنت تستخدم بيانات العرض التوضيحي التي قمت بإنشاءها مسبقًا في هذه المقالة، اتبع الخطوات التالية:

    1. حدد عنوان عمود **علاقة الصنف** لفتح مربع حوار منسدل يتضمن عوامل تصفيه البحث الخاصة بالعمود. ادخل *P0111* في مربع البحث، ثم حدد **تطبيق**
    2. حدد السطر الذي يحتوي على حقل **التشغيل** معينًا على القيمة *إخفاء/ قطع*. قم بتعيين حقل **حد إخطار للتأخير (%)** إلى الحد (كنسبه مئوية) الذي يجب إرسال الإخطار فيه.

1. حدد **التالي**.
1. في صفحة **تنشيط أدوات الاستشعار** في الشبكة، حدد أداه الاستشعار التي قمت بإضافتها، ثم حدد **تنشيط**. بالنسبة لكل أداه استشعار منشطه موجودة في الشبكة، تظهر علامة اختيار في العمود **النشط**.
1. حدد **إنهاء**.

## <a name="work-with-the-production-delays-scenario"></a>العمل باستخدام سيناريو تاخير الإنتاج

### <a name="view-production-delay-data-on-the-resource-status-page"></a>عرض بيانات تأخير الانتاج في صفحة حاله المورد

في الصفحة **حالة المورد** يمكن لمشرفين مراقبه المخطط الزمني الخاص بالإشارات ‎التي يتم تلقيها من أدوات الاستشعار التي تم تعيينها لكل مورد جهاز. اتبع هذه الخطوات لتكوين مخطط زمني.

1. الانتقال إلى **التحكم بالإنتاج \> ‏‫تنفيذ التصنيع‬ \> حالة المورد**.
1. في مربع الحوار **تكوين** ، قم بتعيين الحقول التالية:

    - **المورد** - حدد الموارد التي تريد مراقبتها. إذا كنت تستخدم بيانات العرض التوضيحي، فحدد *3118*.
    - **السلسلة الزمنيه 1** – حدد السجل (المفتاح المتري) والذي يحتوي علي التنسيق التالي لاسمه: *:ProductionJobDelayed:ActualQuantity&lt;JobId‎&gt;*
    - **اسم العرض** – أدخل *اشار الخروج*.