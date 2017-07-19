---
title: "حل الاختلافات أثناء مطابقة إجماليات الفواتير"
description: 
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 63413
ms.assetid: 9ac42457-95b2-4191-ad06-c7e323704466
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 8773773d9686bf5061958fbe414ed1fef7288f81
ms.contentlocale: ar-sa
ms.lasthandoff: 05/25/2017


---

# <a name="resolve-discrepancies-during-invoice-totals-matching"></a>حل الاختلافات أثناء مطابقة إجماليات الفواتير

[!include[banner](../includes/banner.md)]




يتمثل نوع واحد من التحقق من صحة مطابقة الفواتير في مطابقة إجماليات الفواتير. ولتحديد أن النظام يجب عليه تنفيذ مطابقة إجماليات الفواتير، في صفحة **معلمات الحسابات الدائنة**، في علامة التبويب **التحقق من صحة الفواتير**، قم بتعيين خيار **مطابقة إجماليات الفواتير** إلى **نعم**. 

يمكنك استخدام مطابقة إجماليات الفواتير للمساعدة على التأكد من أن مبالغ الفواتير الإجمالية لا تحيد عن المبالغ المتوقعة بما يزيد على فرق مقبول. وتتم مقارنة ستة إجماليات في صفحة **تفاصيل مطابقة إجماليات الفواتير**. وإذا انحرف أي إجمالي من الإجماليات عن إجمالي أمر الشراء المقابل المتوقع، فإنه يتم وضع علامة لاختلاف المطابقة. 

ولمراجعة الفاتورة المشتملة على اختلاف مطابقة الإجماليات، في مساحة عمل **إدخال فاتورة مورد**، انقر فوق تجانب **الفواتير المعلقة**. وبعد ذلك، في جزء الإجراءات، في علامة التبويب **مراجعة**، انقر فوق **تفاصيل المطابقة**. وإذا تم الكشف عن اختلافات في المطابقة، تظهر رموز تحذير بجوار مبلغ الفاتورة. ويمكنك عرض المزيد من التفاصيل حول الإجماليات بعرض تفاصيل مطابقة إجماليات الفواتير. 

وبعد تحديد اختلاف، قد تحتاج إلى الاتصال بالمورّد إذا كنت تعتقد أن المعلومات الموجودة في الفاتورة غير صحيحة. ووفقًا لما ستتفق عليه مع المورّد، يمكنك القيام بأيٍ من الإجراءات التالية:

-   قبول الاختلاف في السعر وترحيل الفاتورة التي تشتمل على اختلافات المطابقة. ويمكن إعداد النظام لتتطلب الموافقة قبل أن يمكنه الترحيل إذا كانت هناك اختلافات في المطابقة. وفي هذه الحالة، يجب عليك الموافقة على اختلاف المطابقة ويمكنك إدخال تعليق موافقة بشكل اختياري. وبعد ذلك، يمكنك اختيار ترحيل الفاتورة.
-   قم بتعديل مبلغ الفاتورة إلى المبلغ المتوقع وترحيل الفاتورة.
-   اطلب ائتمانًا كاملاً، فاتورة مصححة جديدة من المورد.




