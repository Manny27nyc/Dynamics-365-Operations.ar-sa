---
title: إظهار أرصدة الإجازات في واجهة تنفيذ صالة الإنتاج‬
description: يقدم هذا الموضوع مثالاً عن سيناريو الذي يوضح كيفيه إعداد Microsoft Dynamics 365 Supply Chain Management بحيث يستخدم إحصائيات كشوف الرواتب لتزويد العمال بنظرة عامة حول رصيد إجازاتهم للعام الحالي.
author: johanhoffmann
ms.date: 04/22/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-04-22
ms.dyn365.ops.version: 10.0.XX
ms.openlocfilehash: a97858c72b0be50609cee552bd0635e2d68ea478
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645330"
---
# <a name="show-vacation-balances-in-the-production-floor-execution-interface"></a>إظهار أرصدة الإجازات في واجهة تنفيذ صالة الإنتاج‬

[!include [banner](../includes/banner.md)]

يقدم هذا الموضوع مثالاً عن سيناريو الذي يوضح كيفيه إعداد Microsoft Dynamics 365 Supply Chain Management بحيث يستخدم إحصائيات كشوف الرواتب لتزويد كل عامل بنظرة عامة حول رصيد إجازاته للعام الحالي. سيتمكن العاملون من رؤية رصيد إجازاتهم في مربع الحوار **يومي** في واجهه تنفيذ صالة الإنتاج.

يستخدم هذا السيناريو قانون العطلات الدنماركي، حيث تمتد سنة الإجازة من 1 سبتمبر حتى 31 أغسطس. في هذا السيناريو ، قامت شركتك بتوظيف عامل جديد وستمنح هذا العامل رصيدًا عبارة عن إجازة من 10 أيام للقسم المتبقي من سنة الإجازة الحالية.

## <a name="turn-on-the-required-features"></a>تشغيل الميزات المطلوبة

لتشغيل هذا السيناريو ، يجب تمكين الميزة *طريقة العرض "يومي" لواجهة تنفيذ صالة الإنتاج* في [إدارة الميزات](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). للحصول علي معلومات حول كيفيه تمكين هذه الميزة والميزات الأخرى الخاصة بواجهة تنفيذ صالة الإنتاج، راجع [تكوين واجهة تنفيذ صالة الإنتاج](production-floor-execution-configure.md).

## <a name="make-sample-data-available"></a>جعل بيانات العينة متاحة

للعمل بهذا السيناريو باستخدام السجلات والقيم النموذجية المحددة هنا، يجب أن تكون في نظام تم فيه تثبيت [بيانات العرض التوضيحي](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) القياسية. بالإضافة إلى ذلك، يجب أن تحدد الكيان القانوني **USMF** قبل البدء.

## <a name="create-a-new-pay-type"></a>إنشاء نوع دفع جديد

أبدا بإنشاء نوع *نوع دفع* جديد بتعقب أيام إجازات العاملين المكتسبة (يشار اليها أيضًا باسم *رصيد الإجازة*). تُستخدم أنواع الدفع عادةً لحساب الدفع الخاص بالعاملين. ومع ذلك، سيتم استخدام نوع الدفع الذي تقوم بإنشائه هنا لحساب رصيد.

1. انتقل إلى **التوقيت والحضور \> إعداد \> كشف الرواتب \> أنواع الدفع**.
1. في جزء الإجراءات، حدد **جديد** لإضافة صف إلى الشبكة.
1. في الصف الجديد، عيّن القيم التالية:

    - **نوع الدفع:** *5151-1*
    - **الوصف:** *عداد أيام إجازة العامل*
    - **تضمين في التصدير:** *لا*

## <a name="update-the-pay-agreement"></a>تحديث اتفاقية الدفع

في هذا القسم، ستقوم بتحرير *اتفاقية دفع* موجودة عن طريق إضافة نوع الدفع الجديد وإعداد القواعد التي تحدد كيفية تعديل رصيد إجازة كل عامل عند تسجيل أيام الإجازات.

1. انتقل إلى **التوقيت والحضور \> إعداد \> كشف الرواتب \> اتفاقيات الدفع**.
1. حدد اتفاقية الدفع حيث تريد إعداد سياسة الإجازات. (إذا كنت تتعامل مع بيانات عينة USMF القياسية، فهناك اتفاقية دفع واحدة فقط، *Man‎*.)
1. تأكد من صلاحية اتفاقية الدفع المحددة للتاريخ الحالي. إذا كنت تتعامل مع بيانات عينة USMF القياسية، فقد يتم تعيين الحقل **تاريخ الانتهاء** الخاص باتفاقية الدفع *Man* إلى تاريخ يقع في الماضي. قم بتغيير القيمة بحيث تكون سنة أو سنتين في المستقبل، كما هو مطلوب.
1. في جزء الإجراءات، حدد **بنود الاتفاقية**.
1. في الصفحة **بنود اتفاقيه الدفع**، على علامة التبويب السريعة **نظرة عامة**، عيّن القيم التالية على شريط الأدوات:

    - من القائمة المنسدلة الأولى، حدد **الإثنين**.
    - من القائمة المنسدلة الثانية، حدد **الغياب**.

1. في جزء الإجراءات، حدد **جديد** لإضافة صف إلى الشبكة.
1. في الصف الجديد، قم بتعيين حقل **نوع الدفع** إلى نوع الدفع الذي أنشأته لهذا السيناريو (*5151-1*). اترك كافة الحقول الأخرى معينة إلى قيمها الافتراضية.
1. مع استمرار تحديد الصف الجديد، على علامة التبويب السريعة **عام**، قم بتعيين القيم التالية:

    - **كود الغياب:** *إجازة*
    - **استخدام كمية ثابتة:** *نعم*
    - **ثابت:** *-1*

1. في جزء الإجراءات، حدد **نسخ اليوم**.
1. في مربع الحوار **نسخ اليوم**، قم بتعيين القيم التالية:

    - **الثلاثاء** و **الأربعاء** و **الخميس** و **الجمعة:** *نعم*
    - **كتابة فوقية:** *نعم*
    - **الغياب:** *نعم*

1. حدد **موافق**.

## <a name="create-a-payroll-statistic-group"></a>إنشاء مجموعة إحصائيات الرواتب‬

يتم استخدام *مجموعات إحصائيات الرواتب*‬ لإعداد الإحصائيات لتسجيلات العاملين خلال فترة زمنية معينة. في هذا السيناريو، ستستخدم مجموعه إحصائيات الرواتب لحساب عدد أيام الإجازة التي يكسبها العاملون خلال فترة الإجازة. في الدانمرك، تمتد فترة الإجازة من 1 سبتمبر إلى 31 أغسطس.

1. انتقل إلى **التوقيت والحضور \> إعداد \> كشف الرواتب \> مجموعات إحصائيات الرواتب‬**.
1. في جزء الإجراءات، حدد **جديد** لإضافة صف إلى الشبكة.
1. في الصف الجديد، عيّن القيم التالية:

    - **مجموعة إحصائيات الرواتب:** *VAC*
    - **الوصف:** *رصيد الإجازة*
    - **تحويل:** *لا*

1. مع استمرار تحديد الصف الجديد، حدد **إعداد** في جزء الإجراءات.
1. في صفحة **الإعداد**، في جزء الإجراءات، حدد **جديد** لإضافة صف إلى الشبكة.
1. في الصف الجديد، قم بتعيين الحقل **نوع الدفع** إلى *5151-1*.
1. حدد واضغط باستمرار (أو انقر بزر الماوس الأيمن) حقل **كود الفترة**، ثم حدد **عرض التفاصيل**. يمكنك الآن إعداد كود الفترة الذي ستقوم بتعيينه لهذا الحقل لاحقًا.
1. في صفحة **أنواع الدفع**، في جزء الإجراءات، حدد **جديد** لإضافة صف إلى الشبكة.
1. في الصف الجديد، عيّن القيم التالية:

    - **أنواع الفترات:** *VacYear*
    - **الوصف:** *سنة الإجازة*
    - **التكرار:** *سنوات*

1. مع استمرار تحديد الصف الجديد، حدد **إنشاء فترات‬** في جزء الإجراءات.
1. في مربع الحوار **إنشاء فترات‬**، قم بتعيين القيم التالية:

    - **تحديد تاريخ بداية الفترة:** *1 سبتمبر 2021*
    - **طول الفترة:** *5*

1. حدد **موافق**.
1. قم بإغلاق الصفحة أنواع **أنواع الفترات** للرجوع إلى الصفحة **مجموعات إحصائيات الرواتب**.
1. عيّن الحقل **كود الفترة** لنوع الفترة التي بدأتها للتوّ (*VacYear*).

## <a name="create-a-statistical-balance-setup"></a>إنشاء إعداد رصيد إحصائي

في هذا القسم، ستقوم بإنشاء *إعداد رصيد إحصائي* مرتبط بمجموعة إحصائيات الرواتب التي أنشأتها في القسم السابق. وبعد ذلك، ستقوم بربط إعداد الرصيد الإحصائي هذا بطريقة عرض **يومي** في واجهة تنفيذ صالة الإنتاج. ستتمكن عندئذ طريقة عرض **يومي** من عرض أرصدة الإجازة لنوع الدفع المعين إلى مجموعة إحصائيات الرواتب المقترنة.

1. انتقل إلى **التوقيت والحضور \> إعداد \> كشف الرواتب \> إعداد رصيد إحصائي‬**.
1. في جزء الإجراءات، حدد **جديد** لإضافة صف إلى الشبكة.
1. في الصف الجديد، عيّن القيم التالية:

    - **مجموعة إحصائيات الرواتب:** *VAC*
    - **الاسم الخارجي:** *رصيد الإجازة*
    - **مرن:** *لا*

## <a name="create-a-manual-premium"></a>إنشاء مكافأة يدوية

تُستخدم *المكافآت اليدوية* عادةً لمنح العاملين أجرًا إضافيًا مقابل أعمال إضافية. في هذا السيناريو، ستقوم بإنشاء مكافأة يدوية يمكنك استخدامها لتعيين رصيد الإجازة الأولي لكل عامل.

1. انتقل إلى **التوقيت والحضور \> إعداد \> كشف الرواتب \> مكافآت يدوية**.
1. في جزء الإجراءات، حدد **جديد** لإضافة سجل.
1. في السجل الجديد، عيّن القيم التالية:

    - **مكافآت:** *VAC*
    - **الوصف:** *تعديلات على رصيد إجازة العامل*
    - **نوع الدفع:** *5151-1*

## <a name="set-a-workers-initial-vacation-balance-and-adjust-it-by-one-day"></a>تعيين رصيد الإجازة الأولي للعامل وتعديله بمقدار يوم واحد

يستخدم مسؤولو الرواتب الصفحة **موافقة** لمراجعة التسجيلات اليومية للعاملين والموافقة عليها. في هذا السيناريو، ستتولى دور المسؤول بحيث يمكنك تعيين رصيد الإجازة الأولي للعامل وتسجيل أيام الإجازة التي يأخذها العامل.

1. انتقل إلى **التوقيت والحضور \> مراجعة وموافقة \> موافقة**.
1. في مربع الحوار **موافق**، قم بتعيين الحقول التالية:

    - **مجموعة الموافقة** - حدد مجموعة الموافقة التي تنتمي اليها. (إذا كنت تتعامل مع بيانات عينة USMF القياسية، فهناك مجموعة موافقة واحدة فقط، *AdmMan‎*.)
    - **عرض المجموعة بالكامل، يوم واحد‬** – حدد الخيار، ثم عيّن الحقل إلى التاريخ الحالي.

1. حدد **موافق**.
1. تعرض الصفحة **موافقة** قائمة بالسجلات التي تتطابق مع معاييرك. حدد العامل الذي تريد الموافقة عليه. إذا كنت تتعامل مع بيانات عينة USMF القياسية، فحدد العامل *000496* (*كريستينا بورترا*).
1. امنح العامل المحدد إجازة من 10 أيام.

    1. مع استمرار تحديد العامل، حدد **بنود المكافأة‬** في جزء الإجراءات.
    1. في صفحة **بنود المكافأة‬**، في جزء الإجراءات، حدد **جديد** لإضافة صف إلى الشبكة.
    1. في الصف الجديد، عيّن القيم التالية:

        - **مكافآت:** *VAC*
        - **الكمية:** *10*

    1. أغلق صفحة **بنود المكافأة‬**.

1. في الصفحة **موافقة**، سجل حقيقة أن العامل استخدم يومًا من أيام إجازته في التاريخ الحالي:

    1. مع استمرار تحديد العامل، في الجزء السفلي من الصفحة، في علامة التبويب **نظرة عامة**، حدد **جديد** في شريط الأدوات لإضافة صف إلى الشبكة.
    1. في الصف الجديد، عيّن القيم التالية:

        - **نوع تسجيل دفتر اليومية:** *غياب*
        - **المرجع:** *إجازة*

    1. في الجزء العلوي من الصفحة، حدد **تحويل** على شريط الأدوات لتطبيق رصيد الإجازة وحساب الخصم.

## <a name="configure-the-production-floor-execution-interface-so-that-it-includes-the-my-day-dialog-box"></a>تكوين واجهة تنفيذ صالة الإنتاج بحيث تتضمن مربع الحوار "يومي"

في هذا القسم، ستضيف الزر **يومي** إلى واجهة تنفيذ صالة الإنتاج. بعد ذلك، بإمكان العاملين استخدام هذا الزر لفتح مربع الحوار **يومي**.

1. انتقل إلى **التحكم بالإنتاج \> الإعداد \> تنفيذ التصنيع \> تكوين تنفيذ صالة الإنتاج**.
1. حدد تكوينًا، مثل *افتراضي*.
1. في جزء الإجراءات، حدد **تصميم علامات التبويب‬‏‫**.
1. في الصفحة **تصميم علامات التبويب**، في جزء الإجراءات، حدد *كل الوظائف* لعرض إعدادات علامة التبويب هذه. يجب أن يعرض الحقل **طريقة العرض الرئيسية‬** الآن قيمة *كل الوظائف*.
1. في جزء الإجراءات، حدد **تحرير**.
1. على علامة التبويب السريعة **شريط الأدوات الثانوي‬**، في عمود **الإجراءات المتوفرة**، حدد **يومي**. ثم حدد زر السهم إلى اليمين لنقله إلى العمود **الإجراءات المحددة**‬.

## <a name="check-your-balance-in-the-production-floor-execution-interface"></a>راجع رصيدك في واجهة تنفيذ صالة الإنتاج‬.

في هذا القسم، ستقوم بتسجيل الدخول إلى واجهة تنفيذ صالة الإنتاج كالعامل الذي قمت بإعداد وقت إجازته في وقت سابق. ستقوم بعد ذلك بفتح مربع الحوار **يومي**  لعرض رصيد الإجازة.

1. انتقل إلى **التحكم بالإنتاج \> إعداد \> تنفيذ التصنيع \> تنفيذ صالة الإنتاج**.
1. إذا تمت مطالبتك بتحديد تكوين، فحدد التكوين الذي قمت بإعداده في وقت سابق في هذا السيناريو (*افتراضي*).
1. قم بتسجيل الدخول كالمستخدم الذي قمت بإعداده في وقت سابق في هذا السيناريو. ‏إذا كنت تتعامل مع بيانات عينة USMF القياسية، فيجب أن تكون قادرًا على تسجيل الدخول عن طريق إدخال *123* في الحقل **معرف الشارة**. يتطابق معرف الشارة هذا مع كريستينا بورترا.
1. على شريط الأدوات الأيسر، حدد **يومي**.
1. افحص قسم **الأرصدة** في مربع الحوار سيبين هذا القسم الآن أن رصيد أيام الإجازة لديك هو تسعة أيام.