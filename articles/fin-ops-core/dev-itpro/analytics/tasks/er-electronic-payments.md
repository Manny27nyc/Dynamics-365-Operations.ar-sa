---
title: تعمل التقارير الإلكترونية على إنشاء التقارير الإلكترونية للدفعات باستخدام تكوين التنسيق
description: تشرح الخطوات التالية كيف يمكن لمستخدم بدور مسؤول النظام أو مطور التقارير الإلكترونية استخدام تكوين تنسيق تقارير إلكترونية جديد يحتوي على نموذج بيانات لإنشاء مستندات الدفع الإلكتروني لمعالجة الدفعات.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPaymMode, LedgerJournalTable, LedgerJournalTransVendPaym, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fa39a9d459022e391f99e284d41d82215cc10e2b
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142560"
---
# <a name="er-generate-electronic-documents-for-payments-using-a-format-configuration"></a>تعمل التقارير الإلكترونية على إنشاء التقارير الإلكترونية للدفعات باستخدام تكوين التنسيق

[!include [banner](../../includes/banner.md)]

تشرح الخطوات التالية كيف يمكن لمستخدم بدور مسؤول النظام أو مطور التقارير الإلكترونية استخدام تكوين تنسيق تقارير إلكترونية جديد يحتوي على نموذج بيانات لإنشاء مستندات الدفع الإلكتروني لمعالجة الدفعات. يمكن تنفيذ هذه الخطوات في عينة شركة GBSI.

لإكمال هذه الخطوات، يجب أولاً إكمال الخطوات المذكورة في الإجراء "إنشاء تكوين بتنسيق مستند الدفع".


## <a name="change-the-configuration-of-the-electronic-payment-method"></a>تغيير تكوين أسلوب الدفع الإلكتروني
1. انتقل إلى الحسابات المدينة > إعداد الدفع‬ > طرق الدفع.
2. قم بالتبديل بين مقطع تنسيق الملف لتوسيعه، إذا لزم الأمر.
3. استخدم عامل التصفية السريع للبحث عن السجلات. على سبيل المثال، قم بإجراء التصفية على الحقل "طريقة الدفع" بقيمة "إلكتروني".
4. انقر فوق "تحرير".
5. قم بتعيين الحقل "التقارير الإلكترونية العامة" إلى "نعم".
    * حدد "نعم" لاستخدام نمط التقارير الإلكترونية العامة لإنشاء ملفات الدفعات.  
6. في الحقل "الاسم"، انقر فوق زر القائمة المنسدلة لفتح البحث.
7. حدد تكوين تنسيق BACS (وهمي في المملكة المتحدة).
8. انقر فوق "حفظ".
9. قم بإغلاق الصفحة.

## <a name="test-the-format-of-generated-payment-files"></a>اختبار تنسيق ملفات الدفع الذي تم إنشاؤه
1. انتقل إلى الحسابات الدائنة > المدفوعات‬ > دفتر يومية المدفوعات‬‬.
2. انقر فوق "جديد".
3. في القائمة، قم بوضع علامة للصف المحدد.
4. في الحقل "الاسم"، انقر فوق زر القائمة المنسدلة لفتح البحث.
5. في القائمة، انقر فوق الارتباط في الصف المحدد.
    * حدد VendPay.  
6. انقر فوق "حفظ".
7. انقر فوق البنود.
8. في الحقل "الشركة"، اكتب "DEMF".
    * DEMF  
9. في حقل الحساب، حدد قيم "DE-01001".
    * DE - 01001  
10. في حقل "الوصف"، اكتب "الدفع".
    * المدفوعات  
11. في الحقل "مدين"، أدخل رقمًا.
    * 1000  
12. انقر فوق علامة التبويب "الدفع".
13. في الحقل "طريقة الدفع"، انقر فوق زر القائمة المنسدلة لفتح البحث.
14. في القائمة، قم بالبحث عن السجل المطلوب وحدده.
    * حدد القيمة الإلكترونية.  
15. في القائمة، انقر فوق الارتباط في الصف المحدد.
16. انقر فوق "حفظ".
17. انقر فوق إنشاء مدفوعات.
18. في الحقل "طريقة الدفع"، انقر فوق زر القائمة المنسدلة لفتح البحث.
19. في القائمة، قم بالبحث عن السجل المطلوب وحدده.
    * حدد القيمة الإلكترونية.  
20. في القائمة، انقر فوق الارتباط في الصف المحدد.
    * حدد القيمة الإلكترونية.  
21. في حقل "اسم الملف"، أدخل قيمة.
    * على سبيل المثال، اكتب "دفعات".  
22. في الحقل "الحساب البنكي"، انقر فوق زر القائمة المنسدلة لفتح البحث.
23. في القائمة، انقر فوق الارتباط في الصف المحدد.
    * حدد القيمة GBSI OPER.  
24. انقر فوق "موافق".
25. انقر فوق "موافق".
    * حلل ملف الدفع الذي تم إنشاؤه بتنسيق XML. قارنه بمخطط المستند المصمم وحدد سمات حركة الدفع.  
