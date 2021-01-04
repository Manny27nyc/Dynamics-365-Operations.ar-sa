---
title: حدود مخزون الموقع
description: يصف هذا الموضوع وظيفة حدود مخزون المواقع.
author: perlynne
manager: tfehr
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationLimit
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-11-11
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 208662f38b06b1f230bdde5247946a9fefd57cea
ms.sourcegitcommit: d2dea9ce480f35d0c0b10615c18862695e107d55
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/23/2020
ms.locfileid: "4607269"
---
# <a name="location-stocking-limits"></a>حدود مخزون الموقع

[!include [banner](../includes/banner.md)]

يمكن استخدام صفحه **حدود التخزين في الموقع** (**أداره المستودعات \> اعداد \> المستودع \> التخزين في الموقع**) للتحكم في قدره التحميل في مواقع المستودع دون الحاجة إلى استخدام العمليات الأكثر تقدما لحسابات أحجام المنتجات الفعلية.

ويتمثل الغرض من حدود مخزون المواقع في تقييم الحد الأقصى للكمية التي يمكن ان يحتويها الموقع. يمكنك اعداد الميزة في اي مستوي من المستويات الثلاث، والتي يكون لكل منها علامة التبويب الخاصة بها في الصفحة **حدود التخزين في الموقع**:

- المنتجات
- متغيرات المنتجات
- أنواع الحاويات

بالنسبة لكل مستوي ، يمكنك تحديد قيم حقل مختلفه. سيقوم النظام بعد ذلك بتقييم قدره موقع محدد ، استنادا إلى قيمتي **الكمية** و **الوحدة** لكل صف. سيقوم أولا بتحديد سجل المطابقة المفصل. علي سبيل المثال ، سيتم تقييم الصف الذي يحتوي علي قيمه في الحقل **معرف ملف التعريف الموقع** قبل صف يحتوي علي قيمه فقط في حقل **المستودع**. سيتم أيضا تقييم القدرة المتبقية ، استنادا إلى قيمه **الكمية** الخاصة بسجل حد مخزون الموقع المستخدم.

في القسم **المنتجات** من الصفحة، يمكنك تحديد قيم الحقل التالية للبحث عن حدود التخزين في الموقع:

- المستودع
- معرف ملف تعريف الموقع
-  الموق
- معرف فئة حجم العبوة
- رقم العنصر
- الوحدة

> [!NOTE]
> ليس من الضروري تحديد قيمه **الوحدة** لكل سجل من سجلات حد التخزوين في الموقع. ستعتمد حسابات قدره الموقع علي كميات وحدات المخزون. في حاله عدم تحديد تحويل وحده لقيمه يتم استخدامها ، سيتم تخطي سجل حد مخزون الموقع ، كما لو تم تحديد قيمه **رقم صنف** آخر لها.

## <a name="example--purchase-order-receiving"></a>مثال - استلام أمر الشراء

يستند هذا المثال إلى مجموعه بيانات توضيحية *USMF* نظيفة، حيث يتم تعيين القيم التالية في علامة التبويب **متغيرات المنتج** من الصفحة **حدود التخزين في الموقع**.

| المستودع | معرف ملف تعريف الموقع | رقم العنصر | الحجم | الكمية | الوحدة |
|-----------|---------------------|-------------|------|----------|------|
| 24        | الأرضية               | D0013       | ‏‫م‬    | 300      | وحدة   |
| 24        | الأرضية               | D0013       | L    | 240      | وحدة   |
| 24        | الأرضية               | D0013       | س    | 360      | وحدة   |

يتم اعداد متغيرات منتجات مختلفه لوحده القياس. تتم محاذاة هذه المتغيرات مع حدود مخزون الموقع لثلاث بالتات (PL):

- **الحجم المتوسط:** 1 بالتة = 100 لكل واحدة (Ea)
- **الحجم الكبير:** 1 بالتة = 80 Ea
- **الحجم الصغير:** 1 بالتة = 120 Ea

ذلك، فان كل موقع يتم فيه تعيين قيمه **معرف ملف تعريف الموقع** إلى *الارضيه* يمكن ان يحمل *3* *بالتة* لرقم الصنف *D0013*.

### <a name="prepare-for-the-example"></a>تحضير للمثال

في هذا المثال ، ستقوم بتشغيل تدفق استلام أمر شراء لبندين. ومع ذلك ، يجب عليك أولا تحديث بيانات العرض التوضيحي بالطريقة التالية لضمان ان المواقع تسمح بتحويل الأصناف المختلطة ، ولا يتم استخدام الا المواقع الفارغة من *FL-002* إلى *FL-004*، ولا توجد إيه اعمال وارده مفتوحة.

1. بالنسبة للموقع *FL-001*، قم بتغيير قيمه حقل **ملف تعريف الموقع** من *FLOOR* إلى *FLOOR-05*.
1. لملف تعريف الموقع *FLOOR*، قم بتعيين خيار **السماح بالعناصر المختلطة** إلى *نعم*.
1. قم بإنشاء أمر شراء يتضمن البندين التاليين:

    | المستودع | رقم العنصر | الحجم | الكمية | الوحدة |
    |-----------|-------------|------|----------|------|
    | 24        | D0013       | س    | 4        | PL   |
    | 24        | D0013       | L    | 4        | PL   |

### <a name="process-the-example"></a>معالجة المثال

ستتلقى أولا كميه مقدارها *4* من الوحدة *بالتة* بالحجم *صغير*، وتقوم بمراجعه مواقع البنود الموضوعة للعمل الذي تم إنشاؤه. ستتلقى بعد ذل كميه مقدارها *4* من الوحدة *بالتة* بالحجم *كبير*، وتقوم بمراجعه مواقع البنود الموضوعة للعمل الذي تم إنشاؤه.

1. في تطبيق المستودع، سجل دخولك باستخدام *24* كمعرف المستخدم و *1* ككلمة مرور.
1. حدد **الوارد** \> **استلام الشراء**.
1. استلم *4* *بالتة* من رقم الصنف *D0013* بالحجم *صغير*.
1. قم بمراجعه عمل التخزين الذي تم إنشاؤه. يجب أن تشاهد النتيجة التالية:

    - 3 بالتة -\> FL-002
    - 1 بالتة -\> FL-003

1. استلم *4* *بالتة* من رقم الصنف *D0013* بالحجم *كبير*.
1. قم بمراجعه عمل التخزين الذي تم إنشاؤه. يجب أن تشاهد النتيجة التالية:

    - 1 بالتة -\> FL-003
    - 3 بالتة -\> FL-004

استنادا إلى النتائج ، قد تستنتج ان النظام فشل في تخصيص مواقع التخزين الصحيحة. والا ، لماذا قام النظام باضافه *1* *بالتة* بالحجم *كبير* إلى موقع *FL-003* في الخطوة الاخيره فقط، وليس *2* *بالتة*؟ وبذلك ، لماذا لا يوجد إجمالي *3* *بالتة* للتخزين في هذا الموقع؟

لتوضيح هذا الفشل العام ، يجب فهم معايير التحديد لحدود التخزين في الموقع. سيقوم النظام أولا بتحديد سجل المطابقة المفصل. في هذا المثال ، يعد السجل المطابق الأكثر تفصيلا هو البند حيث قيمة **الحجم** هي *كبير* ، وقيمه **الكمية** هي *240*، وقيمه **الوحدة** هي *Ea*. نظرا لأنك تملك العمل المفتوح بالفعل من الاستلام السابق لكميه *120* *Ea* بالحجم *S*، يتم حساب القدرة المتبقية علي انها *240* – *120* = *120* *Ea*. لذلك ، يمكن للقدرة المتبقية ان تحمل *1* *بالتة* بقيمة *80* *Ea*.

> [!NOTE]
> لا يمكنك استخدام حدود التخزين في الموقع للتحكم في ، علي سبيل المثال ، تزويد الأصناف التي لها كميات مختلفه في نفس الموقع. في هذه الحالة ، استخدم *قالب التزويد*.