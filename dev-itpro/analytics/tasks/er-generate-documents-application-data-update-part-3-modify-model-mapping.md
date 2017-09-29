--- 
title: "تعديل النموذج والتعيين لإنشاء مستندات مع تحديث بيانات التطبيق للتقارير الإلكترونية (ER)"
description: "لإكمال الخطوات المذكورة في هذا الإجراء، يجب عليك أولاً إكمال الإجراء، \"التقارير الإلكترونية - إنشاء مستندات بواسطة تحديث بيانات التطبيق (الجزء 2 - إنشاء المستندات)‬\"."
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 5549534700360776ad409c2324a4d84bcde005f9
ms.contentlocale: ar-sa
ms.lasthandoff: 07/27/2017

---
# <a name="modify-model-and-mapping-to-generate-documents-with-application-data-update-for-electronic-reporting-er"></a>تعديل النموذج والتعيين لإنشاء مستندات مع تحديث بيانات التطبيق للتقارير الإلكترونية (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

لإكمال الخطوات المذكورة في هذا الإجراء، يجب عليك أولاً إكمال الإجراء، "التقارير الإلكترونية - إنشاء مستندات بواسطة تحديث بيانات التطبيق (الجزء 2: إنشاء المستندات)‬". 

توضح الخطوات الواردة في هذا الإجراء كيفية تصميم تكوينات التقارير الإلكترونية لإنشاء مستند إلكتروني وتحديث بيانات التطبيق. في هذا الإجراء، ستقوم بتعديل تكوينات التقارير الإلكترونية لبدء استخدامها لإنشاء المستندات الإلكترونية وتحديث بيانات التطبيق. تم إنشاء هذا الإجراء للمستخدمين الذين لديهم دور مسؤول النظام أو مطور التقارير الإلكترونية. يمكن إتمام هذه الخطوات باستخدام مجموعة بيانات DEMF.


## <a name="modify-data-model"></a>تعديل نموذج البيانات
1. انتقل إلى إدارة المؤسسة >إعداد التقارير الإلكتروني >التكوينات.
2. في الشجرة، حدد "نظام جمع المعلومات التجارية بين دول الاتحاد الأوروبي (نموذج)".
    * ستقوم بتوسيع طريقة استخدام نموذج البيانات. بالإضافة إلى استخدامه كمصدر بيانات لإنشاء تقرير نظام جمع المعلومات التجارية، سيتم استخدام نموذج البيانات لجمع تفاصيل حول عملية إعداد تقارير نظام جمع المعلومات التجارية بين دول الاتحاد الأوروبي. سيتم بعد ذلك استخدام التفاصيل لتحديث بيانات التطبيق.   
3. انقر فوق المصمم.
4. انقر فوق "جديد" لفتح مربع حوار الإسقاط‬.
5. في الحقل "عقدة جديدة كـ‬"، أدخل "جذر النموذج‬".
6. في حقل "الاسم"، اكتب "لتحديث بيانات التطبيق‬".
    * لتحديث بيانات التطبيق  
7. وانقر فوق إضافة.
8. في الشجرة، حدد "لتحديث بيانات التطبيق".
    * تتم إضافة العنصر الجذر الجديد هذا لتحديد تدفق البيانات لنقل البيانات من تقرير نظام جمع المعلومات التجارية (تستخدم كمصدر بيانات) إلى جداول التطبيق (وجهة التحديث). لاحظ أنه يجب استخدام عناصر جذر مختلفة للحصول على البيانات التي تم ترحيلها إلى المستند الصادر وكذلك للحصول على البيانات من المستند الذي يُستخدم لتحديث بيانات التطبيق.   
9. انقر فوق "جديد" لفتح مربع حوار الإسقاط‬.
10. في حقل "الاسم"، اكتب "رأس الأرشيف".
    * رأس الأرشيف  
11. في الحقل "نوع الصنف"، حدد "قائمة سجلات".
12. وانقر فوق إضافة.
    * لأنك ستقوم بإنشاء سجل لكل تقرير ينشأ لنظام جمع المعلومات التجارية بين دول الاتحاد الأوروبي، يجب عليك إنشاء عنصر جديد له.  
13. انقر فوق "جديد" لفتح مربع حوار الإسقاط‬.
14. في حقل "الاسم"، اكتب "اسم الملف".
    * اسم الملف  
15. في الحقل "نوع الصنف"، حدد "سلسلة".
16. وانقر فوق إضافة.
17. انقر فوق "جديد" لفتح مربع حوار الإسقاط‬.
18. في حقل "الاسم"، اكتب "عدد البنود".
    * عدد السطور  
19. في الحقل "نوع الصنف"، حدد "Integer".
20. وانقر فوق إضافة.
    * قم بإضافة هذا العنصر لكي يمثل عدد حركات نظام جمع المعلومات التجارية التي تم الإبلاغ عنها أثناء عملية إعداد التقارير الحالية.  
21. انقر فوق "جديد" لفتح مربع حوار الإسقاط‬.
22. في حقل "الاسم"، اكتب "بنود الأرشيف".
    * بنود الأرشيف  
23. في الحقل "نوع الصنف"، حدد "قائمة سجلات".
24. وانقر فوق إضافة.
    * قم بإضافة هذا العنصر لكي يمثل قائمة حركات نظام جمع المعلومات التجارية التي تم الإبلاغ عنها أثناء عملية إعداد التقارير الحالية.  
25. انقر فوق "جديد" لفتح مربع حوار الإسقاط‬.
26. في الحقل "الاسم"، اكتب "المبلغ".
    * المبلغ  
27. في الحقل "نوع الصنف"، حدد "حقيقي".
28. وانقر فوق إضافة.
29. انقر فوق "جديد" لفتح مربع حوار الإسقاط‬.
30. في حقل "الاسم"، اكتب "معرف سجل السلع".
    * معرف سجل السلع  
31. في الحقل "نوع الصنف"، حدد "Int64".
32. وانقر فوق إضافة.
33. انقر فوق "جديد" لفتح مربع حوار الإسقاط‬.
34. في حقل "الاسم"، اكتب "رقم الصنف".
    * رقم العنصر  
35. في الحقل "نوع الصنف"، حدد "سلسلة".
36. وانقر فوق إضافة.
37. انقر فوق "حفظ".
38. قم بإغلاق الصفحة.

## <a name="modify-model-mapping"></a>تعديل تعيين النموذج
1. في الشجرة، قم بتوسيع "نظام جمع المعلومات التجارية بين دول الاتحاد الأوروبي (نموذج)".
2. في الشجرة، حدد "نظام جمع المعلومات التجارية بين دول الاتحاد الأوروبي (نموذج)\نظام جمع المعلومات التجارية بين دول الاتحاد الأوروبي (تعيين)".
    * قم بتعديل تعيين النموذج الموجود لبدء استخدامه لتحديث بيانات التطبيق ولأرشفة تفاصيل إعداد تقارير نظام جمع المعلومات التجارية بين دول الاتحاد الأوروبي.  
3. انقر فوق المصمم.
4. انقر فوق "جديد".
5. في حقل "الاسم"، اكتب "تحديث الأرشيف".
    * تحديث الأرشيف  
6. في الحقل "اتجاه"، حدد "إلى الوجهة".
7. انقر فوق "حفظ".
    * يحدد هذا التعيين الجديد تدفق البيانات لنقل البيانات (تفاصيل إعداد تقارير نظام جمع المعلومات التجارية) من نموذج البيانات إلى جداول التطبيق (وجهة التحديث). لاحظ أنه يجب استخدام عناصر جذر مختلفة خاصة بالنموذج للحصول على البيانات من التطبيق لعملية إعداد التقارير، وبعد ذلك استخدام البيانات من نموذج البيانات لتحديث بيانات التطبيق.   
8. انقر فوق المصمم.
9. في الشجرة، حدد "نموذج البيانات\نموذج البيانات".
    * أضف مصدر البيانات مطلوب. هذا هو نموذج البيانات الذي يحتوي على التفاصيل الخاصة بحركات نظام جمع المعلومات التجارية التي تم الإبلاغ عنها والتي يجب أرشفتها.  
10. انقر فوق "إضافة جذر".
11. في حقل "الاسم"، اكتب "نموذج".
    * النموذج  
12. في حقل "التعريف"، أدخل قيمة "لتحديث بيانات التطبيق" أو حددها.
    * لتحديث بيانات التطبيق  
13. انقر فوق "موافق".
14. في الشجرة ، قم بتوسيع "النموذج"
15. في الشجرة، حدد "الدوال/المحسوب".
16. في الشجرة، حدد "النموذج\رأس الأرشيف".
17. وانقر فوق إضافة.
    * لأنك ترغب في تعداد حركات نظام جمع المعلومات التجارية التي تم الإبلاغ عنها لأرشفتها، يجب إضافة مصدر البيانات الملائم.  
18. في حقل "الاسم"، اكتب "البنود التي تم تعدادها‬".
    * البنود التي تم تعدادها  
19. انقر فوق "تحرير المعادلة".
20. في الشجرة، حدد "قائمة\ENUMERATE".
21. انقر فوق "إضافة دالة".
22. في الشجرة ، قم بتوسيع "النموذج"
23. في الشجرة، قم بتوسيع "النموذج\رأس الأرشيف".
24. في الشجرة، حدد "النموذج\رأس الأرشيف\بنود الأرشيف".
25. انقر فوق "إضافة مصدر بيانات".
26. في حقل المعادلة، أدخل "ENUMERATE(model.'Archive header'.'Archive lines')".
    * ENUMERATE(النموذج.'رأس الأرشيف'.'بنود الأرشيف')  
27. انقر فوق "حفظ".
28. قم بإغلاق الصفحة.
29. انقر فوق "موافق".
30. انقر فوق "إضافة وجهة".
    * قم بإضافة جداول التطبيق كوجهات مطلوبة تتطلب تحديثات لأرشفة التفاصيل الخاصة بحركات نظام جمع المعلومات التجارية التي تم الإبلاغ عنها.  
31. في حقل "الاسم"، اكتب "أرشيف".
    * الأرشيف  
32. في حقل "اسم الجدول"، اكتب "IntrastatArchiveGeneral".
    * IntrastatArchiveGeneral  
    * احتفظ بسجل الإجراء "إدراج" لكي تتمكن من إضافة السجلات أثناء عملية أرشفة التفاصيل الخاصة بكل عمليات إعداد تقارير نظام جمع المعلومات التجارية.  
33. حدد "نعم" في حقل "سجل معلومات السجل‬".
    * حدد "نعم" للحصول على معلومات حول مشكلات تحديث بيانات التطبيق.  
34. حدد "نعم" في الحقل "تخطي التحقق من صحة إجراء السجل‬".
    * حدد "نعم" لمنع أخطاء التحقق من الصحة حول الحقل الفارغ "معرف أرشيف نظام جمع المعلومات التجارية بين دول الاتحاد الأوروبي‬". سيتم إجراء ذلك بعد إضافة السجلات، استنادًا إلى إعدادات الأرقام التسلسلية التي تم تكوينها لهذا الجدول في نموذج "محددات التجارة الخارجية".  
35. انقر فوق "موافق".
    * اعمل على ربط عناصر مصدر البيانات المضاف (النموذج المصفى استنادًا إلى العنصر الجذر المحدد) مع عناصر من الوجهة المضافة.  
36. في الشجرة، قم بتوسيع ''أرشيف".
37. في الشجرة، قم بتوسيع "أرشيف‏‎\<علاقات".
38. في الشجرة، قم بتوسيع "أرشيف\<علاقات\IntrastatArchiveDetail".
39. في الشجرة، حدد "أرشيف\<علاقات\IntrastatArchiveDetail\مبلغ(AmountMST)".
40. في الشجرة، قم بتوسيع "النموذج\رأس الأرشيف\البنود التي تم تعدادها‬".
41. في الشجرة، قم بتوسيع "النموذج\رأس الأرشيف\البنود التي تم تعدادها‬\القيمة".
42. في الشجرة، حدد "النموذج\رأس الأرشيف\البنود التي تم تعدادها\القيمة\المبلغ".
43. انقر فوق "ربط".
44. في الشجرة، حدد "أرشيف\<علاقات\IntrastatArchiveDetail\السلع(IntrastatCommodity)'.
45. في الشجرة، حدد "النموذج\رأس الأرشيف\البنود التي تم تعدادها\القيمة\معرف سجل السلع".
46. انقر فوق "ربط".
47. في الشجرة، حدد "أرشيف\<علاقات\IntrastatArchiveDetail\رقم الصنف(ItemId)".
48. في الشجرة، حدد "النموذج\رأس الأرشيف\البنود التي تم تعدادها\القيمة\رقم الصنف".
49. انقر فوق "ربط".
50. في الشجرة، حدد "أرشيف\<علاقات\IntrastatArchiveDetail\رقم البند(LineNumber)".
51. في الشجرة، حدد "النموذج\رأس الأرشيف\البنود التي تم تعدادها\الرقم".
52. انقر فوق "ربط".
53. في الشجرة، حدد "أرشيف\<علاقات\IntrastatArchiveDetail".
54. في الشجرة، حدد "النموذج\رأس الأرشيف\البنود التي تم تعدادها‬".
55. انقر فوق "ربط".
56. في الشجرة، حدد "أرشيف\اسم الملف(FileName)".
57. في الشجرة، حدد "نموذج\رأس الأرشيف\اسم الملف".
58. انقر فوق "ربط".
59. في الشجرة، حدد "أرشيف\عدد الأسطر(NumberOfLines)".
60. في الشجرة، حدد "النموذج\رأس الأرشيف\عدد الأسطر‬".
61. انقر فوق "ربط".
62. في الشجرة، حدد "أرشيف".
63. في الشجرة، حدد "النموذج\رأس الأرشيف".
64. انقر فوق "ربط".
65. انقر فوق "حفظ".
66. قم بإغلاق الصفحة.
67. قم بإغلاق الصفحة.

