---
title: كتالوجات مركز الاتصال​
description: يصف هذا الموضوع الوظائف الخاصة بمركز الاتصال للكتالوجات في Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailMCRChannelDetailPage, RetailCatalogDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16231
ms.assetid: f28a827c-3a50-4d5e-83eb-e5a768db70a1
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: e4d2b1f4b7fb9394f54674f9622c8a8edd435311
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/01/2020
ms.locfileid: "3021448"
---
# <a name="call-center-catalogs"></a>كتالوجات مركز الاتصال​

[!include [banner](includes/banner.md)]

يصف هذا الموضوع الوظائف الخاصة بمركز الاتصال المرتبطة بقدرات الكتالوجات في Dynamics 365 Commerce.

يمكن استخدام ميزات الكتالوج الموجودة في Commerce لأغراض متعددة. تم إنشاء ميزات الكتالوج لدعم عمليات تكامل التجارة الإلكترونية لجهة أخرى. سمح إعداد الكتالوج للشركات بإنشاء مجموعة من المنتجات والسمات التي يمكن نشرها خارجيًا للاستهلاك بواسطة حل تجارة إلكترونية لطرف آخر.

عندما تمت إضافة دعم قناة مركز الاتصال، تم توسيع مفهوم الكتالوج لإضافة قدرات إضافية لدعم وإدارة الميزات المتعلقة بكتالوجات التسويق التقليدية مباشرة إلى المستهلك. غالباً ما ستنتج شركة المباشر إلى المستهلك الكتالوجات المطبوعة التي يتم إرسالها بالبريد الإلكتروني بعد ذلك على شريحة واحدة أو أكثر من العملاء. ستحتوي هذه الكتالوجات بشكل نموذجي على عروض ترويجية محددة سيتم سدادها فقط إذا كان العميل يقدم كود هوية الكتالوج عند وقت إنشاء أمر.

تعتبر شركات التسويق المباشر إلى المستهلك شديدة التركيز على تعقب الاستجابة إلى هذه الكتالوجات للتأكد من أن التكاليف للإنتاج وإرسالها عبر البريد الإلكتروني أمرًا مضبوطًا. لتعقب الاستجابة، تتم طباعة كود بشكل تقليدي خلف الكتالوج ثم يتم طلب هذا الكود واستخدامه عندما يتصل مستلم الكتالوج لإدخال أمر عن طريق الهاتف (أو قد يتم الآن إدخال الكود بشكل أكثر تقليدية عندما يُدخل العميل الأمر عبر الإنترنت). على الرغم من استخدام مصطلحات مختلفة في المجال لتعريف كود تعقب الكتالوج هذا (بما في ذلك كود المفتاح، والكود الترويجي، وكود كتالوج، والكود المصدر)، نشير نحن إلى الكود في Commerce باسم **معرّف الكود المصدر**.

## <a name="basic-catalog-setup"></a>إعداد كتالوج أساسي

انتقل إلى **البيع بالتجزئة والتجارة** \> **الكتالوجات وعمليات الفرز** \> **جميع الكتالوجات** لتكوين الكتالوج.

عندما تقوم بإنشاء كتالوج جديد، يجب عليك أولاً ربط الكتالوج بقناة أو أكثر. يتم هذا في علامة التبويب السريعة **قنوات التجارة‬** في نموذج **إعداد الكتالوج**. انقر فوق **إضافة** وحدد قناة واحدة أو أكثر. يمكن استخدام العناصر المرتبطة [بعمليات فرز قناتك المحددة](https://docs.microsoft.com/dynamics365/unified-operations/retail/assortments) فقط عند إنشاء الكتالوج.

لإضافة منتجات إلى كتالوج، يجب اختيار تدرج هرمي للتنقل. سيدعم التدرج الهرمي للتنقل بنية الفئة للكتالوج. يجب أن تنتقي من أحد تسلسلات التدرجات الهرمية للتنقل المرتبطة بالقنوات المحددة في علامة التبويب السريعة **قنوات التجارة** في صفحة **الكتالوج**. إذا لم يتم ربط قناة تنقل بقناة في وقت سابق، فاذهب إلى **البيع بالتجزئة والتجارة** \> **إعداد القناة** \> **فئات القناة وسمات المنتج** لربط تدرج هرمي افتراضي للتنقل بكل قناة من قنواتك.

في علامة تبويب القائمة **الكتالوجات**، في الصفحة **إعداد كتالوج**، انقر فوق **إضافة منتجات** لتكوين المنتجات لإضافتها إلى الكتالوج، أو حدد عقدة في التدرج الهرمي للتنقل (تحديد عقده سيغير العرض التقديمي للشاشة ويسمح لك بإضافة منتجات مباشرة إلى فئة في الكتالوج).

انقر فوق العقدة العليا للتدرج الهرمي للكتالوج للرجوع إلى طريقة عرض العنوان الرئيسي للكتالوج. قم بتكوين تواريخ السريان وانتهاء الصلاحية إذا لزم الأمر على علامة التبويب السريعة **عام**.

قبل أن يتوافر الكتالوج المصورة لاستخدامه، فإنه يجب أن يتم نشره. انقر فوق **‏‫التحقق من صحة الكتالوج‬** على قائمة **الكتالوجات** لمعالجة عملية التحقق من الصحة. هذا إجراء مطلوب وسيتم التحقق من دقة الإعداد المطلوب. انقر فوق **عرض نتائج** للاطلاع على تفاصيل التحقق من الصحة. إذا تم العثور على أخطاء، فإنه يجب تصحيح البيانات وتشغيل التحقق من الصحة مرة أخرى حتى اجتياز التحقق من الصحة.

بعد تأكيد التحقق من الصحة، انقر فوق **سير العمل** على القائمة لبدء سير عمل الموافقة. انقر فوق **إرسال** في قائمة **سير العمل** لتنفيذ العملية. قم بتكوين الخطوات والمستخدمين المخولين لسير العمل من **البيع بالتجزئة والتجارة** \> **إعداد المراكز الرئيسية** \> **سير عمل التجارة**. سيحدد سير العمل الخطوات اللازمة لإدخال الكتالوج في حالة **معتمد**. عندما يكون الكتالوج في حالة **معتمد**، فإنه يمكنك النقر فوق خيار **نشر** على قائمة **الكتالوجات** لإكمال العملية. بعد أن يكون الكتالوج في حالة **منشور**، فإنه يمكن استخدامه في إدخال أمر مركز الاتصال وإرسال عمليات الكتالوج.

## <a name="use-catalogs-to-drive-sales-order-pricing-and-promotions"></a>استخدام الكتالوجات لتحديد سعر أمر التوريد والعروض الترويجية

يوجد سبب أساسي لتحديد كتالوج لاستخدامه مع مركز اتصال ألا وهو أن تتمكن من تكوين أسعار وعروض ترويجية محددة لهذا الكتالوج. سيحصل العملاء الذين يطلبون من هذا الكتالوج على هذه الأسعار والعروض الترويجية في إدخال أمر مركز الاتصال إذا تم تطبيقإدخال أمر **‏‫معرف كود المصدر** الخاص بالكتالوج على عنوان أو بنود الأمر.

لتكوين أسعار كتالوج محددة، حدد خيار **مجموعات الأسعار** من علامة تبويب **الكتالوجات** لربط مجموعة أو مجموعات الأسعار الكتالوج. سيتم تطبيق كل الاتفاقيات التجارية ودفاتر يومية تعديل السعر والخصومات المتقدمة (الحد، الكمية، المنتجات المختلفة) التي تم ربطها بمجموعة السعر نفسها عندما يطلب العملاء المنتجات من هذا الكتالوج.

في علامة التبويب السريعة **أكواد المصدر**، انقر فوق **إضافة** لإضافة واحد أو أكثر من معرفات **معرف كود المصدر** في هذا الكتالوج. هذا هو الكود الذي سيتم تطبيقه أثناء إدخال أمر مركز الاتصال برأس أمر التوريد (والبنود). يتم استخدام هذ الكود لربط أمر المبيعات بالكتالوج وفي النهاية بمجموعات الأسعار وأي أسعار وعروض ترويجية خاصة تم تكوينها.

## <a name="use-the-source-id-to-track-costs-and-response-rates"></a>استخدام معرّف المصدر لتعقب التكاليف ومعدلات الاستجابة

عند تعريف **‏‫معرف كود المصدر‬**، فإنه يمكنك بشكل اختياري ربط هذا المعرف **بمعرف السوق المستهدف**. يمكن تعريف **معرف السوق المستهدف** في **البيع بالتجزئة والتجارة** \> **العملاء** \> **السوق المستهدف**. السوق المستهدفة عبارة عن قائمة العملاء و/أو العملاء المتوقعين الذين ينتمون إلى شريحة محددة بواسطة المستخدم. يسمح ربط بيانات العميل أو العميل المتوقع بمعرف كود المصدر‬ برؤية أفضل لمستلمو الكتالوج. إذا كان العميل مرتبطا بالسوق المستهدفة وهذه السوق المستهدفة مرتبطة بمعرف كود المصدر/الكتالوج، فسيكون مستخدمو مركز الاتصال قادرون على رؤية الكتالوجات التي استلمها العميل عن طريق تحديد خيار قائمة **أكواد المصدر** في علامة تبويب قائمة **العملاء** على صفحة **خدمة العملاء**. أثناء إدخال أمر، يستطيع مستخدمو مركز الاتصال كذلك رؤية كتالوجات معينة أرسلها عميل في القائمة المنسدلة **مصدر** في رأس أمر مبيعات. سيعمل تغيير عامل التصفية من **الكل** إلى **المستهدف** على السماح للمستخدم برؤية الكتالوجات النشطة المعينة التي أرسلها العميل. وهذا مفيد في الحالات التي قد ينسى فيها العميل الكتالوج أو لا يستطيعون تحديد كود الكتالوج أو قراءته عندما يُطالبون بإنشاء أمر المبيعات.

من الممكن ربط معرفات كود المصدر بكتالوج. وغالبًا ما يكون هذا مطلوبًا عندما تريد شركة تعقب معدل الاستجابة عن طريق شرائح مختلفة. ستُعطي الشركة كود كتالوج فريد إلى شرائح عملاء مختلفة، مما يسمح بتعقب معدل الاستجابة، لأقل من مستوى الشريحة، في حدث كتالوج معين.

سيعمل تحديد سجل **‏‫معرف كود المصدر‬** معين والنقر فوق خيار **تفاصيل** على علامة التبويب السريعة **أكواد المصدر** على توفير حقول إضافية حيث يمكن الحصول على توقعات المبيعات وتكاليف المراسلة وتواريخ المراسلة. هذه البيانات مفيدة للقيام بتحليل مفصل حول فعالية الكتالوج. يستطيع المستخدمون الرجوع إلى هذه الصفحة على مدار الوقت واستخدام الزرين **تحليل كود المصدر** و **مقارنة العروض** لتشغيل التقارير التحليلية التي تستند إلى بيانات المبيعات الحالية ومقارنة التكاليف والموازنة بالقيم الفعلية.

## <a name="configure-catalog-specific-order-and-item-scripts"></a>تكوين أمر خاص بالكتالوج وبرامج نصية للصنف

عندما يقوم مستخدم مركز اتصال بإنشاء أمر المبيعات، فإنه يمكنه استخدام البرامج النصية التي تظهر على الشاشة. قد توفر هذه البرامج النصية المستندة إلى النص معلومات إضافية ينبغي على المستخدم قولها للعميل، أو قد تكون ملاحظات/تذكيرات داخلية ينبغي على مستخدم مركز الاتصال مراجعتها والتصرف على أنه يقوم بإنشاء أمر المبيعات.

من المفيد غالبًا أن يكون لديك مجموعات مختلفة من البرامج النصية لكتالوجات مختلفة. في علامة التبويب السريعة **البرامج النصية**، يمكن ربط برامج نصية معرفة مسبقًا بكتالوج. استخدم حقل **التوقيت** لتحديد ما إذا كان البرنامج النصي سيظهر في بداية الأمر (بمجرد أن يتم إدخال معرف كود المصدر في رأس الأمر) أم في نهاية الأمر (في نموذج ملخص أمر المبيعات).

عند تحديد عقده في التدرج الهرمي للكتالوج والعمل باستخدام البيانات الموجودة على علامة التبويب السريعة **منتجات**، يستطيع المستخدمون كذلك ربط البرامج النصية الخاصة بكتالوجات أو أصناف باستخدام إجراء **البرامج النصية**.

## <a name="configure-catalog-specific-up-sell-and-cross-sell-items"></a>تكوين الأصناف الإضافية للكتالوج و الأصناف المكملة

يمكن إجراء ربط اقتراحات الأصناف الإضافية/المكملة من إعداد المنتجات، ولكن في بعض الحالات، قد تحتاج شركة إلى ترقية أصناف إضافية/مكملة للعملاء الذين يطلبون منتج معين من كتالوج معين. في علامة التبويب السريعة**المنتجات**، حدد صنفًا وانقر فوق **‏‫الأصناف الإضافية/المكملة‬** لتكوين المنتجات الإضافية أو المكملة للعملاء الذين يشترون الصنف المحدد من الكتالوج. أثناء إدخال أمر مركز الاتصال، ستظهر ‏‫الأصناف الإضافية/المكملة‬ على الشاشة بدلاً من المنتجات الإضافية/المكملة التي قد يتم تكوينها لذلك العنصر خلال تكوين المنتج المعتاد.

يمكن أن تستفيد كذلك الأصناف الإضافية/المكملة من ميزات البرنامج النصي لعرض رسائل معينة سيراها المستخدام عندما يتم عرض الصنف الإضافي/المكمل أثناء إدخال أمر. ستظهر البرامج النصية المرتبطة بمنتجات إضافية/مكملة المكونة خصيصًا لمنتج كتالوج فقط عندما يتم تطبيق كود مصدر الكتالوج هذا في إدخال أمر مركز الاتصال.

## <a name="catalog-page-analysis"></a>تحليل صفحة الكتالوج‬

على علامة التبويب **الكتالوجات**، تتوفر خيارات لتكوين **صفحات الكتالوج**. تسمح لك هذه الميزة بتحديد صفحات معينة وأنواع الصفحات للكتالوجات المطبوعة والتكاليف المقترنة بها.

عند تكوين المنتجات في الكتالوج، استخدم إجراء **تخطيط صفحة المنتج** لتحديد صفحات معينة والنسبة المئوية للصفحة وموضع تفاصيل الصفحة للصنف. سيسمح تكوين هذه البيانات للمستخدمين بالاستفادة من **‏‫تقرير تحليل منطقة الكتالوج‬**. يمكن العثور على هذا التقرير بالانتقال إلى **البيع بالتجزئة والتجارة** \> **تقارير مركز الاتصال** \> **تقرير تحليل منطقة الكتالوج**. يقوم هذا التقرير بتحليل المبيعات التي تم وضعها مقابل الكتالوج (أوامر المبيعات حيث يتم ربط معرف المصدر للكتالوج برأس أو بند الأمر) والنسبة المئوية المرتبطة بالصفحة والتكاليف لتقديم تقرير **‏‫تحليل بالبوصة المربعة‬** للتسويق المباشر التقليدي.

## <a name="catalog-requests"></a>طلبات الكتالوج

نظرًا تكوين الكتالوجات ونشرها في Commerce، يمكن استخدام ميزة **إرسال كتالوج**. تتوفر هذه الميزة على صفحتي **البحث عن عميل** و **خدمة العملاء**. بعد تحديد سجل عميل من خلال **البحث عن عميل** أو أثناء عرض حساب عملاء المحددين من **خدمة العملاء**، يمكن للمستخدمين تحديد خيار **إرسال كتالوج** الذي سيفتح مربع حوار يسمح للمستخدم بالاختيار من قائمة أي كتالوجات منشورة ونشطة. يستطيع مستخدم تحديد كتالوج وكمية ومعرف كود مصدر معين لإرسالة. عند النقر فوق زر **إرسال**، فإنه يتم تخزين طلب يمكن إدارته عن طريق تقرير **طلبات الكتالوج**. يمكن العثور على هذا التقرير بالانتقال إلى **البيع بالتجزئة والتجارة** \> **تقارير مركز الاتصال** \> **تقرير طلبات الكتالوج**. إنه يسرد كافة طلبات الكتالوج، بما في ذلك اسم العميل وتفاصيل عنوان العميل الذي طلب الكتالوج. يمكن استخدام هذا التقرير داخليًا أو يمكن نقل البيانات إلى جهة أخرى تدعم العمليات الخارجية الخاصة بإرسال الكتالوج للعميل فعليًا.

## <a name="additional-features"></a>الميزات الإضافية

في علامة التبويب **الكتالوجات**، تتوافر كذلك خيارات تكوين **جدول الدفع** و **المنتجات المجانية**. إذا تم تطبيق معرف كود المصدر بالكتالوج أثناء إدخال أمر مركز الاتصال، سيكون العميل مؤهلاً للمنتجات مجانية أو استخدام جداول الدفع لكتالوج معين كما هو محدد. إذا كان من الضروري تحديد العميل فقط لإمكانية الاختيار من جداول عمليات الدفع لربط الكتالوج وليس كل جداول عمليات الدفع النشطة في النظام، يمكن تحديد خانة الاختيار **‏‫يُسمح فقط بخطط الكتالوج** لمعرف واحد أو أكثر من معرفات كود المصدر المُعرفة لفرض ذلك الحد.

## <a name="additional-notes"></a>ملاحظات إضافية

في الوقت الحالي، عندما يتم تطبيق معرف كود المصدر على أمر المبيعات في مركز الاتصال، فإنه يتم استخدامها لتحديد الأسعار والعروض الترويجية والبرامج النصية والأصناف الإضافية/المكملة الخاصة بكتالوج. لن يمنع النظام أو يحظر طلب منتج غير موجود في الكتالوج في أمر المبيعات. إذا تم طلب صنف غير موجود بالكتالوج، سيستخدم النظام أولاً **مجموعة الأسعار** المحددة على قناة مركز الاتصال (**البيع بالتجزئة والتجارة** \> **القنوات** \> **مراكز الاتصال** \> **كل مراكز الاتصال**) لسعر الصنف أو العروض الترويجية. إذا تم العثور على أي سعر قناة محددة، فإنه سيتم استخدام سعر بيع الصنف الأساسي.