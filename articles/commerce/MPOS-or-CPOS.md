---
title: الاختيار بين Store Commerce وCloud POS
description: يشرح هذا المقال الاختلافات الرئيسية بين Store Commerce وCloud POS، كما يصف العوامل المتنوعة التي يجب مراعاتها من قِبل بائعي التجزئة الذين يستخدمون Dynamics 365 Commerce لمساعدتهم على إجراء الاختيار الأفضل الذي يناسب متطلباتهم.
author: josaw1
ms.date: 04/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2017-10-12
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: bbb5f3d4c61907243bed404f3ab7bea05c78b1c0
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276444"
---
# <a name="choose-between-store-commerce-and-cloud-pos"></a>الاختيار بين Store Commerce وCloud POS

[!include [banner](includes/banner.md)]

يشرح هذا المقال الاختلافات الرئيسية بين Store Commerce وCloud POS، كما يصف العوامل المتنوعة التي يجب مراعاتها من قِبل بائعي التجزئة الذين يستخدمون Dynamics 365 Commerce لمساعدتهم على إجراء الاختيار الأفضل الذي يناسب متطلباتهم. وهو يوفر أيضًا للمنفذين خلفية إضافية وتلميحات وإرشادات تتعلق بالعوامل التي يجب عليهم أخذها في الاعتبار عندما ينشرون Dynamics 365 Commerce. ومن خلال مراجعة واتباع هذا الدليل كجزء من عملية النشر، يستطيع المنفذون تجنب المشكلات التي قد تؤثر على أداء المستخدم أو رضاه.

## <a name="insights"></a>المعلومات

يوفر Commerce مجموعة كبيرة من خيارات النشر والمخطط. ولذلك، يستطيع تجار التجزئة اختيار التكوين والمكونات التي تلبي طلبات الأعمال والتكنولوجيا لديهم على أفضل نحو. وهناك وجه واحد من التنفيذ يتطلب التقدير الحذر ألا وهو اختيار النظام الأساسي وعامل النموذج لمكون نقطة البيع (POS).

### <a name="pos-platform-and-form-factor-considerations"></a>اعتبارات عامل النموذج والنظام الأساسي لنقطة البيع

يدعم Commerce خيارات نقطة البيع التالية:

- Store Commerce لنظام Microsoft Windows
- Store Commerce لنظامي iOS وAndroid
- Cloud POS (CPOS)، التي تدعم المستعرضات Microsoft Edge وGoogle Chrome
- Modern POS (MPOS) لنظام Microsoft Windows (سيتم إهمال MPOS في شهر أكتوبر 2023.) 

في كل الحالات، تشارك نقطة البيع (Store Commerce وCPOS) نفس التعليمات البرمجية للتطبيق الأساسي. هذه النقطة مهمة للأسباب التالية:

- واجهة المستخدم (UI) متسقة، بغض النظر عن عامل النموذج أو النظام الأساسي.
- معظم إمكانات الوظيفية نفس الشيء، بغض النظر عن عامل النموذج أو النظام الأساسي. ومع ذلك، توجد بعض الاختلافات الهامة. تم تسجيل هذه الاختلافات في هذا المقال.
- في كل متجر، يمكن دمج اختلافات نقطة البيع ويمكن تشغيلها بشكل متزامن. على سبيل المثال، يستطيع أحد بائعي التجزئة، في سجلاته الرئيسية، استخدام Store Commerce على أجهزة الكمبيوتر التي تُشغّل Windows. ومع ذلك، يستطيع بائع التجزئة إكمال هذه السجلات باستخدام أجهزة المحمول أو الوحدات الطرفية المستندة إلى المستعرضات.
- يمكن استخدام التخصيصات والملحقات بسهولة عبر الأنظمة الأساسية وعوامل النماذج. نظرًا لأنه تتم مشاركة كود التطبيق الأساسي، يمكن تنفيذ معظم التخصيصات مرة واحدة بدلاً من عدة مرات.

### <a name="store-commerce-vs-cpos"></a>Store Commerce في مقابل CPOS

وعلى الرغم من أن Store Commerce يشبه CPOS إلى حدٍ بعيد، ولكن ثمة اختلافات مهمة يجب أن تدركها.

#### <a name="store-commerce"></a>Store Commerce

إن Store Commerce عبارة عن تطبيق سطح مكتب يتم تثبيته وصيانته على جهاز.

- **Windows** – يحتوي تطبيق Store Commerce لنظام Windows جميع التعليمات البرمجية للتطبيق وCommerce Runtime (CRT) وHardware Station ‏(HWS).
- **iOS/Android** – على هذين النظامين الأساسيين، يؤدي التطبيق دور المضيف لكود تطبيق CPOS. بمعنى آخر، تأتي التعليمات البرمجية للتطبيق من خادم CPOS المستضاف على Commerce Scale Unit. لمزيد من المعلومات، راجع [نظرة عامة على Commerce Scale Unit](dev-itpro/retail-store-system-begin.md).

#### <a name="cpos"></a>نقطة بيع المجموعة

نظراً لأن نقطة بيع المجموعة تعمل في مستعرض، لا يتم تثبيت التطبيق على الجهاز. بدلاً من ذلك، يصل المستعرض إلى كود التطبيق من خادم نقطة بيع المجموعة. ولذلك، يتعذر على نقطة بيع المجموعة الوصول إلى أجهزة نقطة البيع مباشرةً أو العمل في حالة عدم الاتصال.

### <a name="store-deployment-considerations"></a>اعتبارات نشر المتجر

بالإضافة إلى النظام الأساسي وعامل النموذج، يجب على تجار التجزئة أيضًا اختيار أحد خيارات النشر في المتجر. يعرض الجدول التالي التكوينات المتوفرة لكل خيار نقطة بيع.

| تطبيق نقطة البيع            | Commerce Scale Unit | متوفرة دون اتصال | دعم HWS المحلي |
|----------------------------|---------------------|-------------------|-------------------|
| Store Commerce لنظام Windows | المجموعة أو وحدة قياس متجر البيع بالتجزئة       | ‏‏نعم‬               | ‏‏نعم‬               |
| Store Commerce لنظام Android | المجموعة أو وحدة قياس متجر البيع بالتجزئة       | لا                | ‏‏نعم‬               |
| Store Commerce لنظام iOS     | المجموعة أو وحدة قياس متجر البيع بالتجزئة       | لا                | لا                |
| نقطة بيع المجموعة‬                  | المجموعة أو وحدة قياس متجر البيع بالتجزئة       | لا                | لا                |

#### <a name="commerce-scale-unit"></a>Commerce Scale Unit

تعد Commerce Scale Unit مكونًا يستضيف CRT. يحتوي CRT على كل منطق الأعمال الذي تستخدمه نقطة البيع، ويوفر الوصول إلى قاعدة بيانات القناة. عند الاتصال بالإنترنت، يستخدم جميع عملاء نقطة البيع في المتجر خادم Commerce Scale Unit. يمكن نشر خادم Commerce Scale Unit في المجموعة أو في المتجر.

#### <a name="offline-mode"></a>وضع دون الاتصال

يدعم Store Commerce لنظام Windows وضع عدم الاتصال. في وضع دون الاتصال، يمكن لنقطة البيع الاستمرار في معالجة المبيعات حتى في حالة قطع الاتصال من Commerce Scale Unit. ويمكن بعد ذلك مزامنتها مع قاعدة بيانات القناة عند استعادة الاتصال. يستخدم Store Commerce مثيله المضمن من CRT ويستخدم مؤقتًا مصدر البيانات المحلي الخاص به (قاعدة بيانات SQL Server في وضع عدم الاتصال). لمزيد من المعلومات حول الوظائف غير المتصلة، راجع [الوظائف غير المتصلة لنقطة البيع](pos-offline-functionality.md).

### <a name="pos-peripheralhardware-considerations"></a>اعتبارات أجهزة/الوحدات الطرفية لنقطة البيع

يجب على تجار التجزئة أيضًا مراعاة الكيفية التي ستصل بها نقطة البيع إلى الأجهزة والوحدات الطرفية، مثل الطابعات وأدراج النقدية والوحدات الطرفية للدفع. يمكن تخصيص محطات الأجهزة لسجل نقطة البيع أو مشاركتها بين السجلات في متجر.

| تطبيق نقطة البيع            | HWS OPOS المحلي | الأجهزة الطرفية للشبكة | دعم HWS المشترك |
|----------------------------|----------------|---------------------|--------------------|
| Store Commerce لنظام Windows | ‏‏نعم‬            | ‏‏نعم‬                 | ‏‏نعم‬                |
| Store Commerce لنظام Android | لا             | ‏‏نعم‬                 | ‏‏نعم‬                |
| Store Commerce لنظام iOS     | لا             | لا                  | ‏‏نعم‬                |
| نقطة بيع المجموعة‬                  | لا             | لا                  | ‏‏نعم‬                |

لمزيد من المعلومات حول كيفية تثبيت محطات الأجهزة، راجع [تكوين وتثبيت محطة أجهزة البيع بالتجزئة](retail-hardware-station-configuration-installation.md).

## <a name="implementation-considerations"></a>اعتبارات التنفيذ

خذ بعين الاعتبار المعلومات التالية أثناء تخطيط تنفيذ نقطة البيع في متاجر الخاصة بك:

- **المتطلبات الوظيفية** - إمكانات وعمليات الأعمال الأساسية هي نفس الشيء، بغض النظر عن النظام الأساسي أو عامل النموذج أو مخطط النشر. ولذلك، لا يلزم معظم تجار التجزئة مراعاة المتطلبات الوظيفية أثناء تخطيط تنفيذهم.
- **الاتصال** - يعتبر شبكة الاتصال (شبكة الاتصال العريضة \[WAN\] وشبكة الاتصال المحلية \[LAN\]) هو عاملاً رئيسيًا يتطلب مراعاة خاصة. يتم فقدان أي ميزات ليس لها أي أثر يقدمها حل مستضاف على المجموعة من حيث التكلفة والبساطة، إذا كان النظام غير متوفر للعمليات الهامة للأعمال.

    إذا لم يكن الاتصال بالنسبة لأحد الأجهزة يمكن الاعتماد عليه ويتسم بالمرونة بدرجة كبيرة، أو إذا لم تكن مدة معينة من وقت التعطل عن العمل مقبولة لبائع التجزئة، فإننا نوصي بأحد الخيارات التالية:

    - استخدام Store Commerce في نظام التشغيل Windows، وتمكين وضع عدم الاتصال.
    - توزيع Commerce Scale Unit المحلية.

    هذان الخيارين غير متبادلين بشكل حصري. بالنسة إلى المخطط الأكثر موثوقية، يستطيع بائعو التجزئة نشر وحدة قياس محلية لمتجر البيع بالتجزئة‬ لتقليل الاعتماد على الاتصال بالإنترنت أو توافر Azure، كما يمكنهم نشر سجلات نقطة البيع حيث تم تمكين وضع دون الاتصال، في حالة وجود أي مشكلة في الشبكة أو الخادم المحلي.

- **الأجهزة/الوحدات الطرفية** - إن أحد الأوجه المهمة لنظام نقطة البيع بالتجزئة هي قدرته على استخدم الوحدات الطرفية لنقطة البيع، مثل الطابعات وأدراج النقدية والوحدات الطرفية للدفع. على الرغم من أن جميع خيارات نقطة البيع المتوفرة يمكنها استخدام الأجهزة الطرفية، إلا أن Store Commerce لنظام Windows وحده هو الذي يدعمها بشكل مباشر. بالنسة لجميع التطبيقات الأخرى، يُتطلب وجود محطة أجهزة واحدة أو أكثر. على الرغم من أن هذا الأسلوب يضيف الكثير من المرونة، إلا أنه يجب نشر مكونات إضافية وتكوينها وصيانتها.
- **متطلبات النظام** - تختلف متطلبات النظام الخاصة بتطبيق نقطة البيع. يجب عليك التحقق من الحصول على أحدث المعلومات قبل أن تقوم باختيارك. على سبيل المثال، نظراً لأنه يتم تشغيل نقطة بيع المجموعة في مستعرض، فإنها تدعم عددًا كبيرًا من أنظمة التشغيل. لمزيد من المعلومات حول متطلبات النظام، راجع [متطلبات النظام لعمليات نشر المجموعة](../fin-ops-core/fin-ops/get-started/system-requirements.md).
- **النشر والصيانة** - قد يختلف تعقيد التوزيع والصيانة استنادًا إلى اختيارات التطبيق والنشر. على سبيل المثال، لنشر نقطة بيع مجموعة مستضافة على مجموعة، لا يلزمك التثبيت والتحديث على كل جهاز. ولذلك، يقلل هذا الأسلوب من التعقيد والتكلفة بشكل كبير. ومع ذلك، إذا قمت بنشر Store Commerce على كل سجل وقمت بتمكين وضع عدم الاتصال، وقمت أيضًا بنشر محطات الأجهزة المشتركة، فيمكنك زيادة عدد نقاط النهاية التي يجب أن تتم إدارتها بشكل كبير.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
