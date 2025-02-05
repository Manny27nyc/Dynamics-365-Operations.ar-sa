---
title: تكوين بنيات حساب
description: توفر هذه المقالة معلومات عن بنيات الحساب والأبعاد المالية.
author: aprilolson
ms.date: 07/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerEliminationRule
audience: Application User
ms.reviewer: twheeloc
ms.custom: 13131
ms.assetid: 08fd46ef-2eb8-4942-985d-40fd757b74a8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0f816f0fc894b902c444a3113abfd48d4146d485
ms.sourcegitcommit: e59990780830ac8e3382fea5df851abe86fbf496
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/13/2022
ms.locfileid: "9141267"
---
# <a name="configure-account-structures"></a>تكوين بنيات حساب

[!include[banner](../includes/banner.md)]

تستخدم بنيات الحساب الحساب الرئيسي والأبعاد المالية لإنشاء مجموعة من القواعد التي تحدد الأمر والقيم المستخدمة عند إدخال رقم الحساب. يمكنك إعداد العديد من بنيات الحساب التي تحتاجها للعمل. يتم تعيين بنيات الحسابات لإعداد دفتر الأستاذ للشركة، وبالتالي يمكن مشاركتها.

عندما يتم إنشاء بنية حساب، يكون أقصى عدد للشرائح هو 11. إذا كنت بحاجة إلى شرائح أكثر من هذا، قم بتقييم إعدادك ومتطلباتك بالكامل، لأنها ستؤثر على تجربة المستخدم. ضع في اعتبارك إذا ما كانت الشريحة محددة في سيناريو إعداد التقرير باستخدام التدرج الهرمي بدلاً من وقت إدخال البيانات أو باستخدام حقل محدد من قبل المستخدم. على سبيل المثال، إذا كنت تريد الإبلاغ عن موقع، لكن يمكنك تقرير الموقع حسب القسم أو مركز التكلفة، لن تكون بحاجة إلى موقع كبُعد مالي. بعد التقييم، إذا قمت بتحديد أنك بحاجة إلى أكثر من 11 شريحة، فإنه يمكنك إضافة شرائح إضافية باستخدام قواعد متقدمة.

تتطلب بنيات الحساب الحساب الرئيسي. لا يتطلب الحساب الرئيسي أن يكون الشريحة الأولى في البنية، ولكنه لا يُحدد بنية الحساب التي يتم استخدامها أثناء إدخال رقم الحساب. بسبب هذا، يمكن أن تكون قيمة حساب رئيسي موجودة في بنية واحدة معينة إلى دفتر الأستاذ حتى لا تتداخل. بعد أن يتم تحديد بنية الحساب، فإنه تتم تصفية قائمة القيم المسموحة لإرشاد المستخدم خلال اختيار قيم الأبعاد الصالحة فقط، مما يعمل على تقليل احتمالية إدخال دفتر اليومية غير الصحيحة.

> [!NOTE] 
> إذا كنت تخطط للميزانية مقابل بُعد مالي، فإنها يجب أن تكون جزءًا من بنية الحساب. إعداد الميزانية لا يستخدم قواعد متقدمة حاليًا.

## <a name="example"></a>مثال
لتوضيح أفضل ممارسة لإعداد بنية حساب، فلنفترض أن شركة تريد تعقب حسابات الميزانية العمومية (100000..399999) في الحساب ومستوى بُعد مالي لوحدة الشركة. بالنسبة لحسابات الإيراد والنفقات (400000..999999)، فإنها تتعقب وحدة أعمال البُعد المالي والقسم ومركز التكلفة. إذا قامت بتنفيذ عملية بيع، فإنها ترغب كذلك في تعقب العميل. باستخدام هذا السيناريو، فقد يُوصى بالحصول على بنيتي حساب معينة إلى دفتر أستاذ الشركة - بنية لحسابات الميزانية العمومية وبنية لحسابات الربح والخسارة. لتحسين تجربة المستخدم والتحقق من صحتها، فإنه ينبغي أن يكون العميل قاعدة متقدمة يتم استخدامها عندما يتم استخدام حساب المبيعات فقط.

**بنية حساب ميزانية عمومية**

|الحساب الرئيسي          | وحدة الأعمال    |
|----------------------|-----------|
|100000..399999 | *;” “|

**بنية حساب الربح والخسارة**

|الحساب الرئيسي          | وحدة أعمال    |قسم          | مركز التكلفة    | &nbsp; |
|----------------------|------------------|--------------------|-----------|---|
|400000..999999 | \*;” “| \*;” “| \*;” “| \*;” “|

**قاعدة متقدمة لإضافة عميل**

المعايير: عندما يكون الحساب الرئيسي بين 400000 و499999، قم بأضف عميل. لا يمكن أن يُترك فارغًا.

|العميل         |
|-----------------|
|* |

في هذا المثال المبسط، يُسمح بكل القيم والفراغات، لذلك فإنه يتم استخدام * و" ".

## <a name="segments-and-allowed-values"></a>المقاطع والقيم المسموح بها
يقدم قسم **الشرائح** و **تفاصيل القيم المسموح بها** شبكة مثل تجربة إدخال القواعد التي سيتم اتباعها عند التحقق من الصحة أثناء النشر. يمكنك الكتابة مباشرة في الخلايا داخل الشبكة أو استيرادها من Excel أو استخدام قسم **تفاصيل القيم المسموح بها** لإرشادك خلالها.

يرشدك القسم **تفاصيل القيم المسموح بها** خلال عملية إنشاء المعايير باستخدام **العوامل** مثل البدء بـ ويكون بين ويتضمن والعديد من العوامل.

[![السماح بالقيم.](./media/account.png)](./media/account.png) 

ستُفترض القيم المسموح بها في صفحة إدخال دفتر يومية أو توزيع محاسبي عندما لا توجد قيم أخرى ممكنة للاختيار وفقًا لإعداد هيكل الحساب.

فيما يلي مثال على **بنية حساب الربح والخسارة**.

|الحساب الرئيسي          | وحدة الأعمال    |قسم          | مركز التكلفة    |
|----------------------|-----------|----------------------|-----------|
|400000..999999 | 002 | 022 | 014 |

عند إدخال دفتر يومية وتحديد حساب في نطاق الربح والخسارة، سيؤدي تحديد وحدة العمل "002" إلى جعل القيم 022 و 014 هي القيمة الافتراضية في عنصر التحكم في الحساب. سيحدث هذا السلوك أيضًا في صفحة التوزيع المحاسبي. 

## <a name="more-than-7-criteria-needed"></a>أكثر من 7 معايير ضرورية

إذا كان لديك أكثر من 7 معايير تحتاج إليها، فإنه يمكنك الاستمرار في إضافتها في السطر التالي. ستُلاحظ عند العمل في القسم **تفاصيل القيم المسموح بها** أن المعايير **+إضافة جديد** لم تعد نشطة بعد الآن بعد أن يتم إدخال المعايير السابعة. وهذا بسبب العديد من العوامل مثل: 
 - عرض العمود 
 - كيف يتم تخزين البيانات 
 - أداء عنصر تحكم **تفاصيل القيم المسموح بها**
 - الاستخدام  
 
للاستمرار في إضافة معايير إضافية، انقر فوق **التكرار في الشريحة** و **قسم القيم المسموح بها**. وسينسخ هذا المعايير إلى سطر جديد. يمكنك حينها الكتابة فوق القسم **تفاصيل القيم المسموح بها** أو تعديله.

## <a name="best-practices"></a>أفضل الممارسات
عند إعداد بنيات حسابك، توجد بعض أفضل الممارسات التي يمكنك اتباعها. وعلى الرغم من ذلك، يكون هذا إرشاد فقط، لذلك ينبغي وضع مناقشة كاملة عن شركتك وخطة النمو وخطة الصيانة في الاعتبار كجزء من تلك المناقشة.

- قم بعمل حساب رئيسي أولاً أو قريب من بنية الحساب قدر المستطاع، لذلك، يحصل المستخدمون على أفضل تجربة إرشادية يستطيعون الوصول إليها أثناء إدخال الحساب.
  
  - تحقق من أن أي حلول جهة خارجية تنوي استخدام حساب الدعم الرئيسي في المركز الأول.

- قم بإعادة استخدام بنيات الحساب قدر الإمكان لتقليل الصيانة عبر الكيانات القانونية.

- بالنسبة إلى الاختلافات بين الكيانات القانونية، ضع في اعتبارك استخدام القواعد المتقدمة حتى يمكن إعادة استخدام بنيات الحساب.

- عند تعريف القيم المسموحة، استخدم النطاقات وأحرف البدل قدر المستطاع. وهذا لا يسمح لك بالنمو والتغيير دون صيانة فقط، ولكن يقوم النظام بالتنفيذ بشكل أكثر مثالية باستخدام هذا التكوين أيضًا.

- لا تقتصر على وضع علامة نجمية لكل شريحة في بنية الحساب، بل اعتمد على القواعد المتقدمة فقط. قد يصعب إدارة هذا وغالبًا ما يؤدي إلى خطأ المستخدم أثناء الصيانة التي يمكن أن تجعل النظام غير قادر على النشر.

## <a name="account-structure-activation"></a>تنشيط بنية الحساب
عندما تكون راضيًا بالإعداد الجديد أو بالتغيير إلى بنية الحساب، فإنه يجب تنشيطه. إذا تم تعيين بنية حساب إلى دفتر الأستاذ، يمكن أن يكون هذا التنشيط عملية طويلة المدة، لأن كل المعاملات غير المنشورة في النظام يجب مزامنتها للبنية الجديدة. لن تتأثر المعاملات المنشورة بتغييرات بنية الحساب.

للحصول على المزيد من المعلومات، راجع [خطط دليل الحسابات الخاص بك‬‏‫](plan-chart-of-accounts.md)، و [الأبعاد المالية](financial-dimensions.md) و [‬‏‫إدخال مجموعات الحسابات والأبعاد (عنصر تحكم في الإدخال المقسم)](enter-account-dimension-combinations-segmented-entry-control.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
