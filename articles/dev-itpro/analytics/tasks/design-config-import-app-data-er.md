--- 
title: "تصميم تكوينات التقارير الإلكترونية لتحليل المستندات الواردة"
description: "يُظهر هذا الإجراء كيفية تصميم تكوينات التقارير الإلكترونية لتحليل مستند إلكتروني وارد."
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
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
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 9e5f826afa141c0851a963b33e40c58513e60a07
ms.contentlocale: ar-sa
ms.lasthandoff: 08/08/2018

---
# <a name="design-er-configurations-to-parse-incoming-documents"></a>تصميم تكوينات التقارير الإلكترونية لتحليل المستندات الواردة

[!include [task guide banner](../../includes/task-guide-banner.md)]

يُظهر هذا الإجراء كيفية تصميم تكوينات التقارير الإلكترونية لتحليل مستند إلكتروني وارد. في هذا الإجراء، سوف تستورد تكوينات التقارير الإلكترونية المطلوبة التي تم إنشاؤها للشركة النموذجية Litware, Inc.، ثم تستخدمها لتحليل المستندات الإلكترونية الواردة. لإكمال الخطوات في هذا الإجراء، يجب أولاً إكمال الإجراء "التقارير الإلكترونية - إنشاء موفر تكوين ووضع علامة عليه على أنه نشط‬".

تم إنشاء هذا الإجراء للمستخدمين الذين لديهم دور مسؤول النظام أو مطور التقارير الإلكترونية. 

يمكن إتمام هذه الخطوات باستخدام أي مجموعة بيانات. قبل البدء، قم بتنزيل وحفظ الملفات الواردة في الموضوع، "تحليل المستندات الواردة لتحديث بيانات التطبيق" (https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/analytics/parse-incoming-electronic-documents). الملفات هي: EFSTA model.xml وEFSTA format.xml وResponse1.xml وResponse2.xml وResponse3.xml وResponse4.xml.

1. انتقل إلى إدارة المؤسسة > مساحات العمل‬ > إعداد التقارير الإلكتروني‬.
    * تأكد من وجود موفر التكوين للشركة النموذجية "Litware, Inc." ومن وضع علامة عليه كنشط. إذا لم تشاهد موفر التكوين هذا، فيجب أولاً إكمال الخطوات المذكورة في الإجراء، "إنشاء موفر تكوين ووضع علامة عليه على أنه نشط‬".  
2. انقر فوق "تكوينات إعداد التقارير‬".
    * سيتم استخدام السيناريو التالي لعرض قدرات تحليل المستندات الإلكترونية الواردة بتنسيق XML: يطلب تطبيق ERP (Dynamics 365 for Finance and Operations) البيانات من خدمة ويب (مثل http://efsta.org/ الخدمة المالية EFSTA) ويقوم بتحليل الاستجابات الواردة لتحديث بيانات التطبيق وفقًا لذلك. لاستخدام أفضل طريقة للتحليل، يتم استخدام تنسيق واحد للتقارير الإلكترونية على الرغم من البنية المختلفة للمستندات الواردة المتوقعة بتنسيق XML.   

## <a name="import-and-review-er-configurations"></a>استيراد ومراجعة تكوينات التقارير الإلكترونية
استورد تكوين نموذج التقارير الإلكترونية الذي يحتوي على عينة نموذج البيانات المصممة لتخزين التفاصيل الخاصة بالملف الوارد.  
1. انقر فوق "التبادل‬".
2. انقر فوق "تحميل من ملف XML".
    * انقر فوق "استعراض" وحدد ملف EFSTA model.xml.  
3. انقر فوق "موافق".
4. في الشجرة، حدد "نموذج EFSTA".
5. انقر فوق المصمم.
    * راجع بنية نموذج البيانات المستورد. لاحظ أنه تم تعريف التعداد enumType للتعرف على الأنواع التالية من الاستجابات للخدمة: للحصول على تأكيد حول إرسال الحركة وللحصول على معلومات حول آخر حركة تم إرسالها وللتعرف على أنواع الاستجابات غير المعتمدة.   
6. في الشجرة، وسّع "استجابة".
    * لاحظ أنه يتم تحديد عنصر الجذر "استجابة" لتحديد نوع البيانات الذي يجب أخذه من استجابة معتمدة للخدمة لتحديث بيانات التطبيق وفقًا لذلك.   
7. قم بإغلاق الصفحة.
    * ستقوم باستيراد تكوين تنسيق التقارير الإلكترونية الذي يحدد كيف سيتم تحليل المستندات الواردة لتخزين البيانات في نموذج بيانات التقارير الإلكترونية.   
8. انقر فوق "التبادل‬".
9. انقر فوق "تحميل من ملف XML".
    * انقر فوق "استعراض" وحدد ملف EFSTA format.xml.  
10. انقر فوق "موافق".
11. في الشجرة، وسّع "نموذج EFSTA".
12. في الشجرة، حدد "نموذج EFSTA\تنسيق EFSTA".
13. انقر فوق المصمم.
14. انقر فوق "توسيع/طي".
    * لاحظ أنه يتم استخدام عنصر التنسيق CASE كجذر، وهو يحتوي على ثلاثة عناصر FILE متداخلة، وهذا يعني أنه قد تم تصميم هذا التنسيق لتحليل الملفات الواردة ذات تنسيقات مختلفة.  
15. في الشجرة، حدد "استجابات\إكمال الحركة\TraC".
    * لاحظ أن الاستجابة المتعلقة بالحركة المرسلة تبدأ من عنصر الجذر "TraC".   
16. في الشجرة، حدد "استجابات\طلب الحركة الأخيرة\Tra".
    * لاحظ أن الاستجابة المتعلقة بآخر حركة مرسلة تبدأ من عنصر الجذر "Tra".   
17. في الشجرة، حدد "استجابات\استجابة غير متوقعة\النص".
    * تمت إضافة عنصر FILE الثالث مع عنصر TEXT المتداخل للتعرف على أي أنواع أخرى من الاستجابات التي تختلف عن تلك المذكورة أعلاه.   
18. انقر فوق "تعيين تنسيق لنموذج‬".
    * يحتوي تعيين الطراز هذا على تعريف تدفق البيانات لتخزين التفاصيل الخاصة بالمستند الوارد الذي تم تحليله باستخدام عناصر نموذج البيانات.  
19. انقر فوق المصمم.
20. في الشجرة، قم بتوسيع "تنسيق".
21. في الشجرة، وسّع "تنسيق\استجابات: حالة(استجابات)".
    * راجع بنية نموذج مصدر البيانات "تنسيق". لاحظ أن أنواع الاستجابات الثلات كلها معروضة بشكل منفصل.   
22. في الشجرة، حدد "تنسيق\استجابات: حالة(استجابات)\aType".
    * تم إضافة عنصر مصدر البيانات "aType" للإشارة إلى نوع الاستجابة وهو مرتبط بعنصر نموذج البيانات "Type".  
23. انقر فوق علامة التبويب "عمليات التحقق من الصحة".
24. في الشجرة، حدد "النوع = format.Responses.aType".
    * لاحظ أنه تم تكوين التحقق من صحة التقارير الإلكترونية لإعلام المستخدم حول الحالة عندما لا تتطابق بنية الاستجابة مع التأكيد حول إرسال الحركة أو المعلومات المرتبطة بآخر حركة تم إرسالها (حالة استجابة غير معتمدة).   
25. قم بإغلاق الصفحة.

## <a name="run-model-mapping-of-er-format-configured-for-parsing-incoming-files"></a>تشغيل تعيين نموذج تنسيق تقارير إلكترونية تم تكوينه لتحليل الملفات الواردة
ستقوم بتشغيل تعيين النموذج الذي تم إنشاؤه لأغراض اختبارية لمعرفة كيف سيقوم تنسيق التقارير الإلكترونية المكوّن بتحليل استجابات الخدمة الواردة. تستخدم هذه الخطوة ملفات XML مختلفة لمحاكاة نوع مختلف من استجابات خدمة الويب.   
1. افتح الملف Response1.xml في قارئ xml، مثل مستعرض ويب. لاحظ أن هذا الملف يحتوي على تفاصيل تأكيد حول الحركة المكتملة ("TraC" هو العنصر الجذر).   
2. انقر فوق "تشغيل".
    * انقر فوق "استعراض" وحدد ملف Response1.xml.  
3. انقر فوق "موافق".
    * اعمل على مراجعة المخرجات المنشأة. لاحظ أنه تم التعرف على نوع الاستجابة وتحليله بشكل صحيح (يعني ERModelEnumDataSourceHandler#EFSTA model#enumType#C حالة اكتمال الحركة).   
    * افتح الملف Response2.xml في قارئ XML. لاحظ أن هذا الملف يحتوي على معلومات حول آخر حركة تم إرسالها ("Tra" هو العنصر الجذر).   
4. انقر فوق "تشغيل".
    * انقر فوق "استعراض" وحدد ملف Response2.xml.  
5. انقر فوق "موافق".
    * اعمل على مراجعة المخرجات المنشأة. لاحظ أنه تم التعرف على نوع الاستجابة وتحليله بشكل صحيح (يعني ERModelEnumDataSourceHandler#EFSTA model#enumType#R حالة إعادة بدء النظام).   
    * افتح الملف Response3.xml في قارئ XML. لاحظ أن هذا الملف يبدأ من العنصر الجذر TraZ وأن هذه البنية لم يتم تكوينها باستخدام تنسيق التقارير الإلكترونية.   
6. انقر فوق "تشغيل".
    * انقر فوق "استعراض" وحدد ملف Response3.xml.  
7. انقر فوق "موافق".
    * اعمل على مراجعة المخرجات المنشأة. لاحظ أنه تم التعرف على نوع الاستجابة بشكل صحيح على أنه غير معتمد (ERModelEnumDataSourceHandler#EFSTA model#enumType#U). تم وضع الرسالة المطابقة في سجل المعلومات (وفقًا لإعداد التحقق من صحة التقارير الإلكترونية)، ولم يتم ملء الجزء الأكبر من نموذج البيانات.   
    * افتح الملف Response4.xml في قارئ XML. لاحظ أن بنية هذا الملف هي تقريبًا البنية نفسها للملف Response1.xml الذي تم تحليله بنجاح، ما عدا تسلسل العناصر متداخلة للعنصر الجذر "TraC".   
8. انقر فوق "تشغيل".
    * انقر فوق "استعراض" وحدد ملف Response4.xml.  
9. انقر فوق "موافق".
    * اعمل على مراجعة المخرجات المنشأة. لاحظ أنه تم التعرف على نوع الاستجابة بشكل صحيح على أنه غير معتمد (ERModelEnumDataSourceHandler#EFSTA model#enumType#U)). تم وضع الرسالة المطابقة في سجل المعلومات، ولم يتم ملء الجزء الأكبر من نموذج البيانات. سبب ذلك هو أن الإعداد الحالي لتنسيق التقارير الإلكترونية هذا يفترض تسلسلاً معينًا للعناصر المتداخلة للعنصر الجذر للملف الوارد.   
10. قم بإغلاق الصفحة.
11. في الشجرة، حدد "استجابات\إكمال الحركة\TraC".
12. في الحقل "ترتيب تحليل العناصر المتداخلة"، حدد "أي واحد".
    * حدد "أي واحد" في حقل "ترتيب تحليل العناصر المتداخلة" للسماح لأي تسلسل عناصر متداخلة لعنصر XML الجذر هذا.  
13. انقر فوق "حفظ".
14. انقر فوق "تعيين تنسيق لنموذج‬".
15. انقر فوق "تشغيل".
    * انقر فوق "استعراض" وحدد ملف Response4.xml.  
16. انقر فوق "موافق".
    * اعمل على مراجعة المخرجات المنشأة. لاحظ أنه تم الآن التعرف بشكل صحيح على نوع الاستجابة على أنه مساو للملف Response1.xml.  

