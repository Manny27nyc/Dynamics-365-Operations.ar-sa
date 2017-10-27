---
title: "تحسينات نقطة البيع للمنتجات المتسلسلة"
description: "يسرد هذا الموضوع التحسينات التي تم إدخالها على المنتجات المتسلسلة لمساعدتك في في توفير الوقت وزيادة إنتاجيتك."
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-08-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 214452d0f40265c0ed9fac7a74844ad89782257d
ms.contentlocale: ar-sa
ms.lasthandoff: 09/29/2017

---

# <a name="pos-improvements-for-serialized-products"></a>تحسينات نقطة البيع للمنتجات المتسلسلة

[!include[banner](includes/banner.md)]

## <a name="overview"></a>نظرة عامة 
استنادًا إلى الإعدادات في إدارة البيع بالتجزئة، يمكن تصنيف المنتجات كمتسلسلة أو غير متسلسلة. عندما تكون المنتجات متسلسلة، يتم تعيين رقم فريد لكل صنف، حيث يساعد هذا الرقم على تعقب الضمانات وتتبع الأصناف وتأكيد الملكية. على الرغم من أن القدرة على توفير أرقام تسلسلية للمنتجات المتسلسلة كانت موجودة في نقطة البيع الحديثة ونقطة بيع المجموعة‬ (POS)، إلا أن هناك تحسينات أضيفت التحسينات لمساعدة موظفي الكاشير على توفير الوقت وزيادة إنتاجيتهم.  

## <a name="pos-improvements"></a>تحسينات نقطة البيع

- **الأرقام التسلسلية غير ضرورية حتى السداد مع الخروج** - في السابق، كان يتعين على موظف الكاشير الذي أضاف منتجًا متسلسلاً إلى الحركة توفير رقم تسلسلي. وقد تحول هذا المطلب إلى مشكلة في سيناريوهات التعامل مع العملاء، إذا برزت فرصة البيع الإضافي لموظفي الكاشير والشركاء. حتى الوصول إلى خطوة الدفع، غالبًا ما كان يتم تحديث المنتجات الموجودة في سلة التسوق. وبالتالي، في كل مرة كان موظف الكاشير يضيف منتجًا جديدًا، كان النظام يطالبه بإدخال رقمه التسلسلي. يتضمن الآن مربع حوار الرقم التسلسلي الزر **إضافة في وقت لاحق‬**. وبالتالي، يستطيع شركاء المبيعات إضافة الصنف إلى الحركة ولكن يمكنهم توفير الرقم التسلسلي فيما بعد. باستطاعة شركاء المبيعات إضافة واستبدال الأصناف المتسلسلة بسرعة في سلة التسوق، ويمكنهم توفير الرقم التسلسلي تمامًا قبل السداد مع الخروج. إذا لم يتم توفير الرقم التسلسلي لأي منتج من المنتجات المتسلسلة، فسيتلقى موظف الكاشير الذي يحاول إكمال الحركة رسالة خطأ. تشير هذه الرسائل إلى وجوب قيام الكاشير توفير الأرقام التسلسلية المفقودة قبل أن يتمكن من المتابعة.

    بالنسبة إلى كل صنف متسلسل حيث تم تخطي الرقم التسلسلي، يظهر تعليق تحت بند الحركة. يشير هذا التعليق إلى أن لم يتم توفير الرقم التسلسلي للصنف. وبالتالي، يستطيع موظف الكاشير العثور بسرعة على الأصناف التي تفتقد إلى رقم تسلسلي.

    توفر أيضًا عملية **إضافة رقم تسلسلي** جديدة الرقم التسلسلي للأصناف التي تفتقد إلى رقم تسلسلي. بعد أن يتم توفير الرقم التسلسلي، لا يمكن تحريره. يجب على موظف الكاشير إلغاء السطر وإضافة المنتج مرة أخرى. 
    
- **الأرقام التسلسلية غير مطلوبة لوضع أوامر العملاء** - يمكن وضع أوامر العملاء في متجر وتنفيذها من متجر آخر. لا يتعين على موظف الكاشير الذي يضع أمر عميل توفير الرقم التسلسلي. سيتم توفير الرقم التسلسلي أثناء خطوة الانتقاء أو الالتقاط. ومع ذلك، يجب توفير رقم تسلسلي لكافة الأصناف التي تم تحديد نوع التسليم **تنفيذ** لها. وإلا، سيتعذر إتمام الحركة.    
- **لا يتم تجميع المنتجات المتسلسلة على شاشة الحركة** – يسمح لك الإعداد **تجميع المنتجات** في مجموعة حقل **الوحدة الطرفية‬** في صفحة **ملف تعريف الوظائف‬** تجميع المنتجات غير المتسلسلة نفسها على شاشة الحركة. عندما يتم تجميع نفس المنتجات، سيكون من الأسهل رؤيتها في شبكة الحركات. ومع ذلك، ولأن الأرقام التسلسلية هي عادةً أرقام فريدة، ولا يحتاج شركاء المبيعات إلى إدخال الأرقام التسلسلية إلا عند السداد مع الخروج، لا ينطبق إعداد **تجميع المنتجات** على المنتجات المتسلسلة. وبالتالي، لن يتم تجميع المنتجات المتسلسلة على شاشة الحركة إذا تم تحديد إعداد **تجميع المنتجات**.
