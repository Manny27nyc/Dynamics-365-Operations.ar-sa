---
title: إيقاف التكوينات في المستودع العمومي لـ RCS
description: يوضح هذا الموضوع كيفية إيقاف التكوينات في المستودع العمومي لـ RCS.
author: JaneA07
manager: AnnBe
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-02-02
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 35d0af91161d898b09557a83913019609c71e836
ms.sourcegitcommit: e9d19f25e64cf4d1c1d07c8031a7081454a6f79e
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/18/2021
ms.locfileid: "5474238"
---
# <a name="discontinue-configurations-in-the-rcs-global-repository"></a>إيقاف التكوينات في المستودع العمومي لـ RCS

[!include [banner](../includes/banner.md)]

يوضح هذا الموضوع كيفية إيقاف التكوين في المستودع العمومي لـ RCS. سابقا، كان من الممكن فقط حذف التكوينات التي لم تعد مطلوبة. ومع ذلك يمكنك الآن وضع علامة على التكوين الذي تم إصداره باعتباره **موقوف** في المستودع العمومي لـ RCS. باستخدام هذه الوظيفة، يمكنك أيضًا تنفيذ ما يلي: 
 
 - توفير إخطارات مقدمة عند التخطيط لإيقاف أحد التكوينات.
 - تضمين التفاصيل القابلة للتطبيق حول التكوين البديل.
 - قم بتعيين تاريخ **مدعوم حتى** لتكوين محدد لإعلام المستخدم بمتى سيتم إيقافه.

عندما تقوم بإيقاف إصدار التكوين، يمكنك تحديد المعلومات الاختيارية التالية:

  - **تكوين البديل**
  - **إصدار التكوين البديل**
  - **ملاحظه نص حر**: استخدم هذا الحقل لتوفير ارتباطات أو مراجع الوثائق
  - **مدعوم حتى**: يوفر هذا الحقل التاريخ المقترح الذي سيتم مقابله دعم التكوين/الإصدار الحالي. يجب تحديث هذا التاريخ يدويًا.
  
لإيقاف التكوين، أكمل الخطوات التالية. 

1. حدد ما إذا كنت تريد إيقاف إصدار فردي أو كافة الإصدارات التي لها نفس الإعدادات في عملية واحدة وذلك بإعداد **كافة الإصدارات** إلى **نعم**. 
2. قم بتعيين معلمة **الإيقاف** إلى **نعم**.
3. حدد **موافق** لإيقاف التكوينات. سيتم ملء حقل **تاريخ الإيقاف** عند حفظ التغييرات.

![معلومات إيقاف تكوين](media/Discontinue-details-2.png)
  
يمكنك إعادة التكوين مرة أخرى إلى **مشترك** أو تعديل معلومات الإيقاف في أي وقت. في حالة مشاركة تكوين، حدد تاريخ **مدعوم حتى** وكافة المعلومات الأخرى المرتبطة بالإيقاف للإشارة إلى خطط الإيقاف المستقبلية لك.

إذا كنت ترغب في مشاركة معلومات حول الإيقاف المخطط، قبل إيقاف التكوين الفعلي، فيمكن للمستخدم ملء كافة الحقول المتعلقة بالاستبدال مسبقًا لكن مع ترك المعلمة **إيقاف** معينة إلى **لا**.

> [!NOTE]
> الإيقاف لا يقيد العمليات التي يمكن إجراؤها على التكوينات. يمكنك متابعة استيراد التكوينات أو تشغيلها أو اشتقاقها، تعتبر هذه الحقول معلوماتية.

## <a name="finance-supports-displaying-this-information-starting-in-version-10014"></a>يدعم Finance عرض هذه المعلومات بدءا من الإصدار 10.0.14

بدء من الإصدار 10.0.14، يدعم Dynamics 365 Finance عرض معلومات الإيقاف. في صفحة **المستودع العمومي**، يمكنك عرض أحدث المعلومات المتعلقة بالإيقاف. بشكل افتراضي، تتم تصفية التكوينات التي لم يتم وقفها.
  
تعرض صفحة **التكوينات المستوردة** (ERSolutionTable)، التكوينات التي تم إيقافها بالفعل عند استيرادها. بالنسبة لتلك التكوينات التي لم يتم إيقافها بعد الاستيراد، يمكن مزامنة معلومات الإيقاف عن طريق تشغيل الوظيفة **تحديثات استيراد التكوينات**.

