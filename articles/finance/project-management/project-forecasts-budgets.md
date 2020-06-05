---
title: تنبؤات وموازنات المشاريع
description: يوفر Dynamics 365 Finance Microsoftتنبؤات المشاريع وموازنات المشاريع لإدارة ومراقبة مشاريعك.
author: KimANelson
manager: AnnBe
ms.date: 10/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ForecastModel, ProjYearEndProcess
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 23501
ms.assetid: 4e6d1384-19a2-4232-b3f3-d2590c218bd7
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 85a5577968024bf42449c50d72a11414f9207eec
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185579"
---
# <a name="project-forecasts-and-budgets"></a>تنبؤات وموازنات المشاريع

[!include [banner](../includes/banner.md)]

توجد طريقتين لإدارة ومراقبة المشاريع: تنبؤات المشاريع وموازنات المشاريع. 

استخدم التنبؤ بالمشروع إذا كانت مؤسستك لديها منظور تشغيلي، وتركز على الإيرادات والتكاليف المستمدة من حركات محددة. واستخدم إعداد موازنة المشروع إذا كانت مؤسستك تركز على المبالغ المالية بشكل أكبر. 

ويستخدم كلُّ من التنبؤات المشاريع وموازنات المشاريع نماذج التنبؤ للاحتفاظ بمبالغ الحركة المتوقعة. 

لكل طريقة مزاياها. ويجب عليك مراعاة النقاط التالية قبل تحديد طريقة للمؤسسة الخاصة بك.

|                           |                                          |                                                    |
|---------------------------|------------------------------------------|----------------------------------------------------|
|                           | **التنبؤات بالمشاريع**                  | **إعداد موازنة المشروع**                              |
| **توزيع الفترة**     | لا يمكنك توزيع الحركات بشكل واضح خلال فترة مالية. وبدلاً من ذلك، يستند التنبؤ، والتحكم في التنبؤ، إلى دورة حياة المشروع. ولأن التنبؤات تستند إلى تاريخ محدد، يجب عليك استدلال الفترة من التاريخ. | يمكنك توزيع الحركات خلال المشروع بالكامل أو فترة مالية. وفي حالة توزيع فترة، يمكنك تحميل المبالغ غير المستخدمة إلى الأمام للفترة المالية التالية. |
| **عرض الحركات**  | يمكنك عرض الحركات في نماذج التنبؤ، حيث ترى التنبؤات للشركة بأكملها وللمشاريع كافة، بغض النظر عن التدرج الهرمي. وللتركيز على مشروع معين، يجب عليك تصفية البيانات.                                       | ويمكنك عرض حركات الموازنة لتدرج هرمي مشروع واحد. ولذلك، يمكنك عرض تفاصيل الحركة لمشروع رئيسي أو المشاريع الفرعية الخاصة به.                 |
| **متغيرات الحركات** | عندما تقوم بإدخال حركات التنبؤ، يمكنك استخدام كل سمة موجودة لحركة فعلية. ويسمح هذا بمزيد من التفصيل في التنبؤ. على سبيل المثال، يمكنك إدخال تفاصيل عن الكميات، أو العاملين، أو الأصناف، أو خصائص البند.         | عندما تقوم بإدخال تفاصيل الموازنة، يمكنك استخدام المبالغ والفئات والأنشطة فقط.                    |
| **الأمان**              | يستند التنبؤ إلى الحركات التي تقوم بإدخالها في نماذج التنبؤ ولا يشتمل على أي آلية للتحكم في العملية. ويستطيع أي عامل لديه أذونات للحصول على نموذج تنبؤ مراجعة المعلومات دون الحصول على موافقة.                                        | ويتم في إعداد الموازنات استخدام نظام سير العمل، الذي يتيح إمكانية إدارة التغيير ويتيح لك الاحتفاظ بمحفوظات المراجعات.         |
| **نوع الإدخال**           | تستند إدخالات حركات التنبؤ إلى عدد الوحدات، والتكلفة، وأسعار وحدة المبيعات.  | وتستند تفاصيل الموازنة إلى مبالغ مقسمة بين التكاليف والإيرادات.                                          |
| **نماذج التنبؤ**       | لأن كل تنبؤ يجب أن يقترن بنموذج، يمكنك إنشاء عدة نماذج للتنبؤ وإعداد نماذج فرعية كذلك.           | يعمل إعداد موازنة المشروع على تحديد نماذج التنبؤ المستخدمة لإعداد الموازنة. وقد تساعد نماذج التنبؤ الأقل على زيادة الاتساق في الإسقاطات.                           |
| **تجاوزات التكاليف**         | يمكنك فقط السماح أو عدم السماح بإدخال حركات ستؤدي إلى تجاوز التكاليف.   | ويوفر إعداد موازنة المشروع خيارات تحكم إضافية للمستخدمين. ويمكنك السماح بالتحذيرات والتجاوزات.                    |
| **التحكم**               | يتم تنفيذ مراقبة التنبؤ باستخدام خفض التنبؤ. ويتم خصم المبالغ الفعلية من أرصدة حركات التنبؤ بدون أي سجل مراجعة. ويمكن أن يجعل هذا من تتبع مكان حدوث الحركات الفعلية أمرًا اكثر صعوبة.                   | وفي التحكم في موازنة المشروع، يتم خصم المبالغ الفعلية من مبالغ في الموازنة المتبقية. يسمح هذا بسجل مراجعة أكثر وضوحاً.                                   |

## <a name="project-forecasts"></a>تنبؤات المشروع
عند استخدام تنبؤات المشروع، يمكنك إدخال حركات التنبؤ في نماذج التنبؤ لكل نوع حركة. يمكن استخدام كل سمة متوفرة لحركة فعلية، في حركة تنبؤ؛ على سبيل المثال، سطر الربحية وسمات الخط والعاملين أو الوصف. ويمكنك أيضًا القيام بتحديد المدة في المشروع بعد أن تحمل العميل التكلفة التي ستضعها في فاتورته. 

تعتمد حركات تنبؤ المشروع على الوحدات والمبالغ. 

يجب أن تقوم بإقران كل تنبؤ بالمشروع بنموذج تنبؤ. وعندما تقوم بإدخال حركة تنبؤ، يتم اقتراح نموذج تنبؤ تلقائيًا. ويقوم نموذج التنبؤ بدور الحاوية لحركات التنبؤ. 

ويمكنك تعيين نماذج التنبؤ كنماذج فرعية لنموذج. ويتيح هذا لك إمكانية التنبؤ بحسب المنطقة أو الفترة الزمنية أو القسم. ويمكنك نسخ حركات التنبؤ في نموذج لإنشاء نموذج جديد، ويمكنك أيضًا تحويل الحركات إلى دفتر الأستاذ العام. نظراً لوجود علاقة الواحد بالواحد بين نموذج وتنبؤ، فيجعل لكل نموذج تنبؤ موازنة منفصلة لمشروع. 

استخدام نماذج التنبؤ بخفض التنبؤ كآلية التحكم للمشاريع. وفي خفض التنبؤ، تقلل الحركات الفعلية من أرصدة حركة التنبؤ. ومع ذلك، لأنه يتم تطبيق خفض التنبؤ بالمشروع الأعلى في التدرج الهرمي، فإنه يوفر طريقة عرض محدودة للتغييرات في التنبؤ. على سبيل المثال، إذا كان عامل مقترن بمشروع فرعي، يتم ترحيل الحركات الفعلية للعامل إلى لمشروع الرئيسي. وقد يؤي هذا إلى صعوبة تعقب التغييرات، لأنه لا يمكنك بسهولة تحديد أي حركة في أي مشروع فرعي سببت انخفاض مبلغ التنبؤ. ولذلك، إنها لفكرة جيدة إنشاء نسخة نموذج تنبؤ لخفض التنبؤ للاستخدام. ويمكنك فيما بعد استخدام التقارير لعرض ما كان من المتوقع أصلاً. 

ويمكنك مراجعة أو نسخ أو حذف أو نقل تنبؤات المشروع إلى موازنة دفتر الأستاذ العام. ومع ذلك، لا توجد أي تحكم في العملية. ويمكن لأي عامل لديه إذن لنموذج تنبؤ إجراء المراجعات دون مراجعة.

-   **مراجعة** – يمكن مراجعة حركة تنبؤ في نفس النماذج التي أنشئت فيها الإدخالات الأصلية.
-   **نسخ أو حذف** – عند نسخ حركات التنبؤ، تنسخ سطور حركة نموذج التنبؤ الواحد إلى نموذج تنبؤ آخر. وعند حذف تنبؤ، يمكنك حذف حركات التنبؤ الخاصة بنموذج تنبؤ. ولتحديد حركات التنبؤ التي يتم نسخها أو حذفها، حدد تواريخ وأنواع حركات محددة. ويتيح لك هذا نسخ أو حذف أجزاء معينة فقط من التنبؤ.
-   **تحويل** – عند تحويل تنبؤ مشروع لموازنة دفتر الأستاذ العام، يمكنك تحويل حركات التنبؤ الخاصة بنموذج تنبؤ إلي نموذج موازنة دفتر الأستاذ العام. يمكنك استبدال أية حركات تم تحويلها مسبقًا في موازنة دفتر الأستاذ العام الذي تقوم بتحويل تنبؤ المشروع إليه.

## <a name="project-budgets"></a>موازنات المشروع
إعداد موازنة المشروع هي طريقة أبسط من التنبؤ، على الرغم من أنه لا يتكامل مع نماذج التنبؤ. ويستخدم نموذج إدخال واحد لتفاصيل ومراجعات الموازنة الأصلية، ويسمح بالتوقعات التي تعتمد فقط على المبلغ أو الفئة أو النشاط. 

وفي إعداد موازنة المشروع، يجب إرسال جميع المراجعات والمواونات الأصلية إلى سير عمل مشروع للموافقة عليه. وتمنحك مهام سير العمل مزيدًا من التحكم في العملية وتُنشئ سجل محفوظات تغييرات. 

ويشبه إعداد موازنة المشروع موازنة دفتر الأستاذ العام، ولكنه أسرع وأسهل في الإعداد. ولا يلزم إعداد العديد من الخيارات في إعداد موازنة دفتر الأستاذ العام، مثل الأرقام المسلسلة أو العملة، بشكل منفصل للمشاريع.

ويتم إقران موازنات المشاريع تلقائياً بنموذجي تنبؤ، أحدهما للموازنة الأصلية وأخرى للموازنة المتبقية. ولذلك، يمكن للتقارير التي تستند إلى نماذج التنبؤ استخدام بيانات الموازنة. وعند الالتزام بموازنة مشروع، يقوم النظام بإنشاء حركات تنبؤ استناداً إلى النماذج المقترنة، التي يتم استخدامها لأغراض الإبلاغ والمراقبة.

## <a name="forecast-models"></a>نماذج التنبؤ
تحتوي نماذج التنبؤ على تدرج هرمي طبقة واحدة. ويعني هذا أنه يجب إقران تنبؤ بمشروع واحد بنموذج تنبؤ واحد.

‏‫وإذا كنت تستخدم مشروع التنبؤ، فإنه يمكنك تحديد نماذج كنماذج فرعية. ويمكنك فيما بعد إنشاء التنبؤات بالقسم أو الفترة الزمنية أو المنطقة.‬ على سبيل المثال، يمكنك إنشاء نموذج تنبؤ لمدة سنة، ثم إنشاء النماذج الفرعية لتنبؤات المناطق الشمال الشرقية، والجنوب شرقية، والشمال غربية، والجنوب غربية التي تقدمها الرؤوس الإقليمية. وبتحديد خيارات مختلفة في التقارير المتاحة، يمكنك عرض المعلومات حسب التنبؤ الإجمالي أو النموذج الفرعي.


