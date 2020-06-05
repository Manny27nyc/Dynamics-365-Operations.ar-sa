---
title: "\"التقارير الإلكترونية - استخدام الأبعاد المالية كمصدر بيانات (الجزء 1 - تصميم نموذج البيانات)"
description: تشرح الخطوات التالية كيف يستطيع مسؤول النظام أو مطور التقارير الإلكترونية تكوين نموذج التقارير الإلكترونية لاستخدام الأبعاد المالية كمصدر بيانات للتقارير الإلكترونية.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b02496ebb06e0c2eb644fc7ef3280ca4eca05923
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141990"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-1---design-data-model"></a>"التقارير الإلكترونية - استخدام الأبعاد المالية كمصدر بيانات (الجزء 1 - تصميم نموذج البيانات)

[!include [banner](../../includes/banner.md)]

تشرح الخطوات التالية كيف يستطيع مسؤول النظام أو مطور التقارير الإلكترونية تكوين نموذج التقارير الإلكترونية لاستخدام الأبعاد المالية كمصدر بيانات للتقارير الإلكترونية. يمكن تنفيذ هذه الخطوات في أي شركة.

لإكمال هذه الخطوات، يجب أولاً إكمال الخطوات المذكورة في الإجراء "إنشاء موفر تكوين ووضع علامة عليه على أنه نشط".


## <a name="create-a-new-data-model"></a>إنشاء نموذج بيانات جديد
1. انتقل إلى إدارة المؤسسة > مساحات العمل‬ > إعداد التقارير الإلكتروني‬.
    * تأكد من أن موفر “Litware, Inc.” متوفر ومن وضع علامة عليه كنشط.  
2. انقر فوق "تكوينات إعداد التقارير‬".
3. انقر فوق "إنشاء تكوين" لفتح مربع حوار الإسقاط‬.
4. في حقل "الاسم"، اكتب "نموذج الأبعاد المالية".
5. وانقر فوق إنشاء تكوين.
6. انقر فوق المصمم.
7. انقر فوق "جديد" لفتح مربع حوار الإسقاط‬.
8. في حقل "الاسم"، اكتب "الإدخال".
9. وانقر فوق إضافة.
10. انقر فوق "جديد" لفتح مربع حوار الإسقاط‬.
11. في الحقل "الاسم"، اكتب "الشركة".
12. وانقر فوق إضافة.
    * سوف نضيف إلى نموذجنا قائمة سجلات جديدة. ستعرض هذه القائمة (لأي تقارير إلكترونية تستخدم هذا النموذج كمصدر بيانات) إعدادات أبعاد مالية محددة. سيتم تقديم كل واحد من الأبعاد المالية في هذه القائمة كسجل مع حقول مناسبة تمثل إعداد البُعد.  
13. انقر فوق "جديد" لفتح مربع حوار الإسقاط‬.
14. في حقل "الاسم"، اكتب "إعداد الأبعاد‬".
15. في الحقل "نوع الصنف"، حدد "قائمة سجلات".
16. وانقر فوق إضافة.
17. انقر فوق "جديد" لفتح مربع حوار الإسقاط‬.
18. في حقل "الاسم"، اكتب "الكود".
19. في الحقل "نوع الصنف"، حدد "سلسلة".
20. وانقر فوق إضافة.
21. انقر فوق "جديد" لفتح مربع حوار الإسقاط‬.
22. في الحقل "الاسم"، اكتب "الاسم".
23. وانقر فوق إضافة.
24. في الشجرة، حدد "الإدخال".
25. انقر فوق "جديد" لفتح مربع حوار الإسقاط‬.
26. في حقل "الاسم"، اكتب "دفتر اليومية".
27. في الحقل "نوع الصنف"، حدد "قائمة سجلات".
28. وانقر فوق إضافة.
29. انقر فوق "جديد" لفتح مربع حوار الإسقاط‬.
30. في حقل "الاسم"، اكتب "الدُفعة".
31. في الحقل "نوع الصنف"، حدد "سلسلة".
32. وانقر فوق إضافة.
33. انقر فوق "جديد" لفتح مربع حوار الإسقاط‬.
34. في حقل "الاسم"، اكتب "الحركة".
35. في الحقل "نوع الصنف"، حدد "قائمة سجلات".
36. وانقر فوق إضافة.
37. انقر فوق "جديد" لفتح مربع حوار الإسقاط‬.
38. في حقل "الاسم"، اكتب "التاريخ".
39. في الحقل "نوع الصنف"، حدد "تاريخ".
40. وانقر فوق إضافة.
41. انقر فوق "جديد" لفتح مربع حوار الإسقاط‬.
42. في حقل "الاسم"، اكتب "الدين".
43. في الحقل "نوع الصنف"، حدد "حقيقي".
44. وانقر فوق إضافة.
45. انقر فوق "جديد" لفتح مربع حوار الإسقاط‬.
46. في حقل "الاسم"، اكتب "الائتمان".
47. وانقر فوق إضافة.
48. انقر فوق "جديد" لفتح مربع حوار الإسقاط‬.
49. في الحقل "الاسم"، اكتب "العملة".
50. في الحقل "نوع الصنف"، حدد "سلسلة".
51. وانقر فوق إضافة.
52. انقر فوق "جديد" لفتح مربع حوار الإسقاط‬.
53. في حقل "الاسم"، اكتب "الإيصال".
54. وانقر فوق إضافة.
55. انقر فوق "جديد" لفتح مربع حوار الإسقاط‬.
56. في حقل "الاسم"، اكتب "بيانات الأبعاد‬".
57. في الحقل "نوع الصنف"، حدد "قائمة سجلات".
58. وانقر فوق إضافة.
    * لقد أضفنا قائمة سجلات جديدة إلى نموذجنا. ستعرض هذه القائمة (لأي تقارير إلكترونية تستخدم هذا النموذج كمصدر بيانات) قيم أبعاد مالية محددة. سيتم تقديم كل واحد من الأبعاد المالية في هذه القائمة كسجل مع حقول مناسبة تمثل قيم البُعد. سيتم أيضًا تقديم اسم البُعد في هذا السجل كحقل يجب استخدامه، إذا لزم الأمر، لأغراض التحديد.  
59. انقر فوق "جديد" لفتح مربع حوار الإسقاط‬.
60. في حقل "الاسم"، اكتب "الكود".
61. في الحقل "نوع الصنف"، حدد "سلسلة".
62. وانقر فوق إضافة.
63. انقر فوق "جديد" لفتح مربع حوار الإسقاط‬.
64. في الحقل "الاسم"، اكتب "الوصف".
65. وانقر فوق إضافة.
66. انقر فوق "جديد" لفتح مربع حوار الإسقاط‬.
67. في الحقل "الاسم"، اكتب "الاسم".
68. وانقر فوق إضافة.
69. انقر فوق "حفظ".
70. قم بإغلاق الصفحة.
