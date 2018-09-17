---
title: "إنشاء أوامر الخدمة تلقائيًا"
description: "يمكن إنشاء أوامر خدمة لاتفاقية خدمة واحدة أو للعديد من اتفاقيات الخدمات."
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: c39e5b5eb79859b0a76c357edfee953ca90c0c4a
ms.contentlocale: ar-sa
ms.lasthandoff: 05/08/2018

---

# <a name="create-service-orders-automatically"></a>إنشاء أوامر الخدمة تلقائيًا    

[!include [banner](../includes/banner.md)]


يمكن إنشاء أوامر خدمة لاتفاقية خدمة واحدة أو للعديد من اتفاقيات الخدمات. وعند إنشائها، يمكن عرض أوامر الخدمة في النموذج **أوامر الخدمة**.

يتم إنشاء أوامر الخدمة لفترة صلاحية اتفاقية الخدمات فقط. فإذا كان الفاصل الزمني الذي قمت بتحديده في النموذج **إنشاء أوامر الخدمة** يقع قبل تاريخ بدء أو بعد تاريخ انتهاء اتفاقية الخدمات، فيتم إنشاء أوامر الخدمة لجزء الفاصل الزمني الذي يقع داخل اتفاقية الخدمات فقط.

عندما تقوم بإنشاء أوامر الخدمة يدويًا أو تلقائيًا من بند اتفاقية الخدمة، فلابد من وقوع أمر الخدمة في نطاق الفترة الزمنية التي تم تحديدها من خلال تاريخي البداية والانتهاء للبند إلا إذا لم تقم بتحديد تاريخ انتهاء للبند.

## <a name="create-service-orders-automatically-for-a-service-agreement"></a>إنشاء أوامر خدمة لاتفاقية خدمات تلقائيًا.

1.  انقر فوق **إدارة الخدمة** \> **عام** \> **اتفاقيات الخدمة‬** \> **اتفاقيات الخدمة‬**.

2.  حدد اتفاقية خدمات.

3.  انقر فوق علامة تبويب **تقديم**، ثم انقر فوق **أوامر الخدمة المخططة**.

4.  حدد التواريخ في حقول **من تاريخ** و **إلى تاريخ** لتحديد فترة الخدمة.

5.  حدد خانة الاختيار **إظهار سجل المعلومات** لعرض قائمة بأوامر الخدمات التي يتم إنشاؤها.

6.  حدد أنواع الحركات في مجموعة الحقول **تضمين أنواع الحركات**. تمثل أنواع الحركات البنود التي يتم إنشاؤها في اتفاقية الخدمات، ويقوم كل نوع تختاره من أنواع الحركات بإنشاء العديد من أوامر الخدمة، بناءً على الفاصل الزمني للخدمة الذي يتم تحديده في بند اتفاقية الخدمات.

7.  لإنشاء أي أوامر خدمة مفقودة في السلاسل المتواصلة لأوامر الخدمة، حدد خانة الاختيار **مستمر**.

8.  وانقر فوق **موافق**.

## <a name="create-service-orders-automatically-for-several-service-agreements"></a>إنشاء أوامر خدمة للعديد من اتفاقيات الخدمات تلقائيًا

1.  انقر فوق **إدارة الخدمة** \> **دوري** \> **أوامر الخدمات** \> **إنشاء أوامر الخدمات**.

2.  انقر فوق **حدد** لعمل تحديدات لإضافة أو إزالة المعايير المستخدمة لإنشاء أوامر خدمة.

3.  وانقر فوق **موافق**.

## <a name="see-also"></a>راجع أيضًا

[أوامر الخدمة](service-orders.md)

[إنشاء أوامر الخدمة تلقائيًا](auto-create-service-orders.md)

  


