---
title: تعديل التنسيقات من خلال إعادة تطبيق قوالب Excel
description: لإكمال الخطوات في هذا الإجراء، يجب أولاً إكمال الإجراء "التقارير الإلكترونية - تصميم تكوين لإنشاء التقارير بتنسيق OPENXML".
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5408fd883e91bbff465434ab23974f22bb0f07da
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142976"
---
# <a name="modify-formats-by-reapplying-excel-templates"></a>تعديل التنسيقات من خلال إعادة تطبيق قوالب Excel

[!include [banner](../../includes/banner.md)]

لإكمال الخطوات في هذا الإجراء، يجب أولاً إكمال الإجراء "التقارير الإلكترونية - تصميم تكوين لإنشاء التقارير بتنسيق OPENXML".

يفسر هذا الإجراء كيفية تعديل تكوين تنسيق التقارير الإلكترونية عن طريق إعادة تطبيق قالب Microsoft Excel الذي تم تعديله. في هذا الإجراء، سوف تستورد قالب Excel معدلاً إلى تكوينات تنسيق التقارير الإلكترونية التي تم إنشاؤها للشركة النموذجية Litware, Inc، ثم تنشئ المستندات الإلكترونية. تم تخصيص هذا الإجراء للمستخدمين الذين يؤدون دور مسؤول النظام أو مطور التقارير الإلكترونية. يمكن إتمام هذه الخطوات باستخدام مجموعة بيانات GBSI. قبل البدء، اعمل على تنزيل وحفظ الملف، SampleVendPaymWsReport2.xlsx، المدرج في موضوع التعليمات، ثم عدّل تنسيق إعداد التقارير الإلكترونية من خلال إعادة تطبيق قالب Excel (modify-electronic-reporting-format-reapply-excel-template/).

1. انتقل إلى إدارة المؤسسة > مساحات العمل‬ > إعداد التقارير الإلكتروني‬.
    * تأكد من وجود موفر التكوين للشركة النموذجية "Litware, Inc." ومن وضع علامة عليه كنشط. إذا لم تشاهد موفر التكوين هذا، فيجب أولاً إكمال الخطوات المذكورة في الإجراء، "إنشاء موفر تكوين ووضع علامة عليه على أنه نشط‬".  

## <a name="select-the-er-format"></a>تحديد تنسيق التقارير الإلكترونية
1. انقر فوق "تكوينات إعداد التقارير‬".
2. في الشجرة ، قم بتوسيع "نموذج الدفع".
3. في الشجرة، حدد "Payment model\Sample worksheet report".
4. انقر فوق "المرفقات".
    * لاحظ أن ملف Excel، واسمه SampleVendPaymWsReport.xlsx، يُستخدم حاليًا كقالب لمعالجة دفتر يومية المدفوعات.   
5. انقر فوق "فتح".
    * انقر فوق "فتح" لاستكشاف تخطيط قالب Excel.  
    * راجع القالب. تذكر أنه يتضمن حاليًا التفاصيل التالية لكل بند من بنود الدفع: رقم حساب المورّد واسم المورّد والبنك ورقم التوجيه ورقم الحساب والمدين والدائن والعملة. لهذا المثال، نحن نريد توسيع هذه القائمة من خلال إضافة تفاصيل حول تاريخ الدفع.   
6. قم بإغلاق الصفحة.

## <a name="reapply-a-new-excel-template-to-er-format"></a>إعادة تطبيق قالب Excel جديد على تنسيق التقارير الإلكترونية
1. انقر فوق المصمم.
    * افتح إصدار المسودة لتنسيق التقارير الإلكترونية المحدد لتحريره.  
2. في جزء الإجراءات، انقر فوق "استيراد".
3. انقر فوق "تحديث من Excel".
    * انقر فوق "تحديث القالب"، ثم حدد الملف، SampleVendPaymWsReport2.xlsx.  
    * انقر فوق "تحديث القالب" واستعرض للوصل إلى الملف SampleVendPaymWsReport2.xlsx الذي تم تنزيله في وقت سابق.  
4. انقر فوق "موافق".
    * يتم تطبيق القالب SampleVendPaymWsReport2.xlsx. تتم مزامنة بنية تنسيق التقارير الإلكترونية مع محتوى القالب، الذي تضاف عناصره إلى تنسيق التقارير الإلكترونية. تُزال من تعريف التنسيق أي عناصر موجودة في تنسيق التقارير الإلكترونية غير مضمنة في القالب.  
5. في الشجرة، حدد 'Excel'.
    * لاحظ أن الحقل "القالب" يحتوي الآن على مرجع إلى القالب الجديد.   
6. انقر فوق "المرفقات".
7. انقر فوق "فتح".
    * انقر فوق "فتح" لاستكشاف تخطيط قالب Excel المعدّل.  
    * راجع القالب. لاحظ أنه يحتوي الآن على بند لتاريخ الدفع.   
8. قم بإغلاق الصفحة.
9. في الشجرة، قم بتوسيع 'Excel'.
10. في الشجرة، قم بتوسيع "Excel\PaymLines".
11. في الشجرة، حدد "Excel\PaymLines\PaymDate".
    * لاحظ أن تنسيق التقارير الإلكترونية يحتوي الآن على عنصر إضافي واحد. تمت إضافة خلية، PaymDate، إلى قالب Excel.  
12. انقر فوق علامة التبويب "التعيين".
13. في الشجرة ، قم بتوسيع "النموذج"
14. في الشجرة، قم بتوسيع "النموذج/المدفوعات".
15. في الشجرة، حدد "النموذج/المدفوعات/تاريخ الحركة(TransactionDate)".
16. انقر فوق "ربط".
    * حدد البيانات المضافة إلى الخلية الجديدة في وقت التشغيل.  
17. انقر فوق "حفظ".
18. قم بإغلاق الصفحة.

## <a name="enable-the-modified-draft-version-of-the-er-format-for-use-in-payment-journal-processing"></a>تمكين إصدار المسودة‬ المعدل لتنسيق التقارير الإلكترونية لاستخدامه في معالجة دفتر يومية المدفوعات
1. في جزء الإجراءات، انقر فوق "التكوينات".
2. انقر فوق "محددات المستخدم".
3. حدد "نعم" في حقل "تشغيل الإعدادات".
4. انقر فوق "موافق".
5. انقر فوق "تحرير".
6. حدد "نعم" في حقل "تشغيل المسودة‬".

## <a name="use-the-modified-draft-version-of-the-er-format-for-payment-journal-processing"></a>استخدام إصدار المسودة‬ المعدل لتنسيق التقارير الإلكترونية لاستخدامه في معالجة دفتر يومية المدفوعات
    * قم بمراجعة ورقة العمل التي تم إنشاؤها، بما في ذلك التفاصيل الجديدة لبنود الدفع – تاريخ الدفع.  
