---
title: عملاء التعويض
description: تشرح هذه المقالة كيفية إنشاء حركات التعويض لمجموعة من العملاء. إذا كان للعميل رصيد دائن، يمكن تعويض العميل لمبلغ الرصيد.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransCustPaym, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14191
ms.assetid: 53533ee3-470e-458a-ac8b-3815aa4cb502
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 97982dec140ed440682ae507f40557670ebccd3e
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176275"
---
# <a name="reimburse-customers"></a>عملاء التعويض

[!include [banner](../includes/banner.md)]

تشرح هذه المقالة كيفية إنشاء حركات التعويض لمجموعة من العملاء. إذا كان للعميل رصيد دائن، يمكن تعويض العميل لمبلغ الرصيد. 

يعرض الجدول التالي المتطلبات الأساسية التي يجب أن تكون موجودة قبل البدء.

| المتطلب الأساسي                                                            | الوصف                                                                                                                                                                                 |
|-------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| تحديد الحد الأدنى لمبلغ التعويض للكيان القانوني.          | في صفحة **معلمات الحسابات المدينة**، في المنطقة **عام**، في حقل **الحد الأدنى للتعويض**، أدخل الحد الأدنى للمبلغ الذي يمكن تعويضه للمدفوعات الزائدة للعميل. |
| اختياري: قم بإضافة حساب مورد لكل عميل يمكن تعويضه. | في صفحة **العملاء**، في علامة التبويب السريعة **التفاصيل المتنوعة**، في حقل **حساب المورد**، حدد حساب المورد للعميل.                                           |

عند إنشاء حركات التعويض، يتم إنشاء فاتورة مورد لمبلغ الرصيد الدائن. تقوم عملية التعويض بإزالة الرصيد الدائن لحساب العميل وإنشاء رصيد مستحق لحساب المورد المقابل للعميل.

1.  في الحسابات المدينة، قم بتشغيل عملية **التعويض**.
2.  اتبع إحدى الخطوات التالية:
    -   لتعويض حسابات العميل المحددة، انقر فوق **تحديد**، وقم بتحديد حسابات العميل في الاستعلام.
    -   لتعويض كل حسابات العميل، انقر فوق **موافق**.

    يتم تحويل المبالغ الدائنة لحسابات المورد الخاصة بالعملاءوتتم معالجتها كمدفوعات عادية. إذا لم يكن لدى العميل حساب مورد، فسيتم إنشاء حساب مورد لمرة واحدة تلقائيًا للعميل.
3.  لعرض حركات التعويض التي تم إنشاؤها، استخدم صفحة **التعويض**.
4.  في الحسابات الدائنة، قم بإنشاء عملية دفع فواتير المورد التي تم إنشاؤها بواسطة عملية التعويض.



