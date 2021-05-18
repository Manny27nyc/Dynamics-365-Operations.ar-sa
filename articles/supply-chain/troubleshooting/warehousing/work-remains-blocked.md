---
title: يظل العمل محظورًا
description: يظل العمل محظورًا
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTableListPage_WHSWorkUnblocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f85364d1ecfadc36b26c3395ab4402d3cb3b1603
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924120"
---
# <a name="work-remains-blocked"></a>يظل العمل محظورًا

رمز الخطأ: WHSWorkBlockingExecutingWaveReason_ErrorMessage

## <a name="symptoms"></a>العلامات

يعرض النظام رسالة الخطأ التالية:

> يبقى العمل %1 محظورًا لأن حالة الموجة المرتبطة %2 هي %3.

## <a name="cause"></a>السبب

تتم معالجة العمل حاليًا على موجة ولا يمكن إلغاء حظره، كما يتضح من أحد الشروط التالية:

- في علامة التبويب **أسباب الحظر**، تم تعيين حقل **سبب حظر العمل** لواحد أو أكثر من البنود إلى *موجة المعالجة*.
- عند تحديد **موجة** في مجموعة **المعلومات ذات الصلة** في علامة التبويب **ذات الصلة** في جزء الإجراءات، ويتم تعيين حقل **حالة الموجة** إلى *معالجة*.

## <a name="resolution"></a>الدقة

في جزء الإجراءات، في علامة التبويب **المعلومات ذات الصلة**، في مجموعة **المعلومات ذات الصلة**، حدد **موجة**. وبعد ذلك في صفحة **الموجات**، في جزء الإجراءات، في علامة التبويب **موجة**، في مجموعة **الموجة**، حدد **تنظيف بيانات الموجة**.

## <a name="workaround"></a>حل بديل

إذا لم تؤد الخطوات السابقة إلى حل المشكلة، فيمكنك إلغاء العمل باتباع هذه الخطوات.

1. انتقل إلى **إدارة المستودع \> المهام الدورية \> تنظيف \> إلغاء العمل**.
1. في حقل **معرف العمل**، حدد معرف العمل الذي تريد إلغاؤه، والذي يحتوي حاليًا على قيمة **حالة العمل** التي تكون *مفتوح* أو *قيد التقدم* أو *تم الإلغاء* أو *تم التجميع* أو *مغلق*.
1. حدد **موافق**.
1. حدد **نعم** لتأكيد رغبتك في إلغاء العمل.

لمزيد من المعلومات، راجع [إلغاء عمل المستودع لمعالجة الاستثناء](../../warehousing/cancel-warehouse-work.md).