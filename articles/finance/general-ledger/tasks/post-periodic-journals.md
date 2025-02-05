---
title: ترحيل دفاتر اليومية الدورية
description: دفاتر اليومية الدورية تسمى في بعض الأحيان دفاتر اليومية المتكررة بسبب تكرار المبلع والنص وغير ذلك من المعلومات في كل مرة يتم فيها استرجاع دفتر اليومية الدوري.
author: aprilolson
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransPeriodic, LedgerJournalTransDaily
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 412098c2027344bfc5309d814ee70d6ee98ca765
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/05/2022
ms.locfileid: "8716904"
---
# <a name="post-periodic-journals"></a>ترحيل دفاتر اليومية الدورية

[!include [banner](../../includes/banner.md)]

دفاتر اليومية الدورية تسمى في بعض الأحيان دفاتر اليومية المتكررة بسبب تكرار المبلع والنص وغير ذلك من المعلومات في كل مرة يتم فيها استرجاع دفتر اليومية الدوري. عند إنشاء دفتر اليومية الدوري، ستحدد الفاصل الزمني للتكرار، مثل الأيام أو الشهور. سينشئ دليل المهمة هذا دفتر يومية دوريًا مع تكرار شهري.

1. انتقل إلى جزء التنقل **> الوحدات النمطية > دفتر الأستاذ العام > مهام دورية‬ > تسجيل دفتر اليومية‬**.
2. انقر فوق **جديد**.
3. في الحقل **الاسم** أدخل قيمة أو حددها.
4. في القائمة، انقر فوق الارتباط في الصف المحدد.
5. في حقل **الوصف**، اكتب قيمة. سيكون الوصف اسم دفتر اليومية الدوري عند استرجاعه في وقت لاحق، لذا إدخال اسم ذي صلة له.
6. في **جزء الإجراءات**، انقر فوق **البنود**. يتضمن دفتر اليومية الدوري عادة الكثير من بنود دفتر اليومية. غير أن دليل المهمة هذا سيضيف بندًا واحدًا فقط.
7. في حقل **التاريخ**، أدخل تاريخًا. يحتوي حقل **التاريخ** على تاريخ الترحيل لعملية التحويل التالية إلى دفتر اليومية اليومي. بالنسبة إلى دفاتر اليومية التي يتم استرجاعها كل شهر، من المستحسن استخدام التاريخ في الشهر عند ترحيله، عادة التاريخ الأول أو الأخير في الفترة الزمنية. يمكن ترك حقل "التاريخ" فارغًا وإعطاء تاريخ عند استرجاع دفتر اليومية، باستخدام حقل التاريخ الفارغ. يتم تحديث الحقل تلقائيًا وفق التاريخ المتكرر التالي عندما يتم استرجاع المعاملات. 
8. في حقل **الحساب**، حدد القيم المطلوبة.
9. في حقل **الوصف** ، حدد القيمة.
10. قم بإغلاق الصفحة.
11. في الحقل **مدين** ، أدخل رقمًا.
12. في الحقل **حساب مقابل**، حدد القيم المطلوبة.
13. في الحقل **الوحدة** ، حدد "الأشهر".
14. في الحقل **عدد الوحدات** ، أدخل "1".
15. في الحقل **آخر تاريخ‬** ، أدخل تاريخًا. سيؤدي إدخال آخر تاريخ في الفترة السابقة إلى منع إنشاء دفتر اليومية المتكرر عن طريق الخطأ في فترة البدء غير الصحيحة. سيتم بعد ذلك تحديث آخر تاريخ في كل مرة يتم فيها استرجاع دفتر اليومية الدوري. 
16. انقر فوق **حفظ**.
17. انتقل إلى **جزء التنقل > الوحدات النمطية > دفتر الأستاذ العام > إدخالات دفتر اليومية > دفاتر اليومية العامة‬**.
18. انقر فوق **جديد**.
19. في الحقل **الاسم** أدخل قيمة أو حددها.
20. في القائمة، قم بالبحث عن السجل المطلوب وحدده.
21. في القائمة، انقر فوق الارتباط في الصف المحدد.
22. في حقل **الوصف**، اكتب قيمة.
23. في **جزء الإجراءات**، انقر فوق **البنود**.
24. انقر فوق **التحكم في دفتر اليومية‬‬**، في **جزء الإجراءات**.
25. انقر فوق **استرجاع دفتر اليومية**.
26. في الحقل **إلى تاريخ**، أدخل تاريخًا. يعمل الخيار **إلى ‏‏تاريخ** بمثابة تاريخ الانقطاع لبنود الإيصال الدورية. استنادًا إلى إعداد التكرار، قد يتم تضمين "آخر تاريخ" و"إلى تاريخ" على البند نفسه أكثر من مرة في دفتر اليومية الناتج. يتم تحديث التاريخ تلقائيًا استنادًا إلى تاريخ الجلسة في المرة الأخيرة التي تم فيها تحويل البند الدوري إلى دفتر يومية. 
27. في الحقل **رقم دفتر اليومية الدوري** ، أدخل قيمة أو حددها.
28. في القائمة، انقر فوق الارتباط في الصف المحدد.
29. انقر فوق **موافق**. يمكن الآن مراجعة دفتر يومية الفترة‬ أو الموافقة عليه أو ترحيله تبعًا للمتطلبات والإعداد.   


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
