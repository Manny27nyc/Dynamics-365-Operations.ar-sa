---
title: سيناريوهات حد الائتمان
description: توضح هذه المقالة كيفية التحقق من حد ائتمان العميل عندما ينتمي العميل إلى مجموعة حد ائتمان العميل.
author: JodiChristiansen
ms.date: 06/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2022-06-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 60b17a6b7f57b468610974ae9bd05b7db3584cc1
ms.sourcegitcommit: 85141b21ac90f3db1b378c21f9c7f3d8f74e182f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/09/2022
ms.locfileid: "9130247"
---
# <a name="credit-limit-scenarios"></a>سيناريوهات حد الائتمان

في إدارة الائتمان، يمكن تعيين حد ائتماني للعملاء على مستوى العميل. يمكن تعيين كل عميل *لمجموعة حد ائتمان للعميل*، ولكل مجموعة حد ائتمان. لذا، يمكن أيضًا تعيين حد ائتماني للعملاء على مستوى المجموعة. جميع العملاء الذين تم تعيينهم إلى نفس مجموعة ائتمان العملاء لديهم نفس حد الائتمان.

بشكل عام، يتم فحص حدود ائتمان المجموعة قبل حدود الائتمان الفردية. لا يتجاوز حد الائتمان الفردي دائمًا حد ائتمان المجموعة.

توضح هذه المقالة خمسة سيناريوهات مرتبطة بمجموعات ائتمان العملاء وحدود الائتمان الفردية.

## <a name="the-customer-group-credit-limit-is-more-than-the-individual-credit-limit"></a>يتجاوز حد ائتمان مجموعة العملاء حد الائتمان الفردي

على سبيل المثال، لدى العميل حد ائتمان فردي قدره 10،000 دولار. تم تعيين العميل لمجموعة ائتمان العميل، والحد الائتماني للمجموعة هو 15،000 دولار. في هذه الحالة، يبلغ "حد الائتمان الفعال" للعميل 10،000 دولار أمريكي، لأن هذا المبلغ أقل من حد المجموعة. تتحقق قواعد الحظر أولاً من حد المجموعة. ثم يقومون بفحص الحد الفردي. سيتم حظر أي أمر مبيعات يزيد عن 10،000 دولار.

## <a name="the-individual-credit-limit-is-more-than-the-customer-group-credit-limit"></a>يتجاوز حد الائتمان الفردي حد ائتمان مجموعة العملاء

على سبيل المثال، لدى العميل حد ائتمان فردي قدره 20،000 دولار. تم تعيين العميل لمجموعة ائتمان العميل، والحد الائتماني للمجموعة هو 15،000 دولار. في هذه الحالة، يكون حد الائتمان الفعلي للعميل هو 15،000 دولار، لأن قواعد المنع تتحقق دائمًا من حد المجموعة أولاً. سيتم حظر أي طلبات مبيعات تزيد عن 15،000 دولار.

## <a name="the-individual-credit-limit-is-set-to-000-and-mandatory-credit-limit-is-set-to-yes"></a>تم تعيين حد الائتمان الفردي على 0.00 والحد الائتماني الإلزامي معيّن إلى "نعم"

إذا كان لدى العميل حد ائتماني فردي تم تعيينه إلى **0.00**، وتم تعيين الخيار **حد الائتمان الإلزامي** إلى **نعم**، فإن حد الائتمان الفعلي للعميل هو 0.00 دولار، حتى إذا تم تعيين العميل لمجموعة ائتمان العميل. بهذه الطريقة، يمكن أن يكون العميل جزءًا من مجموعة، لكن جميع الطلبات ستذهب إلى إدارة الائتمان.

## <a name="the-individual-credit-limit-is-set-to-000-and-unlimited-credit-limit-is-set-to-yes"></a>تم تعيين حد الائتمان الفردي إلى 0.00 والحد الائتماني غير المحدود الذي لم يتم تعيينه إلى "نعم"

إذا كان لدى العميل حد ائتماني فردي تم تعيينه إلى **0.00**، ولكن تم تعيين الخيار **حد الائتمان غير المحدود** إلى **نعم**، فسيكون للعميل رصيد غير محدود، حتى إذا تم تعيينه لمجموعة ائتمان العميل.

## <a name="the-individual-credit-limit-is-set-to-000-and-the-customer-is-part-of-a-customer-credit-group"></a>تم تعيين حد الائتمان الفردي إلى 0.00 والعميل جزء من مجموعة ائتمان العملاء

على سبيل المثال، لدى العميل حد ائتماني فردي تم تعيينه إلى **0.00**، وتم تعيين الخيار **الائتمان غير المحدود** إلى **لا**، والخيار **حد الائتمان الإلزامي** إلى **لا**. تم تعيين العميل لمجموعة ائتمان العميل، والحد الائتماني للمجموعة هو 15،000 دولار. في هذه الحالة، يكون الحد الائتماني الفعلي للعميل هو حد المجموعة، وهو 15000 دولار. لذا، سيتم حظر أي أوامر مبيعات تتجاوز هذا المبلغ. يتيح هذا السلوك إدارة حد الائتمان على مستوى مجموعة ائتمان العميل بدلاً من مستوى العميل الفردي. كل العملاء الذين تم تعيينهم لنفس المجموعة لديهم نفس حد الائتمان.