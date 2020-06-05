---
title: التحديث اليدوي لعدادات الأصول
description: يصف هذا الموضوع التحديث اليدوي لعدادات الأصول‬ في إدارة الأصول.
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
ms.openlocfilehash: 9d9cd755f5dec125676a8dbefe63a64e226366ed
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/02/2020
ms.locfileid: "3204506"
---
# <a name="manual-update-of-asset-counters"></a>التحديث اليدوي لعدادات الأصول

[!include [banner](../../includes/banner.md)]



تُستخدم العدادات لإنشاء تسجيلات في أحد الأصول، مثل التسجيلات الخاصة بعدد الساعات التي تم فيها تشغيل الأصل أو الكمية التي تم إنتاجها.

قد يكون نوع العداد المحدد للعداد معينًا ليرث قيم العدادات. بمعني آخر، يتم تعيين الخيار **توارث قيم عداد الأصول** إلى **نعم** في علامة التبويب السريع **عام** في صفحة **العدادات** (**إدارة الأصول** > **إعداد** > **أنواع الأصول** > **العدادات**). في هذه الحالة، عند إنشاء بند عداد جديد من هذا النوع، يتم تحديث كل أصل تابع يستخدم نفس نوع العداد تلقائيًا.

في صفحة **كافة الأصول** ، يمكنك إنشاء تسجيلات العداد للساعات أو الكميات على أصل ما استنادًا إلى قراءاتك على الأصل.

1. حدد **إدارة الأصول** > **مشترك** > **الأصول** > **كافة الأصول**.

2. حدد الأصل، ثم في جزء الإجراء، ضمن علامة التبويب **الأصل** ، في مجموعة **الوقائي** ، حدد **عدادات**. تظهر الصفحة **عدادات الأصول** قائمة بجميع تسجيلات العدادات السابقة التي تم إجراؤها على الأصل المحدد.

3. حدد **جديد** لإنشاء التسجيل. يتم إدخال الاسم تلقائيًا في حقل **الأصل**.

4. في حقل **العداد**، حدد العداد المناسب. لا تتوفر سوى العدادات المرتبطة بنوع الأصل المحدد في الأصل. يتم إدخال الوحدة ذات الصلة بشكل تلقائي في حقل **الوحدة**.

5. في الحقل **مُسجل** ، حدد التاريخ والوقت الخاصين بتسجيل العداد.

6. في حقل **القيمة** ، ادخل الرقم منذ آخر تسجيل للعداد. وبدلاً من ذلك، ادخل إجمالي العدد في حقل **القيمة المجمعة** .

لاحظ النقاط التالية:

- إذا قمت بتثبيت عداد جديد بشكل فعلي على أصل ما، فيجب تسجيل التغيير على الأصل في صفحة **عدادات‏‎ الأصول**. بعد ذلك، يجب أن تقوم بإنشاء اثنين من بنود التسجيل التي تحتوي علي طوابع زمنيه متماثلة. يجب أن يكون البند الأول للعداد الذي تقوم باستبداله. في البند المرتبط بالعداد الجديد، حدد خانه الاختيار **إعادة تعيين العداد** . في حقل **الإجماليات** ، يتطابق العدد الإجمالي مع مجموع إجماليات العداد لكافة القيم المسجلة في نوع هذا العداد.

- إذا تم تحديد خانة الاختيار **إعادة تعيين العداد** على أحد الأصول باستخدام خطة الصيانة التي يكون نوع الفترة الزمنية الخاص بها "مرة واحدة من..." أو "عند الوصول..."، يظل العداد نشطًا على بند العداد الجديد لأنك قمت بإنشاء بند عداد منفصل وبدأت من جديد باستخدام عداد جديد.

يبين الرسم التوضيحي التالي مثالاً لصفحة **عدادات الأصول**.

![الشكل 1](media/11-work-orders.png)

في الصفحة **عدادات الأصول** (**إدارة الأصول** > **استعلامات** > **الأصول** > **عدادات الأصول**)، يمكنك إجراء تسجيلات العداد في العديد من الأصول في نفس الوقت، كما هو مطلوب.

>[!NOTE]
>يمكنك إعداد نطاق لتحديد الانحرافات في تسجيلات العداد يدويًا. يمكنك أيضًا تحديد نوع الرسالة التي يتم عرضها في حالة ما إذا كانت التسجيلات خارج النطاق المحدد. للحصول علي المزيد من المعلومات حول كيفية إعداد العدادات، راجع [العدادات](../setup-for-objects/counters.md).
