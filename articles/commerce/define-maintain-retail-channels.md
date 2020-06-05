---
title: تحديد والاحتفاظ بقنوات البيع بالتجزئة
description: يوفر هذا الموضوع نظرة عامة على عملية إعداد المتاجر التقليدية، والتي يشار إليها كمتاجر في Dynamics 365 Commerce. وهي تتضمن معلومات حول المهام التي يجب إتمامها قبل إعداد متجر وبعده.
author: mugunthanm
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailStoreTable, RetailStoreTableListPagePreviewPane
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16481
ms.assetid: 14496d96-1c72-43ce-a2e7-8467bab4ae46
ms.search.region: Global
ms.search.industry: Retail
ms.author: mumani
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 0fbca2c9178cd372653287afdf72deaf75442604
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057904"
---
# <a name="define-and-maintain-retail-channels"></a>تحديد قنوات البيع بالتجزئة والاحتفاظ بها

[!include [banner](includes/banner.md)]

يوفر هذا الموضوع نظرة عامة على عملية إعداد المتاجر التقليدية، والتي يشار إليها كمتاجر في Dynamics 365 Commerce. وهي تتضمن معلومات حول المهام التي يجب إتمامها قبل إعداد متجر وبعده.

تدعم التجارة قنوات متعددة، مثل المتاجر عبر الإنترنت ومراكز الاتصال والمتاجر التقليدية. يُعرف المتجر التقليدي باسم متجر. وقد يكون لكل متجر طرق الدفع الخاصة ومجموعات الأسعار وسجلات نقاط البيع (POS) وحسابات الإيرادات والمصروفات وفريق العمل. ويجب إعداد كل هذه العناصر للمتجر قبل إنشائه. وبعد إنشاء المتجر، يمكنك تعيين المنتجات التي ترغب في احتواء المتجر عليها. يمكنك أيضًا تعيين الموظفين والسجلات والعملاء للمتجر. وأخيراً، تقوم بإضافة المتجر الجديد إلى تدرج هرمي للمؤسسات.

## <a name="setting-up-stores"></a>إعداد المتاجر

قبل إعداد متجر في التجارة، يجب إتمام بعض مهام المتطلبات الأساسية. يمكنك بعد ذلك إنشاء المتجر وإضافة التفاصيل.

### <a name="prerequisites"></a>المتطلبات الأساسية

يجب إتمام المهام التالية قبل أن تتمكن من إعداد متجر:

1. تكوين بنية المؤسسة الخاصة بك وإعداد تدرجات هرمية للمؤسسات لعمليات فرز البيع بالتجزئة والتزويد و‏‫إعداد التقارير.
2. إعداد ‏‫مستودع‬ لتمثيل المتجر.
3. إعداد التسلسلات الرقمية للمتاجر وكشوف حساباتالمتجر و‏‫إيصالات كشف الحساب‬.
4. تكوين معلمات التجارة.
5. إعداد طرق الدفع التي يقبلها المتجر.
6. لمعالجة حركات بطاقات الائتمان في سجلات نقطة البيع، يمكن أيضًا إعداد خدمات الدفع.
7. إعداد مجموعات ضريبة المبيعات
8. إعداد المنتجات. وكجزء من هذه المهمة، ستكون مسؤولاً أيضًا عن إعداد التدرجات الهرمية للمنتج ومتغيرات المنتج وعمليات فرز المنتجات.
9. إعداد مجموعات سعر المنتج.
10. إعداد تسعير المنتج. وكجزء من هذه المهمة، يمكنك أيضًا إعداد تسويات الأسعار والخصومات وفترات الخصم.
11. إعداد أعضاء الفريق.

    > [!NOTE]
    > يجب أيضًا تعيين الأذونات المناسبة للعاملين، حتى يمكنهم تسجيل الدخول وتنفيذ المهام باستخدام نظام نقطة البيع.

12. تكوين ملفات تعريف نقطة البيع لتعيينها للمتجر. تتضمن هذه المهمة العديد من المهام، مثل إعداد السجلات و‏‫ملفات التعريف غير المتصلة‬ وتنسيقات الإيصالات وملفات التعريف.

مراجعة كافة المهام المضمنة في المتطلبات الأساسية، وإتمام المهام التي تنطبق عليك فقط.

### <a name="set-up-a-store"></a>إعداد متجر

بعد إتمام مهام المتطلبات الأساسية، عليك إتمام هذه المهام لإعداد تفاصيل المتجر:

1. قم بإنشاء متجر.
2. تعيين مجموعات ضرائب مبيعات للمتجر.
3. تعيين طرق الدفع المقبولة للمتجر.
4. إضافة تفاصيل وصف المنتج للمنتجات التي تقدمها في المتاجر. على سبيل المثال، يمكنك إضافة نص منسق وصور. تظهر تفاصيل المنتج هذه في سياقات مختلفة، مثل سجل نقطة البيع أو التسميات المطبوعة.
5. قم بإضافة المتجر إلى التدرج الهرمي الافتراضي للمؤسسات الذي تم تعيينه لغرض **فرز البيع بالتجزئة** أو **تزويد البيع بالتجزئة** أو **تقارير البيع بالتجزئة**.

### <a name="after-you-set-up-a-store"></a>بعد الانتهاء من إعداد متجر

بعد إدخال تفاصيل المتجر، عليك إتمام هذه المهام لإرسال بيانات المتجر الجديد إلى نقطة البيع:

1. تكوين سجلات نقاط البيع (POS)‬ للمتجر.
2. تعيين عمليات فرز المنتجات للمتجر.
3. معالجة عمليات الفرز لإنشاء قائمة المنتجات المضمنة في عملية الفرز وتوفير المنتجات في المتجر.
4. إرسال البيانات كالتسلسلات الرقمية وملفات تعريف الأجهزة وتخطيطات شاشة نقطة البيع إلى سجلات نقاط البيع.
5. نشر المتجر لإرسال بيانات المتجر إلى نقطة البيع.
6. تشغيل الوظائف لإرسال بيانات المتجر إلى نقطة البيع.

## <a name="organization-hierarchies"></a>التدرجات الهرمية للمؤسسات

تستخدم التجارة التدرجات الهرمية للمؤسسات لهيكلة القنوات. تمثل التدرجات الهرمية للمؤسسات العلاقات بين المؤسسات التي تتألف منها أعمالك. عند إعداد المتاجر، يمكنك إضافتها إلى تدرج هرمي للمؤسسات. وقتئذٍ تتشارك المتاجر البيانات المستخدمة لعمليات الفرز، والتزويد، وإعداد التقارير.

> [!NOTE]
> لاستخدام وظيفة مبيعات Commerce، يجب تمكين مفتاح التكوين الخاص بـ **‏‫شحن إلى متعدد‬** . يمكن العثور علي مفتاح التكوين هذا في مفاتيح **تكوين التجارة** ضمن **‏‫إدارة النظام‬**\> **إعداد** \> **تكوين الرخصة**. يُطلب ذلك نظرًا لعمليات تحقق متعددة بناءً على عنوان التسليم الذي تم تكوينه على مستوى سطر أمر المبيعات.
