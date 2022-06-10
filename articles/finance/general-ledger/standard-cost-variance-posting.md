---
title: ترحيل فرق التكلفة المعيارية
description: يوفر هذا الموضوع معلومات حول إعداد ملفات تعريف الترحيل لتقدير التكاليف القياسية.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventItemGroup
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: bc4f1bd7c1bf7a8f214f20460b10d371d8f3c790
ms.sourcegitcommit: 1ea145dc606e243c7f51d91a5c0dd9e385bbda4a
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/25/2022
ms.locfileid: "8804593"
---
# <a name="standard-cost-variance-posting"></a>ترحيل فرق التكلفة المعيارية

عند استخدام التكلفة القياسية لمنتج واحد أو أكثر في مؤسستك، يجب عليك تكوين [المتطلبات الأساسية لتقدير التكاليف القياسية](/supply-chain/cost-management/prerequisites-standard-costs.md). يشرح هذا الموضوع حسابات الترحيل المطلوبة للخطوة 3 من المتطلبات الأساسية، "تعيين حسابات دفتر الأستاذ لترحيلات العناصر المرتبطة بفروق التكلفة القياسية."

يمكن أن تحدث أنواع مختلفة من الفروق لأوامر الشراء والإنتاج. للحصول على أمثلة على فروق الإنتاج، انظر [المصادر المشتركة لفروق الإنتاج](/supply-chain/cost-management/common-sources-of-production-variances.md). تحدث فروق سعر أمر الشراء عند استخدام التكلفة القياسية لصنف تم شراؤه، وهناك فرق بين التكلفة القياسية للمنتج والمبلغ المفوتر في أمر الشراء.

## <a name="sample-posting-profile-configuration"></a>تكوين عينة ملف تعريف الترحيل

يعرض الجدول التالي أمثلة على أنواع الترحيل الافتراضية. يتضمن عينة من الحسابات الرئيسية والأوصاف.

- يشير العمود "المدين/الدائن؟" يشير العمود إلى ما إذا كانت المعاملة عادةً مدين أو ائتمان. في بعض الحالات، يمكن للمعاملة ترحيل إما عمليات خصم أو ائتمانات.
- يشير العمود "حساب المقاصة" إلى أن نوع الترحيل هو حساب مقاصة. بمعنى آخر، يتم عكس المبلغ الذي تم ترحيله في هذا الحساب تلقائيًا عند ترحيل حركة لاحقة.
- يشير عمود "P/F" إلى نوع الترحيل. يمثل "P" الترحيل الفعلي، ويمثل الحرف "F" الترحيل المالي.
- يشير العمود "متابعة" إلى ما إذا كان الحساب الرئيسي لنوع الترحيل هو عادةً نفس الحساب الرئيسي لنوع نشر آخر. على وجه التحديد، يشير إلى نوع الترحيل المستخدم عادةً.

> [!NOTE]
> الحسابات الرئيسية وأسماء الحسابات الرئيسية في الجدول هي اقتراحات. نوصي بالعمل مع المحاسبين لتحديد التكوين الأفضل لاحتياجات عملك.

| نوع الترحيل | مثال على الحساب الرئيسي | مثال على اسم الحساب الرئيسي | نوع الحساب | المدين/الدائن؟ | حساب مقاصة. | P/F | متابعة | ‏‏الوصف‬ |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-----|--------|-------------|
| فرق سعر الشراء | 510310 | فرق سعر الشراء | المصروفات | أي واحد | لا | الجمعة | غير قابل للتطبيق | يتم استخدام هذا الحساب عندما يكون هناك تباين بين سعر الشراء والتكلفة القياسية في أمر الشراء. |
| إعادة تقييم تكلفة المخزون | 510330 | إعادة تقييم تكلفة المخزون | المصروفات | أي واحد | لا | الجمعة | غير قابل للتطبيق | يتم استخدام هذا الحساب عند تنشيط إصدار تكلفة جديد لعنصر تكلفة قياسية لإعادة تقييم المخزون الفعلي. |
| نسبة الفرق في تغيير االتكلفة | 510320 | نسبة الفرق في تغيير االتكلفة | المصروفات | أي واحد | لا | الجمعة | غير قابل للتطبيق | يتم استخدام هذا الحساب عندما يكون هناك اختلاف في التكاليف القياسية بين المواقع، أو عند إرجاع عنصر وهناك تغيير بين التكلفة القياسية الأصلية والتكلفة القياسية الحالية للمنتج. |
| نسبة فرق حجم دفعة الإنتاج | 510370 | نسبة فرق حجم دفعة الإنتاج | المصروفات | أي واحد | لا | الجمعة | غير قابل للتطبيق | يتم استخدام هذا الحساب عند وجود اختلافات بين أساس حساب قائمة مكونات الصنف والكمية الفعلية لحساب تكلفة أمر الإنتاج. |
| فرق سعر الإنتاج | 510340 | فرق سعر الإنتاج | المصروفات | أي واحد | لا | الجمعة | غير قابل للتطبيق | يتم استخدام هذا الحساب عند وجود اختلافات في الأسعار بين التكلفة المقدرة والتكلفة الفعلية لأمر إنتاج. |
| نسبة الفرق في كمية الإنتاج | 510350 | نسبة الفرق في كمية الإنتاج | المصروفات | أي واحد | لا | الجمعة | غير قابل للتطبيق | يتم استخدام هذا الحساب عند وجود اختلافات في الكمية بين التكلفة المقدرة والتكاليف الفعلية لأمر إنتاج. |
| نسبة فرق تبديل الإنتاج | 510360 | نسبة فرق تبديل الإنتاج | المصروفات | أي واحد | لا | الجمعة | غير قابل للتطبيق | يتم استخدام هذا الحساب عند وجود استهلاك غير متوقع في أمر إنتاج. |
| تقريب نسبة الفرق | 618160 | الفرق التقريبي | المصروفات | أي واحد | لا | الجمعة | غير قابل للتطبيق | يتم استخدام هذا الحساب عند وجود فرق تقريب عند حساب تكاليف الإنتاج من التكاليف القياسية. |