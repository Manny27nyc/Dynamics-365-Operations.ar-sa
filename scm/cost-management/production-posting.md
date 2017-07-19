---
title: "ترحيل الإنتاج"
description: "توفر هذه المقالة معلومات حول الأنواع المختلفة لعمليات الترحيل في عملية الإنتاج."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventItemGroup, ProjCategory, WrkCtrResourceGroup, WrkCtrTable
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 54591
ms.assetid: 0917fe64-f643-46ae-98ff-5013b266a067
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: f1d46b7eba42640de09d85fbc18969ee2a85f280
ms.contentlocale: ar-sa
ms.lasthandoff: 05/25/2017


---

# <a name="production-posting"></a>ترحيل الإنتاج

[!include[banner](../includes/banner.md)]


توفر هذه المقالة معلومات حول الأنواع المختلفة لعمليات الترحيل في عملية الإنتاج.

تتبع أنشطة ترحيل الإنتاج عمليات الإنتاج الموضحة في الأقسام التالية.

## <a name="material-consumption"></a>استهلاك المادة
يتم تسجيل المواد كمستهلكة أثناء الإنتاج عند ترحيل دفتر يومية قائمة انتقاء الإنتاج. وتُنشئ هذه العملية حركات الإصدار تخفض المخزون الفعلي. وفي معلمات الإنتاج، يمكنك تحديد ما إذا كان يجب ترحيل قيمة المواد الخام التي هي قيد التنفيذ (أعمال تحت التنفيذ \[WIP\]) في دفتر الأستاذ. ويتم فيما بعد ترحيل قيمة المواد الخام التي هي قيد التنفيذ (WIP) لحساب قائمة انتقاء مخصصة والحساب المقابل لقائمة الانتقاء المخصصة.

## <a name="time-consumption"></a>استهلاك الوقت
ويتم تسجيل الوقت الذي يستغرقه العاملون في وظائف الإنتاج في دفتر يومية بطاقة المسار أو دفتر يومية بطاقة الوظيفة. وعند ترحيل دفاتر اليومية هذه، تتم معالجة ترحيل دفتر الأستاذ إلى حساب مخصص للموارد التي قيد التنفيذ (WIP). ويعرض هذا الترحيل قيمة الوقت المستغرق في أمر الإنتاج. وبعد تسجيل أمر الإنتاج كمنتهي، تتم تسوية حسابات الأعمال تحت التنفيذ (WIP).

## <a name="reporting-finished-goods-and-error-quantities"></a>الإبلاغ عن السلع التامة الصنع وكميات الأخطاء
عند الإبلاغ عن أمر إنتاج كمنتهي، يتم تحديث كمية السلع المنتهية التي تم إكمالها في إدارة المخزون من خلال دفتر يومية الإبلاغ عنه كمنتهٍ. إذا كنت تستخدم محاسبة الأعمال تحت التنفيذ (WIP)، التي يمكن إعدادها في معلمات الإنتاج، فإنه يتم إعداد يومية دفتر الأستاذ لتقليل حسابات الأعمال تحت التنفيذ وزيادة مخزون السلع المنتهية. يستخدم دفتر اليومية التكلفة القياسية التي تم تحديدها للمنتج.

## <a name="ending-the-production-order"></a>إنهاء أمر الإنتاج
قبل إنهاء أمر الإنتاج، يتم حساب التكاليف الفعلية للكمية التي تم إنتاجها. كما يتم عكس كافة التكاليف التقديرية للمواد والعمالة والمصاريف الزائدة واستبدالها بتكاليف فعلية. ويتم طرح التكلفة الإجمالية للأصناف المنتهية من حساب الاستلام الخاص بالمخزون وإضافتها إلى حساب الإصدارات الخاصة بالمخزون. إذا قمت بتحديد خانة الاختيار **إنهاء وظيفة** عند قيامك بحساب التكلفة، تتغير حالة أمر الإنتاج إلى **منتهي**. تحول هذه الحالة دون ترحيل أي تكاليف إضافية بشكل غير مقصود إلى أمر إنتاج مكتمل. ويمكنك تحديد أن يتم تخصيص قيمة كميات الأخطاء - التي يتم الإبلاغ عنها أثناء إعداد التقارير كمنتهية - للكميات الجيدة التي يتم الإبلاغ عنها كمنتهية.‬ وبدلاً من ذلك، يمكنك تحديد أن يتم ترحيل قيمة كميات الأخطاء إلى حساب خردة مخصص.

## <a name="controlling-the-level-of-ledger-posting"></a>التحكم في مستوى ترحيل دفتر الأستاذ
في **معلمات التحكم في الإنتاج**، يمكنك استخدام حقل **ترحيل دفتر الأستاذ** لتعيين مستوى ترحيل دفتر الأستاذ لعمليات الإنتاج. تتوفر القيم التالية:

-   **الصنف والمورد** – استخدام حسابات دفتر الأستاذ التي تم إعدادها في مجموعات الأصناف للمواد الخام والسلع المنتهية. يتم أخذ الأعمال تحت التنفيذ (WIP) لاستهلاك الوقت من المورد أو مجموعة الموارد من عمليات المسار.
-   **الصنف والفئة** – استخدام حسابات دفتر الأستاذ التي تم إعدادها في مجموعات الأصناف للمواد الخام والسلع المنتهية. يتم أخذ الأعمال تحت التنفيذ (WIP) لاستهلاك الوقت من فئات التكلفة المرتبطة بعمليات المسار.
-   **مجموعات الإنتاج** – استخدام حسابات دفتر الأستاذ التي تم إعدادها في مجموعات الإنتاج لكلٍّ من استهلاك المواد والوقت. ويتم ربط مجموعات الإنتاج بالمنتجات الصادرة ويتم نسخها إلى أوامر الإنتاج عند إنشاء تلك الأوامر. وسيتبع ترحيل أوامر الإنتاج مجموعات الإنتاج المرتبطة بأمر الإنتاج.

**ملاحظة:** إذا تم استخدام الطريقة القياسية لحساب تكلفة الصنف المنتهي، فإن الحركات النهائية توضح ذلك. وفي حالة وجود فرق بين التكاليف الفعلية والتكاليف التي تم حسابها باستخدام الطريقة القياسية، فإنه يتم ترحيل هذا الفرق إلى الحساب الذي يوضح الأرباح أو الخسائر.



