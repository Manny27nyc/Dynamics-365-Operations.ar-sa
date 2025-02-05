---
title: مدفوعات المورد لمبلغ جزئي
description: في بعض الأحيان، قد تسدد دفعة لأحد المورّدين تكون أقل من مبلغ الفاتورة. توضح هذه المقالة مختلف الخيارات التي يتم استخدامها لمعالجة هذه الحالة.
author: abruer
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14321
ms.assetid: 9a17075e-5325-4d55-a1e5-1791b8c460a0
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a1be00ef4bd432bc0252e0588a3108b5b0f570e4
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/05/2022
ms.locfileid: "8716259"
---
# <a name="vendor-payments-for-a-partial-amount"></a>دفعات المورد لمبلغ جزئي

[!include [banner](../includes/banner.md)]

في بعض الأحيان، قد تسدد دفعة لأحد المورّدين تكون أقل من مبلغ الفاتورة. توضح هذه المقالة مختلف الخيارات التي يتم استخدامها لمعالجة هذه الحالة. تتوقف الخيارات التي تتوفر لك على تكوين أعمالك ومتطلباتها. 

## <a name="cash-discount-amounts"></a>مبالغ الخصم النقدي

يستطيع المورد أن يقدم لك خصمًا نقديًا لدفع فاتورة قبل تاريخ الاستحقاق. على سبيل المثال، يمكنك إدخال فاتورة بمبلغ 100.00 وتحدد خصمًا نقديًا بنسبة 2 في المائة، إذا تم دفع الفاتورة في غضون 10 أيام. ومدد تاريخ الاستحقاق 30 يومًا. ‏‫وفي حالة استخدام مقترح دفع الخصم النقدي كمعيار لتحديد فاتورة، وتشغيل المقترح في أو قبل تاريخ الخصم النقدي، يتم تحديد الفاتورة للدفع، ويتم إنشاء الدفعة بمبلغ 98.00. كما يمكن الحصول على خصم نقدي لدفعة فريدة تم إنشاؤها يدوياً.‬

## <a name="partial-payments-with-cash-discounts"></a>المدفوعات الجزئية مع الخصومات النقدية
عندما تقوم بسداد دفعة جزئية، قد تخطط لسداد دفعة جزئية إضافية لتسوية الفاتورة بالكامل. وللحصول على خصم نقدي لدفعة جزئية، يجب عليك تعيين خيار **حساب الخصومات النقدية لمدفوعات جزئية** إلى **نعم** في صفحة **معلمات الحسابات الدائنة**. 

على سبيل المثال، تتلقى خصمًا نقديًا بنسبة 2 في المائة، إذا تم دفع الفاتورة في غضون 10 أيام بعد صدورها. ويتم ترحيل فاتورة بمبلغ 100.00. ‏‫إذا قمت بسداد دفعة بمبلغ 49.00 في غضون 10 أيام، أدخل دينًا بمبلغ 49.00 في دفتر يومية مدفوعات. وعند تسوية الدفعة الجزئية في صفحة **تسوية الحركات المفتوحة**، يظهر **1.00** في حقل **مبلغ الخصم النقدي المُراد الحصول عليه**. 

> [!NOTE] 
> إذا قمت بإدخال دفعة جزئية وتركت مبلغ الفاتورة الكامل في حقل **المبلغ المُراد تسويته**، فإنه تتم إعادة حساب حقل **مبلغ الخصم النقدي المراد الحصول عليه** تلقائياً عند ترحيل الحركات.

## <a name="credit-notes-with-cash-discounts"></a>إشعارات الدائن مع الخصومات النقدية
قد تقوم بإرجاع بعض الأصناف في إحدى الفواتير وتتلقى إشعار دائن. إذا تم الحصول على خصم نقدي في الفاتورة الأصلية، فإنه يمكنك طرح قيمة الخصم والحصول على استرداد بالمبلغ الصحيح. وإذا تم تعيين خيار **حساب الخصومات النقدية للإشعارات الدائنة** إلى **نعم** في صفحة **معلمات الحسابات الدائنة**، فإنه يتم حساب الخصم تلقائياً لإشعار الدائن. 

على سبيل المثال، تتلقى خصمًا نقديًا بنسبة 2 في المائة، إذا تم دفع الفاتورة في غضون 10 أيام بعد صدورها. ويتم ترحيل فاتورة بمبلغ 100.00. وفي حالة إعادة البضائع وتلقى إشعار دائن، يمكنك إدخال إشعار الدائن لكامل مبلغ الفاتورة الأصلية 100.00، جنبًا إلى جنب مع الخصم النقدي بنسبة 2 في المائة الذي تم تحديده أيضًا في إشعار الدائن.  وعندما تقوم بعرض إشعار الدائن في صفحة **تسوية الحركات**، يظهر **98.00** في حقل **المبلغ المُراد تسويته** ويظهر **-2.00** في حقل **مبلغ الخصم النقدي**. يتم ترحيل مبلغ الخصم إلى حساب خصم النقدي.

## <a name="overpaymentunderpayment-amounts"></a>مبالغ الدفع بالزيادة/النقصان
قد تقوم بسداد دفعة جزئية يكون فيها المبلغ الذي لا يزال يجب تسويته صغيرًا جداً. على سبيل المثال، قيمة فاتورة المورد تساوي 1,000.00، وتدفع 999.90. إذا كان المبلغ المتبقي أقل من المبلغ الذي تم تعيينه للمدفوعات بالزيادة أو النقصان في صفحة **معلمات الحسابات الدائنة**، فإنه يتم ترحيل الفرق تلقائياً حساب دفتر أستاذ الدفع بالزيادة/النقصان.


للحصول على مزيد من المعلومات، راجع [نظرة عامة على دفع المورّد‬](../cash-bank-management/tasks/vendor-payment-overview.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
