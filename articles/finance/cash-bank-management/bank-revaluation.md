---
title: إعادة تقييم العملة الأجنبية في البنوك
description: توفر هذه المقالة نظرة عامة على عملية إعادة تقييم العملة الأجنبية في البنوك. وهو يتضمن معلومات حول الإعداد، وتشغيل العملية، وحساب العملية، وعكس حركات إعادة التقييم.
author: angelad116
ms.date: 05/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankCurrencyRevalHistory
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2019-03-08
ms.dyn365.ops.version: 10
ms.openlocfilehash: 8efec304e745332c332030b33363403869870532
ms.sourcegitcommit: 0b7a034e644f4d93fe55c7baca5a3f89dbe56898
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151420"
---
# <a name="bank-foreign-currency-revaluation"></a>إعادة تقييم العملة الأجنبية في البنوك

[!include [banner](../includes/banner.md)]


توفر هذه المقالة نظرة عامة على عملية إعادة تقييم العملة الأجنبية في البنوك. ويشرح كيفية إعداد العملية وتشغيلها، ويوفر معلومات حول حساب العملية. ويشرح أيضًا كيفية عكس حركات إعادة التقييم، إذا كان عكسها مطلوبًا.

كجزء من نهاية الفترة، تتطلب القواعد المحاسبية إعادة تقييم أرصدة الحسابات البنكية بالعملات الأجنبية باستخدام أنواع مختلفة من أسعار الصرف (الحالية والقديمة وبالمتوسط، وغير ذلك). يمكن استخدام ميزة إعادة تقييم العملة الأجنبية في البنوك لإعادة تقييم حساب بنكي واحد أو أكثر. وتعتبر أيضًا هذه الميزة ميزة عمومية. وبالتالي، يمكنك، من صفحة واحدة، إعادة تقييم البنوك عبر كافة الكيانات القانونية التي يمكنك الوصول إليها.

> [!NOTE]
> عندما تقوم بتشغيل عملية إعادة التقييم، سيُعاد تقييم الرصيد في كل حساب بنكي تم ترحيله بعملة أجنبية. يقوم النظام بإنشاء حركات الأرباح أو الخسائر غير المحققة التي تنشأ أثناء عملية إعادة التقييم. يجوز إنشاء حركتين، واحدة لعملة المحاسبة والثانية لعملة التقارير، إذا كانت عملة التقارير ذات صلة. وسيتم ترحيل كل إدخال محاسبي إلى الخسائر أو الأرباح غير المحققة والحساب الرئيسي الذي يعُاد تقييمه.

## <a name="prepare-to-run-foreign-currency-revaluation"></a>الإعداد لتشغيل إعادة تقييم العملة الأجنبية

قبل تشغيل عملية عملية التقييم، يجب تنفيذ الخطوة التالية.

- في صفحة **دفتر الأستاذ**، حدد نوع سعر الصرف. إذا لم يتم تحديد نوع سعر الصرف على الحساب الرئيسي، فسيتم استخدام نوع سعر الصرف هذا أثناء إعادة تقييم العملة الأجنبية.
- وفي صفحة **دفتر الأستاذ**، حدد حسابات الربح المحقق والخسارة المحققة والربح غير المحقق والخسارة غير المحققة لإعادة تقييم العملة. تُستخدم حسابات الربح المحقق والخسارة المحققة عند تسوية حركات الحسابات الدائنة والحسابات المدينة. ويتم استخدام حسابات الأرباح غير المحققة والخسارة غير المحققة لإعادة تقييم الحركات المفتوحة والحسابات الرئيسية لدفتر الأستاذ العام.
- في صفحة **حسابات إعادة تقييم العملة**، يمكنك تحديد حسابات مختلفة لإعادة تقييم العملة لكل عملة وشركة. وإذا لم يتم تحديد أي حسابات، فإنه يتم استخدام الحسابات من صفحة **دفتر الأستاذ**.

## <a name="enable-foreign-currency-revaluation"></a>تمكين إعادة تقييم العملة الأجنبية

يجب تشغيل ميزة إعادة تقييم العملة الأجنبية في البنوك قبل أن تتمكن من معالجة عمليات إعادة تقييم العملة الأجنبية.

1. انتقل إلى **إدارة النقد والبنوك‬‏‫ \> الإعداد \> محددات إدارة النقد والبنوك**.
2. على علامة التبويب **عام**، تحت **إعادة تقييم عملة أجنبية**، عيّن الخيار **تمكين إعادة تقييم البنوك** إلى **نعم** لتشغيل الميزة للكيان القانوني الحالي. 
3. على علامة التبويب **التسلسلات الرقمية**، أضف تسلسلاً رقميًا لإعادة تقييم العملة الأجنبية.
4. حدّث المستعرض لرؤية **إعادة تقييم عملة أجنبية** في قسم **المهام الدورية** من صفحة المنطقة.

يجب تشغيل الميزة لكل كيان قانوني سوف يستخدم إعادة تقييم العملة الأجنبية. إذا كنت تؤدي دور مسؤول النظام أو مدير الميزات، فيمكنك استبعاد هذه الخطوة عن طريق تمكين الميزة المسماة **تمكين إعادة تقييم البنوك من دون معلمة** في مساحة العمل **إدارة الميزات**.

> [!NOTE]
> إذا كان الكيان القانوني يستخدم رمز بلد/منطقة روسية أو بولندية أو هنغارية، فيمكنك القيام بعملية إعادة تقييم العملة الأجنبية. لن تتمكن من استخدام إعادة تقييم العملة الأجنبية التي تستخدمها بلدان أو مناطق أخرى.

## <a name="process-foreign-currency-revaluation"></a>معالجة إعادة تقييم عملة أجنبية

بعد اكتمال عملية الإعداد، استخدم الصفحة **إعادة تقييم عملة أجنبية** في "إدارة النقد والبنوك" لإعادة تقييم الأرصدة الخاصة بحساب بنكي واحد أو أكثر عبر جميع الكيانات القانونية. يمكنك تشغيل العملية في الوقت الحقيقي أو يمكنك جدولتها لتشغيلها باستخدام دُفعة.

تعرض الصفحة **إعادة تقييم عملة أجنبية** محفوظات كل عملية إعادة تقييم. هي تعرض الوقت الذي تم فيه تشغيل العملية، والمعايير التي تم تعريفها، وتوفر ارتباطًا إلى الإيصال الذي تم إنشاؤه لعملية إعادة التقييم. وتعرض أيضًا ما إذا تم عكس عملية إعادة تقييم سابقة. لتشغيل عملية إعادة التقييم، حدد **إعادة تقييم عملة أجنبية** في جزء الإجراءات لفتح مربع الحوار **البنك - إعادة تقييم العملة الأجنبية**.

يحدد الحقل **تاريخ‏‎ إعادة التقييم** تاريخ إيقاف حساب رصيد العملات الأجنبية التي سيتم تقييمها. ويُعاد تقييم مجموع كافة الحركات البنكية التي حدثت حتى هذا التاريخ.

يحدد الحقل **تاريخ سعر الصرف** تاريخ سعر الصرف الذي سيتم استخدامه لإعادة تقييم أرصدة العملات. على سبيل المثال، يمكنك إعادة تقييم الأرصدة اعتبارًا من 31 يناير، ولكن باستخدام سعر الصرف الذي تم تحديده للأول من فبراير.

يمكن تشغيل عملية إعادة التقييم لكيان قانوني واحد أو أكثر. تُظهر عملية البحث فقط الكيانات القانونية التي يمكنك الوصول إليها. حدد الكيانات القانونية التي تريد أن تحدد لها الحسابات البنكية المؤهلة لإعادة تقييم العملة الأجنبية. ستظهر جميع الحسابات البنكية لهذه الكيانات القانونية في الشبكة.

عيّن الخيار **معاينة قبل الترحيل** إلى **نعم** لمراجعة نتائج إعادة التقييم قبل ترحيلها. تتضمن عملية إعادة تقييم العملة الأجنبية معاينة لا يمكن ترحيلها. ولست بحاجة إلى إعادة تشغيل عملية إعادة التقييم مرة أخرى. يمكن تصدير النتائج في المعاينة إلى Microsoft Excel للاحتفاظ بمحفوظات تتعلق بكيفية حساب المبالغ. لا يمكنك استخدام المعالجة الدُفعية إذا كنت تريد معاينة نتائج إعادة التقييم.

حدد **موافق** لمعالجة إعادة تقييم العملة الأجنبية. يتم إنشاء سجل لتعقب محفوظات كل تشغيل. ويتم إنشاء سجل منفصل لكل كيان قانوني وطبقة ترحيل.

## <a name="calculate-unrealized-gainloss"></a>حساب الربح/الخسارة غير المحققة

في "إدارة النقد والبنوك"، تعتبر عملة البنك على أنها العملة الأساسية ولا يُعاد تقييمها. يُعاد تقييم رصيد الحساب البنكي بعملة المحاسبة باستخدام أسعار الصرف بين عملة البنك وعملة المحاسبة في **تاريخ سعر الصرف**. ويُعاد أيضًا تقييم رصيد الحساب البنكي بعملة التقارير باستخدام أسعار الصرف بين عملة البنك وعملة التقارير في **تاريخ سعر الصرف**.

يتم إنشاء حركة للفرق بين رصيد الحساب البنكي والرصيد الجديد الذي يتم حسابه لعملة المحاسبة. ويتم إنشاء حركة أخرى للفرق بين رصيد الحساب البنكي والرصيد الجديد الذي يتم حسابه لعملة التقارير. توضع علامة على إدخالات هذه الحركات على أنها إدخالات تمت تسويتها. 

لا يتم إنشاء أي إدخال لعملة المحاسبة إذا تطابقت عملة البنك مع عملة المحاسبة. وبطريقة ممثلة، لا يتم إنشاء أي إدخال لعملة التقارير إذا تطابقت عملة البنك مع عملة التقارير.

ويتم أيضًا تقسيم حركة إعادة تقييم العملة الأجنبية عبر الأبعاد التي يتم العثور عليها في الحركات البنكية. يستند التقسيم إلى الرصيد لكل بُعد. على سبيل المثال، الرصيد البنكي الإجمالي هو 10.000، ولكن رصيد وحدة العمل 001 هو 4000، في حين أن رصيد وحدة العمل 002 هو 6000. في هذه الحالة، يتم ترحيل 40 بالمئة من مبلغ إعادة التقييم إلى حساب إعادة التقييم الذي يتضمن وحدة العمل 001، ويتم ترحيل 60 بالمئة إلى حساب إعادة التقييم الذي يتضمن وحدة العمل 002. إذا لم تتضمن بنية الحساب أي وحدة عمل، فسيتم ترحيل المبلغ بالكامل إلى حساب إعادة التقييم.

## <a name="reverse-foreign-currency-revaluation"></a>عكس إعادة تقييم عملة أجنبية

إذا تعيّن عليك عكس حركة إعادة التقييم، فحدد الزر **عكس الحركة** في جزء الإجراءات في صفحة **إعادة تقييم عملة أجنبية**. سيتم إنشاء سجل تاريخي جديد لعملية إعادة تقييم العملة الأجنبية للمحافظة على سجل المراجعة‬ التاريخي عند حدوث إعادة التقييم أو عكسها.

لعكس عمليات إعادة تقييم متعددة، يجب عكس إعادة التقييم الأحدث أولاً. ثم تابع عكس عمليات إعادة التقييم الأقدم حسب تاريخها. بعد ذلك، يمكنك معالجة عمليات إعادة تقييم جديدة للفترات الزمنية التي قمت بعكسها.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
