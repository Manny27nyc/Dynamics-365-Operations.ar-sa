---
title: الأبعاد المالية
description: يصف هذا الموضوع مختلف أنواع الأبعاد المالية وكيفية إعدادها.
author: aprilolson
manager: AnnBe
ms.date: 01/03/2019
ms.topic: article
ems.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionDetails, DimensionValueDetails, SysTranslationDetail
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 25871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 0715d3e4e4cb167c55d9c7d98cdf599187bf3b43
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176186"
---
# <a name="financial-dimensions"></a>الأبعاد المالية

[!include [banner](../includes/banner.md)]

يصف هذا الموضوع مختلف أنواع الأبعاد المالية وكيفية إعدادها.

استخدم صفحة **الأبعاد المالية** لإنشاء الأبعاد المالية التي تستطيع استخدامها كشرائح حساب لمخططات الحسابات. هناك نوعان من الأبعاد المالية: والأبعاد المخصصة والأبعاد المدعومة من الكيان. تتم مشاركة الأبعاد المخصصة عبر الكيانات القانونية، ويتم إدخال القيم والاحتفاظ بها من قِبل المستخدمين. بالنسبة إلى الأبعاد المدعومة من الكيان، يتم تحديد القيم في مكان آخر في النظام، مثل في العملاء أو كيانات المتاجر. وتتم مشاركة بعض الأبعاد المدعومة من الكيان عبر الكيانات القانونية، في حين تكون لأبعاد الأخرى المدعومة من الكيان خاصة بالشركة.

بعد إنشاء الأبعاد المالية، استخدم صفحة **قيم الأبعاد المالية** لتعيين خصائص إضافية لكل بُعد مالي.

يمكنك استخدام الأبعاد المالية لتمثيل الكيانات القانونية. لست بحاجة إلى إنشاء الكيانات القانونية في Dynamics 365 Finance. ومع ذلك، لم يتم تصميم الأبعاد المالية لمعالجة المتطلبات التشغيلية أو متطلبات الأعمال الخاصة بالكيانات القانونية. تم تصميم وظيفة المحاسبة بين الوحدات في Finance لمعالجة المدخلات المحاسبية التي تم إنشاؤها بواسطة كل حركة.

قبل إعداد الأبعاد المالية ككيانات قانونية، قم بتقييم العمليات التجارية في المجالات التالية لتحديد إذا كان هذا الإعداد سيصلح لمؤسستك:

- المخزون
- المبيعات والمشتريات بين الأبعاد المالية والكيانات القانونية
- حساب ضريبة المبيعات وإعداد التقارير
- التقارير التشغيلية

فيما يلي بعض القيود:

- يمكنك استخدام وظيفة ضريبة المبيعات مع الكيانات القانونية فقط وليس مع الأبعاد المالية.
- لا تتضمن بعض التقارير أبعادًا مالية. وبالتالي، لإعداد تقرير حسب البعد المالي، قد تحتاج إلى تعديل التقارير.

## <a name="custom-dimensions"></a>الأبعاد المخصصة

لإنشاء بُعد مالي محدد من قِبل المستخدم، في حقل **استخدام القيم من**، حدد **بُعد مخصص**.

يمكنك أيضًا تعيين قناع تنسيق لتقييد كمية ونوع المعلومات التي يمكن إدخالها لقيم الأبعاد. تستطيع إدخال الحروف التي تظل كما هي لكل قيمة بُعد مثل الأحرف أو واصلة (-). كما يمكنك إدخال علامات الأرقام (\#) وعلامات العطف (&) كعناصر نائبة للأحرف التي ستتغير كلما يتم إنشاء قيمة بُعد. استخدم علامة الأرقام (\#) كعنصر نائب لرقم وعلامة العطف (&) كعنصر نائب لحرف. يتوفر حقل قناع التنسيق فقط عندما تحدد **بُعد مخصص** في الحقل **استخدام القيم من**.

**مثال**

لتقييد قيمة البُعد بالأحرف "CC" وثلاثة أرقام، أدخل **CC-\#\#\#** كقناع التنسيق.

## <a name="entity-backed-dimensions"></a>الأبعاد المدعومة من الكيان

لإنشاء بُعد مالي مدعوم من كيان، في حقل **استخدام القيم من** حدد كيانًا محددًا من قِبل نظام لتأسيس البُعد المالي عليه. يتم عندئذٍ إنشاء قيم الأبعاد المالية من هذا الكيان. على سبيل المثال، لإنشاء قيم أبعاد للمشاريع، حدد **مشاريع**. يتم عندئذٍ إنشاء قيمة بُعد لكل اسم مشروع. تظهر صفحة **قيم الأبعاد المالية** القيم الخاصة بالكيان. إذا كانت هذه القيم خاصة بالشركة، فستظهر الصفحة الشركة أيضًا.

## <a name="activating-dimensions"></a>تنشيط الأبعاد‬‏‫

عند تنشيط البُعد المالي، يتم تحديث الجدول لكي يتضمن اسم البُعد المالي. يتم إزالة الأبعاد المحذوفة. يمكنك إدخال قيم البُعد قبل أن تقوم بتنشيط بُعد مالي. ومع ذلك، لا يمكن استهلاك البُعد المالي في أي مكان حتى يتم تنشيطه. على سبيل المثال، لا يمكنك إضافة بُعد مالي إلى بنية حساب حتى يتم تنشيط البُعد المالي. عند تحديد **تنشيط**، يتم تحديث كافة الأبعاد وإظهار تغييرات الحالة.

## <a name="translations"></a>الترجمات

في صفحة **ترجمة النص**، يمكنك إدخال نص للبُعد المالي المحدد بلغات متعددة. في صفحة **ترجمة الحساب الرئيسي**، يمكنك إدخال نص للحساب الرئيسي بلغات متعددة. 

## <a name="legal-entity-overrides"></a>تجاوزات الكيان القانوني

لا تصلح كافة الأبعاد لكافة الكيانات القانونية. بالإضافة إلى ذلك، بعض الأبعاد قد تكون ذات صلة فقط بفترة محددة. في هذه الحالات، يمكن استخدام المقطع **تجاوزات الكيان القانوني** لتحديد الشركات التي يجب تعليق البُعد لها، وهو المالك والفترة الزمنية التي يكون البُعد نشطاً خلالها.

## <a name="deleting-financial-dimensions"></a>حذف الأبعاد المالية

للمساعدة في الحفاظ على التكامل المرجعي للبيانات، نادرًا ما يمكن حذف الأبعاد المالية. إذا حاولت حذف بُعد مالي، يتم تقييم المعايير التالية:

- هل تم استخدام البُعد المالي في أي من الحركات المرحلة أو غير المرحلة أو في أي نوع من مجموعة قيم أبعاد؟
- هل البُعد المالي مستخدم في أي بنية حساب نشطة، أو بنية قاعدة متقدمة، أو مجموعة أبعاد مالية؟
- هل البُعد المالي عبارة عن جزء من تنسيق تكامل الأبعاد المالية الافتراضية؟
- هل تم إعداد البُعد كبُعد افتراضي؟

إذا تمت تلبية أي واحد من المعايير، فلا يمكنك حذف البُعد المالي.

## <a name="default-dimension-values"></a>قيم البُعد الافتراضي

يمكنك استخدام القيم من السجلات الرئيسية، مثل العميل والمورد، كقيم افتراضية في الأبعاد الجديدة. عند إنشاء أبعاد جديدة، يتم إدخال مُعرف السجل الرئيسي في قيم الأبعاد لهذه السجلات الرئيسية. على سبيل المثال، عندما تقوم بإنشاء عميل جديد، يتم إدخال مُعرف العميل في بعد العميل. عندما تقوم بإنشاء أوامر مبيعات أو فواتير أو مستندات أخرى تتطلب مُعرف عميل، يتم استخدام القواعد الافتراضية الحالية، وتتم إضافة مُعرف العميل إلى المستند.

يتم التحكم في هذه الميزة عن طريق الإعداد في البُعد. يسمى هذا الإعداد **نسخ القيم لهذا البعد في كل DimensionName جديد يتم إنشائه**، حيث يكون **DimensionName** هو  اسم البعد. بشكل افتراضي، يتم إيقاف تشغيل الميزة. ومع ذلكن فإنه يمكن تشغيلها في أي وقت.

إذا كانت هناك سجلات موجود بالفعل للبعد، يتم تحديث السجلات الرئيسية عند تشغيل هذه الميزة. ومع ذلك، لا يتم تحديث المستندات الموجودة والحركات.

إذا كنت تستخدم قالبًا لإنشاء سجل رئيسي، فتأكد من أن قيمة القالب للبعد الرئيسي فارغة. على سبيل المثال، إذا كنت تعمل على إنشاء عملاء من قالب، فتأكد من أن بُعد العميل في القالب فارغ. ستكون قيمة بُعد العميل بشكل افتراضي القيمة من رقم العميل الجديد عندما تقوم بإنشاء عميل جديد.  

## <a name="derived-dimensions"></a>الأبعاد المشتقة

يمكنك تكوين بعد حيث يتم إدخال معلومات للأبعاد الأخرى تلقائيًا عندما تقوم بإدخال هذا البعد في مستند. على سبيل المثال، إذا قمت بإدخال مركز تكلفة 10، يمكن إدخال قيمة تتكون من **20** تلقائياً في بعد القسم.

يمكنك إعداد قيم مشتقة على صفحة الأبعاد.

1. حدد أحد الأبعاد، ثم حدد **الأبعاد المشتقة**.

    تحتوي صفحة**الأبعاد المشتقة** على شبكة. تمثل شريحة البعد المُحدد العمود الأول في هذه الشبكة.

2. أضف الشرايح التي يجب أن تكون مشتقة. تظهر كل شريحة كعمود.

أدخل مجموعة البُعد التي يتعين اشتقاقها من البعد في العمود الأول. على سبيل المثال، لاستخدام مركز التكلفة كالبعد الذي يتم اشتقاق القسم والموقع منه، أدخل مركز التكلفة 10، والقسم 20، والموقع 30. وبعد ذلك، عندما تقوم بإدخال مركز تكلفة 10 في سجل رئيسي أو في صفحة حركة، يتم إدخال القسم 20 والموقع 30 افتراضيًا.

### <a name="overriding-existing-values-with-derived-dimensions"></a>تجاوز القيم الموجودة بالأبعاد المشتقة
 
بشكل افتراضي، لا تتجاوز عملية البُعد المشتق القيم الموجودة للأبعاد المُشتقة. على سبيل المثال، إذا قمت بإدخال مركز تكلفة 10، ولم يتم إدخال أي بعد آخر، يتم إدخال القسم 20 والموقع 30 بشكل افتراضي. ومع ذلك، إذا قمت بتغيير مركز التكلفة، لا يتم تغيير القيم التي تم تحديدها مسبقًا. لذلك، يمكنك تحديد الأبعاد الافتراضية في السجلات الرئيسية، ولا يمكن تغيير تلك الأبعاد عن طريق الأبعاد المشتقة.

يمكنك تغيير سلوك الأبعاد المشتقة لتجاوز القيم الموجودة عن طريق تحديد خانة الاختيار **استبدال قيم الأبعاد الموجودة بالقيم المشتقة‬** في الصفحة **الأبعاد المشتقة‬**. إذا تم تحديد هذا الحقل، فيمكنك إدخال بُعد مع قيم أبعاد مشتقة، وستتجاوز قيم الأبعاد المشتقة هذه أي قيم موجودة. باستخدام المثال التالي، إذا قمت بإدخال مركز تكلفة 10، ولم يتم إدخال أي بُعد آخر، يتم إدخال القسم 20 والموقع 30 بشكل افتراضي. ومع ذلك، إذا كانت القيم القسم 50 والموقع 60، فستتغير القيم الآن إلى القسم 20 والموقع 30.
 
لا تحل الأبعاد المشتقة التي تستخدم هذا الإعداد تلقائيًا مكان قيم الأبعاد الافتراضية الموجودة عند تعيين قيم الأبعاد الافتراضية. سيتم تجاوز قيم الأبعاد فقط عندما تقوم بإدخال قيمة بُعد جديدة على صفحة توجد فيها قيم مشتقة موجودة لهذا البُعد.

### <a name="preventing-changes-with-derived-dimensions"></a>منع التغييرات مع الأبعاد المشتقة
 
عند استخدام **إضافة شريحة** في **صفحة الأبعاد مشتقة** لإضافة شريحة كبُعد مشتق، يظهر خيار في أسفل صفحة **إضافة شريحة** يسمح لك بمنع إجراء تغييرات على هذا البُعد عندما يتم اشتقاقه على صفحة. يكون الإعداد الافتراضي متوقفًا عن التشغيل وبالتالي لا يمنع تغيير قيم الأبعاد المشتقة. يمكنك تغيير الإعداد إلى **نعم** إذا كنت ترغب في منع تغيير البُعد بعد اشتقاقه. على سبيل المثال، إذا كانت قيمة البُعد "قسم" مشتقة من قيمة البُعد "مركز التكلفة"، فلا يمكن تغيير قيمة القسم إذا كان الإعداد **منع التغييرات** معينًا إلى **نعم**. 
 
الإعداد لا يمنع التغييرات إذا كانت قيمة البُعد صالحة ولكنها غير مذكورة في قائمة الأبعاد المشتقة. على سبيل المثال، إذا تم اشتقاق القسم 20 من مركز التكلفة 10 وأدخلت مركز التكلفة 10، فلن تتمكن من تحرير القسم 20. ولكن إذا أدخلت مركز التكلفة 20 ولم يكن مدرجًا في قائمة الأبعاد المشتقة لمركز التكلفة، يمكنك عندئذٍ تحرير قيمة القسم. 
 
في جميع الحالات، يمكن التحقق من قيمة الحساب وجميع قيم الأبعاد في مقابل بنى الحسابات بعد تطبيق قيم الأبعاد المشتقة. إذا استخدمت الأبعاد المشتقة وفشلت في عملية التحقق من الصحة عند استخدامها في صفحة، يجب تغيير قيم الأبعاد المشتقة في صفحة الأبعاد المشتقة قبل استخدامها في الحركات. 
 
عندما تقوم بتغيير الأبعاد في علامة التبويب السريعة **الأبعاد المالية**، لن يكون البُعد الموضوع عليه علامة لمنع التغييرات قابلاً للتحرير. إذا كنت تعمل على إدخال حساب وأبعاد في عنصر تحكم الإدخال المجزأ‬ على صفحة، فستكون الأبعاد قابلة للتحرير. ومع ذلك، عندما تنقل التمييز خارج عنصر تحكم الإدخال المجزأ وتنتقل إلى حقل آخر أو تتخذ إجراءً ما، سيتم التحقق من صحة الحساب والأبعاد في مقابل قائمة الأبعاد المشتقة وبنى الحسابات للتأكد من أنك أدخلت القيم المناسبة. 

### <a name="derived-dimensions-and-entities"></a>الأبعاد المشتقة والكيانات

يمكنك إعداد شرائح القيم المُشتقة والقيم باستخدام الكيانات.

- يقوم كيان الأبعاد المشتقة بإعداد الأبعاد المشتقة والشرائح المستخدمة لتلك الأبعاد.
- يسمح لك كيان قيمة الأبعاد المشتقة باستيراد القيم التي ينبغي اشتقاقها لكل بُعد مشتق.

عند استخدامك لكيان لاستيراد البيانات، إذا قام هذا الكيان باستيراد الأبعاد، يتم تطبيق قواعد البُعد المشتق خلال عملية الاستيراد ما لم يتجاوز الكيان تحديدًا تلك الأبعاد.

لمزيد من المعلومات، راجع الموضوعات التالية:

- [تحديد الأبعاد المالية](tasks/define-financial-dimensions.md)
- [الاحتفاظ بالقوالب الافتراضية للأبعاد المالية](tasks/maintain-financial-dimension-default-templates.md)