---
title: ما الجديد أو المتغير في Dynamics 365 Human Resources 22 مارس، 2021
description: يصف هذا الموضوع المزايا الجديدة أو المتغيرة في Microsoft Dynamics 365 Human Resources لإصدار 22 مارس، 2021.
author: marcelbf
ms.date: 03/22/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-03-22
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5854fa8c89f1a72c32bd480e71c1cd0a743c6cd7
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803335"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-22-2021"></a>ما الجديد أو المتغير في Dynamics 365 Human Resources 22 مارس، 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

يصف هذا الموضوع الميزات الجديدة أو المتغيرة أو على وشك القدوم في Dynamics 365 Human Resources.

لمزيد من المعلومات حول عملية التحديث الخاصة بنا والجدول، راجع [عملية التحديث](hr-admin-setup-update-process.md).

لمزيد من المعلومات حول الميزات الجديدة وتواريخ التوفر العام المتوقعة الخاصة بها، راجع [نظرة عامة حول Dynamics 365 Human Resources الإصدار 2021، الموجة 1](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>في هذا الإصدار

يتضمن هذا الإصدار الميزات الجديدة التالية وإصلاحات الأخطاء. يتم تطبيق التغييرات على رقم الإصدار 8.1.4049.

### <a name="new-features"></a>الميزات الجديدة

تتوفر الميزات التالية بشكل عام مع هذا الإصدار.

| الميزة | خطة الإصدار | الوثائق |
| --- | --- | --- |
| خيار فرض الإلغاء وإعادة تعيين وظائف الدُفعات المتوقفة (560976) | NA | [إعادة تعيين وظائف الدُفعات المتوقفة](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-troubleshooting-batch-execution) |
| تحديثات تجربة المستخدم البسيطة لإنشاء خطة مزايا جديدة (419941) | NA | [إنشاء خطة المزايا](hr-benefits-plans-setup.md) |

### <a name="bug-fixes"></a>إصلاح الأخطاء

يتضمن هذا الإصدار إصلاحات الأخطاء التالية.

> [!NOTE]
> هدفنا هو الحصول على هذه المعلومات لك في أسرع وقت ممكن. قد نقوم بتحديث هذا الموضوع لتضمين إصلاحات الأخطاء التي أجريتها في البناء بعد أن يتم نشر هذا الموضوع في البداية.

| رقم الإصدار | إصدار |  الوصف |
| --- | --- | --- |
| 554239 | تحسينات الأداء للكيانات ذات الصلة بجدول **BusinessProcessTaskAssignment** | قم بتحسين أداء الكيانات ذات الصلة بجدول **BusinessProcessTaskAssignment** بإضافة الفهارس المقترحة إلى الجدول. |
| 566061 | إزالة الرمز الاحتياطي لكيان V2 من المزامنة الليلية | قم بإزالة الرمز الاحتياطي V2 لمزامنة Dataverse الليلية. لم يعد الإجراء الاحتياطي ضروريًا ويمنع المزامنة التي تمت تصفيتها من العمل كما هو متوقع. ويحسن التغيير من تناسق مزامنة بيانات Dataverse. |
| 538024 | خطط مزايا العمال> إزالة خطأ أثناء السحب | تم إصلاح الخطأ أثناء إزالة السحب لخيار خطة المزايا في نموذج مزايا العمال. |
| 557965 | مساحة عمل **المزايا**: يجب أن يكون ارتباط **أحداث الحياة النشطة** مرئيًا دائمصا في قسم **الارتباطات** | ثم إصلاح مشكلة حيث كان ارتباط **أحداث الحياة النشطة** مرئيًا في قسم **الارتباطات**، ولكنه كان يطرح خطأ أثناء محاولة التنقل في حالة عدم تمكين ميزة **مساحة عمل إدارة المزايا (الإصدار الأولي)**. لمزيد من المعلومات حول تمكين مساحة العمل، راجع [مساحة عمل إدارة الميزات](hr-benefits-management-workspace.md). |
| 556672 | تتعذر معالجة الاستحقاقات لموظف تم إنهاء عمله عند تمكين **إدخال الموظف المبسط** في إدارة الميزات | تمت أضافه خيار الاستحقاق الخاص بخطط الغياب والاجازه إلى **مزيد من الخيارات** ضمن **تاريخ العمل** للموظفين عند تمكين **إدخال الموظف المبسط** في إدارة الميزات. |
| 562656 | يجب تضمين عنصر قائمة **SysRecordChangeLogValidTimeState** في امتياز أمان وامتداد واجب الأمان **SystemExternalBasicMaintain** | فقدت أدوار المسؤول غير الخاصة بالنظام الزر **عرض التغييرات** في نماذج إدارة التواريخ. |
| 505989 | معالجة أحداث الحياة: لم تتم معالجة تغيير الأهلية بشكل صحيح بسبب تاريخ الاستخدام | تم إصلاح المشكلة حيث كان التغيير في معالجة الأهلية يعتمد على تاريخ بدء المركز وليس فقط على الوضع الحالي. |
| 562286 | يرسل عامل الإنهاء تحديثات متعددة إلى Dataverse | عند إنهاء عمل عامل، يتم إرسال أكثر من عملية تحديث إلى Dataverse، مما يؤدي إلى إخطاري تحديث لنفس التغيير. يمكن أن يسبب هذا عدة مشغلات في حالة تكوين تدفق Power Automate للتشغيل من الإجراء. |
| 527340 | يظهر خطأ "DateTime غير قابل للتمثيل" عند فتح تسجيلات الإجازة والغياب | عند اختيار التسجيل في الإجازة والغياب، لم يعد يظهر الخطأ. |
| 561663 | زيادة الفاصل الزمني لوقت الانتظار لتوفير المجموعة | قم بتحسين استقرار البنية التحتية واتساق التوفير من خلال التحديثات الخاصة بتوفير نظام المجموعة. |
| 486129 | لا يمكن تحرير الحقول المخصصة في **المناصب > إدارة التغييرات** | تم إصلاح مشكلة عدم إمكانية تعديل الحقول المخصصة في علامة التبويب **إدارة التغييرات** لـ **المناصب**. |

## <a name="in-preview"></a>قيد المعاينة

الميزات الجديدة التالية موجودة في المعاينة. للحصول على مزيد من المعلومات حول تشغيل الميزات أو إيقاف تشغيلها، راجع [إدارة الميزات](hr-admin-manage-features.md).

| الميزة | خطة الإصدار | الوثائق |
| --- | --- | --- |
| مساحة عمل إدارة المزايا | [مساحة عمل إدارة المزايا (معاينة)](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [مساحة عمل إدارة المزايا](hr-benefits-management-workspace.md) |
| تقييد الموظفين من تحرير تفاصيل جهة اتصال العمل | [تقييد الموظفين من تحرير تفاصيل جهة اتصال العمل](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [تقييد تحرير المعلومات الشخصية](hr-employee-self-service-restrict-editing.md)|

## <a name="coming-soon"></a>قريبًا

| الميزة | تفاصيل |
| --- | --- |
| المهارات التي تم إدخالها بواسطة مدير للموظفين يمكن اعتمادها تلقائيًا من خلال سير عمل | قريبًا. |

للحصول على قائمة كاملة بالميزات المخططة والإصدارات المجدولة الخاصة بها، راجع [نظرة عامة حول Dynamics 365 Human Resources الإصدار 2021، الموجة 1](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>راجع أيضًا

[ما الجديد أو المتغير في Human Resources](hr-admin-whats-new.md)</br>
[نظره عامة حول الموجة 1 من إصدار Dynamics 365 Human Resources  2021](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[تحديث العملية](hr-admin-setup-update-process.md)</br>
[إدارة الميزات](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]