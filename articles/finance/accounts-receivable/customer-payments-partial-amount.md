---
title: مدفوعات العميل لمبلغ جزئي
description: في بعض الأحيان، قد يسدد العملاء دفعة أقل من مبلغ الفاتورة. توضح هذه المقالة مختلف الخيارات التي يتم استخدامها لمعالجة هذه الحالة. تتوقف الخيارات التي تتوفر لك على تكوين أعمالك ومتطلباتها.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/08/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymEntry
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13011
ms.assetid: 20423a2d-6997-4e1c-a596-a77016600071
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a74803d3adf71ef1495ec5b42753d0988cea4133
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189075"
---
# <a name="customer-payments-for-a-partial-amount"></a>مدفوعات العميل لمبلغ جزئي

[!include [banner](../includes/banner.md)]

في بعض الأحيان، قد يسدد العملاء دفعة أقل من مبلغ الفاتورة. توضح هذه المقالة مختلف الخيارات التي يتم استخدامها لمعالجة هذه الحالة. تتوقف الخيارات التي تتوفر لك على تكوين أعمالك ومتطلباتها.

<a name="partial-payment-with-no-discount"></a>الدفع الجزئي دون أي خصم
--------------------------------

قد يقوم العملاء بإجراء دفع جزئي لأنهم لا يملكون ما يكفي من النقد المتوافر لدفع الفاتورة بالكامل، أو بسبب نزاع حول صنف في الفاتورة. وفي هذه الحالة، يمكن تسوية الفاتورة جزئيًا من خلال الدفع. وستبقى هذه الفاتورة مفتوحة وستعرض رصيدًا.

## <a name="discount-amounts"></a>مبالغ الخصمئ
يمكنك أن تقدم للعملاء خصمًا نقديًا لدفع فاتورة قبل تاريخ الاستحقاق. على سبيل المثال، يمكنك إدخال فاتورة بمبلغ 100.00 وتحدد خصمًا نقديًا بنسبة 2 في المائة، إذا تم دفع الفاتورة في غضون 10 أيام. ومدد تاريخ الاستحقاق 30 يومًا. إذا كنت تتلقى دفعة بمبلغ 98.00 في غضون 10 أيام، فيمكنك إدخال دفعة بمبلغ 98.00. وبعد ذلك، عندما يتم وضع علامة على الفاتورة للتسوية، فإنه يتم أخذ الخصم النقدي تلقائياً.

## <a name="partial-payments-with-cash-discounts"></a>المدفوعات الجزئية مع الخصومات النقدية
عندما يقوم العملاء بإجراء دفعة جزئية، قد يخططون لإجراء دفعة جزئية إضافية لتسوية الفاتورة بالكامل. وللحصول على خصم نقدي لدفعة جزئية، يجب عليك تعيين خيار **حساب الخصومات النقدية لمدفوعات جزئية** إلى **نعم** في صفحة **معلمات الحسابات المدينة**. 

على سبيل المثال، أنت تقدم خصمًا نقديًا بنسبة 2 في المائة، إذا تم دفع الفاتورة في غضون 10 أيام بعد صدورها. ويتم ترحيل فاتورة بمبلغ 100.00. إذا كنت تتلقى دفعة بمبلغ 49.00 في غضون 10 أيام، فيمكنك إدخال ائتمان بمبلغ 49.00 في دفتر يومية دفع. وعند تسوية الدفعة الجزئية في **تسوية الحركات**، يظهر **1.00** في حقل **مبلغ الخصم النقدي المُراد الحصول عليه**. يتم ترحيل مبلغ الخصم إلى حساب خصم النقدي. 

> [!NOTE] 
> إذا قمت بإدخال دفعة جزئية وتركت مبلغ الفاتورة الكامل في حقل **المبلغ المُراد تسويته**، فإنه تتم إعادة حساب حقل **مبلغ الخصم النقدي المراد الحصول عليه** تلقائياً عند ترحيل الحركات.

## <a name="credit-notes-with-discounts"></a>إشعارات الدائن بالخصومات
إذا كان العملاء يقومون بإرجاع بعض الأصناف في إحدى الفواتير، فإنه يمكنك إصدار إشعار دائن. وإذا تم الحصول على خصم نقدي في الفاتورة الأصلية، يجب أن يكون إشعار الدائن للعميل صافي الخصم النقدي الذي حصل عليه العميل. وإذا تم تعيين خيار **حساب الخصومات النقدية للإشعارات الدائنة** إلى **نعم** في صفحة **معلمات الحسابات المدينة**، فإنه يتم حساب الخصم تلقائياً لإشعار الدائن. 

على سبيل المثال، قمت أنت بتقدم شروط دفع تحدد خصمًا نقديًا بنسبة 2 في المائة، إذا تم دفع الفاتورة في غضون 10 أيام بعد صدورها. وتم ترحيل فاتورة بمبلغ 100.00، وحصل العميل على الخصم النقدي. إذا كان العميل يقوم بإرجاع البضائع وإصدار إشعار دائن، فيمكنك إدخال إشعار دائن بمبلغ -100.00. وعندما تقوم بعرض إشعار الدائن في صفحة **تسوية الحركات المفتوحة**، يظهر **98.00** في حقل **المبلغ المُراد تسويته** ويظهر **-2.00** في حقل **مبلغ الخصم النقدي**. يتم ترحيل مبلغ الخصم إلى حساب خصم النقدي.

## <a name="overpaymentunderpayment-amounts"></a>مبالغ الدفع بالزيادة/النقصان
عندمت يقوم العملاء بسداد دفعة، فقد يكون هناك مبلغ صغير جداً لا يزال يجب تسويته. على سبيل المثال، يمكنك فوترة العميل بمبلغ 1,000.00، ويدفع العميل 999.90. إذا كان المبلغ المتبقي أقل من المبلغ الذي تم تعيينه للمدفوعات بالزيادة أو النقصان في صفحة **معلمات الحسابات المدينة**، فإنه يتم ترحيل الفرق تلقائياً حساب دفتر أستاذ الدفع بالزيادة/النقصان.

## <a name="full-settlement"></a>التسوية الكاملة
‏‫وقد يقوم العملاء بإجراء دفعة جزئية لن يتم فيها دفع المبلغ المتبقي ولكنها أكبر من مبلغ الدفع بالنقصان الذي تم تحديده في صفحة **معلمات الحساب الدائنة**. إذا كنت ترغب في وضع علامة على الفاتورة باعتبار أنه تمت تسويتها بالكامل، فيمكنك استخدام خيار **التسوية الكاملة‬‏‫** في صفحة **تسوية الحركة**. (يمكنك تمكين وظيفة التسوية الكاملة باستخدام مفتاح تكوين.) على سبيل المثال، يتم ترحيل فاتورة بمبلغ 1,000.00، ويقوم العميل بإجراء دفعة بمبلغ 990.00. ‏‫لقد اتفقنا أن العميل لا يضطر إلى دفع مبلغ 10.00 المتبقي. بعد وضع علامة على الفاتورة للتسوية، يمكنك أيضًا وضع علامة لتحديد **التسوية الكاملة**. وسيُنظر إلى الفاتورة على أنه تمت تسويتها بشكل كامل فيما بعد. ويتم ترحيل الفرق 10.00 إلى حساب خصم النقدي كمبلغ خصم نقدي إضافي.


للحصول على مزيد من المعلومات، راجع [إيداع مدفوعات العميل‬](tasks/deposit-customer-payments.md).