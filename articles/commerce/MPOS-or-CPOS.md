---
title: الاختيار بين نقطة البيع الحديثة (MPOS) وCloud POS
description: يشرح هذا الموضوع الاختلافات الأساسية بين نقطة البيع الحديثة (MPOS) وCloud POS. ويصف أيضًا العوامل المختلفة التي يجب على تجار التجزئة الذين يطبقون Dynamics 365 Commerce وضعها في الاعتبار لمساعدتهم في اختيار الخيار الأفضل لمتطلباتهم.
author: jblucher
manager: AnnBe
ms.date: 10/13/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2017-10-12
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 508fda28d8f815f030e7b163709393f70904a5fd
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057684"
---
# <a name="choose-between-modern-pos-mpos-and-cloud-pos"></a>الاختيار بين نقطة البيع الحديثة (MPOS) وCloud POS

[!include [banner](includes/banner.md)]

يوفر هذا الموضوع للمنفذين خلفية إضافية وتلميحات وإرشادات تتعلق بالعوامل التي يجب عليهم أخذها في الاعتبار عندما ينشرون Dynamics 365 Commerce. ومن خلال مراجعة واتباع هذا الدليل كجزء من عملية النشر، يستطيع المنفذون تجنب المشكلات التي قد تؤثر على أداء المستخدم أو رضاه.

## <a name="insights"></a>المعلومات

يوفر Commerce مجموعة كبيرة من خيارات النشر والمخطط. ولذلك، يستطيع تجار التجزئة اختيار التكوين والمكونات التي تلبي طلبات الأعمال والتكنولوجيا لديهم على أفضل نحو. وهناك وجه واحد من التنفيذ يتطلب التقدير الحذر ألا وهو اختيار النظام الأساسي وعامل النموذج لمكون نقطة البيع (POS).

### <a name="pos-platform-and-form-factor-considerations"></a>اعتبارات عامل النموذج والنظام الأساسي لنقطة البيع

يدعم Commerce خيارات نقطة البيع التالية:

- نقطة البيع الحديثة (MPOS) لـ Microsoft Windows
- MPOS لـ Microsoft Windows Phone
- MPOS لـ Apple iPad أو الكمبيوتر اللوحي Google Android
- Cloud POS (CPOS)، التي تدعم المستعرضات Microsoft Edge وInternet Explorer وGoogle Chrome

في كل الحالات، تشارك نقطة البيع (نقطة البيع الحديثة ونقطة بيع المجموعة) نفس كود التطبيق الأساسي. هذه النقطة مهمة للأسباب التالية:

- واجهة المستخدم (UI) متسقة، بغض النظر عن عامل النموذج أو النظام الأساسي.
- معظم إمكانات الوظيفية نفس الشيء، بغض النظر عن عامل النموذج أو النظام الأساسي. ومع ذلك، توجد بعض الاختلافات الهامة. تم تسجيل هذه الاختلافات في هذا الموضوع.
- في متجر معين، يمكن دمج اختلافات نقطة البيع ويمكن تشغيلها بشكل متزامن. على سبيل المثال، في سجلاته الرئيسية، يستطيع أحد بائعي تجزئة استخدام نقطة البيع الحديثة على أجهزة الكمبيوتر التي تُشغّل Windows. ومع ذلك، يستطيع بائع التجزئة إكمال هذه السجلات باستخدام أجهزة المحمول أو الوحدات الطرفية المستندة إلى المستعرضات.
- يمكن استخدام التخصيصات والملحقات بسهولة عبر الأنظمة الأساسية وعوامل النماذج. نظرًا لأنه تتم مشاركة كود التطبيق الأساسي، يمكن تنفيذ معظم التخصيصات مرة واحدة بدلاً من عدة مرات.

### <a name="mpos-vs-cpos"></a>نقطة البيع الحديثة مقابل نقطة بيع المجموعة

وعلى الرغم من أن نقطة البيع الحديثة ونقطة بيع المجموعة هي نفس الشيء بشكل كبير، إلا أنه توجد بعض الاختلافات المهمة التي يجب أن تدركها.

#### <a name="mpos"></a>نقطة البيع الحديثة (MPOS)

MPOS على جهاز يعمل بنظام التشغيل Windows أو iOS أو Android عبارة عن تطبيق تم حزمه وتثبيته وصيانته على هذا الجهاز.

- **Windows** - تحتوي نقطة البيع الحديثة لتطبيق Windows على كود التطبيق بالكامل ووقت التشغيل التجاري المضمن (CRT). 
- **iOS/Android** – على هذين النظامين الأساسيين، يؤدي التطبيق دور المضيف لكود تطبيق CPOS. بمعنى آخر، تأتي التعليمات البرمجية للتطبيق من خادم CPOS في Microsoft Azure أو Commerce Scale Unit. لمزيد من المعلومات، راجع [نظرة عامة على Commerce Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/retail/dev-itpro/retail-store-system-begin).

#### <a name="cpos"></a>نقطة بيع المجموعة

نظراً لأن نقطة بيع المجموعة تعمل في مستعرض، لا يتم تثبيت التطبيق على الجهاز. بدلاً من ذلك، يصل المستعرض إلى كود التطبيق من خادم نقطة بيع المجموعة. ولذلك، يتعذر على نقطة بيع المجموعة الوصول إلى أجهزة نقطة البيع مباشرةً أو العمل في حالة عدم الاتصال.

### <a name="store-deployment-considerations"></a>اعتبارات نشر المتجر

بالإضافة إلى النظام الأساسي وعامل النموذج، يجب على تجار التجزئة أيضًا اختيار أحد خيارات النشر في المتجر. يعرض الجدول التالي التكوينات المتوفرة لكل خيار نقطة بيع.

| تطبيق نقطة البيع         | Commerce Scale Unit | متوفرة دون اتصال |
|-------------------------|---------------|-------------------|
| نقطة البيع الحديثة لنظام التشغيل Windows        | المجموعة أو وحدة قياس متجر البيع بالتجزئة | ‏‏نعم               |
| MPOS لـ iOS أو Android | المجموعة أو وحدة قياس متجر البيع بالتجزئة | لا                |
| نقطة بيع المجموعة‬               | المجموعة أو وحدة قياس متجر البيع بالتجزئة | لا                |

#### <a name="commerce-scale-unit"></a>Commerce Scale Unit

تعد Commerce Scale Unit مكونًا يستضيف CRT. يحتوي CRT على كل منطق الأعمال الذي تستخدمه نقطة البيع، ويوفر الوصول إلى قاعدة بيانات القناة. عند الاتصال بالإنترنت، يستخدم جميع عملاء نقطة البيع في المتجر خادم Commerce Scale Unit. يمكن نشر خادم Commerce Scale Unit في المجموعة أو في المتجر.

#### <a name="offline-mode"></a>وضع دون الاتصال

تدعم نقطة البيع الحديثة لنظام التشغيل Windows وضع دون الاتصال. في وضع دون الاتصال، يمكن لنقطة البيع الاستمرار في معالجة المبيعات حتى في حالة قطع الاتصال من Commerce Scale Unit. ويمكن بعد ذلك مزامنتها مع قاعدة بيانات القناة عند استعادة الاتصال. تستخدم نقطة البيع الحديثة مثيلها المضمن الخاص بـ CRT وتستخدم مؤقتًا مصدر البيانات المحلي الخاص بها (قاعدة بيانات SQL Server في وضع دون الاتصال). لمزيد من المعلومات حول الوظائف غير المتصلة، راجع [الوظائف غير المتصلة لنقطة البيع](https://docs.microsoft.com/dynamics365/unified-operations/retail/pos-offline-functionality).

### <a name="pos-peripheralhardware-considerations"></a>اعتبارات أجهزة/الوحدات الطرفية لنقطة البيع

يجب على تجار التجزئة أيضًا مراعاة الكيفية التي ستصل بها نقطة البيع إلى الأجهزة والوحدات الطرفية، مثل الطابعات وأدراج النقدية والوحدات الطرفية للدفع. تدعم نقطة البيع الحديثة لنظام التشغيل Windows وحدها الاتصال المباشر بهذه الأجهزة. تتطلب MPOS لنظام التشغيل Windows Phone أو iOS أو Android، وCloud POS حل محطة أجهزة للوصول إلى هذه الأجهزة. يمكن تخصيص محطات الأجهزة لسجل نقطة البيع أو مشاركتها بين السجلات في متجر. لمزيد من المعلومات حول كيفية تثبيت محطات الأجهزة، راجع [تكوين وتثبيت محطة أجهزة البيع بالتجزئة](https://docs.microsoft.com/dynamics365/unified-operations/retail/retail-hardware-station-configuration-installation).

## <a name="implementation-considerations"></a>اعتبارات التنفيذ

خذ بعين الاعتبار المعلومات التالية أثناء تخطيط تنفيذ نقطة البيع في متاجر الخاصة بك:

- **المتطلبات الوظيفية** - إمكانات وعمليات الأعمال الأساسية هي نفس الشيء، بغض النظر عن النظام الأساسي أو عامل النموذج أو مخطط النشر. ولذلك، لا يلزم معظم تجار التجزئة مراعاة المتطلبات الوظيفية أثناء تخطيط تنفيذهم.
- **الاتصال** - يعتبر شبكة الاتصال (شبكة الاتصال العريضة \[WAN\] وشبكة الاتصال المحلية \[LAN\]) هو عاملاً رئيسيًا يتطلب مراعاة خاصة. يتم فقدان أي ميزات ليس لها أي أثر يقدمها حل مستضاف على المجموعة من حيث التكلفة والبساطة، إذا كان النظام غير متوفر للعمليات الهامة للأعمال.

    إذا لم يكن الاتصال بالنسبة لأحد الأجهزة يمكن الاعتماد عليه ويتسم بالمرونة بدرجة كبيرة، أو إذا لم تكن مدة معينة من وقت التعطل عن العمل مقبولة لبائع التجزئة، فإننا نوصي بأحد الخيارات التالية:

    - استخدام نقطة البيع الحديثة في نظام التشغيل Windows، وتمكين وضع دون الاتصال.
    - توزيع Commerce Scale Unit المحلية.

    هذان الخيارين غير متبادلين بشكل حصري. بالنسة إلى المخطط الأكثر موثوقية، يستطيع بائعو التجزئة نشر وحدة قياس محلية لمتجر البيع بالتجزئة‬ لتقليل الاعتماد على الاتصال بالإنترنت أو توافر Azure، كما يمكنهم نشر سجلات نقطة البيع حيث تم تمكين وضع دون الاتصال، في حالة وجود أي مشكلة في الشبكة أو الخادم المحلي.

- **الأجهزة/الوحدات الطرفية** - إن أحد الأوجه المهمة لنظام نقطة البيع بالتجزئة هي قدرته على استخدم الوحدات الطرفية لنقطة البيع، مثل الطابعات وأدراج النقدية والوحدات الطرفية للدفع. على الرغم من أن جميع خيارات نقطة البيع المتوفرة يمكنها استخدام الأجهزة الطرفية، إلا أن نقطة البيع الحديثة لنظام التشغيل Windows وحدها هي التي تدعمها بشكل مباشر. بالنسة لجميع التطبيقات الأخرى، يُتطلب وجود محطة أجهزة واحدة أو أكثر. على الرغم من أن هذا الأسلوب يضيف الكثير من المرونة، إلا أنه يجب نشر مكونات إضافية وتكوينها وصيانتها.
- **متطلبات النظام** - تختلف متطلبات النظام الخاصة بتطبيق نقطة البيع. يجب عليك التحقق من الحصول على أحدث المعلومات قبل أن تقوم باختيارك. على سبيل المثال، نظراً لأنه يتم تشغيل نقطة بيع المجموعة في مستعرض، فإنها تدعم عددًا كبيرًا من أنظمة التشغيل. لمزيد من المعلومات حول متطلبات النظام، راجع [متطلبات النظام لعمليات نشر المجموعة](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/system-requirements).
- **النشر والصيانة** - قد يختلف تعقيد التوزيع والصيانة استنادًا إلى اختيارات التطبيق والنشر. على سبيل المثال، لنشر نقطة بيع مجموعة مستضافة على مجموعة، لا يلزمك التثبيت والتحديث على كل جهاز. ولذلك، يقلل هذا الأسلوب من التعقيد والتكلفة بشكل كبير. ومع ذلك، إذا قمت بنشر نقطة بيع حديثة على كل سجل وتمكين وضع دون الاتصال، وقمت أيضًا بنشر محطات الأجهزة المشتركة، فيمكنك زيادة عدد نقاط النهاية التي يجب أن تتم إدارتها بشكل كبير.