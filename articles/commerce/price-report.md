---
title: تقارير أسعار البيع بالتجزئة
description: يوفر هذا الموضوع نظرة عامة حول ميزة تقرير الأسعار الذي يمكن استخدامه لعرض التغييرات المقبلة في الأسعار للمنتجات المصنفة.
author: shajain
manager: AnnBe
ms.date: 03/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16181
ms.assetid: b1b57734-1406-4ed6-8e28-21c705ee17e2
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2019-01-18
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: 91c0a96abdd7df9e85e63ca6b1b47a57f3f401eb
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/01/2020
ms.locfileid: "3021526"
---
# <a name="retail-price-reports"></a>تقارير أسعار البيع بالتجزئة

[!include [banner](includes/banner.md)]


يعمل بائعو التجزئة في الكثير من الأحيان الأسعار على تغيير أسعار المنتجات بهدف تقديم أسعار تنافسية لعملائهم. يرغب مدراء المتاجر في الحصول على إمكانية الوصول بسهولة إلى التغييرات في الأسعار، الحديثة منها أو القادمة، لكي يتمكنوا من التخطيط للموارد المطلوبة لتحديث ملصقات الأسعار المعروضة على أرفف المتجر. مع الإصدار 10.0 من Retail، بإمكان مدير المتجر أن يفتح تقرير **الأسعار** عن طريق الانتقال إلى **جميع المتاجر \> المتجر \> تقرير الأسعار** وعرض الأسعار المحدّثة للمنتجات المرتبطة بالمتجر. 

لتمكين تقرير الأسعار يجب تشغيل المعلمة، **تمكين تقرير الأسعار لمتجر**. توجد هذه المعلمة على علامة التبويب **معلمات Commerce\> الخصومات \> متنوعة‬**. يؤدي فتح صفحة **تقرير الأسعار** إلى عرض مربع حوار يتضمن تكوينات مختلفة. تم إدراج أدناه التكوينات المتوفرة.

| التكوين | ‏‏الوصف |
|---|---|
| تاريخ "من" / تاريخ "إلى"| نطاق التاريخ الذي يجب إنشاء تقرير الأسعار له. المدة محددة بسبعة (7) أيام في الوقت الحالي. |
| التدفقات| المتجر الذي يجب إنشاء تقرير الأسعار له. |
| عرض منتجات مع المخزون المتوفر| يؤدي تعيين هذا الخيار إلى **نعم** إلى عرض أسعار فقط المنتجات التي لديها مخزون فعلي في المتجر. |
| عرض أسعار للمتغيرات | يؤدي تعيين هذا الخيار إلى **نعم** إلى عرض أسعار المتغيرات مع أصول المنتجات. يجب **تشغيل** هذا الخيار فقط عند وجود أسعار متغيرات معينة، لأن عدد الصفوف يصبح كبيرًا جدًا. في الإصدارات المستقبلية، سنعمل على تمكين الأسعار المستندة إلى الأبعاد لتمكين مدير المتجر من اختيار الأبعاد التي يجب عرض الأسعار لها. |
| عرض منتجات مع تغييرات الأسعار | يؤدي تعيين هذا الخيار إلى **نعم** إلى عرض الأسعار فقط للتواريخ التي تم فيها تغيير السعر. سيكون السعر *قبل يوم واحد* من **التاريخ "من"** المحدد معروضًا بشكل دائم، لتمكين مدير المتجر من التعرف بسهولة على المنتجات التي لم تتغير أسعارها خلال المدة المحددة، ولتمكينه أيضًا من عرض السعر الحالي. |

بعد إنشاء التقرير، يمكن تنزيل ملف Excel لإجراء أي عمليات تصفية إضافية مطلوبة. يمكن استخدام تقرير الأسعار أيضًا للتحقق من الأسعار القديمة للمنتجات للتواريخ السابقة.