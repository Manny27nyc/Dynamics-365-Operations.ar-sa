---
title: مجموعات الأبعاد المالية
description: يصف هذا الموضوع مجموعات الأبعاد المالية ويوفر بعض التلميحات لتحسين استخدامها.
author: yukonpeegs
manager: AnnBe
ms.date: 03/23/2021
ms.topic: article
ems.prod: ''
ms.technology: ''
ms.search.form: DimensionFocus, LedgerTrialBalanceListPage
audience: Application User
ms.reviewer: roschlom
ms.custom: 25871
ms.search.region: Global
ms.author: epegors
ms.search.validFrom: 2021-03-23
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: b719d8eb868cb1722b470be4443d01181078ce21
ms.sourcegitcommit: 97ada5d52ed1829dcf030dad254096cd8df25da8
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/06/2021
ms.locfileid: "5864402"
---
# <a name="financial-dimension-sets"></a>مجموعات الأبعاد المالية

[!include [banner](../includes/banner.md)]

يصف هذا الموضوع مجموعات الأبعاد المالية ويوفر بعض التلميحات لتحسين استخدامها.

تعد مجموعة الأبعاد بمثابة قائمة تتضمن الأبعاد المالية التي يمكن استخدامها لتلخيص بيانات دفتر الأستاذ العام بطريقه معرّفة من قبل المستخدم. الاستخدام الأساسي لمجموعات الأبعاد هو تحديد ميزان المراجعة.

مجموعه الأبعاد القياسية الوحيدة هي مجموعه الأبعاد التي تحتوي على الحساب الرئيسي فقط.

يمكنك استخدام الصفحة **مجموعات الأبعاد المالية** لإنشاء مجموعات الأبعاد المالية وإدارتها.

## <a name="dimension-set-balances"></a>أرصدة مجموعات الأبعاد

بإمكان مجموعة الأبعاد أن تتضمن أرصدة تعتمد على أبعادها المالية. توجد الأرصدة في دفتر الأستاذ العام وتعتمد على تعريف مجموعة الأبعاد. يتم تلخيص الأرصدة من بيانات دفتر الأستاذ العام للمساعدة في تحسين الأداء عند استردادها (على سبيل المثال، عند إنشاء ميزان المراجعة).

## <a name="create-balances"></a>إنشاء أرصدة

استخدم الزر **إنشاء أرصدة** لتهيئة الأرصدة لمجموعة أبعاد ليس لديها أرصدة في الوقت الحالي.

> [!NOTE]
> نوصي بالحد من عدد مجموعات الأبعاد التي لديها أرصدة، وذلك لأن تحديثات الرصيد تؤثر على كافة أنشطة ترحيل دفتر الأستاذ العام.

## <a name="update-balances"></a>تحديث الأرصدة

استخدم الزر **تحديث الأرصدة** لتضمين آخر نشاط ترحيل لدفتر الأستاذ العام في الأرصدة. تعد تحديثات الأرصدة عمليات خفيفة. يجب عليها أن تقوم فقط بترحيل نشاط ترحيل دفتر الأستاذ العام الذي حدث مند آخر تحديث.

> [!NOTE]
> يؤدي عرض ميزان المراجعة إلى فرض تحديث، للتأكد من أن الأرصدة المعروضة هي أرصدة حالية. يمكنك استخدام وظيفة دفعية متكررة بحيث تتم تحديثات مجموعات الأبعاد المستخدمة بشكل متكرر بطريقة أسرع. وبهذه الطريقة، فأنت تساعد على تقليل الوقت الذي يجب علي المستخدمين فيه انتظار ميزان المراجعة.

## <a name="rebuild-balances"></a>إعادة إنشاء الأرصدة

استخدم الزر **إعادة إنشاء الأرصدة** لإعادة إنشاء الأرصدة‏‎ من البداية. وبهذه الطريقة، فأنت تساعد على التأكد من أنها تطابق البيانات في دفتر الأستاذ العام. تتطلب إعادة بناء الأرصدة الكثير من المعالجة ومن غير المفترض أن تكون مطلوبة عادةً.

> [!NOTE]
> إذا كان لديك سيناريو يتطلب إعادة بناء الأرصدة بانتظام، فمن الأفضل أن تتصل بدعم العملاء. بإمكان قسم دعم العملاء أن يساعدك في تحديد سبب عدم تطابق الأرصدة مع البيانات الموجودة في دفتر الأستاذ العام.

## <a name="clear-balances"></a>مسح الأرصدة

استخدم الزر **مسح الأرصدة** لإزالة الأرصدة وإيقاف أي تحديثات لاحقة. ولن يعود لمجموعة الأبعاد أي تأثير على أنشطة ترحيل دفتر الأستاذ العام.

لمزيد من المعلومات، راجع [الأبعاد المالية‬](financial-dimensions.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]