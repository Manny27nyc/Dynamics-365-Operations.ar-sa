---
title: وحدة الشعار الترويجي
description: يتناول هذا الموضوع وحدات الشعارات الترويجية ويصف كيفية إضافتها إلى صفحات الموقع في Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 12cabbf0b8d9f337f15a8cd6cb1f2a85100b75f7
ms.sourcegitcommit: 7a1d01122790b904e2d96a7ea9f1d003392358a6
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/17/2020
ms.locfileid: "3269764"
---
# <a name="promo-banner-module"></a>وحدة الشعار الترويجي


[!include [banner](includes/banner.md)]

يتناول هذا الموضوع وحدات الشعارات الترويجية ويصف كيفية إضافتها إلى صفحات الموقع في Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>نظرة عامة

تستخدم وحدات الشعارات الترويجية لعرض رسائل المعلومات المضمنة في الصفحة. ويُمكن استخدامها للعروض على مستوى الموقع التي تظهر في كافة صفحات موقع التجارة الإلكترونية. 

تدعم وحدات الشعارات الترويجية رسالة نصية وارتباطًا. إذا تمت إضافة رسائل متعددة إلى وحدة شعار ترويجي، تصبح شعارًا دوارًا يسمح للعملاء بالتنقل عبر الرسائل. 

يتم التحكم في وحدات الشعارات الترويجية بواسطة البيانات من نظام إدارة المحتوى (CMS) ويُمكن وضعها في أي صفحة.

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a>أمثلة للاستخدام حول الشعارات الترويجية في التجارة الإلكترونية

يمكن استخدام الشعارات الترويجية في رأس الموقع لإظهار العروض أو الرسائل الترويجية على مستوى الموقع، كما في الأمثلة التالية.

"تنتهي المبيعات السنوية خلال 10 أيام" 

"قم بحفظ big مع عمليات بيع العودة إلى المدرسة. تسوق الآن. "

## <a name="promo-banner-module-properties"></a>خصائص وحدة الشعار الترويجي

| اسم الخاصية             | قيمة                              | ‏‏الوصف |
|---------------------------|------------------------------------|-------------|
| رسائل الافتة           | نص وارتباطات                     | مجموعة من النصوص والارتباطات. |
| تشغيل تلقائي                  | **صحيح** أم **خطأ**              | قيمة تشير إلى ما إذا كان يتم التنقل عبر الرسائل بشكل تلقائي، إذا تم تكوين رسائل متعددة. |
| فاصل المراحل الانتقالية للشرائح | عدد المللي ثواني      | الفاصل الزمني الذي يتم استخدامه للتنقل بين الرسائل. |
| السماح بالاستبعاد             | **صحيح** أم **خطأ**              | إذا تم تعيين القيمة إلى **صحيح**، بإمكان العملاء استبعاد التنبيه. |
| إظهار الذراع الدوار     | **صحيح** أم **خطأ**              | قيمة تشير إلى ما إذا كان يجب عرض القيمة الأذرع الدوارة، لتمكين العملاء من التنقل بطريقة يدوية عبر عناصر الشعار المتعددة. |
| محاذاة النص            | **اليمين**, **اليسار**, أو **الوسط** | محاذاة النص في وحدة الشعار الترويجي. |
| الارتباط                      | عنوان URL                              | عنوان URL لارتباط اختياري. |

## <a name="add-a-promo-banner-module-to-a-page"></a>إضافة وحدة شعار ترويجي إلى صفحة 

لإضافة وحدة شعار ترويجي إلى صفحة وتعيين الخصائص المطلوبة، اتبع الخطوات التالية.

1. حدد **جديد**، لإنشاء قالب صفحة.
1. في مربع الحوار **قالب جديد**، تحت **اسم القالب**، أدخل **قالب شعار ترويجي**، ثم حدد **موافق**.
1. ضمن **المخطط التفصيلي للصفحة**، أضف وحدة **الصفحة الافتراضية** إلى فتحة **النص الأساسي**. 
1. حدد **إنهاء التحرير** لإيداع القالب، ثم حدد **نشر** لنشره. 
1. استخدم القالب الذي أنشأته للتو لإنشاء صفحة مسماة **صفحة الشعار الترويجي**. 
1. في الفتحة **الرئيسية** للصفحة الجديدة، قم بإضافة وحدة الحاوية. 
1. في الجزء إلى اليسار، قم بتعيين قيمة **العرض** إلى **ملء الحاوية**.
1. ضمن **المخطط التفصيلي للصفحة**، أضف وحدة الشعار الترويجي إلى وحدة الحاوية.
1. في إعدادات وحدة الشعار الترويجي، أضف رسالة شعار واحدة أو أكثر. بإمكان كل رسالة أن تتضمن نصًا مع ارتباط. يُمكنك تحرير الخصائص الأخرى إذا كنت ترغب في تخصيص الوحدة.
1. حدد **حفظ**، ثم حدد **معاينة** لمعاينة الصفحة. في أعلى الصفحة، يجب أن ترى تنبيهًا يُظهر النص الذي قمت بإضافته.
1. حدد **إنهاء التحرير** لإيداع الصفحة، ثم حدد **نشر** لنشرها. 

> [!NOTE]
> يتم استخدام الشعار الترويجي عادةً في فتحة رأس الصفحة أو فتحة رأس فرعي.


## <a name="additional-resources"></a>الموارد الإضافية

[نظرة عامة حول أدوات البداية](starter-kit-overview.md)

[وحدة نمطية دوارة](add-carousel.md)

[وحدة كتلة النص](add-content-rich-block.md)

[وحدة كتلة المحتوى](add-hero-module.md)

[وحدة نمطية لمشغل الفيديو](add-video-player.md)