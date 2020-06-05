---
title: تحسينات على وظيفة ترحيل كشف الحساب
description: يصف هذا الموضوع التحسينات التي تم إجراؤها على ميزة ترحيل كشف الحساب.
author: josaw1
manager: AnnBe
ms.date: 05/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: retail
ms.author: anpurush
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 68abef8f28c04a4f6f88e638c8abf944d06a32c4
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057245"
---
# <a name="improvements-to-statement-posting-functionality"></a>تحسينات على وظيفة ترحيل كشف الحساب

[!include [banner](includes/banner.md)]

يصف هذا الموضوع المجموعة الأولى من التحسينات التي تم إجراؤها على ميزة ترحيل كشف الحساب. تتوفر هذه التحسينات في الإصدار 7.3.2 من Microsoft Dynamics 365 for Finance and Operations.

## <a name="activation"></a>التنشيط

افتراضيًا، أثناء نشر Finance and Operations 7.3.2، تم إعداد البرنامج لاستخدام الميزة القديمة لعمليات ترحيل كشف الحساب. لتمكين ميزة ترحيل كشف حساب المحسنة، يجب تشغيل مفتاح التكوين الخاص به.

- انتقل إلى **إدارة النظام** \> **الإعداد** \> **تكوين الترخيص**، ثم تحت عقدة **Retail and Commerce** قم بإلغاء تحديد خانة الاختيار **كشوف الحسابات (قديمة)** وحدد خانة الاختيار **كشوف الحسابات**.

عند تشغيل مفتاح التكوين **كشوف الحسابات** الجديد، يتوفر عنصر قائمة جديد يسمى **كشوف الحسابات**. يتيح لك عنصر القائمة هذا إنشاء وحساب وترحيل كشوف الحساب يدويًا. وسيتوفر أيضًا أي كشف حساب يقوم بالتسبب في حدوث خطأ عند استخدام عملية ترحيل المجموعة من خلال عنصر القائمة هذا. (عند تشغيل مفتاح تكوين **كشوف الحسابات (قديمة)** يتوفر عنصر قائمة يسمى **‏‫فتح كشوف حسابات‬**.)

يتضمن Commerce عمليات التحقق من الصحة التالية التي تتعلق بمفاتيح التكوين هذه:

- لا يمكن تشغيل كلا من مفتاحي التكوين في نفس الوقت.
- يجب استخدام نفس مفاتيح التكوين لكافة العمليات التي يتم تنفيذها على كشف محدد أثناء دورة حياته (الإنشاء والحساب، والمسح والترحيل وهكذا). على سبيل المثال، لا يمكن إنشاء واحتساب كشف حساب أثناء تشغيل مفتاح التكوين **كشوف الحسابات (قديمة)‬** ومن ثم حاول ترحيل كشف الحساب نفسه أثناء تشغيل مفتاح التكوين **كشف حساب**.

> [!NOTE]
> نوصي أن تستخدم مفتاح التكوين **كشوف الحسابات** مع ميزة ترحيل كشف الحساب المحسنة، إلا إذا كان لديك أسباب إجبارية لاستخدام مفتاح التكوين **كشوف الحسابات (قديمة)‬** بدلاً من ذلك. ستستمر Microsoft في الاستثمار في ميزة ترحيل كشف الحساب الجديدة والمحسنة، ومن المهم الانتقال إليها في أقرب فرصة الاستفادة منها. سيتم إهمال ميزة ترحيل كشف الحساب القديمة اعتبارًا من الإصدار 8.0.

## <a name="setup"></a>إعداد

كجزء من التحسينات لميزة ترحيل كشف الحساب، تم تقديم ثلاثة معلمات جديدة في علامة التبويب السريعة **كشف الحساب** في علامة التبويب **ترحيل** في صفحة **معلمات Commerce**:

- **‏‫تعطيل مسح كشف الحساب‬** هذا الخيار قابل للتطبيق فقط على ميزة ترحيل كشف الحساب القديمة. نوصي بتعيين هذا الخيار إلى **لا** لمنع المستخدمين من مسح كشوف الحساب الموجودة بحالة شبه مرحلة. إذا تم مسح كشوف الحساب الموجودة في بحالة شبه مرحلة، تصبح البيانات تالفة. يجب تعيين هذا الخيار إلى **نعم** فقط في الحالات الاستثنائية.
- **حجز المخزون أثناء الحساب‬** - نوصي أن تستخدم الوظيفة الدفعية **ترحيل المخزون** لحجز المخزون، وتعيين هذا الخيار إلى **لا**. عند تعيين هذا الخيار إلى **لا**، فإن ميزة ترحيل كشف الحساب المحسنة لا تحاول إنشاء إدخالات حجز المخزون في وقت الحساب (إذا لم تكن الإدخالات قد تم إنشاؤها بالفعل عن طريق الوظيفة الدفعية **ترحيل المخزون**). بدلاً من ذلك، تقوم هذه الميزة بإنشاء إدخالات مخزون الحجز فقط في وقت الترحيل. وهذا التنفيذ هو اختيار التصميم ويعتمد على أن الإطار الزمني بين عملية الحساب وعملية الترحيل صغير بشكل عام. ومع ذلك، إذا كنت ترغب في حجز المخزون في وقت الحساب، يمكنك تعيين هذا الخيار إلى **نعم**.

    دائمًا ما تحتفظ ميزة ترحيل كشف الحساب القديمة بالمخزون أثناء عملية حساب كشف الحساب (إذا لم يتم إجراء الحجز مسبقاً من خلال الوظيفة الدفعية **ترحيل المخزون**)، بغض النظر إعداد هذا الخيار.

- **تعطيل الجرد مطلوب** – عندما يتم تعيين هذا الخيار إلى **نعم**، تستمر عملية الترحيل لكشف الحساب، حتى لو كان الفرق بين المبلغ المحتسب ومبلغ الحركة في كشف الحساب خارج نطاق الحد المعين في علامة التبويب السريعة **كشف الحساب** للمتاجر.

بالإضافة إلى ذلك، تم تقديم المعلمات التالية في علامة‏‎ التبويب السريعة **معالجة الدُفعات‬** في علامة التبويب **ترحيل** في صفحة **معلمات Commerce**: 

- **الحد الأقصى لعمليات ترحيل الكشوف المتوازية‬** - يحدد هذا الحقل عدد المهام الدفعية التي سيتم استخدامها لترحيل كشوف حساب متعددة. 
- **الحد الأقصى لعدد مؤشرات الترابط لمعالجة الأوامر لكل كشف الحساب** - يمثل هذا الحقل الحد الأقصى لعدد مؤشرات الترابط المستخدمة بواسطة الوظيفة الدفعية لترحيل كشوف الحساب لإنشاء أوامر مبيعات وفوترتها لكشف حساب واحد. سيتم حساب الحد الأقصى لعدد مؤشرات الترابط التي سيتم استخدامها بواسطة عملية ترحيل كشوف الحساب استنادًا إلى القيمة الموجودة في هذه المعلمة مضروبة في المعلمة **الحد الأقصى لعمليات ترحيل الكشوف المتوازية‬**. قد يؤثر تعيين قيمة عالية جدًا لهذه المعلمة على أداء عملية ترحيل كشوف الحساب بشكل سلبي.
- **الحد الأقصى لبنود الحركة المضمنة في التجميع** - يحدد هذا الحقل عدد بنود الحركة التي سيتم تضمينها في حركة مجمعة واحدة قبل إنشاء واحدة جديدة. يتم إنشاء الحركات المجمعة بناء على معايير تجميع مختلفة، مثل العميل أو تاريخ العمل أو الأبعاد المالية. ومن الضروري الملاحظة انه لن يتم تقسيم البنود الواردة من حركة واحدة عبر حركات مجمعة مختلفة. وهذا يعني أنه من المحتمل أن يكون عدد البنود في الحركة المجمعة أعلى قليلاً أو أقل استنادًا إلى عوامل مثل عدد المنتجات المميزة.
- **الحد الأقصى لعدد مؤشرات الترابط للتحقق من حركات المتجر** - يحدد هذا الحقل عدد مؤشرات الترابط التي سيتم استخدامها للتحقق من صحة الحركات. تعتبر عمليه التحقق من صحة الحركات خطوة مطلوبة يجب أن تحدث قبل سحب الحركات إلى كشوف الحسابات. ينبغي أيضًا تحديد **منتج بطاقة الهدايا** على علامة التبويب السريعة **بطاقة الهدايا** على تبويب **الترحيل** من صفحة **معلمات Commerce** . يجب تحديد هذا الأمر حتى لو لم يتم استخدام بطاقات الهدايا من قبل المؤسسة.

> [!NOTE]
> تنطبق كافة الإعدادات والمعلمات المتعلقة بترحيلات كشف الحساب، والتي تم تعريفها في المتاجر وفي صفحة **معلمات Commerce** على ميزة ترحيل كشف الحساب المحسنة.

## <a name="processing"></a>المعالجة

يمكن أن يتم حساب كشوف الحساب وترحيلها في مجموعة باستخدام عنصري القائمة **حساب الكشوف على دُفعات‬** و **‏‫ترحيل الكشوف على دُفعات‬**. بدلاً من ذلك، يمكن أن يتم يدوياً حساب كشوف الحساب وترحيلها باستخدام عنصر القائمة **كشوف الحسابات** الذي توفر ميزة ترحيل كشف الحساب المحسنة.

تعتبر العملية والخطوات اللازمة لحساب وترحيل كشوف الحساب على دفعات متماثلة حيث إنها موجودة في ميزة ترحيل كشف الحساب القديمة. ومع ذلك، تم إجراء تحسينات هامة في المعالجة الأساسية الخلفية لكشوف الحساب. وهذه التحسينات تجعل العملية أكثر مرونة، وتوفر رؤية أفضل للحالات ومعلومات الخطأ. لذلك، يمكن للمستخدمين معالجة السبب الجذري للأخطاء ومتابعة عملية الترحيل دون التسبب في عطب في البيانات ودون أن يتسبب في جعل إصلاحات البيانات ضرورية.

تصف الأقسام التالية بعض التحسينات الهامة لميزة ترحيل كشف الحساب التي تظهر في واجهة المستخدم لكشوف الحساب وكشوف الحساب المرحلة.

### <a name="status-details"></a>تفاصيل الحالة

تم تقديم نموذج حالة جديد في روتين ترحيل كشف الحساب عبر عملية الحساب والترحيل.

يصف الجدول التالي الحالات المختلفة وترتيبها أثناء عملية الحساب.

| ترتيب الحالة | المنطقة‬      | الوصف |
|-------------|------------|-------------|
| 1           | تم البدء    | تم إنشاء كشف الحساب وهو جاهز للحساب. |
| 2           | تم وضع العلامة     | يتم تعريف الحركات الموجودة في نطاق كشف الحساب استناداً إلى محدد كشف الحساب، ويتم تعليمها بمعرف كشف الحساب. |
| 3           | محسوب | يتم حساب بنود كشف الحساب وعرضها. |

يصف الجدول التالي الحالات المختلفة وترتيبها أثناء عملية الترحيل.

| ترتيب الحالة | المنطقة‬                   | الوصف |
|-------------|-------------------------|-------------|
| 1           | تم فحصه                 | يتم تنفيذ عدة عمليات للتحقق من الصحة والتي ترتبط بالمعلمات (على سبيل المثال، تكلفة الإرجاع)، وبكشف الحساب وبنود كشف الحساب (على سبيل المثال، الفرق بين المبلغ المحتسب ومبلغ الحركة). |
| 2           | مجمَّع              | يتم تجميع حركات المبيعات للعملاء الذين تمت تسميتهم ولم تتم تسميتهم استنادًا إلى التكوين. يتم تحويل كل حركة مجمعة في النهاية إلى أمر مبيعات. |
| 3           | إنشاء أمر عميل  | وفقا للعملية المجمعة، يتم إنشاء أوامر المبيعات في النظام. |
| 4           | فوترة أمر العميل | تتم فوترة أوامر المبيعات. |
| 5           | الخصومات المرحّلة        | يجري ترحيل دفاتر يومية الخصم الدوري استناداً إلى التكوين. |
| 6           | الإيرادات/المصروفات المرحّلة   | يتم ترحيل حركات الإيرادات/المصروفات كإيصالات. |
| 7           | الإيصالات المرتبطة         | يتم إنشاء دفاتر يومية المدفوعات وربطها بالفاتورة المتوافقة. |
| 8           | المدفوعات المرحّلة         | يتم ترحيل دفاتر يومية المدفوعات. |
| 9           | بطاقات الهدايا المرحّلة       | يتم ترحيل حركات بطاقات الهدايا كإيصالات. |
| 10          | مُرحَّل                  | تم وضع علامة على كشف الحساب كمرحّل. |

كل حالة في الجداول السابقة مستقلة بطبيعتها، ويتم إنشاء تبعيات ذات تسلسل هرمي بين الحالات. تتدفق هذه التبعية من أعلى إلى أسفل. إذا واجه النظام أية أخطاء أثناء معالجة حالة، ويتم عكس الحالة لكشف الحساب إلى الحالة السابقة. ويتم استئناف أي إعادة محاولة لاحقة للمعالجة من الحالة التي فشلت ويستمر الانتقال للأمام. يتضمن هذا الأسلوب الفوائد التالية:

- يتوفر للمستخدم رؤية الكاملة للحالة التي حدث فيها خطأ.
- يتم تجنب عطب في البيانات. على سبيل المثال، في ميزة ترحيل كشف الحساب القديمة، كان هناك مثيلات حيث تمت فوترة بعض أوامر المبيعات ولكن البعض الآخر تُرك مفتوحًا. وكانت هناك مثيلات أيضًا حيث لم تحتوي بعض دفاتر يومية المدفوعات على فاتورة مقابلة للتسوية، نظراً لأن ترحيل الفواتير كان به خطأ.
- يمكن للمستخدمين مشاهدة الحالة الحالية لكشف الحساب باستخدام زر **تفاصيل حالة** في المجموعة **تفاصيل التنفيذ** لكشف الحساب. تحتوي صفحة تفاصيل الحالة على ثلاثة أقسام:

    - يوضح القسم الأول الحالة الحالية لكشف الحساب، إلى جانب رمز الخطأ ورسالة خطأ مفصلة، إذا حدث خطأ.
    - يوضح القسم الثاني حالات متعددة لعملية الحساب. تشير التلميحات المرئية إلى الحالات التي تم تشغيلها بنجاح، والحالات التي تعذر تشغيلها نظراً لحدوث أخطاء والحالات التي لم يتم بعد تشغيلها.
    - يوضح القسم الثالث حالات متعددة لعملية الترحيل. تشير التلميحات المرئية إلى الحالات التي تم تشغيلها بنجاح، والحالات التي تعذر تشغيلها نظراً لحدوث أخطاء والحالات التي لم يتم بعد تشغيلها.

بالإضافة إلى ذلك، يعرض رأس القسم الثاني والثالث الحالة الكلية للعملية ذات الصلة.

### <a name="event-logs"></a>سجلات الأحداث

يمر كشف الحساب بعمليات عديدة (مثل، الإنشاء والحساب والمسح والترحيل)، ويمكن استدعاء مثيلات متعددة لنفس العملية أثناء دورة حياة كشف الحساب. على سبيل المثال، بعد أن يتم إنشاء كشف حساب وحسابه، يمكن للمستخدم مسح كشف الحساب وحسابه مرة أخرى. يوفر زر **سجلات الأحداث** في مجموعة **تفاصيل التنفيذ** لكشف الحساب سجل مراجعة كامل للعديد من العمليات التي تم استدعائها لكشف الحساب، إلى جانب معلومات حول متى تم استدعاء تلك العمليات.

### <a name="aggregated-transactions"></a>الحركات المجمعة

أثناء عملية الترحيل، يتم تجميع حركات المبيعات بناء على التكوين. ويتم تخزين هذه الحركات المجمعة في النظام واستخدامها لإنشاء أوامر المبيعات. وتقوم كل حركة مجمعة بإنشاء أمر مبيعات مقابل في النظام. يمكنك الحركات المجمعة باستخدام زر **الحركات المجمعة** في المجموعة **تفاصيل التنفيذ** لكشف الحساب.

تعرض علامة تبويب **تفاصيل أمر المبيعات** الخاصة بحركة مجمعة المعلومات التالية:

- **معرف السجل** - المعرف للحركة المجمعة.
- **رقم كشف الحساب** -كشف الحساب الذي تنتمي إليه الحركة المجمعة.
- **التاريخ** – التاريخ الذي تم فيه ترحيل الحركة.
- **معرف المبيعات** -عند إنشاء أمر مبيعات من الحركة المجمعة، فإنه يكون معرف أمر المبيعات. إذا كان هذا الحقل فارغاً، فهذا يعني أنه لم يتم إنشاء أمر المبيعات المقابل.
- **عدد البنود المجمعة** - إجمالي عدد البنود لحركة مجمعة وأمر مبيعات.
- **الحالة** - الحالة الأخيرة للحركة المجمعة.
- **معرف الفاتورة** -عند فوترة أمر المبيعات الخاص بالحركة المجمعة، فهذا يكون معرف فاتورة المبيعات. إذا كان هذا الحقل فارغاً، فهذا يعني أنه لم يتم ترحيل الفاتورة لأمر المبيعات.

تعرض علامة تبويب **تفاصيل الحركة** لحركة مجمعة جميع الحركات التي تم سحبها إلى الحركة المجمعة. تُظهر البنود المجمعة في الحركة المجمعة كافة السجلات المجمعة من الحركات. وتعرض البنود المجمعة أيضا تفاصيل مثل الصنف والمتغير والكمية والسعر والمبلغ الصافي والوحدة والمستودع. بشكل أساسي، يتوافق كل بند مجمع مع بند أمر مبيعات واحد.

من صفحة **الحركات المجمعة**، يمكنك تنزيل ملف XML لحركة مجمعة معينة باستخدام الزر **تصدير أمر المبيعات xml**. يمكنك استخدام XML لتصحيح المشكلات التي تتضمن إنشاء أمر المبيعات والترحيل. قم فقط بتنزيل XML وتحميله إلى بيئة اختبار وتصحيح المشكلة في بيئة الاختبار. الأداء الوظيفي لتنزيل XML للحركات المجمعة غير متوفر لكشوف الحساب التي تم ترحيلها.

توفر طريقة عرض الحركة المجمعة الفوائد التالية:

- يتوفر للمستخدم رؤية للحركات المجمعة التي فشلت أثناء إنشاء أمر المبيعات وأوامر المبيعات التي فشلت أثناء الفوترة.
- يتوفر للمستخدم رؤية كيف يتم تجميع الحركات.
- كما يتوفر للمستخدم سجل مراجعة كامل، من الحركات إلى أوامر المبيعات وإلى فواتير المبيعات. لم يكن سجل المراجعة هذا متوفرًا في ميزة ترحيل كشف الحساب القديمة.
- يعمل ملف XML المجمع على تسهيل التعرف على المشكلات أثناء إنشاء أمر المبيعات والفوترة.

### <a name="journal-vouchers"></a>إيصالات دفتر اليومية

يعرض زر **‏‫إيصالات دفتر اليومية‬** في مجموعة **تفاصيل التنفيذ** لكشف الحساب كافة حركات الإيصال المختلفة التي تم إنشاؤها لكشف الحساب، والتي ترتبط بالخصومات وحسابات الإيرادات/المصروفات وبطاقات الهدايا، وغير ذلك.

في الوقت الحالي، يعرض البرنامج هذه البيانات فقط بشأن كشوف الحساب المرحلة.

### <a name="payment-journals"></a>دفاتر يومية المدفوعات

يعرض زر **دفاتر يومية المدفوعات** في مجموعة **تفاصيل التنفيذ** لكشف الحساب كافة دفاتر يومية المدفوعات المختلفة التي تم إنشاؤها لكشف الحساب.

في الوقت الحالي، يعرض البرنامج هذه البيانات فقط بشأن كشوف الحساب المرحلة.

## <a name="other-improvements"></a>تحسينات أخرى

تم إنشاء البيئات الأخرى الخلفية التي يمكن أن يراها المستخدم لميزة ترحيل كشف الحساب. فيما يلي بعض الأمثلة:

- لا يأخذ التجميع بعين الاعتبار الفريق والوحدات الطرفية وكيانات الورديات. نظراً لوجود معلمات تجميع أقل، فيجب معالجة عدد أقل من بنود أمر المبيعات.
- ويتم تقليل حدوث حالة توقف تام في جداول الحركات بتقديم جداول الملحقات الإضافية وبالقيام بعمليات الإدراج بدلاً من عمليات التحديث على جداول الحركات.
- تم تعيين معلمات لعدد المهام الدفعية التي يتم تنفيذها حاليا وتحديدها. لذلك، يمكن ضبط هذا الرقم خصيصا لبيئة العميل. في ميزة ترحيل كشف الحساب القديمة، تم إنشاء عدد غير محدود من المهام الدفعية في نفس الوقت. ونتج عن ذلك وجود أحمال يصعب التحكم بها وأعباء واختناقات في خادم المجموعة.
- يتم وضع كشوف الحساب بفعالية في قائمة الانتظار للمعالجة حسب أولوية كشوف الحساب التي تحتوي على أقصى عدد من الحركات.
- يتم تنفيذ عمليات معالجة الدفعة مثل **حساب الكشوف على دفعات** و **ترحيل الكشوف على دفعات** في الوضع الدفعي فقط. في ميزة ترحيل كشف الحساب القديمة، يمكن أن يختار المستخدمون تشغيل عمليتي المعالجة الدفعية هاتين في وضع تفاعلي وهو عملية بمؤشر ارتباط واحد على عكس عمليات المعالجة الدفعية التي تكون ذات مؤشرات الارتباط المتعددة.
- في ميزة ترحيل كشف الحساب القديمة، أي إخفاق لمهمة دفعية يضع الوظيفة الدفعية بأكملها في حالة خطأ. في الميزة المحسنة، فإن حالات فشل المهمة الدفعية لا يضع الوظيفة الدفعية في حالة خطأ إذا تم إكمال المهام الدفعية الأخرى بنجاح. يجب أن تقيّم حالة الترحيل الخاصة بتشغيل التنفيذ الدفعي باستخدام صفحة **كشوف الحسابات** حيث يمكنك مشاهدة أي كشوف حساب لم يتم ترحيلها نظراً لوجود أخطاء.
- في ميزة ترحيل كشف الحساب القديمة، فإن أول حدوث لفشل كشف الحساب يؤدي إلى فشل المجموعة بأكملها. ولا تتم معالجة كشوف الحساب المتبقية. في الميزة المحسنة، تستمر المعالجة الدفعية في معالجة كافة كشوف الحساب، حتى في حالة فشل بعض كشوف الحساب. ومن الفوائد الأخرى أنه يتوفر للمستخدمين رؤية العدد الفعلي لكشوف الحساب التي تحتوي على أخطاء. وبالتالي، لن يعلق المستخدمون في حلقة مفرغة من إصلاح الأخطاء وتشغيل عملية الترحيل حتى ترحيل جميع كشوف الحساب.

## <a name="general-guidance-about-the-statement-posting-process"></a>إرشادات عامة حول عملية ترحيل كشف الحساب

- من المستحسن أن تقوم بتشغيل عملية ترحيل كشف الحساب على دفعات، نظراً لأن التشغيل على دفعات يستفيد من إمكانيات إطار عمل المجموعة من حيث التشغيل متعدد العمليات. ويكون تعدد العمليات مطلوبًا للتعامل مع الأحجام الكبيرة للحركات التي تتم مشاهدتها عادة في ترحيلات كشف الحساب.
- من المستحسن أن تقوم بتشغيل المخزون الفعلي السالب في مجموعة نماذج الأصناف، حيث تتاح لك تجربة ترحيل سلسة. في بعض السيناريو، قد لا يمكن ترحيل الكشوف السالبة ما لم يكن هناك مخزون فعلي سالب. على سبيل المثال، من الناحية النظرية، إذا كان هناك وحدة واحدة فقط من أحد الأصناف في المخزون، وكانت هناك حركة مبيعات وحركة إرجاع للصنف، الحركة يجب أن يكون من الممكن ترحيل الحركة حتى إذا لم يتم تشغيل مخزون سالب. ومع ذلك، لأن عملية ترحيل كشف الحساب تسحب كلا من حركة المبيعات وحركة الإرجاع في أمر عميل فردي، ليس هناك ضمان بأن بند المبيعات سيتم ترحيله أولاً، متبوعاً ببند الإرجاع. لذلك، يمكن أن يحدث خطأ. إذا تم تشغيل مخزون سالب في هذا السيناريو، فإن ترحيل الحركة لا يتأثر سلبيا وسيعكس النظام المخزون بشكل صحيح.
- فمن الأفضل أن تستخدم التجميع أثناء حساب وترحيل كشوف الحساب. لذلك، يوصي بالإعدادات التالية لبعض محددات التجميع:

    - انتقل إلى **Retail and Commerce** \> **إعداد Headquarters** \> **المعلمات** \> **معلمات Commerce**. بعد ذلك، من علامة التبويب **ترحيل**، في علامة التبويب السريعة **تحديث المخزون**، في حقل **مستوى التفاصيل**، حدد **ملخص**.
    - انتقل إلى **Retail and Commerce** \> **إعداد Headquarters** \> **المعلمات** \> **معلمات Commerce**. بعد ذلك، من علامة التبويب **ترحيل**، في علامة التبويب السريعة **التجميع**، قم بتعيين خيار **حركات الإيصال** إلى **نعم**.