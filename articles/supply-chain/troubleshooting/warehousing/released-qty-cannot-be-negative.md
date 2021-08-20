---
title: لا يمكن تحديث بند التحميل لأن الكمية التي تم إصدارها ستكون سالبة
description: تحدث هذه المشكلة عند تحديث أو حذف سطر تحميل قد يسبب كمية سالبة تم إصدارها.
author: GalynaFedorova
ms.date: 6/30/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadPlanningListPage_WHSLoadLineUnShipQty,WHSLoadTable_WHSLoadLineUnShipQty,WHSLoadPlanningWorkbench_WHSLoadLineUnShipQty,WHSShipmentDetails_WHSLoadLineUnShipQty,WHSLoadPlanningListPage_DeleteButtonLoadLine,WHSLoadTable_DeleteButtonLoadLine,WHSLoadPlanningWorkbench_DeleteButtonLoadLine,WHSShipmentDetails_DeleteButtonShipment
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: a6325a632e1f68a0a3a9cb6b6091c48da014a405e8ce9ad69ea841f5cceb216f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/05/2021
ms.locfileid: "6728449"
---
# <a name="cant-update-a-load-line-because-the-released-quantity-would-be-negative"></a>لا يمكن تحديث بند التحميل لأن الكمية التي تم إصدارها ستكون سالبة

رمز الخطأ: @WAX:ReleasedQtyCannotBeNegative

## <a name="symptoms"></a>العلامات

تحدث هذه المشكلة عند تحديث أو حذف سطر تحميل قد يسبب كمية سالبة تم إصدارها. في هذه الحالة، عند محاولة تحديث أو حذف سطر التحميل، يظهر النظام رسالة الخطأ التالية:

> لا يمكن أن تكون الكمية التي تم إصدارها سالبة للصنف %1، والدفعة %2.

لذلك، لا يمكنك تحديث أو حذف سطر التحميل.

## <a name="cause"></a>السبب

بعد تحديث أو حذف بند تحميل، يقوم النظام بتحديث الكمية التي تم إصدارها من بند المبيعات ذي الصلة (*whsSalesLine.ReleaseQty*). يقوم النظام بتقييم الكمية التي تم إصدارها، وإذا وجد أن الكمية التي تم إصدارها من البند ستكون سالبة بعد التحديث، فلن يسمح لك بتحديث أو حذف السطر. يحدث التحقق من الصحة هذا عند محاولة تحديث كمية بند التحميل أو وحدة القياس من خلال إجراءات مختلفة، مثل حذف بند تحميل، وحذف شحنة، وتغيير كمية بند التحميل، وتقليل الكمية الانتقاء، والانتقاء القصير.

السبب الجذر الأكثر شيوعا لهذه المشكلة هو تغيير في تحويل الوحدة المستخدمة لخطوط التحميل المفتوحة. على سبيل المثال، كان تحويل الوحدة عند إصدار أمر مبيعات هو *50 Ea = 1 PL*. ومع ذلك، قبل أن يتم الانتهاء من شحنة التحميل ذات الصلة، تم تغيير تحويل الوحدة إلى *100 Ea = 1 PL*.

## <a name="resolution"></a>الحل

الحل هو إعادة تغييرات تحويل الوحدة وتحديث أو حذف بند التحميل ثم إعادة تنفيذ التحويل. يجب منع التحميلات الأخرى التي تتضمن العنصر الذي تسبب في معالجة المشكلة حتى يتم إصلاح المشكلة. وإلا، قد يتم استخدام التحويلات الجديدة للأحمال الأخرى المفتوحة بالفعل.

لإصلاح هذه المشكلة، أكمل المهام التالية:

1. راجع تحويل الوحدة الذي تم استخدامه لبند التحميل.
2. راجع تحويل الوحدة الحالي للصنف، ثم قم بإجراء تعديلات من شأنها تمكين تحديث بند التحميل أو حذفه.
3. تحديث أو حذف بند التحميل، والعودة إلى تسويات تحويل الوحدة.

### <a name="review-the-unit-conversion-that-was-used-for-the-load-line"></a>راجع تحويل الوحدة الذي تم استخدامه لبند التحميل

استخدم الإجراء التالي لمراجعة بنود التحميل الخاصة بك و تدوين ملاحظة حول تحويل الوحدة الذي تم استخدامه لبند التحميل.

1. انتقل إلى **إدارة المستودعات \> الأحمال‏‎ \> جميع الأحمال‏‎**.
1. حدد التحميل الذي يتضمن بند التحميل الذي لا يمكن حذفه أو تحديثه.
1. في جزء الإجراءات، في علامة التبويب **الأحمال**، في مجموعة **المعلومات ذات الصلة**، حدد **العمل**.
1. في الشبكة العليا، حدد معرف العمل ذي الصلة.
1. في علامة التبويب **عام** في أسفل الصفحة، احسب معدل التحويل بين قيمة **كمية عمل المخزون** وقيمة **كمية العمل**. قم بتدوين ملاحظة بالسعر.
1. كرر هذا الإجراء لكافة معرفات العمل ذات الصلة للتأكد من استخدام التحويل نفسه.

### <a name="review-the-current-unit-conversion-for-the-item-and-make-adjustments"></a>مراجعة تحويل الوحدة الحالي للصنف وإجراء تعديلات

استخدم الإجراء التالي لمراجعة تحويل وحدة منتجك وإجراء تعديلات للتأكد من أن تحويل الوحدة يتماشى مع بند التحميل.

1. انتقل إلى **إدارة معلومات المنتج‬ \> المنتجات \> المنتجات الصادرة**.
1. افتح المنتج ذي الصلة للانتقال إلى صفحة **تفاصيل المنتجات الصادرة**.
1. في جزء الإجراءات، في علامة تبويب **المنتج** في مجموعة **إعداد‬**، حدد **تحويلات الوحدات**.
1. حدد التحويل بين الوحدات، ثم قم بإجراء تعديلات باستخدام التحويل الذي وجدته في القسم السابق.

### <a name="update-or-delete-the-load-line-and-revert-the-unit-conversion-adjustments"></a>تحديث أو حذف بند التحميل، والعودة إلى تسويات تحويل الوحدة

استخدم الإجراء التالي لمعالجة بند التحميل كما هو مطلوب والعودة تحويلات الوحدة.

1. انتقل إلى **إدارة المستودعات \> الأحمال‏‎ \> جميع الأحمال‏‎**.
1. افتح التحميل الذي يتضمن بند التحميل الذي لا يمكن حذفه أو تحديثه.
1. في علامة التبويب السريعة **بنود الحمل**، حدد بند الحمل.
1. مواصلة الإجراءات المطلوبة حسب الحاجة. (على سبيل المثال، احذف بند التحميل أو قم بتغيير كميته.)
1. انتقل إلى **إدارة معلومات المنتج‬ \> المنتجات \> المنتجات الصادرة**.
1. افتح المنتج ذي الصلة للانتقال إلى صفحة **تفاصيل المنتجات الصادرة**.
1. في جزء الإجراءات، في علامة تبويب **المنتج** في مجموعة **إعداد‬**، حدد **تحويلات الوحدات**.
1. حدد التحويل بين الوحدات، وأعد التعديلات التي أجريتها في القسم السابق.