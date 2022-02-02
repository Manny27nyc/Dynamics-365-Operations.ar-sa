---
title: تحليلات Commerce (إصدار أولي)
description: يشرح هذا الموضوع كيفية تثبيت إمكانية التحليل واستخدامها في Microsoft Dynamics 365 Commerce.
author: AamirAllaq
ms.date: 11/23/2021
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: aamiral
ms.search.validFrom: 2021-11-12
ms.openlocfilehash: 8cfe2af756315b5be3eb22d99376a96166fffc52
ms.sourcegitcommit: f9fca3d55b47e615e5ef64669dab184e057ec234
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/23/2021
ms.locfileid: "7862763"
---
# <a name="commerce-analytics-preview"></a>تحليلات Commerce (إصدار أولي)

[!include [banner](includes/banner.md)]

يوضح هذا الموضوع كيفية تثبيت تحليلات Commerce (إصدار أولي)، وإمكانية التحليل الوظيفي المضمن في Microsoft Dynamics 365 Commerce.

## <a name="commerce-analytics-preview-live-demo"></a>عرض توضيحي مباشر لتحليلات Commerce (إصدار أولي)

يمكنك تجربة [عرض توضيحي مباشر لتحليلات Commerce (إصدار أولي)](https://aka.ms/CommerceAnalyticsDemo).

![ملخص تحليلات Commerce (إصدار أولي)](media/CommerceAnalytics_Summary.png)
![مدفوعات تحليلات Commerce (إصدار أولي)](media/CommerceAnalytics_Payments.png)
![نشاط ويب تحليلات Commerce (إصدار أولي)](media/CommerceAnalytics_WebActivity.png)


## <a name="commerce-analytics-preview-system-architecture"></a>بنية نظام تحليلات Commerce (إصدار أولي)

### <a name="key-components"></a>المكونات الرئيسية

تتكون تحليلات Commerce (إصدار أولي) من المكونات الأساسية التالية:

- تقارير Power BI التفاعلية الجاهزة للاستخدام
- طرق عرض SQL في تحليلات Azure Synapse
- بيانات العنصر والأنطولوجيا في Azure Data Lake
- البيانات الأولية في Data Lake

![المكونات الأساسية لبنية نظام تحليلات Commerce](media/CommerceAnalyticsArchitecture_v2.png)

### <a name="data-flow"></a>تدفق البيانات

#### <a name="step-1-data-generation"></a>الخطوة 1: إنشاء البيانات

تنشأ البيانات إما كبيانات معاملات أو بيانات سلوكية من أحد المصادر التالية:

- يستخدم إقران مركز الاتصال عميل Commerce HQ لمعالجة أوامر المبيعات.
- يقوم الصراف في نقطة البيع (POS) بمعالجة حركات المبيعات.
- يتم إنشاء المبيعات في التطبيقات المخصصة باستخدام Commerce بلا عنوان (Commerce Scale Unit).
- يقوم متسوق التجارة الإلكترونية باستعراض موقع ويب التجارة الإكترونية.
- يقوم متسوق التجارة الإلكترونية بإصدار طلب على موقع ويب التجارة الإكترونية.
- يتم إنتاج البيانات بواسطة أنظمة أخرى، مثل Dynamics 365 Connected Spaces.

#### <a name="step-2-ingestion-and-pre-processing"></a>الخطوة 2: الاستيعاب والمعالجة المسبقة

تنتقل بيانات الحركة إلى HHQ إما بشكل مباشر (في حالة الأوامر التي يتم التقاطها مباشرة في عميل Commerce HQ) أو عبر Commerce Scale Unit (في حالة الأوامر التي يتم الحصول عليها في نقطة البيع، أو في التجارة الإكترونية، أو في العملاء المخصصين الذين يستخدمون Commerce بدون عنوان).

عندئذ يتم استخدام ميزة التصدير إلى Data Lake لنسخ بيانات المعاملات إلى مستودع البيانات الخاصة بك كبيانات أولية. في مستودع البيانات، يتم تخزين البيانات الأولية في مجلد الجداول.

يتم إرسال بيانات نشاط الويب الخاصة بالتجارة الإلكترونية مباشرة إلى مستودع البيانات. يتم إرسال البيانات التي يتم إنتاجها بواسطة أنظمة أخرى، مثل Dynamics 365 Connected Spaces، مباشرة إلى مستودع البيانات بواسطة تلك الأنظمة.

#### <a name="step-3-transformation-and-aggregation"></a>الخطوة 3: التحويل والتجميع

بعد أن تكون البيانات الأولية موجودة في مستودع البيانات الخاص بك، تقوم خدمة تحليلات Commerce بقراءتها وتحويلها وتجميعها وكتابتها مرة أخرى إلى مستودع البيانات في نموذج الكيانات المنطقية (في مجلد الكيانات) والمقاييس المجمعة (في مجلد الأنطولوجيات).

#### <a name="step-4-querying"></a>الخطوة 4: الاستعلام

يتم استخدام Azure Synapse التحليلات للاستعلام عن البيانات الموجودة في مستودع البيانات الخاص بك عبر واجهة Transact-SQL (T-SQL). تتضمن هذه الواجهة طرق عرض SQL. وتمكن طرق عرض SQL الاستعلام المتحد عن البيانات في مستودع البيانات، سواء كان ذلك بشكل مباشر عبر عميل T-SQL (بالنسبة للتحليل المخصص) أو عبر أداة مرئيات مثل Power BI.

#### <a name="step-5-modeling-and-serving"></a>الخطوة 5: التصميم والخدمة

تنتقل البيانات التي يتم الاستعلام عنها بواسطة تحليلات Azure Synapse إلى semantic model في Power BI. اعتمادًا على نوع البيانات، فإنه إما قد تم استيراده بشكل دوري في الذاكرة إلى Power BI أو يتم الاستعلام عنه بشكل مباشر في وقت التشغيل.

وأخيرًا، يتم تقديم البيانات في مرئيات Power BI، بحيث يمكن للمستخدمين عرضها والتعامل معها.

## <a name="commerce-analytics-preview-functional-overview"></a>نظرة عامة حول وظائف تحليلات Commerce (إصدار أولي)

### <a name="summary"></a>الملخص

يتضمن تطبيق قالب تحليلات Commerce صفحات التقارير الرئيسية التالية:

1. [عوامل تصفية المستوي الأعلى](#TopLevelFilters)
2. [المنتجات](#ProductsPage)
3. [العملاء](#CustomersPage)
4. [القنوات](#ChannelsPage)
5. [ال‏‏مبيعات](#SalesPage)
6. [الهوامش](#MarginsPage)
7. [مرتجعات](#ReturnsPage)
8. [الخصومات](#DiscountsPage)
9. [المدفوعات](#PaymentsPage)
10. [العملاء](#CustomersPage)
11. [مقارنة](#ComparisonPage)
12. [نشاط ويب](#WebActivityPage)
13. [نشاط الويب - عامل تصفية المستوى الأعلى](#WebActivityTopLevelFilters)

####  <a name="top-level-filters"></a>عوامل تصفية <a name="TopLevelFilters"></a> ذات المستوى الأعلى

- إعدادات البيانات

    - السنة
    - ربع السنة
    - الشهر
    - الأسبوع
    - اليوم

- إعدادات القناة

    - كيان قانوني
    - نوع القناة
    - نوع العميل
    - نوع المبيعات
    - التدفقات
    - التدرج الهرمي للمؤسسات

- إعدادات المنتج

    - التدرج الهرمي للفئات
    - ‏‏الفئة‬

####  <a name="products"></a>منتجات <a name="ProductsPage"></a>

- المبيعات
- الهامش
- مرتجعات

####  <a name="customers"></a>عملاء <a name="CustomersPage"></a>

- المبيعات
- الهامش
- مرتجعات

#### <a name="channels"></a>قنوات <a name="ChannelsPage"></a>

- المبيعات
- الهامش
- مرتجعات

### <a name="sales"></a>مبيعات <a name="SalesPage"></a>

- حسب موقع التسليم
- حسب القناة/المتجر/الوحدة الطرفية
- بواسطة الموظف
- حسب التاريخ
- بالساعة
- حسب فئة المنتج

### <a name="margins"></a>هوامش <a name="MarginsPage"></a>

- حسب موقع التسليم
- منتج ثانوي
- حسب التاريخ

### <a name="returns"></a>مرتجعات <a name="ReturnsPage"></a>

- المرتجع حسب المبلغ

    - حسب المتجر
    - منتج ثانوي
    - حسب التاريخ

- المرتجع حسب المعاملة

    - حسب المتجر
    - منتج ثانوي
    - حسب التاريخ

### <a name="discounts"></a>خصومات <a name="DiscountsPage"></a>

- حسب المتجر
- منتج ثانوي
- حسب التاريخ
- التجزئة

    - كيان قانوني
    - المتجر
    - نوع الخصم
    - اسم الخصم
    - المنتج

### <a name="payments"></a>مدفوعات <a name="PaymentsPage"></a>

- حسب القناة/الوحدة الطرفية
- حسب طريقة/نوع الدفع
- حسب التاريخ
- التجزئة

    - كيان قانوني
    - نوع القناة
    - المتجر
    - الوحدة الطرفية
    - طريقة الدفع

### <a name="customers"></a>عملاء <a name="CustomersPage"></a>

- القيمة الدائمة (LTV)

    يتم حساب LTV استنادًا إلى المبلغ الإجمالي الذي يقضيه العميل عبر كافة قنوات مبيعات Dynamics 365 Commerce (بما في ذلك تقطة البيع والتجارة الإلكترونية ومركز الاتصال).

- Recency

    يتم حساب Recency استنادًا إلى عدد الأيام منذ آخر تفاعل تعاملي للعميل مع المؤسسة. حاليًا، لا يضع recency إشارات التفاعل غير التعاملية في الاعتبار، مثل نشاط استعراض التجارة الإلكترونية.

- التكرار

    يتم حساب التردد استنادًا إلى تفاعل التعاملي للعميل مع المؤسسة. حاليًا، لا يضع التردد إشارات التفاعل غير التعاملية في الاعتبار، مثل نشاط استعراض التجارة الإلكترونية.

- طول العلاقة

    يتم حساب طول العلاقة استنادًا إلى عدد الأيام منذ إنشاء سجل العميل في النظام.

- عدد الحركات

### <a name="comparison"></a>مقارنة <a name="ComparisonPage"></a>

- مقارنة المنتجات حسب الفترة الزمنية

    - المبيعات فرق المبيعات
    - الهوامش واختلاف الهوامش

- العميل حسب الفترة

    - المبيعات فرق المبيعات
    - الهوامش واختلاف الهوامش

### <a name="web-activity"></a>نشاط ويب <a name="WebActivityPage"></a>

#### <a name="top-level-filters"></a>عوامل تصفية <a name="WebActivityTopLevelFilters"></a> ذات المستوى الأعلى

- نطاق التاريخ
- نوع القناة
- التدفقات
- التدرج الهرمي للفئات

#### <a name="acquisitions"></a>عمليات الاستحواذ

- طرق عرض الصفحة

    - حسب البلد أو المنطقة
    - منتج ثانوي
    - حسب حالة تسجيل دخول المستخدم
    - حسب التاريخ

- أوامر التجارة الإلكترونية
- معدل التحويل

    - حسب التاريخ

- قمع التحويل

    - طريقة عرض الصفحة حسب نوع الصفحة (الصفحة الرئيسية أو صفحة الفئة أو صفحة تفاصيل المنتج)
    - إضافة إلى عربة التسوق
    - ‏‫سداد‬ مع الخروج
    - الشراء

#### <a name="sessions"></a>جلسات

جلسة العمل عبارة عن حلقة من زيارة المستخدم إلى موقع الويب الخاص بالتجارة الإلكترونية. يتم اعتبار جلسة العمل منتهية بعد 30 دقيقة من عدم النشاط أو 24 ساعة من الاستخدام النشط.

- حسب البلد أو المنطقة
- حسب الأصل (مرجع خارجي)
- حسب حالة تسجيل دخول المستخدم
- عدد جلسات العمل

    - حسب التاريخ
    - حسب صفحة الإدخال

- الأمر لكل جلسة عمل

    - حسب التاريخ

- معدل ارتداد جلسة العمل

    تعتبر جلسة العمل التي تقوم بتجاهلها هي الجلسة التي يقوم المستخدم بالخروج منها فور زيارة موقع ويب التجارة الإلكترونية. لمزيد من المعلومات، راجع [معدل الارتداد](https://en.wikipedia.org/wiki/Bounce_rate).

- معدل النقرات لكل جلسة عمل

#### <a name="visitors"></a>الزوار

يتم تعريف زائر مجهول على موقع التجارة الإلكترونية بشكل فريد استنادًا إلى المستعرض المحدد والجهاز المحدد الذي يستخدمه المستخدم. لا تقوم تحليلات Commerce بتتبع الزوار المجهولين عبر المستعرضات أو الأجهزة المختلفة. ويتم تعريف الزائر المجهول الذي يستخدم المستعرض نفسه على الجهاز نفسه بشكل فريد عبر جلسات المستخدم المتعددة، حتى يتم مسح بيانات المستعرض المخزنة مؤقتًا أو تنقضي المدة الزمنية (عادةً ما تكون 12 شهرًا)، أيهما يحدث أولاً.

إذا قام الزوار باستعراض موقع التجارة الإلكترونية أثناء قيامهم بتسجيل الدخول، فيمكن أن توفر تحليلات Commerce معلومات إضافية عنها. تعتمد هذه المعلومات على العلاقة الموجودة التي تتمتع بها المؤسسة الخاصة بك مع الزوار كنتيجة لعمليات الشراء السابقة الخاصة بهم عبر كافة قنوات مبيعات Dynamics 365 Commerce (بما في ذلك نقاط البيع والتجارة الإلكترونية ومركز الاتصال). تتضمن المعلومات الإضافية recency وطول العلاقة والقيمة الدائمة وبيانات التكرار.

- هامش الزائر
- متوسط أوامر الزائرين
- متوسط مبيعات الزائرين
- عدد زائري التجارة الإلكترونية

    - حسب التاريخ
    - حسب المكان

        في الوقت الحالي، يمكن أن توفر تحليلات Commerce التفاصيل على مستوى البلد/المنطقة فقط لمعرفة المعارف الدقيقة لموقع زوار التجارة الإلكترونية.

    - حسب recency

        يتم حساب Recency استنادًا إلى عدد الأيام منذ آخر تفاعل تعاملي للعميل مع المؤسسة. حاليًا، لا يضع recency إشارات التفاعل غير التعاملية في الاعتبار، مثل نشاط استعراض التجارة الإلكترونية.

    - حسب طول العلاقة

        يتم حساب طول العلاقة استنادًا إلى عدد الأيام منذ إنشاء سجل العميل في النظام.

    - حسب القيمة الدائمة (LTV)

        يتم حساب LTV استنادًا إلى المبلغ الإجمالي الذي يقضيه العميل عبر كافة قنوات مبيعات Dynamics 365 Commerce (بما في ذلك تقطة البيع والتجارة الإلكترونية ومركز الاتصال).

    - حسب التكرار

        يتم حساب التردد استنادًا إلى تفاعل التعاملي للعميل مع المؤسسة. حاليًا، لا يضع التردد إشارات التفاعل غير التعاملية في الاعتبار، مثل نشاط استعراض التجارة الإلكترونية.

#### <a name="impressions"></a>العروض

يُعد العرض طريقة عرض مفردة لمنتج مرئي عن طريق زائر تجارة إلكترونية. على سبيل المثال، يقوم زائر التجارة الإلكترونية بالانتقال إلى الصفحة الرئيسية لموقع ويب التجارة الإلكترونية وعرض منتج سجادة اليوجا في الوحدة النمطية لقائمة **الأعلى مبيعًا**. ثم يقوم الزائر بعرض منتج سجادة اليوجا نفسه في الوحدة النمطية لقائمة **العناصر المقترحة لك**. في هذه الحالة، يوجد عرضين للمنتج. 

حاليًا، يتم تتبع العروض في الأسطح التالية:

- القوائم (على سبيل المثال، **موصى به**، **الأفضل مبيعًا**، **العناصر المقترحة لك**، **المتداول**)
- وحدة عربة التسوق
- حاوية نتائج البحث
- حاوية نتائج بحث الفئة

حاليًا، لا يتم وضع المنتجات التي يتم تقديمها في الوحدة النمطية الدوارة أو المرئيات المخصصة في المقاييس المرتبطة بالعرض في الاعتبار.

تتضمن الصفحة **تقرير العرض** القياسات التالية:

- عدد العروض

    - حسب نوع الصفحة والوحدة النمطية

        نوع الصفحة هو النوع العام للصفحة التي يتم تعريفها لكل صفحة على موقع ويب التجارة الإلكترونية. نوع الوحدة النمطية هو نوع الوحدة النمطية المرئية للتجارة الإلكترونية التي يظهر المنتج فيها.

        لعرض العروض بواسطة الوحدة النمطية، قد تحتاج إلى التنقل لأسفل في مرئيات الصفحة والوحدة النمطية.

    - منتج ثانوي
    - حسب حالة تسجيل دخول المستخدم
    - حسب التاريخ

- عدد نقرات العروض

    يحدث نقر العرض عندما يحدد زائر التجارة الإلكترونية منتجًا مرئيًا. بشكل نموذجي، يتم نقل الزائر بعد ذلك إلى صفحة تفاصيل المنتج الخاصة بالمنتج.

- نسبة النقرات إلى الطلبات (CTR) الخاصة بالعروض

    يتم حساب CTR كإجمالي عدد نقرات العروض مقسومًا على العدد الإجمالي للعروض.

## <a name="commerce-analytics-preview-installation"></a>تثبيت تحليلات Commerce (إصدار أولي)

> [!NOTE]
> إن تحليلات Commerce (إصدار أولي) قيد المعاينة في مناطق الولايات المتحدة وكندا والمملكة المتحدة وأوروبا وجنوب شرق أسيا وشرق أسيا وأستراليا واليابان. إذا كانت بيئة Finance and Operations الخاصة بك في أي من هذه المناطق، فإنه يمكنك تمكين هذه الميزة في البيئة الخاصة بك باستخدام Microsoft Dynamics Lifecycle Services (LCS). قبل أن تتمكن من استخدام هذه الميزة، راجع [تكوين التصدير إلى Azure Data Lake](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).

### <a name="enable-and-configure-commerce-analytics-preview"></a><a name="enableCommerceAnalytics"></a>تمكين تحليلات Commerce وتكوينها (إصدار أولي)

لتثبيت تحليلات Commerce (إصدار أولي)، يجب أن يكون لديك أذونات لإنشاء موارد في اشتراك Azure. كما يجب أن يكون لديك أذونات لتثبيت الوظائف الإضافية في LCS. وفيما يلي نظرة عامة على الخطوات:

1. [قم بإرسال نموذج مأخذ الإصدار الأولي لتحليلات Commerce (إصدار أولي)](#joinPreview).
2. [تمكين التصدير إلى Data Lake وتكوينه](#enableExportToDataLake).
3. [الوظيفة الإضافية تمكين تحليلات Commerce وتكوينها (إصدار أولي)](#enableCommerceAnalyticsAddin).
4. [قم بإنشاء توقيع الرمز المميز للوصول المشترك (SAS) لحساب التخزين الخاص بك](#getSASToken).
5. [قم بتنزيل البرامج النصية الخاصة بالنشر لطرق عرض Azure Synapse ](#downloadSynapseDeploymentScripts).
6. [قم بتثبيت وتكوين Azure Synapse workspace](#configureAzureSynapse).
7. [قم بتثبيت تطبيق قالب Power BI ](#powerbi).

### <a name="submit-the-preview-intake-form-for-commerce-analytics-preview"></a><a name="joinPreview"></a>إرسال نموذج مأخذ الإصدار الأولي لتحليلات Commerce (إصدار أولي)

قم بإرسال [نموذج مأخذ الإصدار الأولي لتحليلات Commerce (إصدار أولي)](https://forms.office.com/r/vW5VLJGXZ2). اسمح بما يصل إلى ثلاثة أيام عمل لمعالجة النموذج. بعد المعالجة، سيتم إرسال بريد إلكتروني للتأكيد إلى عنوان البريد الإلكتروني الذي قمت بتقديمه في النموذج

### <a name="enable-and-configure-export-to-data-lake"></a><a name="enableExportToDataLake"></a>تمكين التصدير إلى Data Lake وتكوينه

تعتمد تحليلات Commerce (الإصدار الأولي) على ميزة تصدير إلى Data Lake لتصدير Commerce HQ إلى Data Lake والحفاظ على البيانات محدثة. قبل تكوين تحليلات Commerce (إصدار أولي)، قم بتمكين التصدير إلى Data Lake وتكوينه باتباع الخطوات التالية في [تكوين التصدير إلى Azure Data Lake](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).

بينما تقوم بتكوين التصدير إلى Data Lake، قم بتدوين المعلومات التالية، لأنه يجب عليك إدخالها لاحقًا:

- <a name="keyVault"></a>اسم نظام اسم المجال (DNS) الخاص بمخزن رئيسي، والأسماء السرية حيث تقوم بتخزين مُعرف التطبيق وسر التطبيق. لمزيد من المعلومات، راجع [إضافة أسرار إلى المخزن الرئيسي](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#addsecrets).
- <a name="storageAccount"></a>اسم حساب التخزين لمثيل Data Lake. لمزيد من المعلومات، راجع [إنشاء حساب Data Lake Storage (Gen2) في الاشتراك الخاص بك](../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md#createsubscription).

### <a name="enable-and-configure-the-commerce-analytics-preview-add-in"></a><a name="enableCommerceAnalyticsAddin"></a>الوظيفة الإضافية تمكين تحليلات Commerce وتكوينها (إصدار أولي)

لتثبيت الوظيفة الإضافية لتحليلات Commerce (إصدار أولي) في LCS، يجب أن تكون مسؤول بيئة في LCS للبيئة التي تخطط لاستخدامها.

لتثبيت الوظيفة الإضافية لتحليلات Commerce (الإصدار الأولي) وتكوينها، اتبع هذه الخطوات.

1. قم بتسجيل الدخول إلى [LCS](https://lcs.dynamics.com/)، وانتقل إلى بيئتك.
2. على الصفحة **البيئة**، انتقل إلى علامة التبويب **الوظائف الإضافية للبيئة**، حدد **تثبيت وظيفة إضافية جديدة**.
3. في مربع الحوار، حدد **تحليلات Commerce (إصدار أولي)**.

    في حالة عدم إدراج **تحليلات Commerce (إصدار أولي)**، تأكد من الانضمام إلى برنامج Insider.

4. في مربع الحوار **إعداد الوظيفة الإضافية**، أدخل المعلومات التالية.

    | المعلومات | المصدر | قيمه المثال |
    |---|---|---|
    | معرف مستأجر Azure AD للبيئة الخاصة بك | قم بتسجيل الدخول إلى [مدخل Azure](https://portal.azure.com/)، وافتح الخدمة **Azure Active Directory**. ثم افتح الصفحة **الخصائص**، وقم بنسخ القيمة في الحقل **معرف الدليل**. | 72f988bf-0000-0000-00000-2d7cd011db47 |
    | اسم DNS للمخزن الرئيسي الخاص بك | أدخل [اسم DNS](#keyVault) للمخزن الرئيسي الخاص بك. يجب عليك تدوين هذه القيمة في القسم السابق. | `https://contosod365datafeedpoc.vault.azure.net/` |
    | السر الذي يحتوي على معرف التطبيق | أدخل [الاسم السري الذي يخزن معرف التطبيق](#keyVault). يجب عليك تدوين هذه القيمة في القسم السابق. | معرف التطبيق |
    | السر الذي يحتوي على سر التطبيق | أدخل [الاسم السري الذي يخزن سر التطبيق](#keyVault). يجب عليك تدوين هذه القيمة في القسم السابق. | سر التطبيق |

5. قم بقبول شروط العرض عن طريق تحديد خانة الاختيار، ثم حدد **تثبيت**.

    يقوم النظام بتثبيت الوظيفة الإضافية لتحليلات Commerce (إصدار أولي) وتكوينها للبيئة. يمكن أن تستغرق هذه العملية بضع دقائق. بعد الاكتمال، فإنه يجب إدراج **تحليلات Commerce (إصدار أولي)** على الصفحة **البيئة**، ويجب **تثبيت** الحالة.

### <a name="generate-a-sas-token-for-your-storage-account"></a><a name="getSASToken"></a>إنشاء رمز SAS المميز لحساب التخزين الخاص بك

يعمل رمز SAS المميز على تمكين الكيانات الخارجية من الوصول إلى حساب التخزين الخاص بك والحصول على مجموعة محددة من الامتيازات لفترة زمنية محدودة. سيستخدم Azure Synapse رمز SAS المميز للوصول إلى البيانات الأساسية في Data Lake.

> [!NOTE]
> وبسبب التقييد المعروف لتحليلات Commerce (الإصدار الأولي)، فسيفقد مثيل Azure Synapse حق الوصول إلى مستودع البيانات عند انتهاء رمز SAS المميز. وبالتالي، عند إنشاء رمز SAS المميز، فإنه يجب تعيين الحد الأقصى لتاريخ انتهاء الصلاحية الذي تسمح به سياسات الأمان الخاصة بمؤسسك.

لإنشاء رمز SAS المميز، اتبع هذه الخطوات.

1. في مدخل Azure، انتقل إلى [حساب التخزين](#storageAccount) الذي قمت بإنشائه أثناء تكوين التصدير إلى Data Lake.
2. في الجزء الأيسر، ضمن حساب التخزين، حدد **توقيع الوصول المشترك**.
3. في الصفحة **خيارات SAS**، قم بتعيين الحقول التالية.

    | الحقل | قيمة |
    |---|---|
    | الخدمات المسموح بها | حدد **كبير الحجم**. |
    | أنواع الموارد المسموح بها | حدد **الخدمة**، و **الكائن**، و **الكائن**. |
    | أذونات مسموح بها | حدد **القراءة**، و **الكتابة**، و **الحذف**، و **القائمة**، و **إضافة**، و **إنشاء**. |
    | أذونات تعيين إصدارات كبيرة الحجم | حدد **يعمل على تمكين حذف الإصدارات**. |
    | وقت/تاريخ البدء وتاريخ انتهاء الصلاحية | قم بتعيين تاريخ ووقت بدء وانتهاء لرمز SAS المميز حسب الاقتضاء. |
    | عناوين IP المسموح بها | اترك هذا الحقل فارغًا. |
    | البروتوكولات المسموح بها | حدد **HTTPS فقط**. |
    | طبقة التوجيه المفضلة | حدد **أساسي (افتراضي)**. |
    | مفتاح التوقيع | حدد **key1** أو **key2**، حسب الاقتضاء. |

4. حدد **إنشاء SAS وسلسلة اتصال**.
5. انسخ القيمة الموجودة في الحقل **رمز SAS المميز**، ثم الصقها في محرر نصوص مثل المفكرة.

### <a name="download-the-deployment-scripts-for-azure-synapse-views"></a><a name="downloadSynapseDeploymentScripts"></a>قم بتنزيل البرامج النصية الخاصة بالنشر لطرق عرض Azure Synapse

لإنشاء طرق العرض المطلوبة ونشرها في Azure Synapse workspace، فإنه يجب تشغيل مجموعة من البرامج النصية. اتبع هذه الخطوات لتنزيل البرامج النصية.

1. في GitHub، انتقل إلى المستودع [microsoft/Dynamics365Commerce.Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions) (repo).
2. قم بتنزيل البرامج النصية على الكمبيوتر المحلي الخاص بك عن طريق استنساخ المستودع أو تنزيله كملف من نوع zip.

### <a name="install-and-configure-an-azure-synapse-workspace"></a><a name="configureAzureSynapse"></a>تثبيت وتكوين Azure Synapse workspace

لتثبيت مساحة العمل  Azure Synapse workspaceوتكوينها، اتبع هذه الخطوات:

1. قم بتثبيت Azure Synapse workspace في اشتراك Azure الخاص بك. لمزيد من المعلومات، راجع [تشغيل سريع: إنشاء Synapse workspace](/azure/synapse-analytics/quickstart-create-workspace).
2. في المفكرة أو في محرر نصوص آخر، افتح ملف البرنامج النصي **SetupSynapse.sql** من المجلد الموجود على الكمبيوتر المحلي الخاص بك الذي قمت باستنساخ مستودع Dynamics365Commerce.Solutions أو تنزيله عليه في القسم السابق. سيكون ملف البرنامج النصي ضمن المجلد /Pipeline/CommerceAnalyticsSynapse/. في البرنامج النصي، استبدل نص العنصر النائب بالقيم كما هو موضح في الجدول التالي.

    | نص العنصر النائب | قيمة الاستبدال |
    |---|---|
    | placeholder_storageaccount | اسم [حساب التخزين](#storageAccount) الذي قمت بإنشائه أثناء تكوين التصدير إلى Data Lake. |
    | <a name="phContainer"></a>placeholder_container | اسم حاوية التخزين التي تم إنشاؤها في مثيل Data Lake الخاص بك بعد تثبيت الوظيفة الإضافية التصدير إلى Data Lake بنجاح في LCS. للحصول على اسم الحاوية، فإنه يجب استخدام "مستكشف التخزين" في مدخل Azure لاستعراض حساب التخزين الخاص بك. |
    | placeholder_sastoken | [رمز SAS المميز](#getSASToken) الذي قمت بإنشاؤه. تأكد من إزالة علامة الاستفهام (**؟**) من بداية قيمة رمز SAS المميز. |
    | <a name="phUserPwd"></a>placeholder_password | كلمة مرور قوية من اختيارك. قم بتدوين كلمة المرور هذه. سيتم تعيينها ككلمة مرور لحساب **reportreadonlyuser** الجديد الذي يقوم البرنامج النصي بإنشاءه. يُرجى **عدم** إدخال كلمة مرور حساب **sqladminuser**. |

3. انسخ المحتويات المحدثة الموجودة في ملف البرنامج النصي.
4. في مدخل Azure، انتقل إلى Azure Synapse workspace الجديدة. في الصفحة **نظرة عامة**، حدد **فتح Synapse Studio**.
5. في Synapse Studio، حدد **جديد \> البرنامج النصي SQL**، والصق المحتويات الخاصة بملف البرنامج النصي إلى محرر البرنامج النصي SQL.
6. تأكد من تعيين الحقل **استخدام قاعدة البيانات** إلى **رئيسي**.
7. حدد **تشغيل**، وانتظر حتى ينتهي البرنامج النصي من العمل. سيؤدي تنفيذ البرنامج النصي بنجاح إلى إنشاء قاعدة البيانات لتحليلات Commerce وبيانات الاعتماد الخاصة بالوصول إلى مستودع البيانات وحساب مستخدم للقراءة فقط الذي سيستخدمه Power BI للاتصال بالمثيل Azure Synapse.
8. على الكمبيوتر المحلي الخاص بك، افتح Windows PowerShell في وضع المسؤول، وانتقل إلى المجلد /Pipeline/CommerceAnalyticsSynapse/ ضمن المجلد الذي قمت باستنساخ المستودع Dynamics365Commerce.Solutions به أو تنزيله.
9. قم بإعداد سياسة تنفيذ Windows PowerShell من خلال تشغيل الأمر التالي.

    ```powershell
    Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
    ```

10. إذا لم تكن الوحدة النمطية لـ SQL Server PowerShell مثبتة بالفعل، قم بتثبيتها من خلال تشغيل الأمر التالي.

    ```powershell
    Install-Module sqlserver
    ```

    > [!NOTE]
    > أثناء تثبيت الوحدة النمطية، قد تتم مطالبتك بتثبيت موفر NuGet. في هذه الحالة، حدد **Y** لتثبيت موفر NuGet. قد تتم مطالبتك أيضًا بتأكيد أنك تقوم بتثبيت الوحدات النمطية من مستودع غير موثوق به. في هذه الحالة، حدد **Y** لمتابعة عملية التثبيت. يمكنك بشكل اختياري تشغيل **Set-PSRepository** cmdlet للوثوق في المستودع **PSGallery**.

11. انشر طرق عرض Azure Synapse عن طريق تشغيل الأمر التالي.

    ```powershell
    .\PublishSynapseViews.ps1 -serverName SERVER_NAME -password PASSWORD -storageAccount STORAGE_ACCOUNT -containerName CONTAINER_NAME -datarootpath DATA_ROOT_PATH
    ```

    عند تشغيل هذا الأمر، استبدل قيم العنصر النائب كما هو موضح في الجدول التالي.

    | قيمة العنصر النائب | قيمة الاستبدال |
    |---|---|
    | SERVER_NAME | اسم النقطة النهائية Azure Synapse SQL بلا خادم. يمكنك الحصول على هذه القيمة من الصفحة **نظرة عامة** لـ Azure Synapse workspace في مدخل Azure. |
    | كلمة المرور | كلمة المرور الخاصة بالحساب **sqladminuser**. |
    | STORAGE_ACCOUNT | اسم حساب التخزين لـ Data Lake. |
    | CONTAINER_NAME | اسم الحاوية التي تم إنشاؤها بواسطة ميزة التصدير إلى Data Lake. هذه الحاوية هي الحاوية نفسها التي قمت بتعيينها كقيمة [placeholder_container](#phContainer) في الخطوة 2. |
    | DATA_ROOT_PATH | اسم المجلد ضمن الحاوية التي تحتوي على كافة البيانات. |

    > [!NOTE]
    > يمكنك العثور على اسم حساب التخزين واسم الحاوية ومسار جذر البيانات باستخدام مستعرض التخزين Azure وحساب تخزين Data Lake الخاص بك في مدخل Azure.

12. انتظر حتى ينتهي البرنامج النصي من العمل. سيؤدي تنفيذ البرنامج النصي بنجاح إلى إنشاء طرق عرض SQL في مثيل Azure Synapse SQL بلا خادم.

### <a name="install-the-power-bi-template-app"></a><a name="powerbi"></a>تثبيت تطبيق قالب Power BI

لتثبيت تطبيق قالب Power BI لتحليلات Commerce (الإصدار الأولي)، اتبع هذه الخطوات.

1. سجل الدخول إلى مدخل [Power BI](https://powerbi.microsoft.com/) باستخدام معرف المؤسسة الخاص بك.
2. قم بتثبيت تطبيق قالب تحليلات Commerce (إصدار أولي) Power BI عن طريق الانتقال إلى [https://aka.ms/cdireport-installapp](https://aka.ms/cdireport-installapp). قد تحصل على تحذير يشير إلى أنه لم يتم إدراج التطبيق على AppSource. حدد **تثبيت**.
3. إذا قمت بتثبيت التطبيق للمرة الأولى، تخطى إلى الخطوة 5. إذا قمت بتثبيت هذا التطبيق من قبل، فإنه يتم عرض الخيارات التالية لتحديث التطبيق:

    - **تحديث مساحة العمل والتطبيق** – قم بتحديث تطبيق القالب الحالي واستبدل إعدادات التطبيق الحالي، مثل اسم مثيل التطبيق وتكوينات الإذن.
    - **تحديث محتوى مساحة العمل فقط دون تحديث التطبيق** – قم بتحديث تطبيق القالب الموجود، لكن مع الاحتفاظ بإعدادات التطبيق الحالية. *يُعد هذا الخيار هو الخيار المُوصى به لتحديثات التطبيقات.*
    - **تثبيت نسخة أخرى من التطبيق في مساحة عمل جديدة** – قم بإنشاء مساحة عمل جديدة، ثم قم بإنشاء نسخة من تطبيق القالب الموجود فيه. ستترك مساحة العمل الموجودة سليمة.

4. حدد أحد خيارات التحديث، ثم حدد **تثبيت**.
5. افتح التطبيق المثبت بتحديد **التطبيقات** في الجزء الأيسر ثم حدد التطبيق.
6. قم بتوصيل التطبيق بمصدر البيانات الخاص بك عن طريق تحديد **اتصال**. إذا قمت بتثبيت التطبيق قبل ذلك، حدد الارتباط **الاتصال بالبيانات الخاص بك** في شريط الرسائل الأصفر.
7. قم بتعيين الحقول التالية.

    | الحقل | قيمة |
    |---|---|
    | الخادم | أدخل اسم نقطة نهاية Azure Synapse SQL بلا خادم التي قمت بإنشاءها في القسم السابق. يمكنك الحصول على هذه القيمة من الصفحة **نظرة عامة** لـ Azure Synapse workspace في مدخل Azure. |
    | قاعدة البيانات | أدخل **CommerceAnalytics**. |
    | اللغة | حدد قيمة في القائمة. يتم استخدام هذا الحقل لأسماء الفئات والمنتجات المترجمة. إن القيمة حساسة لحالة الأحرف. |
    | نطاق التاريخ | حدد قيمة في القائمة. سيتم استيراد البيانات الخاصة بعدد الشهور المحدد إلى مجموعة البيانات Power BI. تؤثر القيمة التي قمت بتحديدها على حجم مجموعة البيانات والوقت المطلوب للمزامنة. |

8. حدد **التالي**. وتتم مطالبتك بإدخال بيانات الاعتماد للاتصال بقاعدة بيانات Azure Synapse SQL. قم بتعيين الحقول كما هو موضح في الجدول التالي.

    | الحقل | قيمة |
    |---|---|
    | طريقة المصادقة | حدد **أساسي**. |
    | اسم المستخدم | أدخل **reportreadonlyuser**. |
    | كلمة المرور | أدخل القيمة التي قمت باستبدال العنصر النائب [placeholder_password](#phUserPwd) داخل البرنامج النصي SetupSynapse.sql. كلمة المرور هذه هي كلمة المرور الخاصة بالحساب **reportreadonlyuser**. |

9. حدد **تسجيل الدخول والاتصال**.
10. انتظر حتى يتم تحديث مجموعة البيانات بنجاح. ثم حدد الزر **تحرير التطبيق** لفتح مساحة عمل التطبيق، حيث يمكنك عرض حالة التحديث لمجموعة البيانات. في مساحة عمل التطبيق، يمكنك أيضًا إعداد جداول تحديث تلقائية لمجموعة البيانات الخاصة بك، وإدارة الأذونات وإعادة تسمية مثيل التطبيق.

### <a name="privacy"></a><a name="privacy"></a>الخصوصية

خصوصيتك تهمنا. لمعرفه المزيد، اقرأ [بيان الخصوصية](https://go.microsoft.com/fwlink/?LinkId=521839).

[!INCLUDE[footer-include](../includes/footer-banner.md)]