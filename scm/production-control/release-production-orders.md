---
title: "إصدار أوامر الإنتاج"
description: "أمر الإنتاج الذي تم إصداره هو أمر تم تخويله للإنتاج. يُستخدم المصطلح \"تم الإصدار\" لوصف حالة في دورة حياة أمر الإنتاج، حيث يُتاح أمر الإنتاج للتنفيذ في صالة الإنتاج ولعمليات المستودع."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdParmRelease
audience: Application User
ms.reviewer: annbe
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2414
ms.assetid: 50c2257b-2924-44f5-b7c1-11f498092053
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 1b033e4bf6705b3c9a33f2184666158049909a80
ms.contentlocale: ar-sa
ms.lasthandoff: 05/25/2017


---

# <a name="release-production-orders"></a>إصدار أوامر الإنتاج

[!include[banner](../includes/banner.md)]


أمر الإنتاج الذي تم إصداره هو أمر تم تخويله للإنتاج. يُستخدم المصطلح "تم الإصدار" لوصف حالة في دورة حياة أمر الإنتاج، حيث يُتاح أمر الإنتاج للتنفيذ في صالة الإنتاج ولعمليات المستودع. 

<a name="characteristics-of-the-released-state"></a>خصائص الحالة الصادرة
-------------------------------------

الحالة **الصادرة** هي حالة في دورة حياة أمر الإنتاج. وتتوفر أوامر الإنتاج الموجودة بحالة **صادرة** للتنفيذ في صالة الإنتاج ولعمليات المستودع. تشمل الحالة **صادرة** الخصائص التالية:

-   يمكن تغيير أمر إنتاج إلى الحالة **صادرة** من أمر الإنتاج أو باستخدام عملية دُفعية. كما يمكن تحديث أمر الإنتاج تلقائياً من أوامر الإنتاج المخططة التي تم تأكيدها باستخدام حقل **الحد الزمني للتأكيد‬** في صفحة **الخطة الرئيسية**.
-   الحالة **صادرة** عبارة عن إشارة للعمال في صالة الإنتاج لبدء تنفيذ وظائف الإنتاج في صالة الإنتاج.
-   توفر أوراق الإنتاج، مثل بطاقات المسار، ووظائف المسار، وبطاقات الوظائف معلومات حول وظائف الإنتاج ويمكن إصدارها.
-   للحصول على المواد المحجوزة فعلياً، يتم إنشاء عمل مستودع لانتقاء المواد لأمر الإنتاج.

## <a name="releasing-jobs-to-the-shop-floor"></a>تحرير الوظائف في صالة الإنتاج
بعد إصدار أمر إنتاج، تصبح وظائف الإنتاج التي ترتبط بالأمر مرئية وجاهزة للتسجيل. ‏‫ويمكن للعمال إجراء تسجيلات الوظائف، مثل البدء، والإيقاف، والإكمال سواء في صفحة **الوحدة الطرفية لبطاقة الوظيفة** أو صفحة **جهاز بطاقة الوظيفة**. ويتم تحويل الوقت والكمية المسجلين تلقائياً من صفحات التسجيل إلى دفاتر يومية الإنتاج لتعقب الوقت والكمية المستهلكين.‬

## <a name="route-cards"></a>بطاقات المسار
تقدم بطاقة المسار نظرة عامة على المعلومات الواردة من المسار وإعدادات العملية ومن طرق جدولة العمليات والوظائف.

## <a name="route-jobs"></a>قوائم المهام
تسرد وظيفة المسار كل وظيفة لعملية معينة بالتفصيل وتتضمن أوقات الإعداد والعملية والانتظار والنقل. فمثلاً، قد تتطلب عملية مثل الدهان إجراء وظائف فردية مثل وقت الإعداد ووقت التشغيل لعملية الدهان ووقت الانتظار للتجفيف.

## <a name="job-cards"></a>بطاقات الوظيفة
تسرد بطاقة الوظيفة أرقام الوظيفة الفردية لعملية بعينها. وتظهر وظيفة واحدة في كل صفحة. وترد الوظائف المتضمنة في بطاقة الوظيفة، وأوقات تقديرها، من معلومات المسار وإعداد العملية. ومن بطاقة وظيفة، يمكنك فتح صفحة **بنود دفتر يومية الإنتاج**، و**بطاقة الوظيفة**. ويمكن للأشخاص الذين يقومون بتشغيل موارد العمليات تقديم ملاحظات حول عملية الإنتاج. وتوجد حقول يمكن إدخال إحصاءات الاستهلاك فيها وكذلك معلومات أخرى مثل كمية الأخطاء.

## <a name="warehouse-work-for-raw-material-picking"></a>عمل المستودع لانتقاء المواد الخام
ويتم إنشاء عمل لانتقاء المواد الخام أثناء الإصدار. ‏‫ويتم إنشاء العمل فقط لكمية المواد التي تم حجزها فعلياً لأمر الإنتاج قبل إصدار الأمر. ويُتطلب الإعداد التالي لإنشاء عمل مستودع لانتقاء المواد الخام:‬

-   توجيه موقع لانتقاء المواد الخام يحدد موقع المستودع لانتقاء المواد في
-   قالب موجه للمواد الخام، حيث تم تكوين سياسات لتنفيذ العمل في المستودع
-   موقع مدخلات إنتاج يحدد مكان وضع المواد




