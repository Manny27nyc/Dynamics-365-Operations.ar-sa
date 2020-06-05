---
title: دورات الصيانة
description: يشرح هذا الموضوع دورات الصيانة في إدارة الأصول.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
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
ms.openlocfilehash: 97f1984b71ab60519f81bb1f6ab38278a0e5aa43
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/02/2020
ms.locfileid: "3206094"
---
# <a name="maintenance-rounds"></a>دورات الصيانة

[!include [banner](../../includes/banner.md)]

 

في **إدارة الأصول**، يمكنك إنشاء دورات الصيانة لأصول مختلفة تحتاج إلى تنفيذ مهمة مماثلة عليها على فترات منتظمة على سبيل المثال، مهام التشحيم أو فحص السلامة التي يجب تنفيذها على عدد من الأجهزة خلال الفترات الزمنية نفسها. يجب أولاً إنشاء دورة صيانة، بما في ذلك الأصول التي تتطلب نموذج مهمة الصيانة نفسه. بعد ذلك، يمكنك جدولة دورات الصيانة. وعند إكمال جدول دورات الصيانة، يمكنك الاطلاع على كافة سجلات المهام المرتبط بدورة الصيانة في **جدول الصيانة بكامله** و**بنود جدول الصيانة المفتوحة**.

>[!NOTE]
>يمكن أيضًا إعداد دورات الصيانة على مواقع العمل التي يجب إكمالها على الأصول المثبتة في موقع العمل عند إنشاء أمر العمل الذي يستند إلى دورة الصيانة. راجع [إنشاء مواقع عمل‬](../functional-locations/create-functional-locations.md) لمزيد من المعلومات حول إعداد دورات الصيانة على مواقع العمل.

## <a name="set-up-a-maintenance-round"></a>إعداد دورة الصيانة

1. انقر فوق **إدارة الأصول** > **الإعداد** > **الصيانة الوقائية** > **دورات الصيانة**.

2. انقر فوق **جديد** لإنشاء دورة صيانة جديدة.

3. أدخل معرفًا في حقل **دورة الصيانة** واسمًا لدورة الصيانة في حقل **الاسم**.

4. في الحقل **تاريخ البدء**، حدد تاريخ بدء دورة الصيانة.

5. في الحقلين **الانتهاء ضمن الأيام** و**الانتهاء ضمن الساعات**، يمكنك إدخال تاريخ الانتهاء المتوقع بالأيام أو الساعات. يتم حساب تاريخ الانتهاء المتوقع بالنسبة إلى تاريخ البدء، والذي يتم حسابه عند إنشاء بنود جدولة الصيانة. على سبيل المثال، يمكنك إدخال "7" في حقل **الانتهاء ضمن الأيام** للإشارة إلى أنه يجب إكمال المهمة ذات الصلة خلال أسبوع من تاريخ البدء.

6. حدد "نعم" على زر التبديل **إنشاء تلقائي** إذا كان يجب إنشاء أوامر العمل تلقائيًا من بنود جدول الصيانة التي يتم إنشاؤها من دورة الصيانة هذه.

7. في الحقل **نوع أمر العمل**، حدد نوع أمر العمل المطلوب استخدامه على أوامر العمل التي تم إنشاؤها لدورة الصيانة هذه.

8. في الحقل **مستوى الخدمة**، حدد مستوى خدمة أمر العمل المطلوب استخدامه على أوامر العمل التي تم إنشاؤها لدورة الصيانة هذه.

9. على علامة التبويب السريعة **بنود الأصول**، انقر فوق **إضافة** لإضافة أصل إلى دورة الصيانة.

10. يتم إدخال رقم بند بشكل تلقائي في حقل **رقم البند** للإشارة إلى تسلسل الأصول في دورة الصيانة.

11. حدد الأصل في حقل **الأصل**.

12. حدد نوع مهمة الصيانة للأصل في الحقل **نوع مهمة الصيانة**.

13. حدد **متغير نوع مهمة الصيانة** و**المعاملات** ذات الصلة بنوع مهمة الصيانة، إذا لزم الأمر.

14. حدد التكرار (يوم، أسبوع، غير ذلك) في الحقل‏‎ **نوع الفترة**.

15. في الحقل **تكرار الفترة**، أدخل عدد مرات التكرار لدورة الصيانة. مثال: إذا قمت بتحديد "يوم" في حقل **نوع الفترة**، وأدخلت الرقم "7" في هذا الحقل، سيتم إنشاء بنود دورة صيانة جديدة أثناء جدولة الصيانة الوقائية مرة واحدة في الأسبوع.

16. حدد تاريخ بدء للأصل ليتم تضمينه في دورة الصيانة في الحقل **تاريخ البدء**. قد يختلف هذا التاريخ عن تاريخ البدء المحدد على دورة الصيانة.

17. كرر الخطوات من 9 إلى 16 لإضافة المزيد من الأصول إلى دورة الصيانة.

18. على علامة التبويب السريعة **بنود موقع العمل**، انقر فوق **إضافة** لإضافة موقع عمل إلى دورة الصيانة. يمكنك مراجعة وصف الحقول ذات الصلة أعلاه. تتوفر الحقول نفسها لإنشاء بند أصل، ولكن يمكنك أيضًا إضافة **شركة مصنعة** و**نموذج** لموقع عمل، إذا لزم الأمر. إذا حددت فقط موقع عمل على بند، ولكن من دون إجراء تحديدات في **نوع الأصل** و**الشركة المصنعة** و**النموذج** و**نوع مهمة الصيانة** و**متغير نوع مهمة الصيانة** و**المعاملات**، فسيتم تضمين جميع الأصول المرتبطة بموقع العمل هذا عند جدولة الصيانة في دورة الصيانة.

19. على علامة التبويب السريعة **المجموعات**، انقر فوق **إضافة** لتحديد مجموعة أوامر عمل لتضمينها في في دورة الصيانة. يمكن ربط العديد من مجموعات أوامر العمل بدورة صيانة واحدة.

20. احفظ إعدادك.

>[!NOTE]
>تعرض حقول **الأصول** و**البنود** في مجموعة **التفاصيل** على علامة التبويب السريعة **الرأس** العدد الإجمالي للأصول والبنود ذات الصلة بدورة الصيانة المحددة.

يُبين الرسم التوضيحي التالي ويضرب مثالًا لدورة الصيانة التي تحتوي على ثلاثة أصول.

![الشكل 1](media/13-preventive-maintenance.png)


## <a name="schedule-maintenance-rounds"></a>دورات الصيانة المجدولة

عند إعداد دورة صيانة، تقوم بتشغيل مهمة جدولة لجدولة جميع المهام المرتبطة بدورة الصيانة.

1. انقر فوق **إدارة الأصول** > **دوري** > **الصيانة الوقائية** > **جدولة دورات الصيانة** أو **إدارة الأصول** > **عام** > **جدول الصيانة** > **جدول الصيانة** أو **بنود جدول الصيانة المفتوحة** أو **مجموعات جداول الصيانة المفتوحة** > حدد بند جدول صيانة في القائمة > زر **دورات الصيانة**.

2. في الحقل‏‎ **الفترة**، حدد نوع الفترة التي يجب استخدامها لوظيفة الجدولة.

3. في الحقل **تكرار الفترة**، أدخل عدد الفترات الزمنية المطلوب تضمينها في وظيفة الجدولة. بداية الجدولة هي التاريخ الحالي.

4. حدد "نعم" على زر التبديل زر **إنشاء تلقائي**  إذا كان يجب إنشاء أمر عمل تلقائيًا استنادًا إلى دورة صيانة.

>[!NOTE]
>إذا تم تعيين زر التبديل هذا إلى "نعم" وأيضًا زر التبديل **تشغيل تلقائي** إلى "نعم" على دورة الصيانة في نموذج **دورات الصيانة**، فسيتم أيضًا إنشاء أوامر العمل استنادًا إلى بنود دورة الصيانة وبنود جدول الصيانة مع الحالة "تم إنشاء أمر العمل". إذا تم تعيين زر واحد فقط من أزرار التبديل **إنشاء تلقائي** إلى "نعم"، في هذه القائمة المنسدلة أو في **دورات الصيانة**، فسيتم إنشاء بنود جدول الصيانة فقط مع الحالة "تم الإنشاء". في هذه الحالة، لا يتم إنشاء أوامر عمل.

5. إذا لزم الأمر، يمكنك تحديد دورات معينة أو تاريخ بدء آخر لوظيفة الجدولة. انقر فوق‏‎ **تصفية**، وأضف الدورات التي سيتم تضمينها.

6. انقر فوق **موافق**.

7. يمكنك الآن رؤية مهام دورات الصيانة في **إدارة الأصول** > **عام** > **جدول الصيانة** > **جدول الصيانة بكامله** أو **بنود جدول الصيانة المفتوحة**. إذا كانت دورات الصيانة المجدولة مرتبطة بمجموعة أوامر عمل أخرى، فسترى أيضًا بنود جدول الصيانة في  **مجموعات جدول الصيانة المفتوحة**. سيكون نوع المرجع لبنود جدول الصيانة التي تم إنشاؤها من دورة "دورات صيانة".

يُبين الرسمان التوضيحيان أدانه مهمة الجدول في مربع حوار **دورات الصيانة المُجدولة**، وبنود جدول الصيانة التي تم إنشاؤها في **كل جداول الصيانة** بناءً على مهمة الجدولة هذه.

![الشكل 2](media/14-preventive-maintenance.png)

![الشكل 3](media/15-preventive-maintenance.png)

- عند إنشاء أوامر العمل يدويًا على الأصول التي تتم تغطيتها بواسطة ضمان المورّد، يتم عرض مربع حوار لإعلام المستخدم بالضمان. ويمكن بعد ذلك إلغاء إنشاء أمر العمل. ويتم حذف عملية الفحص الخاصة بعلاقة الضمان لأوامر العمل التي يتم إنشاؤها تلقائيًا.  
- يمكنك إعداد وظيفة دفعية على علامة التبويب السريعة **تشغيل في الخلفية** لجدولة الدورات على فترات زمنية منتظمة.  
- إذا تم تضمين دورة في مجموعات أوامر عمل متعددة، (راجع [مجموعات أوامر العمل](../work-orders/work-order-pools.md))، يظهر سجل واحد لكل مجموعة في **مجموعات جدول الصيانة المفتوحة‬‏‫**. ويتم ذلك لتحسين خيارات التصفية لمجموعات أوامر العمل.
