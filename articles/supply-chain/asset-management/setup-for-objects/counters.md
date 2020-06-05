---
title: قياسات الأصول
description: يشرح هذا الموضوع كيفية إنشاء أنواع قياسات الأصول في إدارة الأصول.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
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
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d128a7d20891353927441bb343831876d72aecbe
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208882"
---
# <a name="counters"></a>العدادات

[!include [banner](../../includes/banner.md)]

يشرح هذا الموضوع كيفية إنشاء أنواع العدادات في إدارة الأصول. تُستخدم أنواع العدادات لإجراء تسجيلات العدادات على الأصول، على سبيل المثال، فيما يتعلق بعدد ساعات الإنتاج، أو الكمية المنتجة على الأصل. ترتبط أنواع الأصول بأنواع العدادات. وهذا يعني أنه لا يمكن استخدام العداد على أحد الأصول إلا إذا تم إعداد العداد على نوع الأصل المستخدم في الأصل.

قبل أن تتمكن من إجراء تسجيلات العدادات على الأصول، تقوم أولاً بإنشاء أنواع العدادات التي تريد استخدامها في **العدادات**. بعد ذلك، يمكنك إنشاء تسجيلات العدادات على الأصول في **العدادات**. 

يمكن استخدام العدادات في خطط الصيانة. بإمكان بند خطة الصيانة أن يكون من نوع "العداد"، على سبيل المثال، فيما يتعلق بعدد ساعات الإنتاج أو الكمية المنتجة. 

ويمكن تحديث تسجيل العداد يدويًا أو تلقائيًا استنادًا إلى ساعات الإنتاج أو الكمية المنتجة. يمكن إعداد العداد لاستخدام إحدى طرق التحديث الثلاث (محددة في الحقل **تحديث** في **العدادات**):
  
- يدوي - يجب تسجيل قيم العداد يدويًا.  
- ساعات الإنتاج - يتم تحديث العداد تلقائيًا استنادًا إلى عدد ساعات الإنتاج.  
- كمية الإنتاج - يتم تحديث العداد تلقائيًا استنادًا إلى كميات الإنتاج.  

>[!NOTE]
>إذا تم استخدام الكمية المنتجة، فسيتم تضمين *جميع* الأصناف المسجلة في تسجيلات العداد، الكمية الجيدة بالإضافة إلى الكمية التي تتضمن أخطاء. من الممكن دائمًا إجراء تسجيلات يدوية للعداد، إذا لزم الأمر.

## <a name="create-counter-types-for-asset-counter-registrations"></a>إنشاء أنواع عدادات لتسجيلات عدادات الأصول

1. حدد **إدارة الأصول** > **الإعداد** > **أنواع‏‎ الأصول** > **العدادات‏‎**.
2. حدد **جديد** لإنشاء نوع عداد جديد.
3. أدخل معرفًا في حقل **العداد** واسم عداد في حقل **الاسم**.
4. على علامة التبويب السريعة **عام** ، حدد وحدة العداد في حقل **الوحدة** .
5. في الحقل‏‎ **تحديث** ، حدد طريقة التحديث المراد استخدامها للعداد.
6. حدد "نعم" على زر التبديل **توارث قيم العداد** إذا كان يجب على الأصول التابعة في بنية الأصول أن ترث بشكل تلقائي تسجيلات العداد التي تم إجراؤها على الأصل الأساسي.
7. في حقل **إجمالي المجموع‬** ، حدد طريقة التجميع المراد استخدامها للعداد باستخدام نوع العداد هذا. التحديد القياسي المستخدم لإضافة قيم مسجلة باستمرار إلى القيمة الإجمالية هو "الجمع". يمكن استخدام "المتوسط" إذا تم إعداد العداد لمراقبة حد، على سبيل المثال، فيما يتعلق بدرجة الحرارة أو الاهتزازات أو تآكل الأصل نتيجة الاستهلاك. 
8. في الحقل **انحراف لأعلى‬** ، أدخل المستوى الأعلى بالنسبة المئوية للتحقق مما إذا كانت تسجيلات العداد اليدوية ضمن نطاق متوقع. تستند عملية التحقق من الصحة إلى زيادة خطية في تسجيلات العداد الموجودة.
9. في الحقل **انحراف تحت‬** ، أدخل المستوى الأقل بالنسبة المئوية للتحقق مما إذا كانت تسجيلات العداد اليدوية ضمن نطاق متوقع. تستند عملية التحقق من الصحة إلى انخفاض خطي في تسجيلات العداد الموجودة.
10. في حقل **النوع** ، حدد نوع الرسالة (معلومات، تحذير، خطأ) التي سيتم عرضها في حالة حدوث انحرافات خارج النطاق المحدد عند إجراء تسجيلات العداد اليدوية.
11. على علامة التبويب السريعة **أنواع الأصول** ، أضف أنواع الأصول التي يجب أن تكون قادرة على استخدام العداد.
12. على علامة التبويب السريعة **عدادات الأصل ذات الصلة** ، أضف العداد الذي تريد تحديثه تلقائيًا عند تحديث هذا العداد.


>[!NOTE]
>لا يتم تحديث العداد ذو الصلة تلقائيًا إلا إذا كان العداد ذو الصلة يحتوي على نوع الأصل، الذي يرتبط به، في إعداد العداد. على سبيل المثال: يمكنك إعداد العداد "لساعات الإنتاج" وإضافة نوع الأصل "محرك الشاحنة". وعندما يتم تحديث هذا العداد، يتم أيضًا تحديث عداد "الزيت" ذي الصلة بنفس قيم العداد. يتضمن الإعداد في **العدادات** الإعداد على "الساعات". كذلك الأمر، يجب إضافة نوع الأصل "محرك الشاحنة" على عداد "الزيت" إلى علامة التبويب السريعة **أنواع الأصول** لضمان علاقة العداد. راجع لقطات الشاشة أدناه للحصول على مثال على الإعداد على عدادات "الساعات" و"الزيت".

عند إضافة أنواع الأصول إلى نوع العداد في **العدادات**، يُضاف هذا العداد تلقائيًا إلى أنواع الأصول على علامة التبويب السريعة **العدادات** في [أنواع الأصول](../setup-for-objects/object-types.md).

![الشكل 1](media/071-setup-for-objects.png)
