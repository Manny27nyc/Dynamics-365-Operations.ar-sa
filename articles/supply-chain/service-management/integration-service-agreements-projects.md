---
title: "التكامل للمشاريع واتفاقيات الخدمات"
description: "عند التعامل مع اتفاقيات الخدمة وبنود اتفاقيات الخدمات، يتم استخدام البيانات التي تم إعدادها في المناطق في إدارة المشاريع ومحاسبتها."
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 9f2640eae299411d633c68795bc16883dbb5eeaf
ms.contentlocale: ar-sa
ms.lasthandoff: 05/08/2018

---

# <a name="integration-for-service-agreements-and-projects"></a>التكامل للمشاريع واتفاقيات الخدمات 

[!include [banner](../includes/banner.md)]


عند التعامل مع اتفاقيات الخدمة وبنود اتفاقيات الخدمات، يتم استخدام البيانات التي تم إعدادها في المناطق التالية في **إدارة المشاريع ومحاسبتها**.

## <a name="project-prices"></a>أسعار المشاريع

يتم اشتقاق سعر التكلفة والمبيعات لحركة اتفاقية خدمة من إعداد سعر التكلفة الذي ينطبق على المشروع الذي تم إرفاقه باتفاقية الخدمة. ويمكن إعداد أسعار التكلفة والمبيعات حسب المشروع والموظف والفئة. 

## <a name="project-validation"></a>التحقق من صحة المشروع

يمكن تقييد المشاريع والموظفين والفئات التي تكون متاحة للتحديد في بند اتفاقية الخدمة عن طريق إعداد التحقق من الصحة في **إدارة المشاريع ومحاسبتها**. ويمكن باستخدام إعداد التحقق من الصحة تجميع الموظفين والمشاريع والفئات لأجل التحكم بالوصول. 

## <a name="project-line-properties"></a>خصائص بند المشروع

يتم إدخال خاصية بند لبند اتفاقية الخدمة تلقائيًا.

يتم إنشاء خواص البنود في نموذج **خواص البنود** في **إدارة المشاريع والمحاسبة**. يتم إرفاق خاصية البند التي تم إدخالها في اتفاقية الخدمة بالمشروع الذي تم تحديده لاتفاقية الخدمة وبالتالي يتم استيراده عن طريق بند اتفاقية الخدمة. 

## <a name="default-offset-accounts"></a>حسابات مقابلة افتراضية

إذا تم إدخال حركة مصروفات، فسيتم تلقائيًا تحديد حساب مقابل افتراضي للمصروفات للحركة. ويتم إعداد حساب المصروفات الافتراضي للمشروع الذي تم إرفاقه باتفاقية الخدمة الحالية.

## <a name="project-categories"></a>فئات المشروع

يتم إعداد الفئات المتاحة لبنود اتفاقية الخدمة في النموذج **فئات المشروع** في **إدارة المشاريع ومحاسبتها**. 

> [!NOTE]
> <P>تتوفر الفئات التي تم تحديد خانة اختيار <STRONG>نشط في دفاتر اليومية</STRONG> بالنسبة لها في علامة تبويب <STRONG>المشروع</STRONG> في نموذج <STRONG>فئات المشروع</STRONG> للتحديد. ومع ذلك، إذا تم تحديد خانة اختيار <STRONG>فئات غير نشطة</STRONG> في علامة تبويب <STRONG>دفاتر يومية</STRONG> في نموذج <STRONG>محددات إدارة المشاريع والمحاسبة</STRONG>، فإن كل الفئات تصبح متوفرة للتحديد.</P>

## <a name="project-parameters"></a>محددات المشروع

إذا كان حقل **عاملون تم إنهاء خدمتهم** في علامة تبويب **دفاتر يومية** في نموذج **محددات إدارة المشاريع والمحاسبة** محدداً، فيمكنك تحديد الموظفين غير النشطين والموظفين النشطين في نماذج **اتفاقيات الخدمة** و**أوامر الخدمة**.

أيضًا، يمكنك تمكين حقلي **وقت البدء** و**وقت الانتهاء** في علامة تبويب **المشروع** في نموذج **أوامر الخدمة** لإدخال أوقات البدء والانتهاء لبنود أوامر الخدمة.

## <a name="enable-the-starting-and-ending-time-feature-for-service-orders"></a>تمكين ميزة أوقات البدء والانتهاء لأوامر الخدمة

1.  انقر فوق **إدارة المشاريع‬ والمحاسبة** \> **الإعدادات** \> **محددات إدارة المشاريع‬ والمحاسبة**.

2.  انقر فوق علامة تبويب **دفاتر يومية** ثم حدد خانة الاختيار **إظهار أوقات البدء/الانتهاء**.

3.  ‏‫انقر فوق **‏‫إدارة المشاريع والمحاسبة** \> **الإعداد** \> **دفاتر اليومية‬** \> **أسماء دفاتر اليومية**.

4.  حدد اسم دفتر اليومية الذي تم إرفاقه بأمر الخدمة.

5.  انقر فوق علامة تبويب **عام**، ثم حدد خانة الاختيار **إظهار أوقات البدء/الانتهاء**.


> [!NOTE]
> <P>حدد اسم دفتر اليومية لأمر الخدمة في الحقل <STRONG>الساعة</STRONG> في علامة التبويب <STRONG>دفاتر اليومية</STRONG> في النموذج <STRONG>محددات إدارة الخدمة</STRONG>.</P>





