---
title: إعداد تحليل قيم قرب المدة والتكرار والنقد (RFM) للعملاء
description: يشرح هذا الموضوع كيفية إعداد تحليل قيم قرب المدة والتكرار والنقد (RFM) للعملاء.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: MCRRFMDefinition
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 78943
ms.assetid: 8ff9aac3-5ada-4150-85fd-18901c926d53
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: c7cb79fa82b579bee01e51cb635597cc5f711a98
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/01/2020
ms.locfileid: "3021495"
---
# <a name="set-up-recency-frequency-and-monetary-rfm-analysis"></a>إعداد تحليل قيم قرب المدة والتكرار والنقد (RFM) للعملاء

[!include [banner](includes/banner.md)]

يشرح هذا الموضوع كيفية إعداد تحليل قيم قرب المدة والتكرار والنقد (RFM) للعملاء.

تحليل الحداثة والتكرار والقيم النقدية (RFM) هو أداة تسويق تستخدمها مؤسستك لتقييم البيانات التي يتم إنشاؤها بواسطة مشتريات العميل. بعد إعداد تحليل RFM، يتم تعيين مجموع RFM المحسوب للعملاء عند إجراء عمليات الشراء. يمكن أن يكون مجموع RFM تصنيف من ثلاثة أرقام أو عدد تجميع، اعتمادًا على كيفية تكوين المؤسسة لتحليل RFM. إليك كيفية عمل التصنيف إذا كانت مؤسستك تستخدم تصنيفًا مكوناً من ثلاثة أرقام للنتيجة:

- الرقم الأول هو تصنيف حداثة العميل، ويقصد به الطريقة التي أجرى بها العميل مؤخرًا عملية شراء من مؤسستك.
- الرقم الثاني هو تصنيف تكرار العميل، ويقصد به عدد مرات قيام العميل بإجراء مشتريات من مؤسستك.
- والرقم الثالث هو تصنيف القيمة النقدية للعميل، ويقصد به المبلغ الذي ينفقه العميل عندما يقوم بإجراء مشتريات من مؤسستك.

على سبيل المثال، قامت مؤسستك بتعيين التصنيفات على مقياس من 1 إلى 5، حيث يمثل 5 أعلى تصنيف. وفي هذه حالة، يخبرك تصنيف العميل 535 بالمعلومات التالية فيما يتعلق بالعميل:

- **تصنيف الحداثة 5** – أجرى العميل عملية شراء مؤخرًا.
- **تصنيف التكرار 3** – يشتري العميل منتجات من المؤسسة الخاصة بك بمعدل تكرار متوسط.
- **تصنيف القيمة النقدية 5** – عندما يقوم العميل بشراء، وينفق مبلغًا كبيرًا من المال.

إذا كانت مؤسستك تستخدم رقمًا مجمعًا للمصدر، فإنه تتم إضافة التصنيفات الفردية معًا. على سبيل المثال نفسه، العميل يمتلك تصنيف 13 (5 + 3 + 5).

## <a name="set-up-rfm-analysis-for-the-customers-in-your-organization"></a>إعداد تحليل RFM للعملاء في مؤسستك

1. انتقل إلى **مركز الاتصال** \> **دوري** \> **تحليل RFM**.
2. في صفحة **تحليل RFM**، حدد **جديد**. في الحقل **تعريف RFM**، أدخل اسمًا لتعريف RFM. على سبيل المثال، يمكن استدعاء تعريف RFM-A.
3. أدخل تاريخ البداية وتاريخ النهاية لتعريف RFM هذا.
4. في علامة التبويب **عام**، قم بما يلي:

    - إذا كان من الضروري لكل قسم مجموع نقاط RFM أن يحتوي على عدد مساوٍ من العملاء، حدد خانة الاختيار **‏‫توزيع متعادل** .
    - حدد خانة الاختيار **‏‫إضافة درجات‬** لتجميع مجموع النقاط الثلاثة. على سبيل المثال، يعطي ذلك الأمر للعميل مجموع نقاط RFM من 13 بدلاً من 535.
    - حدد خانة الاختيار **حفظ السجل** لطلب النظام بحفظ البيانات الإحصائية للعملاء بحيث يمكن استخدام البيانات لحساب مجموع نقاط RFM.

5. في علامة التبويب السريعة **الحداثة**، قم بما يلي:

    - بالحقل **أقسام‬**، أدخل عدد الأقسام أو المجموعات التي سيتم استخدامها لحساب مجموع نقاط مدى قرب عمليات شراء العملاء. على سبيل المثال، إذا كان لديك 100 عميل، يعني قسم مكون من 5 عملاء أن هناك 20 عميلاً لكل مجموع نقاط. ‏‫يحصل العملاء العشرون الذين أجروا عمليات شراء مؤخرًا على مجموع نقاط مكون من 5. ويحصل العملاء العشرون التاليون على مجموع نقاط مكون من 4، وهكذا.‬ إذا كان لديك 50 عميلاً، يحصل 10 عملاء منهم على مجموع نقاط مكون من 5 لمدى قرب عملية الشراء، ويحصل 10 آخرين على مجموع نقاط مكون من 4 لمدى قرب عملية الشراء، وهكذا.
    - في الحقل **الأولوية‬**، حدد مقدار الوزن المُعطى لمعلمة مدى القرب فيما يتعلق بمعلمات أخرى عند حساب مجموع نقاط RFM لعميل. على سبيل المثال، قد تضع قيمة لمجموع نقاط مدى القرب أكبر من مجموع نقاط المبلغ النقدي.
    - في الحقل **‏‫المضاعف‬**، أدخل القيمة التي تريد ضرب مجموع نقاط مدى القرب بها. إذا لم تقم بإدخال قيمة، لن يتم ضرب مجموع النقاط.
    - في الحقل **الفترة**، حدد الفترة الزمنية التي يتم حساب مجموع نقاط مدى القرب بها. على سبيل المثال، حسب الأسبوع أو الشهر.

6. في علامة التبويب السريعة **التكرار**، قم بما يلي:

    - بالحقل **أقسام‬**، أدخل عدد الأقسام أو المجموعات التي سيتم استخدامها لحساب مجموع نقاط تكرار عمليات شراء العملاء.‬
    - في الحقل **الأولوية‬**، حدد مقدار الوزن المُعطى لمعلمة التكرار فيما يتعلق بمعلمات أخرى عند حساب مجموع نقاط RFM لعميل.
    - في الحقل **‏‫المضاعف‬**، أدخل القيمة التي تريد ضرب مجموع نقاط التكرار بها.‬ إذا لم تقم بإدخال قيمة، لن يتم ضرب مجموع النقاط.

7. في علامة التبويب السريعة **‏‫مبلغ نقدي‬**، قم بما يلي:

    - بالحقل **أقسام‬**، أدخل عدد الأقسام أو المجموعات التي سيتم استخدامها لحساب مجموع نقاط المبلغ النقدي لعمليات شراء العملاء.‬
    - في الحقل **الأولوية‬**، حدد مقدار الوزن المُعطى لمعلمة المبلغ النقدي فيما يتعلق بمعلمات أخرى عند حساب مجموع نقاط RFM لعميل.
    - في الحقل **‏‫المضاعف‬**، أدخل القيمة التي تريد ضرب مجموع نقاط المبلغ النقدي بها.‬‬ إذا لم تقم بإدخال قيمة، لن يتم ضرب مجموع النقاط.
    - في الحقل **إجمالي/صافي‬** حدد ما إذا كان يجب حساب مجموع نقاط المبلغ النقدي للعميل باستخدام الإجمالي أو صافي مبلغ الفاتورة.
    - إذا كان يجب طرح مبالغ مرتجعات العميل من حساب إجمالي الفاتورة للعميل، فحدد خانة الاختيار **‏‫عائدات الخصم‬**.

## <a name="view-a-customers-rfm-score"></a>عرض نقاط RFM للعميل

استخدم هذا الإجراء لعرض نقاط RFM للعميل.

1. انتقل إلى **مركز الاتصال** \> **دفاتر اليومية** \> **خدمة العملاء**.
2. في صفحة **خدمة العملاء**، ومن جزء **خدمة العملاء**، في حقول البحث، حدد نوع الكلمة الأساسية للبحث عن وإدخال نص البحث.
3. حدد **بحث**.
4. على صفحة **البحث عن عميل**، حدد سجل العميل الذي تريده، ثم انقر فوق **حدد عميل**.

يتم عرض نقاط RFM في مجموعة **سجل الأمر** على الجانب الأيمن من صفحة **خدمة العملاء**.

## <a name="view-or-clear-the-history-of-an-rfm-analysis-record"></a>عرض أو مسح محفوظات سجل تحليل RFM

استخدم هذا الإجراء لعرض أو مسح محفوظات سجل تحليل RFM.

1. انتقل إلى **مركز الاتصال** \> **دوري** \> **تحليل RFM**.
2. في صفحة **تحليل RFM**، حدد السجل الذي ترغب في عرضه.
3. لعرض محفوظات السجل، حدد علامة التبويب السريعة **المحفوظات‬**.
4. لمسح محفوظات السجل، حدد  **‏‫مسح المحفوظات‬**.