---
title: وحدة كتلة النص‏‎
description: يتناول هذا الموضوع وحدات كتل النص ويصف كيفية إضافتها إلى صفحات الموقع في Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: fc5b2fa35633b1ce7f7ffefacec318e14fa8db3f
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025587"
---
# <a name="text-block-module"></a>وحدة كتلة النص‏‎


[!include [banner](includes/banner.md)]

يتناول هذا الموضوع وحدات كتل النص ويصف كيفية إضافتها إلى صفحات الموقع في Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>نظرة عامة

وحدة كتلة النص عبارة عن وحدة تُستخدم لإضافة محتوى سياقي. قد يكون هذا المحتوى معلوماتي أو ترويجي.

يتم التحكم في وحدات كتل النص بواسطة البيانات من نظام إدارة المحتوى (CMS) ويُمكن وضعها في أي صفحة. فهي وحدات نمطية مستقلة لا تعتمد على سياق الصفحة أو على أي وحدات نمطية أخرى.

## <a name="examples-of-text-block-modules-in-e-commerce"></a>أمثلة عن وحدات كتل النص في التجارة الإلكترونية

يُمكن استخدام وحدات كتلة النص بالطرق التالية:

* لإظهار ميزات المنتج في صفحة تفاصيل المنتج.
* لأغراض إعلامية على أي صفحة. على سبيل المثال، يُمكن لهذه الوحدات توضيح مزايا برامج الولاء وسرد سياسات الشحن والإرجاع والرد على الأسئلة الشائعة أو توفير محتوى "نبذة عنا".
* لإضافة رسائل مخصصة في صفحة تفاصيل المنتج. (على سبيل المثال، "شحن مجاني للأوامر التي تزيد عن 50 دولار").
* بالنسبة لإخلاء المسؤولية وتفاصيل جهة الاتصال على صفحات تفاصيل المنتج وصفحات سلة التسوق وصفحات السداد مع الخروج والصفحات الأخرى (على سبيل المثال، "تخضع عمليات الشحن والإرجاع لسياسات المتجر").

## <a name="text-block-module-properties"></a>خصائص وحدة كتلة النص

| اسم الخاصية     | قيمة                                            | ‏‏الوصف |
|-------------------|--------------------------------------------------|-------------|
| نص منسق         | نص منسق                                        | نص الفقرة. يتم دعم بعض إمكانيات النص المنسق الأساسية، مثل النص الغامق والمُسطر والمائل. |
| اسم فئة مخصصة | اسم فئة أوراق الأنماط المتتالية (CSS)        | اسم فئة CSS مخصصة CSS يوفرها المطور لتنسيق هذه الوحدة. يجب تعريف اسم الفئة في حزمة النسق. |
| حجم الخط         | **صغير**أو **متوسط** أو **كبير** أو **كبير‏‎ جدًا** | حجم خط المحتوى. |

## <a name="add-a-text-block-module-to-a-page"></a>إضافة وحدة كتلة نص إلى صفحة

لإضافة وحدة كتلة نص إلى صفحة جديدة وتعيين الخصائص المطلوبة، اتبع الخطوات التالية.

1. إنشاء قالب صفحة تُسمى **قالب المحتوى**. 
1. في فتحة **النص الأساسي** ، أضف الوحدة النمطية **الصفحة الافتراضية** .
1. انشر القالب بعد الانتهاء من تحريره.
1. استخدم قالب المحتوى الذي قمت بإنشاءه للتو لإنشاء صفحة تُسمى **صفحة المحتوى**.
1. في الفتحة **الرئيسية** للصفحة الجديدة، قم بإضافة وحدة الحاوية.
1. في جزء الخاصية لوحدة الحاوية، عيّن خاصية **العرض** إلى **ملء الحاوية**.
1. أضف وحدة كتلة نص إلى وحدة الحاوية. 
1. في جزء الخصائص لوحدة كتلة النص، أضف نصًا إلى حقل **النص المنسق**.
1. انشر الصفحة بعد الانتهاء من تحريرها.

## <a name="additional-resources"></a>الموارد الإضافية

[نظرة عامة حول أدوات البداية](starter-kit-overview.md)

[وحدة الشعار الترويجي](add-alert.md)

[وحدة نمطية دوارة](add-carousel.md)

[وحدة كتلة المحتوى](add-hero-module.md)

[وحدة نمطية لمشغل الفيديو](add-video-player.md)
