---
title: مبدأ المحاسبة ترحيل إلى حساب التكاليف
description: يقدم هذا الموضوع نظرة عامة على مبدأ المحاسبة ترحيل إلى حساب التكاليف.
author: rachel-profitt
ms.date: 05/02/2022
ms.topic: article
ms.search.form: InventPosting, InventItemGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2022-05-02
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 45dc1775c0db83faa89a7a1fa799bdd070d1b09a
ms.sourcegitcommit: 283e237d7bd2a76dd3a8ff64685b0a5f146edd25
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/06/2022
ms.locfileid: "8721387"
---
# <a name="post-to-charge-account-accounting-principle"></a>مبدأ المحاسبة ترحيل إلى حساب التكاليف

يسمح لك مبدأ المحاسبة *ترحيل إلى حساب المصاريف* حساب أي فروق تحدث في سعر الوحدة وتسويتها بسهولة أكبر بين الترحيل المادي والترحيل المالي أو التكاليف غير المباشرة على الأصناف المشتراة أو المصاريف في أمر الشراء. 

بإمكان تكوينين لأكواد التكاليف للحسابات الدائنة في صفحة **كود التكاليف‬** (**الحسابات الدائنة‬ \> إعداد التكاليف‬ \> كود التكاليف‬**) أن تتسبب في تأثير أمر الشراء على تقييم أصول المخزون:

- بالنسبة إلى أكواد التكاليف حيث تم تعيين **نوع المدين‬** إلى *صنف* وحقل **نوع الائتمان‬** إلى *حساب دفتر الأستاذ*، يعمل حساب دفتر الأستاذ المحدد كحساب استيعاب كحساب اختلاف المخزون‬.
- بالنسبة إلى أكواد التكاليف حيث تم تعيين **نوع المدين‬** إلى *صنف* وحقل **نوع الائتمان** إلى *عميل/مورّد*، سيتم احتساب التكاليف على أنها تكلفة مادية، وسيتم استخدام حساب تغيير المخزون الخاص بالصنف.

## <a name="european-special-accounting-rule"></a>قاعدة المحاسبة الخاصة الأوروبية

في أوروبا، يتم استخدام مبدأ المحاسبة *ترحيل إلى حساب التكاليف* في أغلب الأحيان لتضمين قاعدة محاسبة معينة. على سبيل المثال، يتم عادةً استخدام أحد الأساليب التالية لحساب تغييرات المخزون:

- **أسلوب تكلفة المبيعات** – يدعم تكوين ملف تعريف ترحيل المخزون القياسي هذا الأسلوب. مبدأ المحاسبة *ترحيل إلى حساب التكاليف* غير مطلوب.
- **طبيعة أسلوب المصروفات** – تستخدم المؤسسات الصغيرة هذا الأسلوب في أغلب الأحيان. إنه يتضمن عادة الخطوات التالية:

    1. يتم حساب مصروفات السلع أو الخدمات بالكامل في وقت الاستلام
    2. في نهاية الفترة، يتم جرد المخزون.
    3. يتم ترحيل تعديل يدوي للكمية والقيمة إلى المخزون. (الحساب المقابل هو حساب تباين المخزون الذي يعوض المصاريف التي تم ترحيلها في الخطوة 1. وبالتالي، فإنك ترى التباين في قيمة المخزون في هذا الحساب فقط.)

يسمح لك مبدأ *الترحيل إلى حساب التكاليف* أتمتة عمليتي الترحيل. وبهذه الطريقة، يمكنك إزالة ترحيل تسوية إقفال نهاية الفترة يدويًا.

## <a name="enable-the-post-to-charge-account-accounting-principle"></a>تمكين مبدأ المحاسبة ترحيل إلى حساب التكاليف

لتمكين مبدأ المحاسبة *ترحيل إلى حساب التكاليف*، اتبع الخطوات التالية.

1. انتقل إلى **الحسابات الدائنة \> الإعداد \> محددات الحسابات الدائنة**.
2. من علامة التبويب **الفاتورة**، على علامة التبويب السريعة **الفاتورة**، عيّن الخيار **ترحيل إلى حساب التكاليف في دفتر الأستاذ** إلى *نعم*.
3. قم بإغلاق الصفحة.

## <a name="prerequisites-and-recommended-parameters-for-the-post-to-charge-account-accounting-principle"></a>المتطلبات الأساسية والمعلمات الموصى بها لمبدأ المحاسبة "ترحيل إلى حساب التكاليف"

إذا كنت تخطط لحساب مصاريف الشراء واختلافات المخزون، فيجب استيفاء المتطلبات الأساسية التالية:

- على علامة تبويب **الفاتورة** في صفحة **معلمات الحسابات الدائنة** (**الحسابات الدائنة \> الإعداد \> معلمات الحسابات الدائنة**)، يجب تعيين الخيار **ترحيل إلى حساب التكاليف في دفتر الأستاذ** إلى *نعم*.
- في صفحة **مجموعات نماذج الصنف‬** (**إدارة التكلفة‬ \> إعداد سياسات محاسبة المخزون‬ \> مجموعات نماذج الصنف**)، يجب تعيين جميع الخيارات التالية إلى *نعم* لكل مجموعة نماذج ذات صلة تحتوي على أصناف تم تضمينها في أمر الشراء:

    - ترحيل المخزون الفعلي
    - ترحيل المخزون المالي
    - استحقاق الالتزام على إيصال استلام المنتجات

- على علامة التبويب **التسليم** في صفحة **معلمات التدبير والتوريد** (**التدبير والتوريد \> الإعداد \> معلمات التدبير والتوريد**)، يجب تعيين الخيار **إنشاء تكاليف في إيصال استلام المنتجات‬** إلى *نعم*.
- على علامة التبويب **محاسبة المخزون** في صفحة **معلمات إدارة المخزون والمستودعات** (**إدارة المخزون \> الإعداد \> معلمات إدارة المخزون والمستودعات**)، يجب تعيين الخيار **ترحيل إيصال التعبئة في دفتر الأستاذ‬** إلى *نعم*.
- على علامة التبويب **أمر الشراء** في صفحة **الترحيل** (**إدارة المخزون \> الإعداد \> الترحيل‏‎ \>الترحيل‏‎**)، يجب تحديد الحسابات الرئيسية التي تنطبق على كل صنف ذي صلة لكل نوع من أنواع الترحيل التالية:

    - نفقات الشراء، غير المفوترة
    - نفقات الشراء للمنتج
    - اختلاف المخزون

## <a name="example-scenario-1-change-in-unit-cost-price"></a>سيناريو المثال 1: التغيير في سعر تكلفة الوحدة

المثال التالي هذا السيناريو لديه المتطلبات الأساسية التالية:

- نموذج التكلفة م يرد أولاً يصرف أولاً‬ (FIFO)

يوفر الإجراء التالي مثالاً يوضح ما يحدث عند تغيير سعر تكلفة الوحدة في أمر الشراء.

1. إنشاء أمر شراء لكمية قيمتها 1 لصنف ما لديه سعر وحدة من 100.00.
2. أكد أمر الشراء.
3. ترحيل إيصال استلام المنتجات لأمر الشراء.
4. التحقق من صحة الإيصال على إيصال استلام المنتجات. يعرض الجدول التالي عينة إيصال.

    | نوع الترحيل | الحساب الرئيسي | اسم الحساب الرئيسي | نوع الحساب | المدين/الدائن؟ | حساب مقاصة. | مادي/فعلي؟ | ‏‏المبلغ‬ |
    |---|---|---|---|---|---|---|---|
    | الشراء، اختلاف المخزون | 600170 | مواد اختلاف المخزون | المصروفات | دائن‬ | لا | الفعلي | 100.00- |
    | تكلفة المواد المشتراة المستلمة | 140100 | مخزون المواد | الأصل | مدين | ‏‏نعم‬ | الفعلي | 100.00 |
    | نفقات الشراء، غير المفوترة | 600180 | إيصالات المواد | المصروفات | مدين | ‏‏نعم‬ | الفعلي | 100.00 |
    | الشراء، الاستحقاق | 200140 | عمليات الشراء المستحقة | الالتزام | دائن‬ | ‏‏نعم‬ | الفعلي | 100.00- |

5. ترحيل الفاتورة لأمر الشراء يتضمن سعر وحدة محدثًا من 110.00.
6. التحقق من صحة الإيصال في الفاتورة. يعرض الجدول التالي عينة إيصال.

    | نوع الترحيل | الحساب الرئيسي | اسم الحساب الرئيسي | نوع الحساب | المدين/الدائن؟ | حساب مقاصة. | مادي/فعلي؟ | ‏‏المبلغ‬ |
    |---|---|---|---|---|---|---|---|
    | الشراء، اختلاف المخزون | 600170 | مواد اختلاف المخزون | المصروفات | دائن‬ | لا | المالية | -10.00 |
    | تكلفة المواد المشتراة المستلمة | 140100 | مخزون المواد | الأصل | مدين | ‏‏نعم‬ | المالية | 100.00- |
    | نفقات الشراء، غير المفوترة | 600180 | إيصالات المواد | المصروفات | مدين | ‏‏نعم‬ | المالية | 100.00- |
    | الشراء، الاستحقاق | 200140 | عمليات الشراء المستحقة | الالتزام | دائن‬ | ‏‏نعم‬ | المالية | 100.00 |
    | تكلفة المواد المشتراة المفوترة | 140100 | مخزون المواد | الأصل | مدين | لا | المالية | 110.00 |
    | نفقات الشراء للمنتج | 600180 | إيصالات المواد | المصروفات | دائن‬ | لا | المالية | 110.00 |
    | رصيد المورد | 211000 | الحساب التجاري للحسابات الدائنة | الالتزام | دائن‬ | لا | المالية | -110.00 |

## <a name="example-2-charges-and-indirect-costs-on-the-purchase-order"></a>المثال رقم 2: المصاريف والتكاليف غير المباشرة في أمر الشراء

المثال التالي هذا السيناريو لديه المتطلبات الأساسية التالية:

- نموذج التكلفة FIFO
- **كود التكاليف 1:** بند الخصم وحساب دفتر الأستاذ بنسبة 10%
- **كود التكاليف 2:** بند الخصم وائتمان العميل/المورّد لـ 10.00 متناسب
- **التكلفة غير المباشرة:** إضافة 2.00% إلى سعر الشراء.

يوفر الإجراء التالي مثالاً يوضح ما يحدث عند تضمين التكاليف والتكاليف غير المباشرة في أمر الشراء.

1. إنشاء أمر شراء لكمية قيمتها 1 لصنف ما لديه سعر وحدة من 100.00.
2. إضافة كود تكاليف واحد لـ 10.00 يخصم الصنف ويضيف إلى دفتر الأستاذ.
3. إضافة كود تكاليف واحد لـ 10.00 يخصم الصنف ويضيف إلى العميل/المورّد.
4. توزيع التكاليف على بنود أوامر الشراء.
5. أكد أمر الشراء.
6. ترحيل إيصال استلام المنتجات لأمر الشراء.
7. التحقق من صحة الإيصال على إيصال استلام المنتجات. يعرض الجدول التالي عينة إيصال.

    | نوع الترحيل | الحساب الرئيسي | اسم الحساب الرئيسي | نوع الحساب | مدين/دائن؟ | حساب مقاصة. | مادي أو فعلي | ‏‏المبلغ‬ |
    |---|---|---|---|---|---|---|---|
    | الشراء، اختلاف المخزون | 600170 | مواد اختلاف المخزون | المصروفات | دائن‬ | لا | الفعلي | -110.00 |
    | التكلفة غير المباشرة المقدرة المدمجة | 600520 | التكاليف غير المباشرة المستوعبة | المصروفات | دائن‬ | ‏‏نعم‬ | الفعلي | -2.40 |
    | شحن المشتريات | 600120 | تكاليف الشحن/ النقل | المصروفات | دائن‬ | لا | الفعلي | -10.00 |
    | تكلفة المواد المشتراة المستلمة | 140100 | مخزون المواد | الأصل | مدين | ‏‏نعم‬ | الفعلي | 122.40 |
    | نفقات الشراء، غير المفوترة | 600180 | إيصالات المواد | المصروفات | مدين | ‏‏نعم‬ | الفعلي | 110.00 |
    | الشراء، الاستحقاق | 200140 | عمليات الشراء المستحقة | الالتزام | دائن‬ | ‏‏نعم‬ | الفعلي | -110.00 |

8. ترحيل الفاتورة لأمر الشراء.
9. التحقق من صحة الإيصال في الفاتورة. يعرض الجدول التالي عينة إيصال.

    | نوع الترحيل | الحساب الرئيسي | اسم الحساب الرئيسي | نوع الحساب | المدين/الدائن؟ | حساب مقاصة. | مادي/فعلي؟ | ‏‏المبلغ‬ |
    |---|---|---|---|---|---|---|---|
    | الشراء، اختلاف المخزون | 600170 | مواد اختلاف المخزون | المصروفات | دائن‬ | لا | المالية | 0.00 |
    | التكلفة غير المباشرة المقدرة المدمجة | 600520 | التكاليف غير المباشرة المستوعبة | المصروفات | مدين | ‏‏نعم‬ | المالية | 2.40 |
    | التكلفة غير المباشرة المدمجة | 600520 | التكاليف غير المباشرة المستوعبة | المصروفات | مدين | لا | المالية | -2.40 |
    | تكلفة المواد المشتراة المستلمة | 140100 | مخزون المواد | الأصل | دائن‬ | ‏‏نعم‬ | المالية | -110.00 |
    | نفقات الشراء، غير المفوترة | 600180 | إيصالات المواد | المصروفات | دائن‬ | ‏‏نعم‬ | المالية | -110.00 |
    | الشراء، الاستحقاق | 200140 | عمليات الشراء المستحقة | الالتزام | مدين | ‏‏نعم‬ | المالية | 110.00 |
    | تكلفة المواد المشتراة المفوترة | 140100 | مخزون المواد | الأصل | مدين | لا | المالية | 110.00 |
    | نفقات الشراء للمنتج | 600180 | إيصالات المواد | المصروفات | دائن‬ | لا | المالية | 110.00 |
    | رصيد المورد | 211000 | الحساب التجاري للحسابات الدائنة | الالتزام | دائن‬ | لا | المالية | -110.00 |