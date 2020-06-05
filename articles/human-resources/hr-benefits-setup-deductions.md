---
title: تكوين الخصومات
description: استخدم الخصومات في Microsoft Dynamics 365 Human Resources لتحديد مقدار، إن وُجد، الخصم من شيكات أجور العمل للموظف مقابل كل ميزة.
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
ms.openlocfilehash: 5e645c3f098163626cb686aba347897781d7ebc0
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/06/2020
ms.locfileid: "3230052"
---
# <a name="configure-deductions"></a>تكوين الخصومات

استخدم الخصومات في Microsoft Dynamics 365 Human Resources لتحديد مقدار، إن وُجد، الخصم من شيكات أجور العمل للموظف مقابل كل ميزة. الخصومات لها تاريخ سريان، بحيث يمكنك الاحتفاظ بسجل محفوظات خاص بمعلومات الخصم. 

1. في مساحة العمل **إدارة الميزات**، ضمن **إعداد**، حدد **الخصومات**.

2. حدد **جديد**.

3. حدد قيمًا للحقول التالية:

   | الحقل | ‏‏الوصف |
   | --- | --- |
   | **خصم** | معرف فريد يستخدم لتحديد الخصم الخاص بالميزة. |
   | **‏‏الوصف** | وصف الخصم. |
   | **فعالة** | تاريخ البدء. والقيمة الافتراضية هي تاريخ النظام الحالي. |
   | **انتهاء الصلاحية** | تاريخ الانتهاء. القيمة الافتراضية هي 12/31/2154، والتي تشير إلى ابدًا. |
   | **العنوان** | كود العنوان من نظام الرواتب الذي سيستخدمه هذا الخصم لجزء الموظف من الخصم عند معالجة الميزات لكشف الرواتب. يستخدم هذا عند استخدام موفر رواتب من طرف آخر. |
   | **مرجع الخصم في كشف رواتب الموظف** | كود الخصم من نظام كشف الرواتب الذي سيستخدمه هذا الخصم لجزء الموظف من الخصم عند معالجة المزايا لكشف الرواتب. |
   | **عنوان المبلغ** | كود العنوان من نظام الرواتب الذي سيستخدمه مبلغ الخصم هذا لجزء الموظف من الخصم عند معالجة الميزات لكشف الرواتب. عادة ما يستخدم هذا عند استخدام موفر رواتب من طرف آخر. |
   | **يمكن حذف** | يحدد ما إذا كانت القيمة المصدرة من Dynamics 365 for Finance and Operations يمكن أن تؤدي إلى حذف القيمة في نظام الرواتب. |
   | **الأعمدة المقترنة** | يحدد ما إذا كان سيتم تصدير مبلغ العنوان والخصم في أعمدة متجاورة مزدوجة إلى نظام الرواتب. |
   | **تاريخ سريان التغيير** | سيصبح التاريخ الذي يتغير به خصم الميزة ساريًا. في هذا التاريخ، سيقوم النظام تلقائيًا بتغيير خصم الميزات وتحديث كافة خطط الميزات المرتبطة بهذا الخصم، طالما قمت بتشغيل معالجة **تحديث تغيير الخصم**. |
   | **اكتمل تغيير الخصم** | سيتم تحديد خانة الاختيار **اكتمل تغيير الخصم‬** تلقائيًا بمجرد اكتمال تغييرات خصم الميزة عن طريق معالجة تغيير تحديث الخصم. |
   
4. لتتبع التغييرات التي تم إجراؤها على إعداد معدل الميزة والاحتفاظ بها، حدد **إجراءات**، ثم حدد **الاحتفاظ بالإصدارات**.

5. حدد **حفظ**. 