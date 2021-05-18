---
title: آخر بند عمل مقفل يجب أن يكون "وضع"
description: آخر بند عمل مقفل يجب أن يكون "وضع"
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWorkTable_WHSWorkCancel, WHSWorkTableListPage_WHSWorkCancel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: a5b78154b51252b3ac96ba28c254e823caf87019
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924365"
---
# <a name="the-last-closed-work-line-must-be-a-put"></a>آخر بند عمل مقفل يجب أن يكون "وضع"

رمز الخطأ: WAX1285

## <a name="symptoms"></a>العلامات

يعرض النظام رسالة الخطأ التالية:

> آخر بند عمل مقفل يجب أن يكون "وضع".

## <a name="cause"></a>السبب

لا يمكن إلغاء العمل في حالته الحالية.

في بند العمل الأخير، تم تعيين حقل **حالة العمل** إلى *مقفل*، ولكن لم يتم تعيين **نوع العمل** إلى *وضع*.

## <a name="resolution"></a>الدقة

لإلغاء العمل، اتبع الخطوات التالية.

1. انتقل إلى **إدارة المستودع \> المهام الدورية \> تنظيف \> إلغاء العمل**.
1. في حقل **معرف العمل**، حدد معرف العمل الذي ترغب في إلغائه.
1. حدد **موافق**.
1. حدد **نعم** لتأكيد رغبتك في إلغاء العمل.

لمزيد من المعلومات، راجع [إلغاء عمل المستودع لمعالجة الاستثناء](../../warehousing/cancel-warehouse-work.md).