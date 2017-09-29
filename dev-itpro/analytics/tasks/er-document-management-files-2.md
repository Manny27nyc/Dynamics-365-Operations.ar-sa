--- 
title: "توسيع نموذج بيانات لاستخدام ملفات إدارة المستندات في مخرجات التنسيق للتقارير الإلكترونية (ER)"
description: "تشرح الخطوات التالية كيف يستطيع مستخدم تم تعيينه إلى دور مسؤول النظام أو دور مطور التقارير الإلكترونية تكوين تنسيق تقارير إلكترونية لاستخدام ملفات إدارة المستندات (مرفقات) في مخرجات التقارير الإلكترونية."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
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
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 92177f4653325f6a43c704097d8d5d54d0e15ba9
ms.contentlocale: ar-sa
ms.lasthandoff: 07/27/2017

---
# <a name="extend-data-model-to-use-document-management-files-in-format-outputs-for-electronic-reporting-er"></a>توسيع نموذج بيانات لاستخدام ملفات إدارة المستندات في مخرجات التنسيق للتقارير الإلكترونية (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

تشرح الخطوات التالية كيف يستطيع مستخدم تم تعيينه إلى دور مسؤول النظام أو دور مطور التقارير الإلكترونية تكوين تنسيق تقارير إلكترونية لاستخدام ملفات إدارة المستندات (مرفقات) في مخرجات التقارير الإلكترونية. يمكن تنفيذ هذه الخطوات في أي شركة.

لإكمال هذه الخطوات، يجب أولاً إكمال الخطوات المذكورة في دليل المهمة "التقارير الإلكترونية - استخدام ملفات إدارة المستندات في مخرجات التنسيق (الجزء 1: إعداد نموذج البيانات").

يتم استخدام هذا الإجراء لميزة تمت إضافتها في Dynamics 365 for Operations، الإصدار 1611.


## <a name="extend-data-model-to-present-the-document-management-files-in-it"></a>توسيع نموذج البيانات لتقديم ملفات إدارة المستندات فيه
1. انتقل إلى إدارة المؤسسة > مساحات العمل‬ > إعداد التقارير الإلكتروني‬.
2. انقر فوق "تكوينات إعداد التقارير‬".
3. في الشجرة، قم بتوسيع "نموذج فاتورة العميل".
4. في الشجرة، حدد "نموذج فاتورة العميل‬/نموذج فاتورة العميل‬ (مخصص)".
5. انقر فوق المصمم.
6. في الشجرة، حدد "فاتورة العميل(InvoiceCustomer)".
    * سنقوم بتوسيع نموذج البيانات هذا لعرضه في أية ملفات تم إرفاقها بأمر مبيعات يرتبط بفاتورة تتم معالجتها إلكترونيًا.  
7. انقر فوق "جديد" لفتح مربع حوار الإسقاط‬.
8. في حقل "الاسم"، اكتب "مرفقات الفواتير".
    * مرفقات الفاتورة  
9. في الحقل "نوع الصنف"، حدد "قائمة سجلات".
10. وانقر فوق إضافة.
11. انقر فوق "جديد" لفتح مربع حوار الإسقاط‬.
12. في حقل "الاسم"، اكتب "محتوى الملف".
    * محتوى الملف  
13. في الحقل "نوع الصنف"، حدد "الحاوية".
14. وانقر فوق إضافة.
15. انقر فوق "جديد" لفتح مربع حوار الإسقاط‬.
16. في حقل "الاسم"، اكتب "اسم الملف".
    * اسم الملف  
17. في الحقل "نوع الصنف"، حدد "سلسلة".
18. وانقر فوق إضافة.

## <a name="map-new-data-model-elements-to-dynamics-365-for-finance-and-operations-enterprise-edition-data-sources"></a>تعيين عناصر نموذج بيانات جديد إلى مصادر بيانات Dynamics 365 for Finance and Operations, Enterprise edition
1. انقر فوق "تعيين النموذج لمصدر البيانات".
2. استخدم عامل التصفية السريع لإجراء التصفية باستخدام حقل "التعريف" بالقيمة "InvoiceCustomer".
    * InvoiceCustomer  
    * سنقوم بتعيين عناصر نماذج جديدة إلى مصادر البيانات المناسبة.  
3. انقر فوق المصمم.
4. في الشجرة، حدد "مرفقات الفاتورة‬".
5. في الشجرة، قم بتوسيع "مرفقات الفاتورة‬".
6. في الشجرة، حدد "مرفقات الفاتورة\اسم الملف‬".
7. انقر فوق "تحرير".
8. في حقل المعادلة، أدخل 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()''.
    * CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'originalFileName()'  
9. انقر فوق "حفظ".
10. قم بإغلاق الصفحة.
11. في الشجرة، حدد "مرفقات الفاتورة\محتوى الملف".
12. انقر فوق "تحرير".
13. في حقل المعادلة، أدخل 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()''.
    * CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'.'getFileContentAsContainer()'  
14. انقر فوق "حفظ".
15. قم بإغلاق الصفحة.
16. في الشجرة، حدد "مرفقات الفاتورة‬".
17. انقر فوق "تحرير".
18. في حقل المعادلة، أدخل 'CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents''.
    * CustInvoiceJour.'>Relations'.SalesTable.'<Relations'.'<Documents'  
19. انقر فوق "حفظ".
20. قم بإغلاق الصفحة.
21. انقر فوق "حفظ".
22. قم بإغلاق الصفحة.
23. قم بإغلاق الصفحة.
24. قم بإغلاق الصفحة.
25. انقر فوق "تغيير الحالة".
26. انقر فوق "مكتمل".
27. انقر فوق "موافق".

