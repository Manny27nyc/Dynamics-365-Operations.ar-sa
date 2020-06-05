---
title: إنشاء وتصدير دفعات المورّد باستخدام تنسيق الدفع ISO20022
description: يوضح هذا الإجراء كيفية إنشاء بنود الدفع في دفتر يومية دفع المورّد وإنشاء ملف دفع المورّد باستخدام مثال تحوي الائتمان ISO2022.
author: mrolecki
manager: AnnBe
ms.date: 01/17/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendPaym, SysQueryForm, VendPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ff8a2858bfa96eb1d4b0afa1e48ebd1b578a4431
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143114"
---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a>إنشاء وتصدير دفعات المورّد باستخدام تنسيق الدفع ISO20022

[!include [banner](../../includes/banner.md)]

يوضح هذا الموضوع كيفية إنشاء بنود الدفع في دفتر يومية دفع المورّد وإنشاء ملف دفع المورّد باستخدام مثال تحويل الائتمان ISO2022.

هذا هو الإجراء الخامس من ضمن الإجراءات الخمسة، هدفه توضيح عملية معالجة مدفوعات المورّد باستخدام تكوينات التقارير الإلكترونية. استخدم شركة بيانات العرض التوضيحي DEMF لإكمال هذا المثال.

## <a name="example"></a>مثال

1.    انتقل إلى **الحسابات الدائنة > المدفوعات‬ > دفتر يومية المدفوعات‬**.
2.    انقر فوق **جديد**.
3.    في الحقل **الاسم** أدخل قيمة أو حددها.
4.    انقر فوق **البنود > مقترح الدفع > إنشاء مقترح الدفع**.
5.    وسّع القسم **السجلات المطلوب تضمينها**.
6.    انقر فوق **تصفية**.
7.    في القائمة، حدد صف **جدول المورّدين** وحقل **حساب المورّد**.
8.    في الحقل **المعايير‬**، أدخل قيمة أو حددها. يمكنك تطبيق أي معايير لتحديد حركات المورّد للدفع، لهذا لمثال استخدم DE-001 كحساب مورّد.
12.    وانقر فوق **موافق**.
13.    وانقر فوق **موافق**.
14.    انقر فوق **إنشاء مدفوعات**.
15. أنشئ ملف دفع ISO20022.
    1.    انقر فوق **إنشاء مدفوعات**.
    2.    في الحقل **أسلوب الدفع**، أدخل قيمة أو حددها.
    3.    في الحقل **اسم الملف**، اكتب قيمة. بالنسبة إلى هذا المثال، نظراً للدفع باليورو، سيكون الملف الذي تم إنشاؤه متوافقًا مع SEPA. يمكن أيضًا استخدام تحويل الائتمان ISO20022 بالإضافة إلى تنسيقات دفع أخرى خاصة بالمورّد لإنشاء مدفوعات بعملات أخرى.
    4.    في الحقل **الحساب البنكي**، أدخل قيمة أو حددها.
