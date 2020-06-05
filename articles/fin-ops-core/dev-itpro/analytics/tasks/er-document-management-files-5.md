---
title: التقارير الإلكترونية - استخدام ملفات إدارة المستندات في مخرجات التنسيق‬ (الجزء 5 - تعديل التنسيق وتشغيله)
description: تشرح الخطوات التالية كيف يستطيع مستخدم تم تعيينه إلى دور مسؤول النظام أو دور مطور التقارير الإلكترونية تكوين تنسيق تقارير إلكترونية لاستخدام ملفات إدارة المستندات (مرفقات) في مخرجات التقارير الإلكترونية.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERComponentTypeDropDialog, ERExpressionDesignerFormula, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1a52a7dd3b31c0189577422a79d47b318aae4a05
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141984"
---
# <a name="er-use-document-management-files-in-format-outputs-part-5---modify-and-run-format"></a>التقارير الإلكترونية - استخدام ملفات إدارة المستندات في مخرجات التنسيق‬ (الجزء 5 - تعديل التنسيق وتشغيله)

[!include [banner](../../includes/banner.md)]

تشرح الخطوات التالية كيف يستطيع مستخدم تم تعيينه إلى دور مسؤول النظام أو دور مطور التقارير الإلكترونية تكوين تنسيق تقارير إلكترونية لاستخدام ملفات إدارة المستندات (مرفقات) في مخرجات التقارير الإلكترونية. يمكن تنفيذ هذه الخطوات في شركة DEMF.

لإكمال هذه الخطوات، يجب أولاً إكمال الخطوات المذكورة في الإجراء "التقارير الإلكترونية - استخدام ملفات إدارة المستندات في مخرجات التنسيق (الجزء 4: تشغيل التنسيق)".

يتم استخدام هذا الإجراء لميزة تمت إضافتها في Dynamics 365 for Operations، الإصدار 1611.


## <a name="modify-the-format-to-populate-attachments-into-generating-messages-in-binary-format"></a>تعديل التنسيق لتعبئة المرفقات في الرسائل الناشئة بتنسيق ثنائي
1. انتقل إلى إدارة المؤسسة >إعداد التقارير الإلكتروني >التكوينات.
2. في الشجرة، قم بتوسيع "نموذج فاتورة العميل".
3. في الشجرة، قم بتوسيع "نموذج فاتورة العميل‬/نموذج فاتورة العميل‬ (مخصص)".
4. في الشجرة، حدد "نموذج فاتورة العميل‬/نموذج فاتورة العميل‬ (مخصص)/رسالة نموذج فاتورة إلكترونية."
5. انقر فوق المصمم.
    * ستقوم بتعبئة رسالة الفاتورة في الإخراج الناشئ كملف XML باستخدام ترميز UNICODE.  
6. انقر فوق "إضافة جذر" لفتح مربع حوار الإسقاط‬.
7. في الشجرة، حدد "Common\File".
8. في الحقل "الاسم"، اكتب "رسالة Xml".
    * رسالة Xml  
9. في الحقل"الترميز"، اكتب "UTF-8".
    * UTF-8  
10. انقر فوق "موافق".
    * قم بتكوين الإخراج الناشئ كملف مضغوط.  
11. انقر فوق "إضافة جذر" لفتح مربع حوار الإسقاط‬.
12. في الشجرة، حدد "عام\مجلد".
13. في الحقل "الاسم"، اكتب "إخراج ملف Zip".
    * إخراج ملف Zip  
14. انقر فوق "موافق".
15. في الشجرة، حدد "إخراج ملف Zip".
    * أضف المرفقات إلى الملف المضغوط الناشئ كالملفات ذات الأسماء والملحقات الأصلية.  
16. انقر فوق "إضافة" لفتح مربع حوار الإسقاط‬.
17. في الشجرة، حدد "Common\File".
18. في حقل "الاسم"، اكتب "الملف المرفق".
    * الملف المرفق  
19. انقر فوق "موافق".
20. في الشجرة، حدد "إخراج ملف Zip\ملف مرفق".
21. انقر فوق "إضافة" لفتح مربع حوار الإسقاط‬.
22. في الشجرة، حدد "النص\Base64".
23. انقر فوق "موافق".

## <a name="map-new-format-elements-to-data-model"></a>تعيين عناصر التنسيق الجديد إلى نموذج بيانات
1. انقر فوق علامة التبويب "التعيين".
2. في الشجرة، قم بتوسيع "النموذج"
3. في الشجرة، قم بتوسيع "النموذج\مرفقات الفاتورة".
4. في الشجرة، حدد "إخراج ملف Zip\ملف مرفق\Base64".
5. في الشجرة، حدد "النموذج\مرفقات الفاتورة\محتوى الملف".
6. انقر فوق "ربط".
7. في الشجرة، حدد "إخراج ملف Zip\ملف مرفق".
8. انقر فوق "تحرير اسم الملف".
9. في الشجرة، قم بتوسيع "النموذج"
10. في الشجرة، قم بتوسيع "النموذج\مرفقات الفاتورة".
11. في الشجرة، حدد "النموذج\مرفقات الفاتورة\اسم الملف‬".
12. انقر فوق "إضافة مصدر بيانات".
13. انقر فوق حفظ.
14. قم بإغلاق الصفحة.
15. في الشجرة، حدد "النموذج\مرفقات الفاتورة".
16. انقر فوق "ربط".
17. انقر فوق "حفظ".
18. قم بإغلاق الصفحة.

## <a name="run-the-designed-report-for-the-selected-invoice"></a>تشغيل التقرير المصمم للفاتورة المحددة
1. انقر فوق "تشغيل".
2. وسّع المقطع "السجلات المطلوب تضمينها‬ ()".
3. انقر فوق "عامل التصفية".
4. حدد الصف لحقل دفتر يومية فاتورة العميل وأمر المبيعات.
5. في حقل المعايير"، في حقل "أمر المبيعات" للمعايير، اكتب رقم الأمر 000148.
    * 000148  
6. انقر فوق موافق.
7. انقر فوق موافق.
    * اعمل على مراجعة المخرجات المنشأة. لاحظ أنه تم إنشاء ملف واحد لكل مرفق، بالإضافة إلى رسالة الفاتورة بتنسيق XML. تتم تعبئة ملفات المرفقات بالإخراج المضغوط بتنسيق ثنائي.  
