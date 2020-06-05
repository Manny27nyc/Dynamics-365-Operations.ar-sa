---
title: التقارير الإلكترونية - تكوين التنسيق لتنفيذ عمليات الجرد والتجميع (الجزء 3 - استخدام العمليات الحسابية لإنشاء المخرجات)
description: تشرح الخطوات التالية كيف يستطيع مستخدم تم تعيينه إلى دور مسؤول النظام أو دور مطور التقارير الإلكترونية تكوين تنسيق تقارير إلكترونية لتنفيذ عمليات الجرد والتجميع بالاستناد إلى البيانات الخاصة بالمخرجات النصية المُنشأة بالفعل.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e8a4965c07c5a084b21da40667747db36530284c
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141938"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-3---use-computations-to-make-the-output"></a>التقارير الإلكترونية - تكوين التنسيق لتنفيذ عمليات الجرد والتجميع (الجزء 3 - استخدام العمليات الحسابية لإنشاء المخرجات)

[!include [banner](../../includes/banner.md)]

تشرح الخطوات التالية كيف يستطيع مستخدم تم تعيينه إلى دور مسؤول النظام أو دور مطور التقارير الإلكترونية تكوين تنسيق تقارير إلكترونية لتنفيذ عمليات الجرد والتجميع بالاستناد إلى البيانات الخاصة بالمخرجات النصية المُنشأة بالفعل. يمكن تنفيذ هذه الخطوات في أي شركة.

لإكمال هذه الخطوات، يجب أولاً إكمال الخطوات المذكورة في الإجراء "التقارير الإلكترونية - تكوين التنسيق لتنفيذ عمليات الجرد والتجميع‬ (الجزء 2: العمليات الحسابية)".

يتم استخدام هذا الإجراء لميزة تمت إضافتها في Dynamics 365 for Operations، الإصدار 1611.


## <a name="configure-this-report-to-use-counting-and-summing-info"></a>تكوين هذا التقرير لاستخدام معلومات الجرد والتجميع
1. انتقل إلى إدارة المؤسسة > مساحات العمل‬ > إعداد التقارير الإلكتروني‬.
2. انقر فوق "تكوينات إعداد التقارير‬".
3. في الشجرة، قم بتوسيع "نموذج نظام جمع المعلومات التجارية بين دول الاتحاد الأوروبي".
4. في الشجرة، قم بتوسيع "نموذج نظام جمع المعلومات التجارية بين دول الاتحاد الأوروبي‬\نظام جمع المعلومات التجارية بين دول الاتحاد الأوروبي (DE)"
5. في الشجرة، حدد "نموذج نظام جمع المعلومات التجارية بين دول الاتحاد الأوروبي‬\نظام جمع المعلومات التجارية بين دول الاتحاد الأوروبي (DE)\Intrastat (DE) مع الجرد والتجميع".
6. انقر فوق المصمم.
7. انقر فوق علامة التبويب "التعيين".
8. انقر فوق "إضافة جذر" لفتح مربع حوار الإسقاط‬.
    * أضف مصدر بيانات جديدًا للحصول على قائمة الكتل المحفوظة.  
9. في الشجرة، حدد "الدوال/المحسوب".
10. في حقل "الاسم"، اكتب "$BlocksList".
    * $BlocksList  
11. انقر فوق "تحرير المعادلة".
12. في الشجرة، حدد "وظائف تجميع البيانات\COLLECTEDLIST".
13. انقر فوق "إضافة دالة".
14. انقر فوق "إضافة مصدر بيانات".
15. في حقل "المعادلة"، أدخل 'COLLECTEDLIST('$BlockName', '.
    * COLLECTEDLIST('$BlockName',  
16. في حقل "المعادلة"، أدخل 'COLLECTEDLIST('$BlockName', "*")'.
    * COLLECTEDLIST('$BlockName', "*")  
17. انقر فوق حفظ.
    * يعني النمط "*" أنه سيتم تضمين جميع الكتل لهذا السجل في القائمة.  
18. قم بإغلاق الصفحة.
19. انقر فوق "موافق".
20. انقر فوق علامة التبويب "تنسيق".
21. في الشجرة، حدد "نظام جمع المعلومات التجارية بين دول الاتحاد الأوروبي\البيانات".
22. انقر فوق "إضافة" لفتح مربع حوار الإسقاط‬.
23. في الشجرة، حدد "النص\التسلسل".
24. في الحقل "الاسم"، اكتب "الإجماليات بكتل‬‬".‬
    * الإجماليات بكتل‬  
25. في الحقل "أحرف خاصة‬"، حدد "سطر جديد - Windows (CR LF)".
26. انقر فوق موافق.
27. في الشجرة، حدد "نموذج نظام جمع المعلومات التجارية بين دول الاتحاد الأوروبي\البيانات\الإجماليات بكتل‬‬".
28. انقر فوق "إضافة" لفتح مربع حوار الإسقاط‬.
29. في الشجرة، حدد "Text\String".
30. في حقل "الاسم"، اكتب "كود الكتلة".
    * كود الكتلة  
31. انقر فوق "موافق".
32. انقر فوق "إضافة سلسلة".
33. في الحقل "الاسم"، اكتب "تعداد البنود‬".
    * تعداد البنود  
34. انقر فوق "موافق".
35. انقر فوق "إضافة سلسلة".
36. في الحقل "الاسم"، اكتب "المبلغ الإجمالي".
    * المبلغ الإجمالي  
37. انقر فوق "موافق".
38. انقر فوق علامة التبويب "التعيين".
39. في الشجرة، حدد "$BlocksList".
40. انقر فوق "ربط".
    * أنشئ بند تلخيص لكل كتلة محفوظة.  
41. انقر فوق علامة التبويب "تنسيق".
42. في الشجرة، حدد "نموذج نظام جمع المعلومات التجارية بين دول الاتحاد الأوروبي\البيانات\الإجماليات بكتل‬‬\كود الكتلة".
43. انقر فوق علامة التبويب "التعيين".
44. انقر فوق "تحرير المعادلة".
45. في حقل "المعادلة"، أدخل '"معرف الكتلة: " & '.
    * "معرف الكتلة: " &  
46. في الشجرة، قم بتوسيع "$BlocksList".
47. في الشجرة، حدد "$BlocksList\Value".
48. انقر فوق "إضافة مصدر بيانات".
49. انقر فوق "حفظ".
50. قم بإغلاق الصفحة.
51. انقر فوق علامة التبويب "تنسيق".
52. في الشجرة، حدد "نموذج نظام جمع المعلومات التجارية بين دول الاتحاد الأوروبي\البيانات\الإجماليات بكتل‬‬\تعداد البنود".
53. انقر فوق علامة التبويب "التعيين".
54. انقر فوق "تحرير المعادلة".
    * أنشئ مخرجات لعدد البنود لكل كتلة واردة في هذا التقرير.  
55. في حقل "المعادلة"، أدخل '"عدد البنود في هذه الكتلة: " & '.
    * "عدد البنود في هذه الكتلة: " &  
56. في حقل "المعادلة"، أدخل '"عدد البنود في هذه الكتلة: " & TEXT('.
    * "عدد البنود في هذه الكتلة: " & TEXT(  
57. في الشجرة، حدد "وظائف تجميع البيانات\COUNTIFS".
58. انقر فوق "إضافة دالة".
59. انقر فوق "إضافة مصدر بيانات".
60. في حقل "المعادلة"، أدخل '"عدد البنود في هذه الكتلة: " & TEXT(COUNTIFS('$BlockName', '.
    * "عدد البنود في هذه الكتلة: " & TEXT(COUNTIFS('$BlockName',  
61. في الشجرة، قم بتوسيع "$BlocksList".
62. في الشجرة، حدد "$BlocksList\Value".
63. انقر فوق "إضافة مصدر بيانات".
64. في حقل "المعادلة"، أدخل '"عدد البنود في هذه الكتلة: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.
    * "عدد البنود في هذه الكتلة: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,  
65. في الشجرة، حدد "$RecName".
66. انقر فوق "إضافة مصدر بيانات".
67. في حقل "المعادلة، أدخل '"عدد البنود في هذه الكتلة: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "*"))'.
    * "عدد البنود في هذه الكتلة: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "*"))  
68. انقر فوق "حفظ".
69. قم بإغلاق الصفحة.
70. انقر فوق علامة التبويب "تنسيق".
71. في الشجرة، حدد "نموذج نظام جمع المعلومات التجارية بين دول الاتحاد الأوروبي\البيانات\الإجماليات بكتل‬‬\المبلغ الإجمالي".
72. انقر فوق علامة التبويب "التعيين".
73. انقر فوق "تحرير المعادلة".
    * أنشئ مخرجات ستكون إجمالي المبلغ المفوتر لكل كتلة واردة في هذا التقرير.  
74. في حقل "المعادلة"، أدخل '"مجموع المبلغ المفوتر: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "*"))'.
    * "مجموع المبلغ المفوتر: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "*"))  
75. انقر فوق "حفظ".
76. قم بإغلاق الصفحة.
77. انقر فوق "حفظ".
78. قم بإغلاق الصفحة.
