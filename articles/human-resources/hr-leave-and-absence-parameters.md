---
title: تكوين مُحددات الإجازة والغياب
description: تتيح تحديد معلمات الموارد البشرية للإجازات والغياب في Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: eb992cbfbed33f88e125d3a8b721f8815414599a
ms.sourcegitcommit: 79f8aa2c0b166a423db9b8503da53e96e3fc43dc
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/01/2020
ms.locfileid: "3197971"
---
# <a name="configure-leave-and-absence-parameters"></a>تكوين مُحددات الإجازة والغياب

قبل إعداد خطط الإجازات والإجازات في Dynamics 365 Human Resources، من الأفضل التحقق من الإعدادات لكافة المحددات المتعلقة بالموارد البشرية، بما في ذلك:

- التسلسل الرقمي لطلبات الإجازات
- إعدادات قانون الأسرة والإجازات الطبية (FMLA)
- إعدادات الخدمة الذاتية للموظفين لطلبات الإجازة والغياب
- معلمات الإجازة والغياب

## <a name="view-and-change-human-resources-parameters"></a>عرض محددات الموارد البشرية وتغييرها

1. في صفحة **‏‫الإجازة والغياب‬** حدد علامة التبويب **الارتباطات**.

2. ضمن **الإعداد**، حدد **محددات الموارد البشرية**.

3. في علامة التبويب **التسلسلات الرقمية**، تحقق من **كود التسلسل الرقمي** لـ **معرف طلب الإجازة** وقم بالتغيير حسب الضرورة. يحدد هذا الإعداد التسلسل المستخدم لتعيين المعرفات تلقائيا لطلبات الإجازات.

4. في علامة التبويب **FMLA**، تحقق من إعدادات FMLA وقم بتغييرها حسب الضرورة.

5. في علامة التبويب **الخدمة الذاتية للموظفين**، حدد ما إذا كان بإمكان المديرين إدخال الإجازات وطلبات الغياب نيابة عن موظفيهم.

6. في علامة التبويب **الإجازة والغياب**، تحقق من الإعدادات وقم بتغييرها حسب الضرورة.

7. حدد **حفظ**.

## <a name="view-and-change-leave-and-absence-parameters"></a>عرض وتغيير معلمات الإجازة والغياب

1. في صفحة **‏‫الإجازة والغياب‬** حدد علامة التبويب **الارتباطات**.

2. ضمن **الإعداد**، حدد **معلمات الإجازة والغياب**.

3. على علامة التبويب **عام**، عيّن المعلمات التالية:
 
    - قم بتعيين **وحدة الإجازة والغياب** إلى ساعات أو أيام. إذا اخترت الأيام، فيمكنك تحديد **تمكين تعريف نصف اليوم** للسماح للموظفين باختيار النصف الأول أو النص الثاني لليوم في طلبات الإجازة. 

    - حدد **تاريخ سريان أشهر الخدمة** التي يجب تعيينها عندما تسري معدلات الاستحقاق لخطط الإجازة باستخدام أشهر الخدمة.

    - حدد **حساب الرصيد** لعرض الأرصدة اعتبارًا من اليوم أو من فترة الاستحقاق. إذا حددت **الرصيد اعتبارًا من اليوم**، فسيعرض الرصيد إجمالي كافة الاستحقاقات والتسويات والطلبات اعتبارًا من اليوم. إذا حدد **الرصيد اعتبارًا من فترة الاستحقاق**، فسيعرض الرصيد إجمالي كافة الاستحقاقات والتسويات والطلبات اعتبارًا من فترة الاستحقاق المحددة بواسطة التكرار في خطة الإجازة. 

## <a name="configure-calendar-parameters"></a>تكوين معلمات التقويم

1. في صفحة **‏‫الإجازة والغياب‬** حدد علامة التبويب **الارتباطات**.

2. ضمن **الإعداد**، حدد **معلمات الإجازة والغياب**.

3. في علامة التبويب **تقويم**، وقم بتغيير الإعدادات حسب الضرورة.

4. حدد **حفظ**.

## <a name="see-also"></a>راجع أيضًا

- [نظرة عامة على الإجازة والغياب](hr-leave-and-absence-overview.md)