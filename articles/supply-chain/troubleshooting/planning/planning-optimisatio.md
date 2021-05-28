---
title: يتم إنشاء أمر الشراء المخطط عندما يكون الشراء موجودًا خلال الأيام السالبة
description: إذا كان الحد الأدنى/الحد الأقصى لكود التغطية، فإن تحسين التخطيط يؤدي إلى إنشاء أمر شراء مخطط عندما يكون الشراء موجودًا خلال الأيام السالبة.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo,MpsIntegrationParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 826496c2de956ff949dd79ab8aa643053719bf75
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026241"
---
# <a name="planned-purchase-order-is-created-when-a-purchase-exists-within-negative-days"></a>يتم إنشاء أمر الشراء المخطط عندما يكون الشراء موجودًا خلال الأيام السالبة

رقم KB: 4614298

## <a name="symptoms"></a>العلامات

إذا كان *الحد الأدنى/الحد الأقصى* لكود التغطية، فإن تحسين التخطيط يؤدي إلى إنشاء أمر شراء مخطط عندما يكون الشراء موجودًا خلال الأيام السالبة.

## <a name="resolution"></a>الدقة

لا يدعم تحسين التخطيط الأيام السالبة. ومع ذلك، فإنه يضمن دومًا أنه لن تتم جدولة الأوامر المخططة خلال زمن وصول البضاعة بالنسبة للتاريخ الحالي. على سبيل المثال، يكون وقت إنتاج المشتريات 10 أيام، ويتوقع أن يصل أمر الشراء إلى ثمانية أيام بدءًا اليوم. في هذه الحالة، سيتم استخدام أمر الشراء كتوريد للطلب الذي يكون خمسة أيام بدءًا من اليوم.

وبالتالي، نوصي بضبط أوقات الإنتاج المحتمل لتغطية جميع (أو الكل تقريبًا) من وحدات السيناريو الخاصة بك.