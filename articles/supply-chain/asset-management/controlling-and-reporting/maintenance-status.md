---
title: حالة الصيانة
description: يشرح هذا الموضوع كيفية حساب حالة الصيانة في إدارة الأصول.
author: josaw1
manager: tfehr
ms.date: 08/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: fbe2b3fd9ce63c34aedb790583dea572d3d9b079
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205450"
---
# <a name="maintenance-status"></a>حالة الصيانة

[!include [banner](../../includes/banner.md)]

 

في إدارة الأصول، يمكنك إجراء عملية حسابية عامة لفترة زمنية محددة للاطلاع على طلبات الصيانة الجديدة والنشطة والمكتملة وأوامر العمل وأنشطة وقت تعطل الصيانة. يمكنك أيضًا رؤية عدد تقييمات الحالات المكتملة لنفس الفترة. استخدم هذه العملية الحسابية للحصول على نظرة عامة حول حمل العمل فيما يتعلق بأوامر العمل وطلبات الصيانة الواردة والمكتملة.

## <a name="make-a-maintenance-status-calculation"></a>إجراء حساب لحالة الصيانة

1. انقر فوق **إدارة الأصول** > **استعلامات** > **حالة الصيانة**.

2. في مربع الحوار **حساب الحالة** ، حدد الفترة التي تريد إجراء حساب لها في الحقلين **من تاريخ** و **إلى تاريخ**.

3. يمكنك استخدام حقل **المستوى** للإشارة إلى مستوى التفصيل الذي ترغب فيه في بنود الصيانة فيما يتعلق بمواقع العمل. 

  على سبيل المثال، إذا قمت بإدراج الرقم "1" في الحقل، وكان لديك بنية موقع عمل متعدد المستويات، فستظهر جميع بنود مراقبة تكاليف أخطاء الأصول لموقع عمل في المستوى العلوي، وبالتالي فإن الحالة على البند قد تُضاف من مواقع عمل موجودة في مستوى أدنى. 
  
  إذا قمت بإدراج الرقم "0" في حقل **المستوى**، فسترى نتيجة مفصلة تعرض جميع بنود الصيانة على جميع مستويات مواقع العمل التي ترتبط بها.

4. انقر فوق **موافق** لبدء الحساب.

5. انقر على الأزرار **تجميع حسب** لإظهار مستوى التفاصيل المطلوب للحساب. يتم تمييز أزرار **تجميع حسب** المحددة. انقر فوق زر لتنشيطه أو إلغاء تنشيطه.

6. تذكر ضرورة النقر فوق الزر **تحديث** لتحديث الحساب في كل مرة تقوم فيها بإدخال تغييرات عن طريق تنشيط الأزرار **تجميع حسب** أو إلغاء تنشيطها، أو من خلال إجراء حسابات لفترة جديدة.

7. انقر فوق **الحالة** إذا كنت تريد إنشاء حساب حالة صيانة جديدة.

>[!NOTE]
>تتضمن النتائج التي تظهر في **حالة الصيانة** فقط طلبات الصيانة وأوامر العمل التي لها تاريخ ووقت بدء فعليين. قد يكون تاريخ ووقت الانتهاء فارغين.

## <a name="example-1"></a>مثال1

في لقطة الشاشة أدناه، تم تنشيط الزرين **السنة** و **الشهر**. من خلال الخيارات **تجميع حسب** المحددة، يمكنك الحصول على نظرة عامة على أساس شهري لحمل العمل والإنتاجية المرتبطة بطلبات الصيانة وأوامر العمل. 

![مثال علي حمل العمل الشهري](media/13-controlling-and-reporting.png)

## <a name="example-2"></a>مثال2

في لقطة الشاشة أدناه، تمت إضافة معلومات حول مواقع العمل. يمكنك الآن مقارنة حمل العمل والإنتاجية عبر مواقع العمل، التي قد تمثل مواقع جغرافية أو مصانع أو مناطق عمل. 

![مثال علي حمل العمل الشهري مع مواقع العمل](media/14-controlling-and-reporting.png)
