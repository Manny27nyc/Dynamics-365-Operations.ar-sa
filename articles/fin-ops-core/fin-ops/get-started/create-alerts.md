---
title: إنشاء قواعد تنبيه
description: يشمل هذا الموضوع معلومات حول التنبيهات ويوضح كيفية إنشاء قاعدة تنبيه بحيث يتم إعلامك بالأحداث مثل تاريخ يتم بلوغه أو تغييرًا محددًا يحدث.
author: tjvass
manager: AnnBe
ms.date: 02/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.openlocfilehash: 85d4774bc710f0c48b384601e5505f11394cf5d5
ms.sourcegitcommit: a688c864fc609e35072ad8fd2c01d71f6a5ee7b9
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/20/2020
ms.locfileid: "3075914"
---
# <a name="create-alert-rules"></a>إنشاء قواعد تنبيه

[!include [banner](../includes/banner.md)]

## <a name="getting-started"></a>بدء الاستخدام

قبل إعداد قاعدة تنبيه، قرر متى وفي أي مواقف تحتاج فيها إلى تلقي التنبيهات. عندما تعرف الحدث الذي تريد أن يتم إعلامك به، ابحث عن الصفحة التي توجد فيها البيانات التي تؤدي إلى ظهور هذا الحدث. يمكن أن يكون الحدث تاريخًا يتم بلوغه أو تغييرًا محددًا يحدث. لذلك، يجب البحث عن الصفحة التي يتم فيها تحديد التاريخ، أو الحقل الذي تظهر فيها هذه التغييرات أو السجل الجديد الذي تم إنشاؤه. بعد أن تتوفر لديك هذه المعلومات، يمكنك إنشاء قاعدة التنبيه.

عندما تقوم بإنشاء قاعدة تنبيه، يمكنك تحديد المعايير التي يجب أن تتحقق قبل أن يتم تشغيل أحد التنبيهات. تمثل المعايير حالة من التوافق بين حدوث حدث وتحقق شروط محددة بشكل أساسي. وعند حدوث حدث معين، يقوم النظام بتنفيذ عملية تحقق وفقًا للشروط التي تم إعدادها.

## <a name="ensure-the-alert-batch-jobs-are-running"></a>التأكد من تشغيل وظائف دفعية للتنبيه

يجب تشغيل الوظائف الدفعية الخاصة بتغيير البيانات وتنبيهات تاريخ الاستحقاق لشروط التنبيه المراد معالجتها والإخطارات المراد إرسالها. لتشغيل الوظائف الدفعية، انتقل إلى **إدارة النظام** > **المهام الدورية** > **التنبيهات** وأضف وظيفة دفعية جديدة لـ **تنبيهات مستندة إلى التغيير** و/أو **تنبيهات تاريخ الاستحقاق**. في حالة الحاجة إلى وظيفة دفعية، حدد **التكرار** وقم بتعيين **لا يوجد تاريخ انتهاء** باستخدام **نمط التكرار** من **دقائق** و **العدد** من **1**.

## <a name="events"></a>الأحداث

قد يكون الحدث الذي يقوم بتشغيل قاعدة تنبيه تاريخ يتم بلوغه أو تغييرًا محددًا يحدث. يتم تحديد مشغلات الأحداث في علامة التبويب السريعة **تنبيهي عند** في مربع الحوار **إنشاء قاعدة تنبيه**. تعتمد الأحداث المتوفرة لحقل محدد على المشغل الذي تم تحديده.

على سبيل المثال، إذا كنت تقوم بإعداد قاعدة تنبيه لحقل **تاريخ البدء**، تكون أحداث تواريخ الاستحقاق‬ مناسبة. ولذلك، يكون نوع الحدث **مستحق في‬** متوفرًا لهذا الحقل. ومع ذلك، بالنسبة لحقل مثل **مركز التكلفة**، لا يكون حدث تاريخ الاستحقاق مناسبًا. ولذلك، يكون نوع الحدث **مستحق في‬** غير متوفر. بدلاً من ذلك، يكون نوع الحدث **تم تغييره** متوفرًا.

## <a name="event-types"></a>أنواع الحدث

يمكن أن تحدث ثلاثة أنواع من الأحداث:

- **أحداث إنشاء-نوع وحذف-نوع‬** - تشغل هذه الأحداث أحد التنبيهات عندما يتم إنشاء سجل أو حذفه.
- **أحداث من نوع التحديث** - تشغل هذه الأحداث أحد التنبيهات عندما تتغير البيانات الموجودة في حقل معين.
- **أحداث من نوع تاريخ الاستحقاق** - تشغل هذه الأحداث أحد التنبيهات عندما تصل إلى تاريخ.
    
يمكن للتغييرات التي تحدث أن تبدأ من قِبل مستخدم. على سبيل المثال، يقوم مستخدم بتغيير تاريخ التسليم لأمر الشراء. بدلاً من ذلك، يمكن أن تحدث التغييرات كجزء من عملية. على سبيل المثال، يتغير الحقل **حالة** في صفحة لإظهار دورة حياة العديد من العمليات في النظام.

## <a name="conditions"></a>الشروط

في علامة التبويب السريعة **التنبيه عن** في مربع الحوار **إنشاء قاعدة تنبيه‬**، يمكنك استخدام الشروط للتحكم عندما يتم تنبيهك بشأن أحداث.

على سبيل المثال، يمكنك تحديد أن النظام يجب أن يقوم بتنبيهك عندما تتغير حالة أوامر الشراء، ولكن فقط إذا كانت الحالة تتطابق مع مجموعة معينة من الشروط. بشكل خاص، أنت تريد أن تتلقى تنبيهًا عندما يتم تعيين حالة أمر الشراء إلى **مُستَلم**. هذا التغيير في الحالة هو الحدث الذي يشغل التنبيه.

بعد ذلك، يجب أن تحدد أوامر الشراء التي ترغب في أن يتم تنبيهك إليها. على سبيل المثال، يمكنك تحديد أحد الخيارات التالية. تحديد هذه الخيارات شروط قاعدة التنبيه.

- **السجل الحالي المحدد** -تتلقى تنبيهًا عندما تتغير حالة أمر شراء محدد إلى **مُستَلم‬**.
- **جميع السجلات** - تتلقى تحذيرًا عند تغيير حالة أمر شراء لصنف في طريقة عرض الصفحة النشطة. يمكنك استخدام التصفية المتقدمة المتوفرة على الصفحة لإنشاء قواعد لمجموعة معينة من السجلات. على سبيل المثال، يمكنك إنشاء تنبيه يتم تشغيله لجميع أوامر الشراء للعملاء في مجموعة عملاء محددة.
    
## <a name="expiry-of-rule"></a>انتهاء صلاحية القاعدة

في علامة التبويب **‏‫التنبيه حتى‬** في مربع الحوار **إنشاء قاعدة تنبيه**، يمكنك تحديد المدة التي يجب أن تكون قاعدة التنبيه نشطة خلالها.

## <a name="alert-contents"></a>محتويات التنبيهات

في علامة التبويب السريعة **التنبيه باستخدام** في مربع الحوار **إنشاء قاعدة تنبيه**، يمكنك تحديد نص الموضوع ونص الرسالة التي يجب أن تستخدمها رسائل التنبيه.

## <a name="user-id"></a>معرّف المستخدم

في علامة التبويب السريعة **‏‫التنبيه باستخدام‬** في مربع الحوار **إنشاء قاعدة تنبيه**، يمكنك تحديد المستخدم الذي يجب أن يتلقى رسائل التنبيه. بشكل افتراضي، يتم تحديد معرف المستخدم الخاص بك. تقتصر القدرة على تغيير المستخدم الذي يستلم التنبيه على مسؤولي المؤسسة.

## <a name="alerts-as-business-events"></a>التنبيهات كأحداث أعمال

يمكن إرسال التنبيهات خارجيًا باستخدام إطار عمل أحداث الأعمال. عند إنشاء تنبيه، قم بتعيين **على مستوى المؤسسة** إلى **لا** وقم بتعيين **الإرسال خارجيًا** إلى **نعم**. بعد أن تحصل على التنبيه بتشغيل حدث الأعمال، يمكنك تشغيل تدفق تم إنشاؤه في Power Automate باستخدام **عند حدوث حدث أعمال** على الموصل Finance and Operations، أو إرسال الحدث بشكل صريح إلى نقطة نهاية أحداث العمل من خلال **كتالوج أحداث الأعمال**.

## <a name="create-an-alert-rule"></a>إنشاء قاعدة تنبيه

0. التأكد من تشغيل وظائف دفعية للتنبيه (انظر أعلاه).
1. افتح الصفحة التي تحتوي على البيانات المطلوب مراقبتها.
2. في جزء الإجراءات، في علامة التبويب **خيارات**، في المجموعة **مشاركة**، حدد **إنشاء قاعدة تنبيه**.
3. في مربع الحوار **إنشاء قاعدة تنبيه**، في الحقل **حقل**، حدد الحقل المطلوب مراقبته.
4. في الحقل **حدث**، حدد نوع الحدث.
5. في علامة التبويب السريعة **‏‫التنبيه عن‬**، حدد الخيار المطلوب. إذا كنت ترغب في إرسال التنبيه كحدث أعمال، فتأكد من تعيين **على مستوى المؤسسة** على **لا**.
6. إذا كان يجب أن تكون القاعدة غير نشطة في تاريخ معين، في علامة التبويب السريعة **التنبيه حتى‬**، فحدد تاريخ انتهاء.
7. في علامة التبويب السريعة **التنبيه باستخدام** في الحقل **موضوع**، اقبل عنوان الموضوع الافتراضي لرسالة البريد الإلكتروني أو أدخل موضوعًا جديدًا. يتم استخدام النص كعنوان للموضوع لرسالة البريد الإلكتروني التي تتلقاها عند تشغيل تنبيه. إذا أردت إرسال التنبيه كحدث أعمال، قم بتعيين **الإرسال خارجيًا** إلى **نعم**.
8. في الحقل **رسالة**، أدخل رسالة اختيارية. يتم استخدام النص كرسالة تتلقاها عند تشغيل تنبيه.
9. حدد **موافق** لحفظ الإعدادات وإنشاء قاعدة التنبيه.