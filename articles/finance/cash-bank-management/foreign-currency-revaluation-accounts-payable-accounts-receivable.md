---
title: إعادة تقييم العملة للحسابات الدائنة والحسابات المدينة
description: توفر هذه المقالة معلومات حول عملية إعادة تقييم العملة الأجنبية التي تقوم بتشغيلها لتحديث قيمة الحركات المفتوحة في الحسابات الدائنة والحسابات المدينة.
author: angelad116
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustExchRateAdjustment, VendExchRateAdjustment
audience: Application User
ms.reviewer: kfend
ms.custom: 14211
ms.assetid: defb1ea5-1f3e-4859-87d8-3f9954d3f388
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4ffa4e1a02c84eda5f6710cb9049eab06955fac0
ms.sourcegitcommit: 0b7a034e644f4d93fe55c7baca5a3f89dbe56898
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151809"
---
# <a name="currency-revaluation-for-accounts-payable-and-accounts-receivable"></a>إعادة تقييم العملة للحسابات الدائنة والحسابات المدينة

[!include [banner](../includes/banner.md)]

بإمكان التقلبات في أسعار الصرف أن تؤدي إلى حدوث اختلافات في القيمة النظرية (القيمة الدفترية) للحركات المفتوحة بالعملات الأجنبية بمرور الوقت. توفر هذه المقالة معلومات حول عملية إعادة تقييم العملة الأجنبية التي تقوم بتشغيلها لتحديث قيمة الحركات المفتوحة في الحسابات الدائنة والحسابات المدينة. 

تختلف القيمة النظرية (القيمة الدفترية) الخاصة بحركات مفتوحة بالعملات الأجنبية من وقتٍ لآخر بسبب التغييرات في سعر الصرف. ولتحديث قيمة حركات مفتوحة في الحسابات الدائنة والحسابات المدينة، قم بتشغيل عملية إعادة تقييم العملة الأجنبية. ويمكن تشغيل إعادة تقييم العملة الأجنبية للحسابات الدائنة والحسابات المدينة. وتستخدم العملية سعر صرف جديدًا لإعادة تقييم مبالغ مفتوحة، أو لم مبالغ لم تتم تسويتها، في تاريخ محدد. ‏‫وستؤدي الاختلافات بين المبالغ الأصلية والمبالغ التي تمت إعادة تقييمها إلى ظهور ربح غير محقق أو خسارة لكل حركة مفتوحة. ويتم فيما بعد تحديث دفاتر الأستاذ الفرعية للحسابات الدائنة والحسابات المدينة لعكس الخسائر أو الأرباح غير المحققة، ويتم ترحيل إدخال محاسبة إلى دفتر الأستاذ العام.‬

## <a name="simulate-a-foreign-currency-revaluation"></a>محاكاة إعادة تقييم العملة الأجنبية
وقبل إعادة تقييم مبالغ العملات الأجنبية في الحركات المفتوحة، يمكنك تشغيل تقرير محاكاة إعادة تقييم العملة الأجنبية لنفس التاريخ والطريقة. ولتشغيل تقرير المحاكاة، في صفحة **إعادة تقييم العملة الأجنبية**، انقر فوق الزر **محاكاة**. ويوفر التقرير معاينة لمبلغ الخسارة أو الأرباح غير المحققة، استناداً إلى المعلمات التي تم تحديدها للمحاكاة.

## <a name="process-a-foreign-currency-revaluation"></a>معالجة إعادة تقييم عملة أجنبية
‏‫استخدم صفحة **إعادة تقييم العملة الأجنبية** ضمن **المهام الدورية** لإعادة تقييم الحركات المفتوحة. ويمكنك تشغيل العملية في الوقت الحقيقي أو جدولتها لتشغيلها باستخدام دُفعة. وعندما تقوم بتحديد إعدادات عملية إعادة التقييم، تأكد من التحقق من ما إذا كنت تريد طباعة تقرير بالنتائج. ولا يمكن إعادة طباعة تقرير إعادة التقييم بعد اكتمال العملية.‬ وفي حالة إنشاء تقرير إعادة تقييم العملات الأجنبية، سوف تظهر مختلف الأرصدة على مستوى العميل/المورد ومستوى العملة:

-   أرصدة العملاء أو الموردين التي تشتمل على حركات العملة الأجنبية والتي تمت إعادة تقييمها. وتم توضيح الأرصدة التالية:
    -   مجموع الرصيد الأصلي بالعملة الأجنبية.
    -   إجمالي مبلغ العملة الأجنبية ‬بعملة المحاسبة، اعتبارًا من عملية إعادة التقييم السابقة.
    -   إجمالي مبلغ العملة الأجنبية ‬بعملة المحاسبة، اعتبارًا من عملية إعادة التقييم الحالية.
    -   الفرق بين عمليتي إعادة التقييم السابقة والحالية. هذا الفرق عبارة عن الخسائر أو الأرباح غير المحققة الإضافية.
-   إجمالي الأرباح غير المحققة أو الخسارة لكل عملة.

يتم حفظ سجل في كل مرة تقوم فيها بتشغيل إعادة تقييم عمله أجنبية. من السجل في صفحة **تقييم العملة الأجنبية**، حدد **الحركات** لعرض قائمة مفصلة من الحركات التي تم إنشاؤها بسبب إعادة التقييم. ‏‫وتمثل كل حركة إيصال الحركة المفتوحة التي تمت إعادة تقييمها. وإذا تمت إعادة تقييم حركة مفتوحة أكثر من مرة، فسترى اثنين من السجلات التي تستخدم نفس الإيصال. وسيكون أحدهما لإلغاء الخسائر أو الأرباح غير المحققة، وسيكون السجل الآخر للخسائر أو الأرباح غير المحققة الجديدة.‬ ولتشغيل عملية إعادة التقييم، انقر فوق الزر **إعادة تقييم العملة الأجنبية**. حدد الإعدادات المناسبة للمعلمات التالية:

-   **الطريقة** – الطريقة التي تم استخدامها في وظيفة إعادة تقييم العملة الأجنبية المحددة:
    -   **قياسي** – يتم ترحيل مهام إعادة تقييم العملة الأجنبية بغض النظر عما إذا كانت النتيجة ربحًا أو خسارة.
    -   **الحد الأدنى** – يتم ترحيل مهام إعادة تقييم العملة الأجنبية فقط إذا كانت النتيجة خسارة.
    -   **تاريخ الفاتورة** – تستخدم مهام إعادة تقييم العملة الأجنبية سعر صرف الحركات، الذي يتم إعادة تقييمه إلى قيمته الأصلية بعملة المحاسبة. يتم إلغاء تأثير أي عملية إعادة تقييم سابقة للعملة الأجنبية.
-   **التاريخ المحدد** – التاريخ الذي يُعثر فيه على كل الحركات التي قمت بفتح مبالغ لها (لم تقم بالتسوية) في ذلك التاريخ. يُعاد تقييم مبالغ العملات الأجنبية باستخدام أسعار الصرف التي تم إدخالها في صفحة **أسعار صرف العملة الأجنبية** للتاريخ المحدد. وعندما يُعاد تقييم مبالغ العملات الأجنبية في تاريخ محدد، يصبح هذا التاريخ هو آخر تاريخ لإعادة تقييم العملة الأجنبية للحركات التي تم تعديلها. وإذا أجريت إعادة تقييم عملة أجنبية لتاريخ اعتباري يسبق التاريخ الأخير لإعادة تقييم العملة الأجنبية في الحركات التي تمت تسويتها بالفعل، لا تتم تسوية الحركات المفتوحة في التاريخ الاعتباري السابق وإنما تتم تسوية الحركات التي لها تاريخ أحدث لإعادة تقييم العملة الأجنبية بواسطة الوظيفة الدورية.
-   **تاريخ السعر** – التاريخ الذي يحدد سعر الصرف الذي يتم استخدامه في حركة إعادة تقييم العملة الأجنبية.
-   **استخدام ملف تعريف الترحيل من** – ملف تعريف الترحيل المستخدم لإدخال الحساب الأساسي الافتراضي للحسابات المدينة أو الحسابات الدائنة للقيود المحاسبية لحركات إعادة تقييم العملة الأجنبية:
    -   **الترحيل** – يتم استخدام ملف تعريف الترحيل الخاص بحركة العميل.
    -   **تحديد** – أدخل ملف تعريف الترحيل في حقل **ملف تعريف الترحيل**.
-   **ملف تعريف الترحيل** – في حالة تحديد **تحديد** في حقل **استخدام ملف تعريف الترحيل من**، يحدد ملف تعريف الترحيل الذي تقوم بإدخاله في الحقل ملف تعريف الترحيل الخاص بحركات إعادة تقييم العملة الأجنبية.
-   **الأبعاد المالية** – الأبعاد المالية التي يتم ترحيلها في الإدخالات المحاسبية لحركات إعادة تقييم العملة الأجنبية. لا يتم التحقق من صحة الأبعاد المالية في مقابل قواعد بنية الحساب. قد لا تكون بنية الحساب التي كانت في الوقت الذي تم فيه ترحيل الفواتير هي نفسها القواعد التي كانت موجودة في المكان الذي تم فيه إكمال إعادة التقييم. لا يوجد خيار لتحديد أبعاد مالية معينة في عملية إعادة التقييم، لذلك يتم تخطي التحقق من صحة بنية الحساب.  
    -   **لا شيء** – لا يتم ترحيل أي أبعاد مالية. إذا كان لديك بعد مالي مطلوب في بنية الحساب الخاص بك، لا تزال تعمل عملية إعادة التقييم وتقوم بإنشاء الإدخالات المحاسبية التي لا تشتمل على أي أبعاد مالية. سوف تتلقى رسالة تحذير أولاً، بحيث يمكنك إلغاء إعادة التقييم.
    -   **الجدول** – يتم ترحيل الأبعاد المالية لحساب العميل أو حساب المورد في حركات إعادة تقييم العملة الأجنبية.
    -   **الترحيل** – يتم ترحيل الأبعاد المالية للحركة التي تتم إعادة تقييمها في حركات إعادة تقييم العملة الأجنبية. بشكل افتراضي، سيتم استخدام الأبعاد المالية من حساب دفتر أستاذ الحسابات المدينة/الحسابات الدائنة للحركة الأصلية للحساب الرئيسي للحسابات المدينة/الحسابات الدائنة لحركة إعادة التقييم، وسيتم استخدام الأبعاد المالية من حساب دفتر أستاذ مصروفات/أصول/إيرادات الحركة الأصلية للحساب الرئيسي للخسائر/الأرباح غير المحققة لحركة إعادة التقييم.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
