---
title: الجدولة بقدرة غير محدودة
description: يوفر هذا المقال معلومات حول جدولة قدرة غير محدودة لتحسين التخطيط. كما يصف قيود الميزات الحالية.
author: t-benebo
ms.date: 08/09/2022
ms.topic: article
ms.search.form: RouteInventProd
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-06-09
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: c6e0190899abb544b559bb5f26ba974155989c3a
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335304"
---
# <a name="scheduling-with-infinite-capacity"></a>الجدولة بقدرة غير محدودة

[!include [banner](../../includes/banner.md)]

تقدم ميزة *جدولة قدرة غير محدودة لتحسين التخطيط* جدولة تستند إلى معلومات المسار. وتتيح لك إمكانية جدولة الوظائف استنادا إلى نطاق واسع من إعدادات المسار. تغطي الجدولة لتحسين التخطيط إعدادات المسارات المستخدمة بشكل متكرر، بما في ذلك تسلسل عمليات المسار أو متطلبات موارد عملية المسار.

## <a name="turn-the-infinite-capacity-scheduling-feature-on-or-off"></a>قم بتشغيل ميزة جدولة السعة اللانهائية أو إيقاف تشغيلها

لاستخدام هذه الميزة ، يجب تشغيلها لنظامك. اعتبارًا من الإصدار 10.0.29 من Supply Chain Management، يتم تشغيل هذه الميزة افتراضيًا. بإمكان المسؤولين تشغيل هذه الوظيفة أو إيقاف تشغيلها عن طريق البحث عن ميزة *جدولة سعة لانهائية لتحسين التخطيط‬* في مساحة عمل [إدارة الميزات](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

لمزيد من المعلومات حول هذه الميزة، راجع [الجدولة باستخدام تحديد المورد بالاستناد إلى القدرة‬‏‫](capability-based-scheduling.md).

## <a name="added-functionality"></a> الوظائف المضافة

تتيح ميزة *جدولة قدرة غير محدودة لتحسين التخطيط* جدولة الوظائف استنادًا إلى معلومات المسار. بالتالي، يمكن استخدام إعداد المسار لجدولة عمليات الإنتاج. على الرغم من أن هذه الميزة بها بعض القيود غير الموجودة في التخطيط الرئيسي المضمن، لكنها تدعم وظائف أكثر شيوعا تكون مطلوبة لسيناريوهات التصنيع.

تراعي الميزة *المسارات البسيطة* و *شبكات المسارات*. باستخدام حقل **التالي** في عملية مسار، يمكن إعداد المسارات المعقدة التي تحتوي على نقاط بداية متعددة وعمليات متعددة تعمل بشكل متواز. سيراعي النظام بنيات المسارات المعقدة من هذا النوع أثناء الجدولة.

بالإضافة إلى ذلك، تدعم الميزة *العمليات المتوازية* في المسارات. باستخدام خياري *الأساسي* و *الثانوي* في حقل **الأولوية** في عمليات المسار، يمكنك تحديد بنية مسار حيث تكون إحدى عمليات المسار هي العملية الأساسية والعملية أخرى هي الثانوية. في هذه الحالة، سيراعي النظام بنية المسار أثناء الجدولة.

أثناء عملية الجدولة، يراعي النظام أيضا *متطلبات الموارد* المحددة لعملية ما. يستخدم النظام متطلبات الموارد لتحديد الموارد المطلوبة لتنفيذ العملية. حاليًا، تدعم ميزة *جدولة القدرة غير المحدودة لتحسين التخطيط* الأنواع التالية من متطلبات الموارد:

- نوع المَورد
- مورد
- مجموعة الموارد
- القدرة (لمزيد من المعلومات حول، راجع [الجدولة باستخدام تحديد المورد بالاستناد إلى القدرة](capability-based-scheduling.md).)

> [!NOTE]
>
> - إذا تم تعيين المورد و/أو مجموعة الموارد إلى سعة غير محدودة، فسيعتبرها التخطيط الرئيسي سعة غير محدودة.
> - المتطلبات المرتبطة بالموارد البشرية، مثل المهارات أو متطلبات الشهادات، غير معتمدة بعد.

تدعم الميزة أيضًا الخصائص التشغيلية **وقت الإعداد** و **وقت التشغيل**. عند تعيين هذه الخصائص في عملية مسار، ستقوم عملية الجدولة بإنشاء وظائف الإعداد والمعالجة المناسبة.

باختصار، تدعم جدولة تحسين التخطيط السيناريوهات المستخدمة بشكل متكرر. يمكنك إنشاء المسار وإضافة عمليات أساسية وثانوية وتحديد العمليات التالية وإضافة متطلبات الموارد وإضافة وقت الإعداد ووقت التشغيل. سيقوم النظام بعد ذلك بمراعاة هذه المعلومات أثناء الجدولة.

## <a name="limitations"></a>قيود

تنطبق القيود التالية عند استخدام الجدولة لتحسين التخطيط:

- تدعم الميزة القدرة غير المحدودة فقط.
- لا تدعم الميزة وظيفة تحميل الموارد.
- لا تراعي الميزة خردة المسار.
- تدعم الميزة *المدة* المحددة للمورد الأساسي فقط.

لاحظ أنه يتم تحسين *جدولة القدرة غير المحدودة لتحسين التخطيط* باستمرار. وتتوقع Microsoft تقديم دعم لإعدادات الجدولة الإضافية في الإصدارات المستقبلية.
