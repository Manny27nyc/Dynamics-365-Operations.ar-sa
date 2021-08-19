---
title: جاهز للدفع
description: يوضح هذا الموضوع كيفية وضع علامة على الموظف على أنه جاهز للدفع في Dynamics 365 Human Resources.
author: marcelbf
ms.date: 07/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-07-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f9aa9e60b51b1801c07981ad120cb77f65fee286
ms.sourcegitcommit: baad2723291774f610324a8054fc14abf3287fe1
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/14/2021
ms.locfileid: "6560089"
---
# <a name="ready-to-pay"></a>جاهز للدفع

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [preview feature](./includes/preview-feature.md)]

> [!NOTE]
> إذا كنت تريد وضع علامة على الموظف على أنه جاهز للدفع، فيجب عليك أولا تمكين **(معاينة) وظيفة تكامل الرواتب** في إدارة الميزات. لمزيد من المعلومات حول تمكين ميزات المعاينة، راجع [إدارة الميزات](hr-admin-manage-features.md).

تمكن هذه الميزة محترفي الموارد البشرية من فهم الموظفين المستعدين لمعالجة كشوف المرتبات والذين يحتاجون إلى إجراء قبل استهلاكهم من قبل موفر رواتب تابع لجهة خارجية.

## <a name="mark-employee-as-ready-to-pay"></a>وضع علامة على الموظف على أنه جاهز للدفع

يمكن أن يستغرق جمع معلومات الموظف والتحقق من صحتها وقتا طويلا وعرضة للخطأ. من خلال توفير وسيلة لمحترفي الموارد البشرية لمراجعة معلومات الموظفين وتحديثها بسهولة، يساعد Dynamics 365 Human Resources على تقليل الوقت الذي يقضيه في الاستعداد لمعالجة كشوف المرتبات.

لوضع علامة على الموظف كجاهز للدفع:

1. انقر فوق **إدارة التعويض**. هناك نوعان من التجانبات في مساحة العمل 
    - **الموظفون جاهزون للدفع**
    - **الموظفون غير مستعدين لدفع**
    ![مساحة عمل إدارة التعويض.](./media/hr-ready-to-pay-1-workspace.png)

2. حدد المربع **الموظفون غير المستعدين للدفع**.

3. حدد الموظفين المطلوب التحقق من صحتها. في **علامة التبويب الرواتب**، في المجموعة **جاهز للدفع**، حدد **التحقق من صحة**.
    ![التحقق من صحة الموظفين.](./media/hr-ready-to-pay-2-validate.png)

4. لمراجعة النتائج، في **علامة التبويب الرواتب**، في المجموعة **جاهز للدفع**، حدد **النتائج**.

## <a name="validation"></a>التحقق من الصحة

قبل وضع علامة على الموظف على أنه مستعد للدفع، سيقوم النظام بالتحقق الأساسي من صحة اكتمال الملف الشخصي.

![التحقق من صحة النتائج.](./media/hr-ready-to-pay-3-results.png)

يوفر الجدول التالي معلومات حول كل عملية تحقق من الصحة يتم تنفيذها. 

| التحقق من الصحة | تفاصيل |
| --- | --- |
| معلمة غرض العنوان | التحقق من صحة إذا كانت المعلمة **استخدام الرواتب عنوان الغرض** قيد تشغيل. |
| عنوان كشف الرواتب | التحقق من صحة ما إذا كان ملف تعريف العامل يحتوي على عنوان واحد على الأقل مع الغرض "موقع الإقامة في المرتبات" أو "موقع عمل الرواتب"، وهناك عنوان واحد فقط لكل غرض. |
| التوظيف | تحقق مما إذا كان العامل لديه وظيفة واحدة على الأقل (الحالية أو السابقة أو المستقبلية). |
| رقم التعريف | التحقق من صحة إذا كانت المعلمة "استخدام أنواع التعريف في معالجة كشوف المرتبات" نعم، وإذا تم تعبئة نوع التعريف المشار إليه في المعلمة في ملف تعريف العامل. |
| الاسم الأول واسم العائلة | التحقق من صحة إذا كان ملف تعريف العامل صالحا، التحقق مما إذا كان الحقلان **الاسم** و **اسم العائلة** قم تمت تعبئتهما.|
| الموضع | تحقق مما إذا كان العامل لديه منصب معين. |
| تاريخ الميلاد | التحقق من صحة إذا كان ملف تعريف العامل صالحا، التحقق مما إذا كان الحقل **عيد الميلاد** قم تمت تعبئته. |
| التعويض | تحقق مما إذا كان العامل مسجلا في خطة تعويض ثابتة. |

إذا فشل أحد عمليات التحقق من الصحة هذه، لا يمكنك وضع علامة على الموظف على أنه مستعد للدفع.

إذا كان الحقل **جاهز للدفع** هو **لا**، فهذا مؤشر على أنه يجب تنفيذ إجراء لضمان اكتمال ملف تعريف العامل. لن يوقف هذا البيانات ليتم كشفها في أي كيان بيانات. 

## <a name="known-issues"></a>مشكلات معروفة

- يجب تعطيل ميزة **إدخال الموظف المبسط** في إدارة الميزات. لن تعمل الإطارات المتجانبة في مساحة عمل إدارة التعويض بشكل صحيح إذا كنت تستخدم هذه الميزة.
- في نموذج العامل، تتوفر **علامة التبويب الرواتب**، مجموعة **جاهز للدفع** لأي دور مستخدم. 

## <a name="see-also"></a>راجع أيضًا

[‏‫مقدمة إلى واجهة API لتكامل كشف الرواتب](hr-admin-integration-payroll-api-introduction.md)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]