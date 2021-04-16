---
title: حسابات نموذج تكوين المنتج
description: يصف هذا الموضوع كيفية إنشاء عمليات حسابية للسمات في نموذج تكوين المنتج
author: t-benebo
ms.date: 03/18/2021
ms.topic: article
ms.search.form: PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-03-18
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: eaf6264f060d33575740ad38e7a65158baba296b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829608"
---
# <a name="product-configuration-model-calculations"></a>حسابات نموذج تكوين المنتج

[!include [banner](../includes/banner.md)]

يصف هذا الموضوع كيفية إنشاء عمليات حسابية للسمات في نموذج تكوين المنتج.

## <a name="prerequisites"></a>المتطلبات الأساسية

يتم استخدام العمليات الحسابية بنموذج تكوين منتج لحساب قيم التكوين لمنتج. قبل أن تتمكن من البدء في إعداد الحسابات، يجب أن يكون نموذج تكوين المنتج ذي الصلة موجودًا. للحصول على نظرة عامة على عملية الإعداد لنماذج التكوين والمهام ذات الصلة، راجع [إعداد نموذج تكوين المنتج](set-up-maintain-product-configuration-model.md).

## <a name="create-a-calculation"></a>إنشاء عملية حسابية

تتكون العملية الحسابية من تعبير وسمة هدف. لمزيد من المعلومات، راجع [أسئلة شائعة حول حسابات نماذج تكوين المنتج](calculate-product-configuration-models.md).

لإنشاء حساب لنموذج منتج موجود، اتبع الخطوات التالية.

1. انتقل إلى **إدارة معلومات المنتج \> عام \>  نماذج تكوين المنتجات**.
1. افتح نموذج تكوين منتج، ثم حدد **تحرير**.
1. في علامة التبويب السريعة **العمليات الحسابية**، حدد **إضافة** لإضافة عملية حسابية، ثم عيِّن الحقول التالية:

    - **الاسم‏‎** – أدخل اسمًا للعملية الحسابية.
    - **الوصف** - أدخل وصفًا للعملية الحسابية.
    - **السمة الهدف** - حدد السمة التي تقوم باجراء الحساب لها.

1. حدد **تحرير التعبير**.
1. في مربع الحوار **إدخال حساب**، أضف السمات والعوامل والقيم المطلوبة إلى التعبير. لمزيد من المعلومات حول كيفية التعامل مع هذه العناصر، راجع [قيود التعبير وقيود الجدول في نماذج تكوين المنتجات](expression-constraints-table-constraints-product-configuration-models.md).
1. عندما يكون التعبير الخاص بك جاهزًا، حدد **موافق**.

## <a name="calculation-examples"></a>أمثلة العمليات الحسابية

يوفر هذا القسم بعض الامثله التي تعرض كيفيه عمل الحسابات.

### <a name="example-1"></a>مثال1

السمة الهدف هي قيمة منطقية، ويستخدم الحساب التعبير الشرطي التالي:

`If[(decimalAttribute1 / decimalAttribute2) < 1, True, False]`

يقوم هذا التعبير بإرجاع قيمة *صواب* للسمة الهدف إذا كانت `decimalAttribute2` أكبر من أو يساوي `decimalAttribute1`. بخلاف ذلك، تقوم بإرجاع قيمة *خطأ*.

### <a name="example-2"></a>مثال2

يستخدم هذا المثال سمة النص `textFixedList` كسمة هدف. تحتوي هذه السمة على القائمة الثابتة التالية.

| قيمة | قيمة الحلول |
|---|---|
| أ | 1a |
| B | 2b |
| C | 2c |

تظهر اللقطة التالية كيف قد تبدو إعدادات هذه السمة في النظام الخاص بك.

![إعدادات نوع السمة للمثال 2](media/model-calculations-example2.png "إعدادات نوع السمة للمثال 2")

يتم استخدام السمة في العبارة الشرطية التالية:

`If[integerAttribute < 150, 0, 2]`

إذا كانت `integerAttribute` أقل من 150، تُرجع هذه العبارة القيمة النصية للسجل الأول في القائمة الثابتة، *A*. وبخلاف ذلك، تقوم بإرجاع القيمة النصية للسجل الثالث في القائمة الثابتة، *C*.

> [!NOTE]
> القائمة الثابتة تعادل التعداد الصفري (التعداد)، ويتم الوصول إلى قيمها من خلال قيمة عدد صحيح مناسب. لذلك، تتم مطابقة أول قيمة قائمة ثابتة (*A*) مع *0*، وتتم مطابقة القيمة الثانية (*B*) مع *1*، وتتم مطابقة القيمة الثالثة (*C*) مع *2*.

### <a name="example-3"></a>المثال الثالث

يستخدم هذا المثال سمة النص `textFixedList` من المثال السابق. يستخدم أيضًا سمة نص أخرى، `textAttribute`، التي تحتوي علي القائمة الثابتة التالية.

| قيمة | قيمة الحلول |
|---|---|
| AA | 1aa |
| BB | 2bb |

تظهر اللقطة التالية كيف قد تبدو إعدادات هذه السمة في النظام الخاص بك.

![إعدادات نوع السمة للمثال 3](media/model-calculations-example3.png "إعدادات نوع السمة للمثال 3")

يتم حساب قيمة السمة `textFixedList` باستخدام العبارة الشرطية التالية:

`If[textAttribute == "1aa", 0, 2]`

إذا كانت القيمة `textAttribute` تشتمل على قيمة حل تساوي *1aa*، فإن هاذ التعبير يقوم بإرجاع القيمة النصية للسجل الأول في القائمة الثابتة `textFixedList`، *A*. بخلاف ذلك، تقوم بإرجاع القيمة النصية للسجل الثالث في القائمة الثابتة `textFixedList`، *C*.

> [!NOTE]
> - يجب ان تستخدم العبارة الشرطية قيمه الحل الخاصة بالسمة
> - يمكن استخدام سمات نص القائمة الثابتة فقط في العمليات الحسابية.

## <a name="see-also"></a>راجع أيضًا

- [‬‏‫الأسئلة المتداولة حول حسابات نماذج تكوين المنتجات](calculate-product-configuration-models.md)
- [إضافة قيد تعبير إلى نموذج تكوين منتج](tasks/add-expression-constraint-product-configuration-model.md)
- [نظرة عامة على نماذج تكوين المنتجات](product-configuration-models.md)