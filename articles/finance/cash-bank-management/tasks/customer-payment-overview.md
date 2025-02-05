---
title: نظرة عامة على دفعات العملاء
description: يوضح هذا الإجراء مختلف الطرق التي تُستخدم لإدخال مدفوعات العميل.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, CustPaymEntry, CustTableLookup, LedgerJournalTransCustPaym, CustOpenTrans, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.custom: intro-internal
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 99e2e04064d717040cf43469683fd143dc124c4f
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/05/2022
ms.locfileid: "8714355"
---
# <a name="customer-payment-overview"></a>نظرة عامة على دفعات العملاء

[!include [banner](../../includes/banner.md)]

يوضح هذا الإجراء مختلف الطرق التي تُستخدم لإدخال مدفوعات العميل. تستخدم هذه المهمة شركة بيانات العرض التوضيحي USMF.

1. انتقل إلى **جزء التنقل > الوحدات النمطية > الحسابات المدينة > المدفوعات > دفتر يومية المدفوعات‬**.
2. انقر فوق **جديد**.
3. حدد دفتر يومية المدفوعات الذي ستُحفظ به مدفوعات العميل.
4. حدد دفتر اليومية أو قم بإدخاله يدوياً.
5. في **جزء الإجراءات**، انقر فوق **إدخال مدفوعات العميل**. يستخدم خيار "إدخال مدفوعات العميل" لتسجيل مدفوعات عميل واحد في كل مرة. تقوم بإدخال معلومات الدفع في الجزء العلوي، ثم يمكنك وضع علامة تميز بها الفواتير التي تم دفعها خلال عملية الدفع، وتقوم بذلك كله من نفس الصفحة.  
6. أدخل اسم العميل الذي تلقيت الدفع منه. إذا لم تكن تعرف العميل، ولكنك تعرف الحركة التي تم دفعها، يمكنك استخدام حقل "الحركة" لإدخال الدفع. قم بإدخال أو تحديد الفاتورة في حقل "الحركة". سوف يتم تعيين العميل افتراضيًا بشكل تلقائي بعد تحديد الحركة.
7. في الحقل **مرجع الدفع**، أدخل مرجع الدفع. قد يكون مرجع الدفع هو رقم الشيك الخاص بالعميل أو مرجع من الدفع الإلكتروني الخاص بالعميل. ويكون مرجع الدفع مطلوبًا فقط إذا قمت بوضع علامة لاختيار تضمين الدفع في إيصال الإيداع.  
8. حدد ما إذا كان سيتم تضمين الدفع في قسيمة إيداع في الحقل **قسيمة إيداع**. 
9. في الحقل **المبلغ**، أدخل مبلغ دفع العميل. ولن يُعين مبلغ الدفع افتراضيًا. بل يجب إدخاله يدوياً. 
10. قم بوضع علامة على الفواتير التي دُفعت بواسطة العميل. إذا كان الدفع في صورة دفعة مقدمة، فلن تضطر إلى وضع علامة لتمييز أية فواتير للتسوية. ولا يزال من الممكن حفظ الدفع وترحيله. وقد تحدث تسوية إحدى الفواتير في وقت لاحق.
11. أدخل مبلغ الدفع المطلوب تسويته للفاتورة المميزة بعلامة. يمكن استخدام هذا الحقل عندما يكون الدفع خاص بدفع جزئي. إذا لم يتم إدخال مبلغ، سيُحدد المبلغ المراد تسويته تلقائياً.
12. انقر فوق **حفظ في دفتر اليومية**. قبل حفظ الدفع في دفتر اليومية، تأكد من تحديد الحساب المقابل. سيؤدي استخدام خيار **حفظ في دفتر اليومية** إلى حفظ الدفع ونقله إلى دفتر اليومية. ثم يمكنك المتابعة بإدخال الدفع التالي.
13. قم بإغلاق الصفحة.
14. في **جزء الإجراءات**، انقر فوق "البنود". عند فتح البنود، ستشاهد أية مدفوعات سجلتَها على صفحة **إدخال مدفوعات العميل** وحفظتَها في دفتر اليومية. ويمكنك أيضًا استخدام هذه الصفحة لإدخال مدفوعات عميل جديدة أو تحرير دفع عميل موجود قبل ترحيله.
15. انقر فوق **جديد** لإنشاء دفع آخر. 
16. حدد العميل الذي تلقيت الدفع منه. إذا لم تكن تعرف العميل ولكن تعرف إحدى الفواتير المدفوعة عبر الدفع، فاستخدم الحقل "الفاتورة" لإدخال الفاتورة يدوياً أو تحديدها. سيتم تعيين العميل افتراضيًا بعد تحديد الفاتورة.  
17. انقر فوق **تسوية الحركات** لتمييز الفواتير التي تم دفعها بعلامة. ولن تُضطر لتسوية المدفوعات إلى أية فواتير. إذا كان الدفع في صورة دفعة مقدمة أو كنت لا تعرف الفاتورة التي تم دفعها، يمكنك إدخال الدفع وترحيله. يمكن تسوية الدفع لفاتورة في وقت لاحق.  
18. قم بتمييز الفواتير المدفوعة بواسطة الدفع بعلامة. 
19. أدخل مبلغ الدفع الذي سيتم تسويته للفاتورة في حقل **المبلغ**.
20. انقر فوق **موافق**.
21. في الحقل **مرجع الدفع**، أدخل مرجع الدفع. ويكون مرجع الدفع مطلوبًا فقط إذا قمت بوضع علامة لاختيار تضمين الدفع في إيصال الإيداع.  
22. في **جزء الإجراءات**، انقر فوق **ترحيل** لترحيل دفعات العميل. 



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
