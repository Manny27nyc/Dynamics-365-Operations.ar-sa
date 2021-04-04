---
title: معلمات الشراء وتحديد الموارد للتكلفة المستلمة
description: يوضح هذا الموضوع كيفيه إعداد معلمات الشراء والتوريد ذات الصلة عند استخدام وحدة التكلفة المستلمة.
author: sherry-zheng
manager: tfehr
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SrmParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 49e046a1437917cfa866f690511789496fac2c53
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500732"
---
# <a name="procurement-and-sourcing-parameters-for-landed-cost"></a>معلمات الشراء وتحديد الموارد للتكلفة المستلمة

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

تحتوي صفحة **معلمات الشراء وتحديد الموارد** على إعدادات قليلة ذات صلة خاصة عند استخدامك وحدة **التكلفة المستلمة**. استخدم مربع الحوار **تحديث بنود الأمر** الذي يتم فتحه من صفحة **معلمات الشراء وتحديد الموارد** لتحديد ما إذا كان يجب تحديث بنود أمر الشراء تلقائيًا عند إجراء تغييرات على رأس أمر الشراء.

لإكمال هذا الإعداد، اتبع الخطوات التالية.

1. انتقل إلى **التدبير والتوريد‬ \> الإعداد \> معلمات التدبير والتوريد**.
1. في علامة التبويب **عام**، حدد الارتباط **تحديث بنود الأمر**.
1. يسرد مربع الحوار **تحديث بنود الأمر** الحقول في البيانات الرئيسية للأمر والتي يمكنها أيضا تطبيق تحديثات تلقائية علي الحقول المرتبطة في بنود الأمر. قم بتعيين كل حقل في القائمة إلى إحدى القيم التالية:

    - **دائمًا** – يجب تحديث بنود الأوامر تلقائياً عند تحديث البيانات الرئيسية للأمر.
    - **أبدًا** – يجب ألا يتم تحديث بنود الأوامر عند تحديث البيانات الرئيسية للأمر.
    - **المطالبة** – ستتم مطالبة المستخدم بتحديد ما إذا كان يجب تحديث بنود الأمر أو لا.