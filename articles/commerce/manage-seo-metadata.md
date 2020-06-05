---
title: إدارة بيانات تعريف SEO
description: يوضح هذا الموضوع كيفية إدارة بيانات تعريف تحسين محرك البحث في Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 74229628e48ffb8ac974acd868e325eeca77d91e
ms.sourcegitcommit: 7a1d01122790b904e2d96a7ea9f1d003392358a6
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/17/2020
ms.locfileid: "3270035"
---
# <a name="manage-seo-metadata"></a>إدارة بيانات تعريف SEO


[!include [banner](includes/banner.md)]

يوضح هذا الموضوع كيفية إدارة بيانات تعريف تحسين محرك البحث في Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>نظرة عامة

يمكن إدارة بيانات تعريف تحسين محرك البحث لموقع باستخدام خريطة الموقع وبيانات تعريف الصفحة.
    
## <a name="site-maps"></a>خرائط المواقع

خريطة الموقع هي عبارة عن قائمة يمكن للجهاز قراءتها، بتنسيق XML، للصفحات الموجودة على موقع الويب الخاص بك. والهدف منها هو استخدامها من قبل محركات البحث، بحيث يمكنها توفير نتائج بحث أفضل من الموقع الخاص بك. يمكن تضمين خرائط المواقع يدويًا من خلال محركات البحث أو نشرها في ملف robots.txt.

يدعم تطبيق Dynamics 365 Commerce الإنشاء التلقائي لخرائط المواقع. يتم تحديث خرائط المواقع تلقائيًا عند نشر الصفحات وإلغاء نشرها.

### <a name="turn-on-site-map-generation"></a>تشغيل إنشاء خريطة الموقع

1. سجل الدخول إلى أداة التأليف.
1. تحت **المواقع**، حدد **شركه الاتحاد للتصنيع** (أو اسم موقعك).
1. في جزء التنقل علي اليسار، حدد **إدارة الموقع**.
1. تأكد من تشغيل الخيار **خريطة الموقع ممكنة**.

## <a name="page-metadata"></a>بيانات تعريف الصفحة

يتيح لك تطبيق Dynamics 365 Commerce إدارة بيانات تعريف تحسين محرك البحث للصفحات الفردية. يمكنك عرض هذه المعلومات وتعديلها في الجزء **خصائص SEO** لحاوية الصفحة. يتم حاليًا اعتماد خصائص بيانات تعريف SEO التالية:

- المسمى الوظيفي
- ‏‏الوصف
- كلمات SEO الأساسية
- تسميات Aria
- noindex
- nofollow
- noarchive
- nocache
- noOpenDirectoryProject
- nosnippet
- noImageIndex
- unavailableAfter

### <a name="modify-page-metadata"></a>تعديل بيانات تعريف الصفحة

لتعديل بيانات تعريف صفحة، اتبع الخطوات التالية:

1. ضمن **المواقع**، حدد **شركه الاتحاد للتصنيع** (أو اسم موقعك).
1. في جزء التنقل على اليسار، حدد **الصفحات**.
1. حدد الصفحة الرئيسية لفتحها في محرر الصفحة.
1. في شريط الأوامر، حدد **تحرير**.
1. في جزء الخصائص الموجود على اليسار، قم بتوسيع **علامات التعريف الافتراضية**.
1. لإضافة علامة تعريف جديدة، حدد **إضافة**، ثم أدخل العلامة في الحقل. لإزالة علامة تعريفموجودة، حدد رمز سلة المهملات على اليمين.
1. حدد **حفظ**، ثم قم بتحديد **إنهاء التحرير**.
1. في حقل **التعليقات**، أدخل **علامات التعريف المحدثة**، ثم حدد **موافق**.
1. حدد **معاينة** لمعاينه الصفحة الخاصة بك. عند الانتهاء، قم بإغلاق علامة تبويب المعاينة للرجوع إلى أداة التأليف.
1. حدد **نشر**.

## <a name="additional-resources"></a>الموارد الإضافية

[تعديل صفحة موقع موجودة](modify-existing-page.md)

[إضافة صفحة موقع جديدة](add-new-page.md)

[تحديد تخطيطات الصفحة](select-page-layouts.md)

[حفظ صفحة ومعاينتها ونشرها](save-preview-publish-page.md)

[إثراء صفحة منتج](enrich-product-page.md)

[إثراء الصفحة المنتقل إليها‬ لفئة](enrich-category-page.md)

[التحقق من إمكانية الوصول إلى محتوي الصفحة](verify-accessibility.md)