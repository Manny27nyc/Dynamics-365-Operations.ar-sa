---
title: تحديد سياسات المراجعة للمستندات المصدر
description: يوضح هذا الموضوع كيفية إعداد وتشغيل قواعد سياسة التدقيق.
author: ryansandness
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysFieldLookUp, SysPolicyListPage, SysPolicy, AuditPolicyRule, SysQueryForm, SysQueryFieldLookUp, AuditPolicyDateSelection, AuditPolicyAdditionalOption, BatchJob, CaseDetail
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ba720fd1bbbbf8b4f3b936d65d9d7840432f291a
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145019"
---
# <a name="define-audit-policies-for-source-documents"></a>تحديد سياسات المراجعة للمستندات المصدر

[!include [banner](../../includes/banner.md)]

يوضح هذا الموضوع كيفية إعداد وتشغيل قواعد سياسة التدقيق. يستخدم المثال تقارير المصروفات مع نوع مصروفات الفندق. يستخدم هذا الإجراء شركة بيانات العرض التوضيحي USMF. يحتوي دور المراجع يحتوي على الأذونات الصحيحة لتنفيذ هذه المهام.

1. في جزء التنقل، انتقل إلى **الوحدات النمطية > منضدة عمل التدقيق‬ >الإعداد > نوع قاعدة السياسة**.
2. حدد **جديد**.
3. في الحقل **اسم القاعدة**، اكتب قيمة.
4. في حقل **الوصف**، اكتب قيمة.
5. في الحقل **اسم الاستعلام**، حدد **بند تقرير المصروفات**
6. في الحقل **نوع الاستعلام**، حدد **مجمَّع‬**
7. في الحقل **الكيان القانوني**، حدد **الكيان القانوني**
8. في حقل **مرجع تاريخ المستند**، حدد **تاريخ ووقت التعديل‬**
9. حدد **حفظ**.
10. في جزء التنقل، انتقل إلى **الوحدات النمطية > منضدة عمل التدقيق‬ >الإعداد > سياسات التدقيق**.
11. حدد **جديد**.
12. في الحقل **الاسم**، اكتب قيمة.
13. وسّع قسم **مؤسسات السياسات‬**.
14. في الشجرة، حدد **Contoso Entertainment System USA**، ثم حدد **إضافة**.
15. في الشجرة، حدد **Contoso Consulting USA**، ثم حدد **إضافة**.
16. في الشجرة، حدد **Contoso Retail USA**، ثم حدد **إضافة**.
17. قم بطيّ قسم **مؤسسات السياسات‬**.
18. وسّع قسم **قواعد السياسة‬**.
19. في القائمة، ابحث عن "قاعدة السياسة" التي تم إنشاؤها في السابق وحددها.
20. حدد **إنشاء قاعدة السياسة**.
21. في الحقل **تاريخ السريان**، أدخل تاريخًا ووقتًا.
22. حدد **عامل تصفية**.
23. في القائمة، حدد صف **فئة المصروفات**، وعيّن التفاصيل إلى **فندق**.
24. في الحقل **المعايير‬**، أدخل قيمة أو حددها.
25. حدد علامة التبويب **تجميع‬**:
26. حدد **إضافة**.
27. في القائمة، حدد قيمة حقل **مبلغ الحركة**.
28. في حقل **الحقل**، أدخل قيمة أو حددها.
29. في حقل **AggregateFunction**، حدد **المجموع**.
30. حدد علامة التبويب **تجميع حسب**.
31. حدد **إضافة**.
32. في القائمة، حدد قيمة **الموظف**.
33. حدد **إضافة**.
34. في القائمة، حدد قيمة **فئة المصروفات**.
35. في حقل **الحقل**، أدخل قيمة أو حددها.
36. حدد علامة التبويب **يحتوي**.
37. حدد **إضافة**.
38. حدد **مبلغ الحركة**.
39. في حقل **الحقل**، أدخل قيمة أو حددها.
40. في حقل **AggregateFunction**، حدد **المجموع**.
41. في حقل **المعايير‏‎**، اكتب `>2000`.
42. حدد **موافق**.
43. حدد **اختبار**.
44. في الحقل **تاريخ بدء تحديد المستند‬**، أدخل تاريخًا ووقتًا.
45. في الحقل **تاريخ انتهاء تحديد المستند‬**، أدخل تاريخًا ووقتًا.
46. حدد **تشغيل الاختبار**.
47. في جزء الإجراءات، حدد **سياسة التدقيق**.
48. حدد **خيارات إضافية**.
49. في الحقل **تاريخ البدء**، أدخل تاريخًا ووقتًا.
50. في الحقل **تاريخ الانتهاء‬**، أدخل تاريخًا ووقتًا.
51. حدد **الدُفعة**.
52. وسّع القسم **تشغيل في الخلفية‬‬**.
53. حدد **نعم** في حقل **معالجة الدُفعات**.
54. حدد **موافق**.
55. في جزء التنقل، انتقل إلى **الوحدات النمطية > منضدة عمل التدقيق‬ >الإعداد > تدقيق الحالات**.
56. في القائمة، قم بالبحث عن السجل المطلوب وحدده.
57. وسّع القسم **اقترانات‬‬‬**.
58. في القائمة، قم بالبحث عن السجل المطلوب وحدده.
