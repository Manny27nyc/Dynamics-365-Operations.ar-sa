---
title: إعداد تكرارات المدفوعات
description: يستخدم Microsoft Dynamics 365 Human Resources تكرارات الدفع لحساب راتب الميزة السنوي وتحديد مبلغ قسط الميزة الذي يدفعه الموظف كل فترة دفع ومدى تكرار عمليات دفع الموفرين.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 74ff97550ee5b47a28ff9815528677b6e685e25b
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/06/2020
ms.locfileid: "3229730"
---
# <a name="set-up-payment-frequencies"></a>إعداد تكرارات المدفوعات

يستخدم Microsoft Dynamics 365 Human Resources تكرارات الدفع لحساب راتب الميزة السنوي وتحديد مبلغ قسط الميزة الذي يدفعه الموظف كل فترة دفع ومدى تكرار عمليات دفع الموفرين.

تستخدم تكرارات دفع الميزة عوامل التحويل لتحويل فترات دفع الميزة بين تكرارات الدفع الشهرية ونصف الشهرية والنصف أسبوعية والأسبوعية واليومية. ويسمح ذلك للشركات بتحديد التبعيات المتداخلة بين تكرارات الدفع خلال خطة ميزة.

تقوم حقول عوامل التحويل بتعريف عامل التحويل من تكرار الدفع إلى فترات الدفع القياسية والسماح للنظام بالقيام بالحسابات بين تكرارات الدفع. يحدد أيضًا مبلغ عامل التحويل مبلغ قسط الميزة الذي يجب أن يدفعه موظف كل فترة تكرار الدفع.

1. في مساحة العمل **إدارة الميزات**، ضمن **إعداد**، حدد **تكرارات الدفع**.

2. حدد **جديد**.

3. حدد قيمًا للحقول التالية:

   | الحقل | ‏‏الوصف |
   | --- | --- |
   | **تكرار الدفع** | اسم تكرار دفع فريد. |
   | **‏‏الوصف** | وصف تكرار الدفع. |
   | **الفترة** | الفترة المناسبة التي يطابق بها تكرار دفع موفر الميزة والموظف بشكل أفضل. تتكون قائمة الفترة من فترات الدفع القياسية. |
   | **عدد فترات الدفع** | عدد فترات الدفع التي تمثل عدد المرات التي يقوم بها موفر الميزة أو الموظفين بالدفع. سيتم استخدام هذا المبلغ لحساب مبلغ راتب الميزة السنوي الخاص بالموظف. |
   | **معامل التحويل السنوي** | عامل التحويل السنوي لتكرار الدفع. على سبيل المثال، عامل التحويل السنوي لتكرار الدفع شهريًا هو: </br></br>(12 دفعة شهرية / 1 سنة) = 12 |
   | **معامل التحويل نصف السنوي** | عامل التحويل نصف السنوي لتكرار الدفع. على سبيل المثال، عامل التحويل نصف السنوي لتكرار الدفع شهريًا هو: </br></br>(12 دفعة شهرية / مرتين سنويًا) = 6 |
   | **معامل التحويل ربع السنوي** | عامل التحويل ربع السنوي لتكرار الدفع. على سبيل المثال، عامل التحويل ربع السنوي لتكرار الدفع شهريًا هو: </br></br>(12 دفعة شهرية / 4 أرباع) = 3 |
   | **معامل التحويل الشهري** | عامل التحويل الشهري لتكرار الدفع. على سبيل المثال، عامل التحويل الشهري لتكرار الدفع شهريًا هو: </br></br>(12 دفعة شهرية / 12 شهرًا) = 1 |
   | **معامل التحويل نصف الشهري** | عامل التحويل نصف الشهري لتكرار الدفع. على سبيل المثال، عامل التحويل نصف الشهري لتكرار الدفع شهريًا هو: </br></br>(12 دفعة شهرية / 24 (2 × الشهر)) = 0.5 | 
   | **معامل التحويل نصف الأسبوعي** | عامل التحويل السنوي لتكرار الدفع. على سبيل المثال، عامل التحويل السنوي لتكرار الدفع شهريًا هو: </br></br>(12 دفعة شهرية / 26 أسبوعًا) = 0.461538 |
   | **معامل التحويل الأسبوعي** | عامل التحويل السنوي لتكرار الدفع. على سبيل المثال، عامل التحويل السنوي لتكرار الدفع شهريًا هو: </br></br>(12 دفعة شهرية / 52 أسبوعًا) = 0.230769 |
   | **معامل التحويل اليومي** | عامل التحويل السنوي لتكرار الدفع. على سبيل المثال، عامل التحويل السنوي لتكرار الدفع شهريًا هو: </br></br>(12 دفعة شهرية / 365 يومًا) = 0.032877 |
   | **معامل التحويل في الساعة** | عامل التحويل السنوي لتكرار الدفع. على سبيل المثال، عامل التحويل السنوي لتكرار الدفع شهريًا هو: </br></br>(12 دفعة شهرية / 2080 ساعة) = 0.005769

4. حدد **حفظ**. 