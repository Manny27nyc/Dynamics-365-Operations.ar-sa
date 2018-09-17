---
title: "أوامر الخدمة"
description: "يمثل أمر الخدمة الزيارة التي قام بها فني الخدمة إلى موقع العميل في تاريخ معين."
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
ms.openlocfilehash: 647bbe9cca0167d33048ad07e092708f90b41fc3
ms.contentlocale: ar-sa
ms.lasthandoff: 05/08/2018

---

# <a name="service-orders"></a>أوامر الخدمة   

[!include [banner](../includes/banner.md)]


يمثل أمر الخدمة الزيارة التي قام بها فني الخدمة إلى موقع العميل في تاريخ معين. يتكون كل أمر من أوامر الخدمة من بند واحد أو أكثر من بنود الخدمة. وتمثل بنود أمر الخدمة ساعات العمل التي يجب أن ينفذها فني الخدمة، والأصناف والمصاريف والرسوم.

يمكنك إرفاق المهام والكائنات ببند أمر خدمة. بعد ذلك يمكنك تجميع بنود أوامر الخدمة حسب المهام أو كائن. كما يمكن أيضًا إرفاق الأصناف التي تم إدراجها في المخزون ببنود أوامر الخدمة.

## <a name="create-service-orders"></a>إنشاء أوامر الخدمة

ويمكنك إنشاء أوامر الخدمات استنادًا إلى اتفاقية الخدمة والبنود الواردة في تلك الاتفاقية. ومع ذلك، يمكنك إنشاء أوامر الخدمة المرتبطة باتفاقية خدمة فقط في الفترة المحددة في الاتفاقية. على سبيل المثال، إذا كانت اتفاقية خدمة ما صالحة لسنة التقويم 2011، يمكنك إنشاء أوامر الخدمة للاتفاقية من 1 يناير 2011، و31 ديسمبر عام 2011.

ويمكنك أيضًا إنشاء أوامر الخدمة فرديا، دون إقرانها باتفاقية. يمكن استخدام أوامر الخدمة هذه لمعالجة زيارات الخدمة الطارئة أو لمرة واحدة. على سبيل المثال، في شهر مارس يريد العميل تلقي خدمة على آلتين، بالإضافة للآلات المخصصة في اتفاقية الخدمة. في هذه المهمة، يمكنك إنشاء أوامر الخدمة ولكن دون إقرانها باتفاقية.


> [!NOTE]
> <P>لإنشاء أوامر الخدمة التي لا ترتبط باتفاقية خدمة، يجب عليك تحديد خانة الاختيار <STRONG>السماح بدون اتفاقية خدمات</STRONG> في النموذج <STRONG>محددات إدارة الخدمة</STRONG>.</P>

**سيناريو**

يوضح السيناريو التالي موقفًا آخر حيث يكون من المفيد إنشاء أمر خدمة غير مرتبط باتفاقية خدمة.

يستلم مرسِل الشركة مكالمة لطلب خدمة طوارئ لأحد المصاعد. لا يوجد وقت لإعداد اتفاقية خدمة ومشروع للخدمة. لذلك، أنشأ المرسل أمر خدمة مباشرة في النموذج **أوامر الخدمة** ، وأرفق أمر الخدمة بمشروع موجود، ثم أنشأ بنود أمر الخدمة. أنشأ المرسل أيضًا مهمة أو علاقة كائن لأمر خدمة موجود بالفعل، لتسجيل عمل غير مرتبط باتفاقية الخدمة. للحصول على مزيد من المعلومات، راجع [إنشاء أوامر خدمة يدوياً](create-service-orders-manually.md) و [إنشاء علاقات مهام الخدمة](create-service-task-relations.md).

## <a name="monitor-the-progress-of-service-orders"></a>مراقبة تقدم أوامر الخدمة

لمراقبة تقدم أمر مبيعات عبر الفرق المختلفة وعمليات العمل، يمكنك إعداد نظام مراحل وأكواد سبب لأوامر الخدمة. ولكل مرحلة، يمكنك تحديد الإجراءات المسموح بها. لمزيد من المعلومات، راجع [إنشاء أكواد السبب](create-reason-codes.md).

**مثال**

يتم اعتماد أمر خدمة بواسطة المرسل. يقوم المرسل بتحديث مرحلة أمر الخدمة ويحدد كود سبب والذي يشير إلى أنه قد تم إصدار أمر الخدمة لفني الخدمة. ويتوجه الفني إلى موقع العميل ويؤدي الخدمة.

## <a name="specify-item-requirements-for-service-orders"></a>تحديد متطلبات الصنف لأوامر الخدمة

يمكنك تحديد أصناف المخزون المطلوبة لأوامر الخدمة. ومع ذلك، يجب أن يكون أمر الخدمة مرتبطًا بمشروع. تتم معالجة متطلبات الصنف لأوامر الخدمة من خلال مشروع. 

**مثال**

ويقوم المرسِل بمعالجة أوامر الخدمة التي تم إنشاؤها من اتفاقية الخدمة. ويدرك المرسِل من أول أمر خدمة أن الفني يطلب قطعة غيار مهمة وغير متاحة في المخزون. لذلك، يقوم المرسل بإنشاء متطلب صنف لقطعة الغيار مباشرة من أمر الخدمة.

## <a name="move-and-post-lines"></a>بنود النقل والترحيل

عند عودة الفني من زيارة الخدمة، وبعد ذلك يقوم بتعديل بنود أوامر الخدمة ويحدّثها. أثناء قيامه بالزيارة، نفذ الفني مهمة الخدمة التي كان من المجدول تنفيذها في زيارة الخدمة التالية. بالتالي، ينقل الفني البنود من زيارة الخدمة التالية إلى زيارة الخدمة الحالية. بعد ذلك يرحِّل الفني أمر الخدمة. لمزيد من المعلومات، راجع [ترحيل بنود أمر الخدمة](move-service-order-lines.md).

## <a name="cancel-service-orders"></a>إلغاء أوامر الخدمة

أصبح أحد أوامر الخدمة الذي تم إنشاؤه لشهر يناير مهملاً بسبب إلغاء المهمة. لذلك، يقوم مرسِل الخدمة بإلغاء أمر الخدمة. لمزيد من المعلومات، راجع [إلغاء أوامر الخدمة](cancel-service-orders.md).

## <a name="post-from-projects"></a>الترحيل من المشروعات

يريد المرسل في نهاية كل أسبوع ترحيل كل أوامر الخدمة التي تم إرفاقها بمشروع معين. لذلك، يقوم المرسل بتحديد موقع المشروع ذي الصلة في نموذج **المشاريع** ويرحِّل أوامر الخدمة التي تم إكمالها. لمزيد من المعلومات، راجع [ترحيل أوامر الخدمة (نموذج الفئة)](https://technet.microsoft.com/en-us/library/aa574685\(v=ax.60\)).

## <a name="delete-service-orders"></a>حذف أوامر الخدمة

وأثناء النصف الثاني من السنة، يقرر العميل أن زيارات الخدمة أقل من اللازم. ويجب إنشاء سلسلة زيارات جديدة ومتكررة الحدوث بشكل أكبر خلال الفترة المتبقية في اتفاقية الخدمة. لذلك يجب حذف أوامر الخدمة الموجودة وإنشاء أوامر خدمة جديدة. لمزيد من المعلومات، راجع [حذف أوامر الخدمة](delete-service-orders.md).

## <a name="see-also"></a>راجع أيضًا

[أوامر الخدمة (نموذج)](https://technet.microsoft.com/en-us/library/aa554361\(v=ax.60\))

  


