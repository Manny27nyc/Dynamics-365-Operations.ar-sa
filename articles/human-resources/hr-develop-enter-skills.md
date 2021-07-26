---
title: إدخال المهارات
description: يمكن للعمال والمديرين إدخال المهارات في Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 5a65f1884ea87bbf2519cc94e4c52a40ac1a91bd
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193967"
---
# <a name="enter-skills"></a>إدخال المهارات

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

يمكنك إدخال المهارات المستهدفة أو المهارات الفعلية للعمال أو مقدمي الطلبات أو جهات الاتصال في Dynamics 365 Human Resources. المهارة المستهدفة هي المهارة التي يخطط الشخص لتحقيقها. المهارة الفعلية هي مهارات لدى الشخص حاليًا.

## <a name="create-a-workflow-to-auto-approve-skills"></a>إنشاء سير عمل لاعتماد المهارات تلقائيًا

لإدخال المهارات دون الحاجة إلى اعتماد، يجب إنشاء سير عمل لاعتماد المهارات تلقائيًا.

> [!NOTE]
> تتطلب المهارات التي تم إدخالها بواسطة العاملين اعتماد المدير دائمًا. يقوم سير العمل هذا بالاعتماد التلقائي على المهارات التي يتم إدخالها بواسطة المديرين نيابةً عن العمال.

1. في مساحة عمل **إدارة العاملين**، حدد **ارتباطات**.

2. ضمن **الإعداد**، حدد **سير عمل الموارد البشرية**.

3. حدد **جديد**.

4. في الجزء **إنشاء سير عمل**، حدد **مهارات العامل**.

   [![تحديد سير عمل مهارات العامل](media/hr-develop-skills-new-workflow.png)](media/hr-develop-skills-new-workflow.png)

5. في مربع الخوار **هل تريد فتح هذا الملف؟**، حدد **فتح**. عند المطالبة، أدخل بيانات اعتمادك.

6. في محرر سير العمل، حدد عنصر سير العمل **اعتماد المهارات** واسحبه إلى اللوحة.

   [![تحديد عنصر سير عمل مهارات الاعتماد](media/hr-develop-skills-element.png)](media/hr-develop-skills-element.png)

7. قم بتوصيل العنصر **البدء** لعنصر **اعتماد المهارات**، ثم قم بتوصيل العنصر **اعتماد المهارات** بالعنصر **إنهاء**. قد تحتاج إلى التمرير لأسفل لرؤية العنصر **النهاية**. يمكنك سحبه بالقرب من العناصر الأخرى.

   [![توصيل عناصر سير العمل](media/hr-develop-skills-connect-elements.png)](media/hr-develop-skills-connect-elements.png)

8. انقر نقرًا مزدوجًا فوق عنصر سير العمل **اعتماد المهارات 1**، ثم انقر بزر الماوس الأيمن فوق العنصر **الخطوة 1**. انقر بزر الماوس الأيمن فوق العنصر **الخطوة 1**، ثم حدد **خصائص**.

9. في النافذة **الخصائص**، حدد **شرط** من شريط التنقل الموجود على الجانب الأيسر.

10. حدد **تشغيل هذه الخطوة فقط عند الوفاء بالشرط التالي**.

11. حدد **إضافة الشرط**. بعد **المكان**، حدد **مهارات خدمة الموظف الذاتية**، ثم حدد **خدمة الموظف الذاتيةskills.Person**. بعد **يكون**، حدد **الحقل**، ثم حدد **المستخدم إلى الشخص relationship.Person**.

    [![تحديد شرط](media/hr-develop-skills-condition.png)](media/hr-develop-skills-condition.png)

12. حدد **مهمة** في شريط التنقل بالجانب الأيسر.

13. في علامة التبويب **نوع المهمة**، حدد **التدرج الهرمي**.

14. في علامة التبويب **تحديد التدرج الهرمي**، في الحقل **نوع التدرج الهرمي:**، حدد **التدرج الهرمي الإداري**.

    [![تحديد التدرج الهرمي الإداري](media/hr-develop-skills-hierarchy.png)](media/hr-develop-skills-hierarchy.png)

15. حدد **إغلاق**، حدد **سير العمل** في مسار تنقل اللوحة، ثم حدد **حفظ وإغلاق**.

لمزيد من المعلومات حول إنشاء مهام سير العمل، راجع [نظرة عامة حول نظام سير العمل](../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md?toc=/dynamics365/human-resources/toc.json)

## <a name="enter-skills-for-a-worker"></a>إدخال مهارات لعامل

1. حدد عاملاً.

2. في شريط الإجراءات الخاص بالصفحة **العامل**، حدد **شخص**، ثم حدد **المهارات**.

3. في الصفحة **المهارات**، أكمل الحقول التالية لكل مهارة:

   - **المهارة**: حدد مهارة.
   - **نوع المستوى**: حدد **فعلي** للمهارة التي يمتلكها العامل، أو حدد **هدف** للمهارة التي يحاول العامل اكتسابها.
   - **المستوى**: حدد مستوى لمهارة العامل.
   - **تاريخ المستوى**: حدد تاريخًا في أداة التقويم.
   - **مسؤول اختبار**: إذا كانت ذلك مناسبًا، حدد مسؤول اختبار من القائمة. يمكنك تصفية البحث الخاص بك.
   - **سنوات الخبرة**: أدخل سنوات الخبرة.
   - **تم التحقق من الصحة**: إذا تم التحقق من صحة المهارة، حدد المربع.
   - **تم التحقق بواسطة**: أدخل اسم أداة التحقق.

4. عند الانتهاء من إدخال المهارات، حدد **حفظ**.

## <a name="see-also"></a>راجع أيضًا

[تكوين المهارات](hr-develop-skills.md)<br>
[تعيين المهارات](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]