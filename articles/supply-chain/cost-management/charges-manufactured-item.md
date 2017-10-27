---
title: "عرض المصاريف لصنف مصنّع"
description: "تعكس التكاليف الثابتة لصنف مصنّع أوقات إعداد العمليات والمكونات ذات كمية ثابتة أو قيمة خردة ثابتة."
author: AndersGirke
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 274483
ms.assetid: 6f5b851b-c5a7-43ef-b380-0d316667c1ef
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.dyn365.ops.intro: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 66dbd107b47b8a064cbe2e284bcabea47c471089
ms.contentlocale: ar-sa
ms.lasthandoff: 09/29/2017

---

# <a name="display-charges-for-a-manufactured-item"></a>عرض المصاريف لصنف مصنّع

[!include[banner](../includes/banner.md)]


تعكس التكاليف الثابتة لصنف مصنّع أوقات إعداد العمليات والمكونات ذات كمية ثابتة أو قيمة خردة ثابتة.

يمكن عرض المبلغ المحسوب لمصاريف صنف ما مع تكاليف وحدة الصنف. ومع ذلك، تظهر المصاريف في بعض الأحيان كحقول منفصلة، ولا يتم تضمينها في تكاليف وحدة الصنف. عندما تظهر المصاريف كحقول منفصلة، يعرض أحد الحقول إجمالي مبلغ المصاريف، بينما يعرض الحقل الآخر حجم دفعة التكلفة المستخدم لاستهلاك المبلغ. على سبيل المثال، تعرض صفحة سعر الصنف المصاريف كحقلين منفصلين. ومع ذلك، تعرض الصفحة "كامل" إجمالي تكلفة الصنف لكل وحدة، ويتم تضمين التكاليف المستهلكة في تكاليف الوحدة.

يتم دائمًا تضمين المصاريف لصنف مصنّع في تكلفة وحدة الصنف لأغراض التكلفة القياسية. ويمكن تضمينها بشكل اختياري لأغراض التكلفة المخططة. تقوم سياسة في إصدار التكاليف بفرض تضمين المصاريف في تكلفة الصنف المصنّع. عند تنشيط سجل التكلفة لصنف ما، ستقوم بتحديث المصاريف لمعلومات التكلفة الأساسية الخاصة بالصنف، التي تظهر في صفحة سعر الصنف. تظهر المصاريف كحقلين منفصلين، ولا يتم تضمينها في تكلفة وحدة الصنف. وتقوم كل عملية تنشيط بتحديث معلومات التكلفة الأساسية، حتى لو كانت جهود التنشيط تعكس مواقع مختلفة. وبالتالي، يجب عرض معلومات التكلفة الأساسية كمعلومات مرجعية.





