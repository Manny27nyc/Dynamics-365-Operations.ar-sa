---
title: تاريخ سجل ضريبة القيمة المضافة للمورد
description: يوفر هذا الموضوع معلومات حول ميزة لتمكين سجل ضريبة القيمة المضافة للمورّد
author: anasyash
ms.date: 01/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: intro-internal
ms.search.region: global
ms.author: anasyash
ms.search.validFrom: 2022-01-15
ms.dyn365.ops.version: AX 10.0.24
ms.openlocfilehash: 882d5a8718d819cff80bfa5b86e054a39e9db159
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 01/15/2022
ms.locfileid: "7992054"
---
# <a name="date-of-vendor-vat-register"></a>تاريخ سجل ضريبة القيمة المضافة للمورد

في الإصدار 10.0.24 من Microsoft Dynamics 365 Finance، يتوفر حقل جديد **تاريخ سجل ضريبة القيمة المضافة للمورّد‬** لفواتير المورّد. يحدد هذا الحقل تاريخ التوريد الخاضع للضريبة الخاص بالشراء.

لتمكين الحقل الجديد، انتقل إلى مساحة عمل **إدارة الميزات**، وابحث عن الميزة  **تمكين تاريخ سجل ضريبة القيمة المضافة للمورّد في فواتير المورّد**، ثم حدد **التمكين الآن**.

يمكن أن تحتوي الفواتير الواردة من المورّدين على تاريخين: التاريخ الذي أصدر فيه المورّد الفاتورة وتاريخ التوريد الخاضع للضريبة (أي التاريخ الذي فرض فيه المورّد ضريبة القيمة المضافة [VAT] المستحقة الدفع). قد يختلف هذين التاريخين في بعض السيناريوهات.

يمكنك خصم مبلغ ضريبة القيمة المضافة الواردة لفاتورة شراء وتضمين تلك الفاتورة في تقارير ضريبة القيمة المضافة لاحقًا، في تاريخ يختلف عن التاريخين المذكورين سابقًا. يخضع هذا التاريخ لقواعد التشريعات المحلية المتعلقة بخصم ضريبة القيمة المضافة الواردة المؤجلة لبعض السيناريوهات. وهو يختلف باختلاف البلد أو المنطقة.

تتطلب بعض تقارير ضريبة القيمة المضافة، مثل [تقرير بيان مراقبة ضريبة القيمة المضافة](emea-cze-vat-declaration-tax-declaration-model.md#vat-control-statement) في جمهورية التشيك، الإبلاغ عن تاريخ التوريد الخاضع للضريبة لمستند الشراء. يجب الإبلاغ عن هذا التاريخ حتى تتمكن السلطات الضريبية من تسوية تقارير ضريبة القيمة المضافة بين الأطراف المقابلة.

في Finance، يمكنك تحديد التواريخ في الحقول التالية:

- **تاريخ الفاتورة** – التاريخ الذي تم فيه إصدار الفاتورة من قبل المورّد.
- **تاريخ سجل ضريبة القيمة المضافة** – تاريخ خصم مبلغ ضريبة القيمة المضافة لفاتورة الشراء.
- **تاريخ سجل ضريبة القيمة المضافة للمورّد** -تاريخ التوريد الخاضع للضريبة الخاص بالمورّد.
- **تاريخ استلام المستند** – التاريخ الذي استلمت فيه الفاتورة.

هذه الحقول مضمنة في الصفحات التالية:

- فاتورة المورد
- سجل فواتير المورّد
- الموافقة على فاتورة المورّد
- دفتر يومية فاتورة المورّد

بعد ترحيل فاتورة المورّد، يمكنك مراجعة التواريخ في الصفحتين **دفتر يومية الفاتورة** و **حركات المورّد**.