---
title: "محتوى Power BI لأداء المستودع"
description: "يوضح هذا الموضوع ما هو مدرج في محتوى Power BI لأداء المستودع. فهو يوضح كيفية الوصول إلى تقارير Power BI، ويوفر معلومات حول نموذج البيانات والكيانات التي يتم استخدامها لإنشاء المحتوى."
author: Mirzaab
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 272953
ms.assetid: 4e4d4323-78cf-4ffa-8d5a-05e856c33db6
ms.search.region: Global
ms.author: mirzaab
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 3daa69a1f042c2eb525e7e26eb0fe29253fe9e90
ms.contentlocale: ar-sa
ms.lasthandoff: 06/13/2017


---

# <a name="warehouse-performance-power-bi-content"></a>محتوى Power BI لأداء المستودع

[!include[banner](../includes/banner.md)]

يوضح هذا الموضوع ما هو مدرج في محتوى Microsoft Power BI **أداء المستودع**. فهو يوضح كيفية الوصول إلى تقارير Power BI، ويوفر معلومات حول نموذج البيانات والكيانات التي يتم استخدامها لإنشاء المحتوى.

## <a name="overview"></a>نظرة عامة

تم إنشاء محتوى Power BI **أداء المستودع** لتمكين مدراء المستودعات والعمليات من مراقبة المقاييس الواردة والصادرة ومقاييس المخزون المهمة. إنه يستخدم بيانات إدارة المستودعات والمنتجات وبيانات أخرى خاصة بالحركات‬ من نظامك، ويوفر طريقة عرض إجمالية لأداء المستودع بالإضافة إلى تصنيف للموردين ومجموعات المنتجات والمنتجات والمواقع والمستودعات. 

باستطاعة مدراء المستودعات استخدام محتوى Power BI **أداء المستودع** لقياس النواحي الثلاث التالية:

-   **الأداء الوارد**: لقياس مستوى أداء المورّد في مقابل متطلبات العميل (بمعنى آخر، قياس أداء التسليم)، وقياس أداء التخزين، لكي تتمكن من التعرّف عل المشاكل التي تتعلق بالعاملين أو الأصناف خلال فترة زمنية. من الضروري أن تعرف ما إذا كان الموردّون يقومون بعمليات التسليم في الوقت المحدد أو في وقت مبكر أو متأخر، لكي تتمكن من تحديد كيفية تأثير أداء الموردّ على أداء التخزين بشكل عام. باستطاعة المورّد الذي يقوم بالتسليم خارج نطاق التواريخ التي تم الاتفاق عليها أن يتسبب في وضع ضغط إضافي على المستودع بسبب العمل غير المتوقع، وبإمكانه زيادة متوسط وقت التخزين.
-   **أداء الشحن** – قياس ما إذا كان المستودع يشحن الأصناف بشكل كامل وفي الوقت المحدد للعملاء (بمعنى آخر، قياس أداء الشحن الخارجي وأداء التسليم)، لكي تتمكن من التعرّف عل المشاكل التي تتعلق بالمنتجات أو المواقع أو المستودعات أو العملاء المخصصين. إذا وجدت أنك تقوم بعمليات شحن متأخر لمناطق أو بلدات معينة، فقد تحتاج إلى إيلاء المزيد من الاهتمام لعمليات إدارة النقل أو الحسابات.
-   **دقة مخزون الموقع** – تعتبر دقة المخزون بمثابة المعلومات المهنية الداخلية للمستودع. من الضروري جدًا أن تحدد مدى الدقة التي تقوم فيها بعمليات الجرد بشكل عام. ومع ذلك، من الضروري أيضًا أن تحدد مستوى الدقة التي تخزن العناصر بها في المواقع الصحيحة، وأن تسلط الضوء على البيانات المختلفة، لكي تتمكن من العثور على مواضع أفضل للأصناف أو بدء عملية جرد إجمالي لأصناف محددة. (في الوقت الحالي، يتم تقديم وظيفة الجرد الجديدة القائمة على الأصناف كإصلاح عاجل.) إذا كنت تستخدم محتوى Power BI هذا لتحديد صحة بيانات المخزون الفعلي لكل موقع، فيمكنك أيضًا تحديد السرقات في محلاتك التجارية. يمكنك أيضًا تحديد ما إذا كان هناك أية مواقع لديها كميات فعلية تختلف عن بيانات تخطيط موارد المؤسسة (ERP). قد تكون هذه المواقع كبيرة للغاية، أو قد يكون من المستحيل جردها. بدلاً من ذلك، قد تكون بعض المواضع الفعلية سيئة، حيث تصعب المحافظة على مزامنة نوع صنف واحد مع البيانات الفعلية.

## <a name="accessing-the-power-bi-content-pack"></a>الوصول إلى حزمة محتوى Power BI
إذا كنت تستخدم Microsoft Dynamics 365 for Finance and Operations, Enterprise edition، تحديث شهر يوليو 2017، فسيظهر محتوى Power B **أداء المستودع** في صفحة **أداء المستودع** (**إدارة المستودعات‬** > **الاستعلامات والتقارير** > **تحليل أداء المستودع** > **أداء المستودع**). 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>المقاييس المُدرجة في محتوى Power BI
يتضمن محتوى Power BI **أداء المستودع** تقريرًا. يتكون هذا التقرير من مجموعة من المقاييس المصورة مرئيًا مثل المخططات والإطارات المتجانبة والجداول. يوفر الجدول التالي نظرة عامة حول مجموعة الرسوم المرئية في محتوى Power BI **أداء المستودع**.

| صفحة التقرير                 | مخططات                                   | ‏‏الوصف                                                                                                                                                                                                                                                                                                                                                                                                     |
|-----------------------------|------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| الأداء الوارد         | إجمالي عمليات التخزين                          | عدد بنود عمل التخزين التي تمت معالجتها خلال فترة زمنية محددة.                                                                                                                                                                                                                                                                                                                                       |
| الأداء الوارد         | متوسط وقت التخزين                    | متوسط الوقت، بالساعات، لكل بنود تخزين في أمر الشراء التي تتم معالجتها، من تسجيل الأصناف حتى معالجة آخر وضع.                                                                                                                                                                                                                                                           |
| الأداء الوارد         | تم الاستلام مبكرًا                           | عدد بنود أوامر الشراء التي تم استلامها في وقت مبكر.                                                                                                                                                                                                                                                                                                                                                     |
| الأداء الوارد         | تم الاستلام في الموعد                         | عدد بنود أوامر الشراء التي تم استلامها في الوقت المحدد.                                                                                                                                                                                                                                                                                                                                                   |
| الأداء الوارد         | تأخير الاستلام                            | عدد بنود أوامر الشراء التي تم استلامها في وقت متأخر.                                                                                                                                                                                                                                                                                                                                                      |
| الأداء الوارد         | في الوقت المحدد بواسطة المورّد                        | طريقة عرض النسبة المئوية لبنود أمر الشراء التي تم تلقيها من مورّد أو مجموعة مورّدين في وقت مبكر وفي الوقت المحدد وفي وقت متأخر.                                                                                                                                                                                                                                                                                      |
| الأداء الوارد         | متوسط وقت التخزين من الرصيف إلى المخزون (بالساعات) | متوسط وقت التخزين من الرصيف إلى المخزون بالساعات مع مرور الوقت.                                                                                                                                                                                                                                                                                                                                                     |
| الأداء الوارد         | متوسط وقت التخزين من العامل               | متوسط الوقت، بالساعات، الذي أمضاه العامل في معالجة تخزين بنود أمر الشراء.                                                                                                                                                                                                                                                                                                      |
| الأداء الوارد         | متوسط التخزين بالساعة حسب المورّد          | متوسط التخزين بالساعات حسب المورّد أو مجموعة مورّدين.                                                                                                                                                                                                                                                                                                                                                   |
| الأداء الوارد         | متوسط التخزين بالساعة حسب المنتج         | متوسط التخزين بالساعات حسب الصنف أو مجموعة أصناف.                                                                                                                                                                                                                                                                                                                                                       |
| دقة موقع المخزون | إجمالي العدد                              | عدد بنود عمل الجرد التي تتم معالجتها خلال فترة زمنية محددة.                                                                                                                                                                                                                                                                                                                                        |
| دقة موقع المخزون | معدل التباين                         | معدل التباين الإجمالي كنسبة مئوية لكافة البنود التي يتم جردها لفترة معينة.                                                                                                                                                                                                                                                                                                                    |
| دقة موقع المخزون | الجرد من دون تباين                | من العدد الإجمالي لبنود عمل الجرد التي تتم معالجتها، عدد البنود التي تتم معالجتها من دون أي تباين.                                                                                                                                                                                                                                                                                  |
| دقة موقع المخزون | الأصناف التي تم جردها مع مرور الوقت                  | النسبة المئوية للأصناف التي يتم جردها وبدون تباين مع مرور الوقت.                                                                                                                                                                                                                                                                                                                                |
| دقة موقع المخزون | تباين كمية الصنف أكبر من % | طريقة عرض جدول لبنود الجرد التي لديها تباينات تتجاوز نسبة مئوية محددة. يحتوي الجدول على معلومات حول المواقع، والأصناف، ومتوسط التباين، وإجمالي بنود عمل الجرد التي يتم جردها، وعدد بنود الجرد التي لديها تباينات في الموقع، ومتوسط الكمية التي يتم جردها، وإجمالي الكمية المتوقعة التي سيتم جردها، وكمية الأصناف الفعلية التي يتم جردها. |
| دقة موقع المخزون | جرد الأصناف حسب العامل                     | أداء الجرد لدى العاملين. يتم التعبير عن الأداء كنسبة مئوية لبنود عمل الجرد التي لديها تباينات أم لا.                                                                                                                                                                                                                                                                    |
| دقة موقع المخزون | جرد الأصناف حسب الموقع/المستودع           | أداء الجرد حسب عدد بنود أمر الجرد التي تمت معالجتها حسب الموقع أو المستودع والتي لديها أو ليس لديها تباينات.                                                                                                                                                                                                                                                                                |
| دقة موقع المخزون | معدل التباين حسب المنتج              | معدل التباين لأداء الجرد. يتم التعبير عن المعدل كنسبة مئوية لبنود عمل الجرد التي تمت معالجتها حسب الصنف أو مجموعة الأصناف.                                                                                                                                                                                                                                                                    |
| أداء الشحن        | البنود التي تم شحنها                            | العدد الإجمالي لبنود الجرد التي تم شحنها خلال فترة زمنية محددة.                                                                                                                                                                                                                                                                                                                                        |
| أداء الشحن        | مبكرًا                                    | النسبة المئوية لبنود الشحن التي تم شحنها في وقت مبكر.                                                                                                                                                                                                                                                                                                                                                        |
| أداء الشحن        | في الوقت المحدد                                  | النسبة المئوية لبنود الشحن التي تم شحنها في الوقت المحدد.                                                                                                                                                                                                                                                                                                                                                      |
| أداء الشحن        | متأخر                                     | النسبة المئوية لبنود الشحن التي تم شحنها في وقت متأخر.                                                                                                                                                                                                                                                                                                                                                         |
| أداء الشحن        | عمليات الشحن مع مرور الوقت                      | النسبة المئوية لبنود الشحن التي تم شحنها في الوقت المحدد أو في وقت مبكر أو متأخر أو خلال فترة زمنية معينة. يعرض بند الاتجاه اتجاه البنود التي تم شحنها في الوقت المحدد.                                                                                                                                                                                                                                                 |
| أداء الشحن        | شحن متأخر حسب المدينة                     | عرض مرئي لخريطة المدن والمناطق التي تأثرت بالشحنات المتأخرة.                                                                                                                                                                                                                                                                                                                                    |
| أداء الشحن        | الشحن حسب المنتج                       | النسبة المئوية التي تم شحنها في وقت مبكر أو في الوقت المحدد أو في وقت متأخر حسب الصنف أو مجموعة الأصناف.                                                                                                                                                                                                                                                                                                                                   |
| أداء الشحن        | الشحن بواسطة العميل                      | النسبة المئوية التي تم شحنها في وقت مبكر أو في الوقت المحدد أو في وقت متأخر حسب العميل أو مجموعة العملاء.                                                                                                                                                                                                                                                                                                                           |
| أداء الشحن        | الشحن حسب الموقع/المستودع              | النسبة المئوية التي تم شحنها في وقت مبكر أو في الوقت المحدد أو في وقت متأخر حسب الموقع أو المستودع.                                                                                                                                                                                                                                                                                                                                    |
## <a name="extending-the-power-bi-content"></a>توسيع محتوى Power BI
باستخدام حزم المحتوى المتاحة في Microsoft Dynamics Lifecycle Services (LCS)، يمكنك تقديم تحليلات رائعة للأشخاص الذين لم يقوموا بتسجيل الدخول إلى Microsoft Dynamics 365. يمكنك تعديل حزم المحتوى هذه بحيث تتضمن تقارير أخرى أو رسوم مرئية، ثم قم بنشر حزم المحتوى لمستأجر Power BI.com الخاص بك لتحليلها. 

يمكنك العثور على محتوى Power BI **أداء المستودع** في مكتبة الأصول المشتركة في LCS. للمزيد من المعلومات حول كيفية تنزيل المحتوى وتطبيقه في مؤسستك، راجع [محتوى Power BI في LCS من Microsoft والشركاء‬‏‫](power-bi-content-microsoft-partners.md). لمشاهدة عرض توضيحي يعرض كيفية تطبيق محتوى Power BI، راجع [محتوى Power BI من Microsoft والشركاء في Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w)Office Mix.

احرص على تنزيل محتوى **أداء المستودع** الذي ينطبق على إصدار Dynamics 365 الذي تستخدمه.

> [!NOTE]
> إذا كنت تستخدم الإصدار 1611 من Microsoft Dynamics 365 for Operations، فإن KB 4011327 عبارة عن مطلب أساسي لمحتوى Power BI هذا. بعد تسجيل الدخول إلى LCS، يمكنك الوصول إلى KB من خلال هذا الرابط: https://fix.lcs.dynamics.com/issue/results/?q=kb4011327.

## <a name="understanding-the-data-model-and-calculations"></a>فهم نموذج البيانات وعمليات الحساب
تُستخدم البيانات التالية لملء صفحات التقارير في محتوى Power BI **أداء المستودع**. يتم تمثيل هذه البيانات كقياسات مجمعة تم تجهيزها في مخزن الكيانات. مخزن الكيانات هو قاعدة بيانات لخادم Microsoft SQL تم تحسينها للتحليلات. لمزيد من المعلومات، راجع [نظرة عامة عن تكامل Power BI مع متجر الكيان](power-bi-integration-entity-store.md). 

تستخدم القياسات التجميعية الرئيسية التالية كأساس للمحتوى.

| صفحة التقرير                 | مخططات                                   | جداول                                | أوصاف الحساب                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|-----------------------------|------------------------------------------|---------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| الأداء الوارد         | إجمالي عمليات التخزين                          | WHSWorkLine                           | عدد بنود العمل حيث نوع العمل **وضع**.                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| الأداء الوارد         | متوسط وقت التخزين                    | WHSWorkLine                           | مجموع الوقت الأقصى لبنود العمل مقسومًا على الوقت الأقصى لبنود العمل، حيث الوقت الأقصى لبنود العمل هو الحد الأقصى للتفاوت بين تاريخ إنشاء العمل وتاريخ إغلاقه.                                                                                                                                                                                                                                                                                                                |
| الأداء الوارد         | تم الاستلام مبكرًا                           | WHSWorkLine                           | عدد بنود العمل حيث تاريخ إنشاء العمل يقع قبل تاريخ التسليم المستخدم. إذا لم يتم تعيين تاريخ التسليم المؤكد، فاستخدم تاريخ التسليم الافتراضي.                                                                                                                                                                                                                                                                                                                  |
| الأداء الوارد         | تم الاستلام في الموعد                         | WHSWorkLine                           | عدد بنود العمل حيث تاريخ إنشاء العمل يساوي تاريخ التسليم المستخدم. إذا لم يتم تعيين تاريخ التسليم المؤكد، فاستخدم تاريخ التسليم الافتراضي.                                                                                                                                                                                                                                                                                                                      |
| الأداء الوارد         | تأخير الاستلام                            | WHSWorkLine                           | عدد بنود العمل حيث تاريخ إنشاء العمل يقع بعد تاريخ التسليم المستخدم. إذا لم يتم تعيين تاريخ التسليم المؤكد، فاستخدم تاريخ التسليم الافتراضي.                                                                                                                                                                                                                                                                                                                    |
| الأداء الوارد         | في الوقت المحدد بواسطة المورّد                        | WHSWorkLine                           | تم الاستلام مبكرًا‬، تم الاستلام في الموعد، وتأخير الاستلام (راجع الأوصاف سابقًا في هذا الجدول).                                                                                                                                                                                                                                                                                                                                                                                             |
| الأداء الوارد         | متوسط وقت التخزين من الرصيف إلى المخزون (بالساعات) | WHSWorkLine                           | متوسط وقت التخزين (راجع الوصف سابقًا في هذا الجدول).                                                                                                                                                                                                                                                                                                                                                                                                                            |
| الأداء الوارد         | متوسط وقت التخزين من العامل               | WHSWorkLine                           | متوسط وقت التخزين (راجع الوصف سابقًا في هذا الجدول).                                                                                                                                                                                                                                                                                                                                                                                                                            |
| الأداء الوارد         | متوسط التخزين بالساعة حسب المورّد          | WHSWorkLine                           | متوسط وقت التخزين (راجع الوصف سابقًا في هذا الجدول).                                                                                                                                                                                                                                                                                                                                                                                                                            |
| الأداء الوارد         | متوسط التخزين بالساعة حسب المنتج         | WHSWorkLine                           | متوسط وقت التخزين (راجع الوصف سابقًا في هذا الجدول).                                                                                                                                                                                                                                                                                                                                                                                                                            |
| دقة موقع المخزون | إجمالي العدد                              | WHSWorkLineCycleCount                 | عمليات الجرد الدوري حيث تساوي كمية التباين المطلق 0 (صفر) أو حيث هي أكبر منه.                                                                                                                                                                                                                                                                                                                                                                                                       |
| دقة موقع المخزون | معدل التباين                         | WHSWorkLineCycleCount                 | عمليات الجرد الدوري التي تحتوي على تباينات، مقسومة على إجمالي العدد‬. تحتوي عملية الجرد الدوري على تباينات إذا كانت كمية التباين المطلق أكبر من 0 (صفر).                                                                                                                                                                                                                                                                                                               |
| دقة موقع المخزون | الجرد من دون تباين                | WHSWorkLineCycleCount                 | عمليات الجرد الدوري حيث كمية التباين المطلق أكبر من 0 (صفر).                                                                                                                                                                                                                                                                                                                                                                                                                   |
| دقة موقع المخزون | الجرد مع تباين                   | WHSWorkLineCycleCount                 | عمليات الجرد الدوري حيث تساوي كمية التباين المطلق 0 (صفر).                                                                                                                                                                                                                                                                                                                                                                                                                    |
| دقة موقع المخزون | الأصناف التي تم جردها مع مرور الوقت                  | WHSWorkLineCycleCount                 | الجرد من دون تباين‬ والجرد مع تباين‬ (راجع الأوصاف سابقًا في هذا الجدول.)                                                                                                                                                                                                                                                                                                                                                                                            |
| دقة موقع المخزون | تباين كمية الصنف أكبر من % | WHSWorkLineCycleCount                 | متوسط التباين هو كمية التباين المطلق مقسومة على الكمية المتوقعة حيث كمية التباين المطلق أكبر من 0 (صفر). متوسط كمية التباين هو متوسط كمية التباين المطلق حيث كمية التباين المطلق أكبر من 0 (صفر). الجرد مع تباين وإجمالي العدد والكمية المتوقعة والكمية المجرودة حيث يتم تجميع الكمية بكاملها حسب الصنف والموقع (راجع الأوصاف سابقًا في هذا الجدول). |
| دقة موقع المخزون | جرد الأصناف حسب العامل                     | WHSWorkLineCycleCount                 | الجرد من دون تباين‬ والجرد مع تباين‬ (راجع الأوصاف سابقًا في هذا الجدول).                                                                                                                                                                                                                                                                                                                                                                                            |
| دقة موقع المخزون | جرد الأصناف حسب الموقع/المستودع           | WHSWorkLineCycleCount                 | الجرد من دون تباين‬ والجرد مع تباين‬ (راجع الأوصاف سابقًا في هذا الجدول).                                                                                                                                                                                                                                                                                                                                                                                            |
| دقة موقع المخزون | معدل التباين حسب المنتج              | WHSWorkLineCycleCount                 | معدل التباين‬ (راجع الوصف سابقًا في هذا الجدول).                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| أداء الشحن        | البنود التي تم شحنها                            | بند المبيعات                             | عدد بنود المبيعات حيث تم شحن بنود المبيعات.                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| أداء الشحن        | مبكرًا                                    | CustPackingSlipOnTimeStatus           | بنود المبيعات حيث حالة تاريخ الشحن **1 (مبكرًا)**. يعني الشحن المبكر أن تاريخ الشحن على إيصال التعبئة يقع قبل تاريخ الشحن المؤكد لبند المبيعات. إذا لم يتم تعيين تاريخ الشحن المؤكد، فاستخدم تاريخ الشحن المطلوب.                                                                                                                                                                                                                                                     |
| أداء الشحن        | في الوقت المحدد                                  | CustPackingSlipOnTimeStatus           | بنود المبيعات حيث حالة تاريخ الشحن **2 (في الوقت المحدد‬)**. يعني الشحن في الوقت المحدد أن تاريخ الشحن على إيصال التعبئة يساوي تاريخ الشحن المؤكد لبند المبيعات. إذا لم يتم تعيين تاريخ الشحن المؤكد، فاستخدم تاريخ الشحن المطلوب.                                                                                                                                                                                                                                                     |
| أداء الشحن        | متأخر                                     | CustPackingSlipOnTimeStatus           | بنود المبيعات حيث حالة تاريخ الشحن **3 (متأخر‬)**. يعني الشحن المتأخر أن تاريخ الشحن على إيصال التعبئة يقع بعد تاريخ الشحن المؤكد لبند المبيعات. إذا لم يتم تعيين تاريخ الشحن المؤكد، فاستخدم تاريخ الشحن المطلوب.                                                                                                                                                                                                                                                         |
| أداء الشحن        | عمليات الشحن مع مرور الوقت                      | SalesLine CustPackingSlipOnTimeStatus | الأوامر التي تم شحنها بالكامل، حيث تم شحن الكمية الكاملة لبند المبيعات، بالإضافة إلى الشحن المبكر وفي الوقت المحدد والمتأخر (راجع الأوصاف سابقًا في هذا الجدول).                                                                                                                                                                                                                                                                                                                             |
| أداء الشحن        | شحن متأخر حسب المدينة                     | CustPackingSlipOnTimeStatus           | متأخر‬ (راجع الأوصاف سابقًا في هذا الجدول).                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| أداء الشحن        | الشحن حسب المنتج                       | CustPackingSlipOnTimeStatus           | مبكرًا‬ وفي الوقت المحدد ومتأخر (راجع الأوصاف سابقًا في هذا الجدول).                                                                                                                                                                                                                                                                                                                                                                                                                        |
| أداء الشحن        | الشحن بواسطة العميل                      | CustPackingSlipOnTimeStatus           | مبكرًا‬ وفي الوقت المحدد ومتأخر (راجع الأوصاف سابقًا في هذا الجدول).                                                                                                                                                                                                                                                                                                                                                                                                                        |
| أداء الشحن        | الشحن حسب الموقع/المستودع              | CustPackingSlipOnTimeStatus           | مبكرًا‬ وفي الوقت المحدد ومتأخر (راجع الأوصاف سابقًا في هذا الجدول).                                                                                                                                                                                                                                                                                                                                                                                                                        |
