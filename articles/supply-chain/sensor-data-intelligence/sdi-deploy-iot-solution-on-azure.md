---
title: نشر حل IoT على Azure
description: تستخدم ذكاء بيانات أداه الاستشعار البيانات من أدوات الاستشعار المتصلة بها Microsoft Azure. يوضح هذا المقال كيفيه نشر إنترنت الأشياء التي تم حلها (IoT) علي اشتراكك في Azure.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreAzureResourceDeploymentWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 284aba91aa436ed1dfc02b5a93b4358ffc518017
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428283"
---
# <a name="deploy-an-iot-solution-on-azure"></a>نشر حل IoT على Azure

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

تستخدم ذكاء بيانات أداه الاستشعار البيانات من أدوات الاستشعار المتصلة بها Microsoft Azure. لتمكين Azure لاسترداد البيانات من أدوات الاستشعار ومشاركتها مع Dynamics 365 Supply Chain Management ، يجب نشر حل الأشياء (IoT) علي اشتراكك في Azure. يوفر الرسم التخطيطي المعماري التالي نظره عامه حول الحل ومكوناته.

![الرسم التخطيطي المعماري لمعلومات بيانات إداة الاستشعار.](media/sdi-architecture.png "الرسم التخطيطي المعماري لمعلومات بيانات إداة الاستشعار")

اتبع هذه الخطوات لنشر الموارد المطلوبة على Azure.

1. سجل دخولك إلى Supply Chain Management كمسؤول.
1. الانتقال إلى **إعداد \> إداه النظام \>‏‫الوظيفة الإضافية \> نشر البيانات وربط موارد Azure** لفتح معالج النشر.
1. في صفحة **الترحيب** ، أقرأ المعلومات، ثم حدد **التالي**.
1. في صفحة **نشر نموذج حل IoT على Azure** ، أقرأ المعلومات، ثم في قسم **الإرشادات** ، حدد **نشر**.
1. يتم فتح علامة تبويب مستعرض جديدة، ويتم نقلك إلى مدخل Azure بحيث يمكنك نشر موارد Azure. في حاله المطالبة، قم بتسجيل الدخول باستخدام بيانات اعتمادك لاشتراكك في Azure.
1. في صفحة **النشر المخصص** ، في الحقل **اشتراك** ، حدد الاشتراك.
1. ضمن الحقل **مجموعه الموارد** ، حدد **إنشاء جديد** لإنشاء مجموعه موارد لمكونات Azure التي ستقوم بنشرها.
1. في مربع الحوار المنسدل الذي يظهر في **اسم** الحقل، ادخل اسمًا لمجموعه الموارد الجديدة (علي سبيل المثال، *العرض التوضيحي الخاص ب IoT*). ثم حدد **موافق**.
1. قم بتعيين الحقول التالية:

    - **مجموعه الموارد** - حدد مجموعة الموارد التي قمت بإنشاءها لتوك.
    - **المنطقة** -حدد منطقه، وبشكل مثالي المنطقة التي يتم فيها نشر بيئة Supply Chain Management. ضع في اعتبارك ان مناطق Azure لها أسعار مختلفه. يمكنك عرض التكاليف المقدرة لمنطقك باستخدام حاسبه [سعر معلومات بيانات أداه الاستشعار](https://azure.com/e/c36c4947ebff4215b2e62590c2a24c68).
    - **عنوان URL الخاص ببيئة ‎Supply Chain Management** – أدخل عنوان URL لبيئة Supply Chain Management.
    - **إعاده استخدام مركز Azure IoT الموجود** – اترك خانه الاختيار هذه ممسوحة.

1. حدد **التالي: مراجعة وإنشاء**.
1. في صفحة **النشر المخصص** تحقق من مرور عملية التحقق، ثم اختار **إنشاء**.
1. تتعقب صفحة **النشر قيد التقدم** التقدم في عمليه النشر. قد تستغرق عمليه النشر 30 دقيقة. عندما تكون صفحة **النشر قيد التقدم** تشير إلى اكتمال النشر، حدد الإرتباط الخاص باسم مجموعة الموارد لفتح الصفحة التي تعرض قائمه الموارد التي يتم نشرها في المجموعة.
1. في قائمه الموارد، ابحث عن السجل حيث تم تعيين حقل **النوع** إلى *هوية مُدارة*. في عمود **الاسم** حدد الاسم لفتح صفحة البيانات الخاصة بالموارد.
1. قم بنسخ القيمة في حقل **معرف العميل** (علي سبيل المثال ، عن طريق تحديد الزر **نسخ إلى الحافظة** ).
1. قم بالرجوع إلى علامة تبويب المستعرض حيث يتم تشغيل Supply Chain Management ، *ولكن لا تقم بإغلاق علامة التبويب الخاصة بمدخل Azure*. يجب ان يستمر فتح صفحه نشر **نموذج حل IoT على Azure‎**. 
1. حدد **التالي**.
1. في الصفحة **الاتصال بموارد Azure** في حقل **Azure AD معرف عميل التطبيق** ، قم بلصق قيمة **معرف العميل** التي قمت بنسخها.
1. ارجع إلى علامة تبويب المستعرض حيث يتم فتح بوابة Azure, *ولكن لا تغلق علامة التبويب Supply Chain Management*. يجب أن تظل صفحة تفاصيل المورد مفتوحة.
1. حدد **زر الخلف** الخاص بالمستعرض للرجوع إلى قائمه الموارد الموجودة في مجموعه الموارد الجديدة.
1. في قائمه الموارد، ابحث عن السجل حيث تم تعيين حقل **النوع** إلى *ذاكرة تخزين Azure المؤقتة لـ Redis‬‏‫*. في عمود **الاسم** حدد الاسم لفتح صفحة البيانات الخاصة بالموارد.
1. في جزء التنقل الأيسر، حدد **مفاتيح الوصول**.
1. في صفحة **مفاتيح الوصول** ، قم بنسخ القيمة التي تظهر ل **سلسلة الاتصال الاساسيه (StackExchange.Redis)** (علي سبيل المثال، عن طريق تحديد **زر النسخ إلى الحافظة** ).
1. قم بالرجوع إلى علامة تبويب المستعرض حيث يتم تشغيل Supply Chain Management. يجب ان تظل صفحه **الاتصال بموارد Azure** مفتوحة.
1. في حقل سلسله **‏‫اتصال مخزن Redis القياسي‬** ، قم بلصق قيمة **سلسلة الاتصال الاساسية (StackExchange.Redis)** التي قمت بنسخها.
1. حدد **إنهاء**.

يتم الآن نشر موارد Azure لمعلومات بيانات الاستشعار علي اشتراكك في Azure.

> [!NOTE]
> في أي وقت، يمكنك عرض أو تحرير معلومات الاتصال التي تم حفظها في Supply Chain Management عن طريق فتح الصفحة **‏‫معلمات Sensor Data Intelligence** . - لمزيد من المعلومات، راجع [‏‫معلمات Sensor Data Intelligence‬](sdi-parameters.md).