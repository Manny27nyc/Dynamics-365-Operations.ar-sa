---
title: تخطيط دليل الحسابات المحلية
description: يوفر هذا الموضوع معلومات تساعدك في تخطيط دليل الحسابات عندما يكون لديك متطلبات لقانوني/المتطلبات المحلية لمؤسسك.
author: veneva
ms.date: 10/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts, LedgerConsolidateAccountGroup, MainAccountConsolidateAccount, DimensionDetails, MainAccountDetails
ROBOTS: ''
audience: Application User
ms.devlang: ''
ms.reviewer: roschlom
ms.tgt_pltfrm: ''
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.search.industry: ''
ms.author: veneva
ms.search.validFrom: 10/07/2021
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a99e4ef3355188f574930c1d885e53fcb3134ad1
ms.sourcegitcommit: c4500b626667185643b3a2e7fc3a004d42198d07
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 10/29/2021
ms.locfileid: "7725165"
---
# <a name="plan-your-local-chart-of-accounts"></a>تخطيط دليل الحسابات المحلية

[!include [banner](../includes/banner.md)]

يوفر هذا الموضوع معلومات تساعدك في تخطيط دليل الحسابات في حاله احتواء المؤسسة علي كيانات قانونيه يجب ان تفي بالمتطلبات الخاصة بإعدادت محلية محدده حيث تقوم باعمالها. يستخدم هذا الموضوع الشروط التالية لوصف مخططات الحسابات:

- **عمومي** - دليل الحسابات التي تستخدمها المؤسسة بشكل عام. في معظم الحالات ، ستقوم بالدمج في دليل الحسابات هذا.
- **محلي** – دليل الحسابات التي يتم تحديد الكيانات القانونية لها في بلد أو منطقه محدده.
- **مشترك** – دليل الحسابات الذي يمكن لأكثر من كيان قانوني استخدامه. يمكن مشاركه كل من الدليل العمومي للحسابات والمخططات المحلية للحسابات.

يمكنك إنشاء ومشاركه مخططات متعددة من الحسابات. يمكن استخدام دليل مشترك لحسابات أكثر من كيان قانوني ، ولكن يمكن تعيين مخطط واحد فقط لكل كيان قانوني. ويتم تحديد مخطط الحسابات المستخدم من قِبل كيان قانوني في صفحة **دفتر الأستاذ**.

عند تصميم دليل الحسابات ، يهدف العديد من المؤسسات لدليل عمومي من الحسابات. يسمح الدليل المشترك للحسابات بإنشاء دليل عمومي للحسابات. هناك فوائد لإنشاء واستخدام دليل حسابات مفرد. علي سبيل المثال ، فان الاداره والتحكم والصيانة واعداد التقارير أسهل.

يفضل معظم المؤسسات دليل عمومي للحسابات ، وهو النوع الأسهل للتطبيق. لكن بعض الكيانات القانونية تتطلب دليلا محليا من الحسابات للأسباب التالية:

- متطلبات القانوني المحلية
- متطلبات المعايير المحاسبية المحلية
- متطلبات الصناعة
- متطلبات التقارير والتحليل الخاصة بالشركة

إذا كانت مؤسستك تتطلب ان يستخدم الكيان القانوني دليلا محليا للحسابات المحلية ، سيتوفر خياران لتطبيقه:

- قم بتعيين الدليل العمومي للحسابات ، وحدد وسائل أخرى للاجتماع بالمتطلبات المحلية.
- قم بتعيين دليل محلي للحسابات للكيان القانوني ، وحدد علاقات لدليل الحسابات العمومي.

تحدد بنيه المؤسسة وبنيه التقرير الخيار الذي يتم استخدامه.

[![مخطط يوضح كيف تحدد بنيه المؤسسة ما إذا كان سيتم استخدام دليل حسابات عمومي أو محلي](./media/local-chart-of-accounts-diagram.png)](./media/local-chart-of-accounts-diagram.png)

إذا تم تعيين الدليل العمومي للحسابات إلى الكيان القانوني ، ستكون الخيارات التالية متاحه لمتطلبات التقارير المحلية للاجتماع:

- إجراء دمج المواقع.
- استخدم البعد المالي لتتبع دليل الحسابات المحلي.
- قم بإنشاء حسابات رئيسيه محليه في الدليل العمومي للحسابات.
- قم بالتعيين الخارجي إلى دليل الحسابات المحلي.

إذا تم تعيين الدليل العمومي المحلي للحسابات إلى الكيان القانوني ، ستكون الخيار التالي متاح لمتطلبات التقارير العامة للاجتماع.

## <a name="global-chart-of-accounts-assigned-to-a-legal-entity"></a>دليل عمومي للحسابات التي تم تعيينها إلى كيان قانوني

إذا كان من الضروري تعيين الدليل العمومي للحسابات إلى كيان قانوني ، ستتوفر أربعه خيارات لتكوين النظام ، كما هو موضح سابقا. بالنسبة لكافة الخيارات الأربع ، يتم تكوين دليل واحد للحسابات الفردية ويتم ربطه بكل كيان قانوني في صفحة **دفتر الأستاذ**. ويقوم كل خيار بعد ذلك باستخدام طريقه مختلفه لتلبيه متطلبات الترجمة. توضح الأقسام التالية الخطوات العالية المستوي لتكوين النظام لمتطلبات الترجمة. كما انها تصف مزايا وعيوب كل خيار.

### <a name="do-local-consolidation"></a>إجراء الدمج المحلي.

الدمج المحلي هو الطريقة الموصي بها لدليل متطلبات الحساب المحلي للاجتماع والاستفادة من وظائف النظام التي تم تصميمها لهذا الغرض.

#### <a name="set-up-consolidation-for-a-local-chart-of-accounts"></a>اعداد التوحيد لدليل محلي من الحسابات

1. قم بإنشاء دليل عمومي مفرد للحسابات التي تتضمن كافة الحسابات الرئيسية المطلوبة.
2. في كل كيان قانوني ، قم بتعيين دليل الحسابات العمومي في صحفة **دفتر الأستاذ**.
3. قم بإنشاء كيان التوحيد القانوني لكل ترجمه مطلوبه.
4. اتبع إحدى الخطوات التالية:

    - في حاله طلب ترجمه واحده فقط ، قم بتكوين حساب التوحيد في الصفحة **الحساب الرئيسي** ، أو استخدم **مجموعات التوحيد** وصفحات **حسابات التوحيد الاضافيه**.
    - إذا كان هناك أكثر من ترجمه واحده مطلوبه ، أو إذا كان كل من رقم الحساب واسم الحساب يتطلب ترجمه ، استخدم الصفحات **مجموعات التوحيد** و **حسابات التوحيد الاضافيه** لتمثل متطلبات التعريب.

5. قم بتشغيل عمليه التوحيد لتحويل القيمة من الكيان القانوني المصدر والذي يستخدم الدليل العمومي للحسابات إلى الشركة الموحدة التي تستخدم دليل الحسابات المحلي.

#### <a name="advantages"></a>فوائد

- يوفر هذا الأسلوب طريقه متناسقة للعمل عبر المؤسسة.
- تم اجراء ترجمه واحده للموضع المحلي.
- يدعم هذا الأسلوب ترجمه كل من معرف الحساب الرئيسي واسم كل حساب رئيسي.
- وهو يدعم إعدادات محلية متعددة.

#### <a name="disadvantages"></a>أضرار

- يتم إنشاء شركه توحيد اضافيه.
- تم إكمال عملية توحيد اضافيه.
- يمكن لهذا الأسلوب تقرير علي المخطط المترجم فقط بعد إتمام عمليه التوحيد.

### <a name="use-a-financial-dimension-to-track-the-local-chart-of-accounts"></a>استخدم البعد المالي لتتبع دليل الحسابات المحلي

يستخدم هذا الأسلوب بعدا ماليا يمثل قيم الابعاد المالية الحسابات الرئيسية المحلية المطلوبة للترجمة. تعمل بشكل جيد إذا كان هناك عمليه ترجمه واحده فقط مطلوبه. ومع ذلك فانه يصبح اقل استخداما عند أضافه المزيد من الترجمة والابعاد المالية.

#### <a name="set-up-a-financial-dimension-for-a-local-chart-of-accounts"></a>إعداد البعد المالي لدليل الحسابات المحلي

1. قم بإنشاء دليل عمومي مفرد للحسابات التي تتضمن كافة الحسابات الرئيسية المطلوبة.
2. في كل كيان قانوني ، قم بتعيين دليل الحسابات العمومي في صحفة **دفتر الأستاذ**.
3. قم بإنشاء البعد المالي الذي يمثل دليل الحسابات المحلي.
4. قم بإنشاء قيم البعد المالي الذي يمثل دليل الحسابات المحلي في الدليل المحلي للحسابات.
5. تحديث بنيه الحساب بحيث تتضمن البعد المالي "الدليل المحلي للحسابات".
6. تاكد ان "المخطط المحلي للحسابات" المحلي للبعد المالي له دائما قيمه ، وانه لا يسمح بقيمه فارغه. فكر في استخدام الابعاد المشتقة أو الابعاد الثابتة.
7. قم بإنشاء مجموعه الابعاد المالية حيث يكون البعد المالي "الدليل المحلي للحسابات" هو أول بعد مالي تم تحديده. يمكن استخدام مجموعه الابعاد المالية عند إنشاء ميزان المراجعة.

#### <a name="advantages"></a>فوائد

- توجد الحسابات الرئيسية لكل من المخططين العمومي والمحلي للحسابات علي مستوي الحركة. الحساب الرئيسي عمومي ، وقيمه البعد المالي محليه.
- يوفر هذا الأسلوب تقارير الوقت الحقيقي وطرق العرض الخاصة بكل من موضع التمويل العام وموضع التمويل المحلي.

#### <a name="disadvantages"></a>أضرار

- في محددات دفتر الأستاذ العام ، إذا تم تعيين حقل **القيم المستخدمة لحساب الملخص** علي **التوزيعات المحاسبية** ، سيتم استخدام الابعاد المالية التي تمثل الحساب الرئيسي للمصروفات/الأصل/الإيراد بشكل غير صحيح لحساب ملخص الحسابات المدينة والحسابات الدائنة. ونوصي بتعيين الحقل إلى مستند مصدر بدلا من استخدام قيم الابعاد المالية الصحيحة.
- إذا كانت العديد من مخططات الحسابات المحلية مطلوبه ، وتم استخدام بعدا ماليا واحدا لجميعها ، فيمكن ان تصبح قائمه قيم الابعاد المالية المستخدمة طويلة ويصعب التعامل معها.
- في حاله الحاجة إلى العديد من المخططات المحلية للحسابات ، واستخدام بعد مالي منفصل لتمثيل كل واحد منها ، يمكن ان يتاثر قابليه الاستخدام والأداء للنظام باضافه الابعاد المالية ومجموعات الابعاد المالية.
- نوصي بمراعاه عدد الابعاد المالية التي تتطلبها وعدد القيم في كل منها وعدد مجموعات الابعاد المالية ، وذلك لان كافة هذه العوامل يمكن ان تؤثر علي أداء النظام.

### <a name="create-local-main-accounts-in-the-global-chart-of-accounts"></a>قم بإنشاء حسابات رئيسيه محليه في الدليل العمومي للحسابات

*ما هو محرر النسخ الذي يطالب بـ:* في هذا المنهج، تتضمن الحسابات الرئيسية المحلية في دليل الحسابات العمومي الحسابات الرئيسية في دليل الحسابات المحلي في دليل الحسابات العمومي.

*الإصدار الأصلي:* الحسابات الرئيسية المحلية داخل أسلوب شهادة الاصاله العمومية هي انه يتم تضمين الحسابات الرئيسية لشهادة الاصاله المحلية في شهادة الاصاله العمومية.

*هل يجب ان تقول هذا:* بهذه الطريقة، يتم تضمين الحسابات الرئيسية المحلية في الدليل المحلي للحسابات في دليل الحسابات العمومي.


#### <a name="set-up-local-main-accounts-in-the-global-chart-of-accounts"></a>قم بإعداد حسابات رئيسيه محليه في الدليل العمومي للحسابات

1. إنشاء دليل حسابات مفرد يتضمن الحسابات الرئيسية لكل من الدليل العمومي للحسابات ودليل الحسابات المحلي.
2. في كل كيان قانوني ، قم بتعيين دليل الحسابات في صفحة **دفتر الأستاذ**.
3. قم بإنشاء إجمالي الحسابات في دليل الحسابات لجمع الحسابات الرئيسية التي تمثل نفس الغرض.
4. إنشاء تجاوزات الكيانات القانونية في كل حساب محلي لمنع الحركات من الكيانات القانونية الأخرى التي لم يتم تصميم الحساب المحلي لها.
5. إنشاء تجاوزات الكيان القانوني في كل حساب عمومي لمنع الحركات من الكيانات القانونية للترجمة.

#### <a name="advantages"></a>فوائد

- يتوفر عرض الوقت الحقيقي لكل من موضع التمويل العام وموضع التمويل المحلي في التقارير المحددة وكذلك في طرق عرض معينه في النظام ، مثل التقرير المالي لميزانيه الميزانية. كما يمكن الوصول اليها باستخدام الزر **فتره** في الحساب الإجمالي.
- ليس لديك إيه شريحة اضافيه في حساب دفتر الأستاذ.

#### <a name="disadvantages"></a>أضرار

- ويتم تحديد إجمالي استخدام الحساب وامكانيه الظهور. علي سبيل المثال ، لا تظهر الحسابات الاجماليه في صفحة قائمة **ميزان المراجعة**.
- ويتطلب الصيانة مجهودا إضافيا.
- ويتطلب إنشاء التقارير المالية مجهودا يدويا إضافيا.

### <a name="do-external-mapping-to-the-local-chart-of-accounts"></a>قم بالتعيين الخارجي إلى دليل الحسابات المحلي

يفترض تبني الدليل العمومي للحسابات انك تقوم باداره التعيين والترجمة خارج النظام. في هذا الأسلوب ، يمكنك فقط إنشاء دليل عمومي مفرد للحسابات في Microsoft Dynamics 365 Finance ومعالجه المتطلبات خارج النظام.

#### <a name="set-up-external-mapping-to-a-local-chart-of-accounts"></a>قم بإعداد التعيين الخارجي إلى دليل الحسابات المحلي

1. قم بإنشاء دليل عمومي مفرد للحسابات التي تتضمن كافة الحسابات الرئيسية المطلوبة.
2. في كل كيان قانوني ، قم بتعيين دليل الحسابات العمومي في صحفة **دفتر الأستاذ**.
3. قم بالتعيين إلى دليل الحسابات المحلي خارج Finance.

#### <a name="advantages"></a>فوائد

- يوفر هذا الأسلوب طريق موحدة للعمل عبر المؤسسة.

#### <a name="disadvantages"></a>أضرار

- لا يتوفر اي تقارير محليه من النظام.
- يعد هذا الأسلوب عرضه للخطا عند إنشاء التقارير المالية.

## <a name="local-chart-of-accounts-assigned-to-legal-entity"></a>دليل محلي للحسابات التي تم تعيينها إلى كيان قانوني

إذا قررت المؤسسة عدم استخدام دليل عمومي للحسابات عبر الكيانات القانونية ، يتم إنشاء دليل منفصل لحسابات كل دليل محلي فريد. ويتم بعد ذلك ربط كل كيان قانوني بدليل الحسابات المطابق في صفحة **دفتر الأستاذ**.

### <a name="do-global-consolidation"></a>إجراء الدمج العمومي

في هذا الأسلوب ، يتم استخدام شركه توحيد لإظهار ودمج الارصده من كل شركه محليه في الدليل العمومي المرتبط بالحسابات العامة في الشركة الموحدة. تتطلب هذه الطريقة الاحتفاظ بتعيين لكل دليل محلي من الحسابات لدليل عمومي للحسابات في الشركة الموحدة.

#### <a name="set-up-global-consolidation"></a>إعداد الدمج العمومي

1. قم بإنشاء دليل منفصل للحسابات لكل كيان قانوني يحتوي علي دليل محلي مختلف من الحسابات. إذا كان لآيه كيانات قانونيه نفس دليل الحسابات المحلي ، يكون هناك دليل محلي واحد فقط للحسابات ، ويمكن مشاركته.
2. في كل كيان قانوني ، قم بتعيين دليل الحسابات المناسب في صحفة **دفتر الأستاذ**.
3. اختياري: قم بإنشاء دليل حسابات لدليل عمومي لحسابات كل شركه توحيد تحتوي علي دليل حسابات عمومي مختلف.
4. إنشاء كيان قانوني للدمج لكل مستوي من مستويات التوحيد المطلوبة ، وتعيين دليل الحسابات المناسب في صفحة **دفتر الأستاذ**.
5. اتبع إحدى الخطوات التالية:

    - إذا كان هناك توحيد واحد مطلوب ، فقم بتكوين حساب التوحيد في الصفحة **الحساب الرئيسي**.
    - إذا كان هناك أكثر من دمج واحد مطلوب، أو إذا كان كل من رقم الحساب واسم الحساب يتطلب ترجمه ، استخدم الصفحات **مجموعات الدمج** و **حسابات الدمج الاضافيه** لتمثل متطلبات دليل الحسابات العمومي.

6. قم بتشغيل عمليه التوحيد لتحويل الارصده من الكيانات القانونية المحلية إلى الكيان القانوني المجمع. يستخدم هذا الكيان القانوني المدمج حسابات التوحيد التي قمت بتحديدها في الخطوة 5.

#### <a name="advantages"></a>فوائد

- يتم تطبيق تنسيق مقاييس المحاسبة المحلية أصلا.
- ويوفر هذا الأسلوب لفريق التمويل المحلي طريقه أسهل للعمل.

#### <a name="disadvantages"></a>أضرار

- لا يتوفر عرض في الوقت الحقيقي للمنصب العام.
- قد يتم تشغيل عمليه التوحيد بشكل أكثر من مره.

## <a name="additional-resources"></a>الموارد الإضافية

- [تخطيط دليل الحسابات](plan-chart-of-accounts.md)
- [تكوين دفاتر الأستاذ](configure-ledger.md)
- [الأبعاد المالية والترحيل](Default-dimensions.md#balancing-dimension)
- [مجموعات الأبعاد المالية](financial-dimension-sets.md)
- [نظرة عامة على التجميع والاستبعاد](../budgeting/consolidation-elimination-overview.md)
- [مجموعات حساب التوحيد وحساب التوحيد الإضافية](../budgeting/consolidation-account-groups-consolidation-accounts.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]