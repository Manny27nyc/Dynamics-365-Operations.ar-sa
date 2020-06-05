---
title: نظرة عامة على طباعة المستند
description: يمكنك طباعة المستندات باستخدام طابعة محلية أو أحد الأجهزة المتصلة بشبكة الاتصال. يقدم هذا المقال نظرة عامة على كيفية طباعة المستندات.
author: TJVass
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: IT Pro, Application User
ms.reviewer: kfend
ms.search.scope: Operations, Core
ms.custom: 69161
ms.assetid: 7815bddd-c4f4-4bc3-a29b-315458065374
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9acc4c26febacf4ec7647cf436ac678e52df3973
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772548"
---
# <a name="document-printing-overview"></a>نظرة عامة على طباعة المستند

[!include [banner](../includes/banner.md)]

يمكنك طباعة المستندات باستخدام طابعة محلية أو أحد الأجهزة المتصلة بشبكة الاتصال. يقدم هذا المقال نظرة عامة على كيفية طباعة المستندات.

## <a name="printing-overview"></a>نظرة عامة على الطباعة

يوفر التطبيق خدمات متكاملة وتطبيقات العميل التي تجعل من السهل إنشاء وتخزين وتوزيع المستندات التي تدعم نشاط الشركة. يمكنك طباعة المستندات باستخدام طابعة محلية أو أحد الأجهزة المتصلة بشبكة الاتصال. بالإضافة إلى ذلك، يمكنك تصدير صفحات وتقارير مباشرةً من العميل، كملفات PDF أو مستندات Microsoft Office. وأخيراً، يتيح لك حمل العمل الموزع طباعة مستندات العمل مباشرةً من جهاز محمول باستخدام موارد الشبكة. على الرغم من أنه قد تختلف متطلبات الطباعة، يجب على كل الصناعات عادةً إنشاء نسخ من مستندات الأعمال باستخدام التطبيق. تمثل طباعة المستندات على أجهزة الشبكة من التطبيقات المضيفة مجموعة فريدة من التحديات. فيما يلي بعض الأمثلة:

- قد تكون برامج تشغيل الطباعة غير متوفرة على جهاز المستخدم.
- قد لا يكون الجهاز الخاص بالمستخدم متصلاً بشبكة الشركة.

باستخدام مضيف مخصص واتباع خطوات بسيطة قليلة، يمكن لمسؤولي النظام تكوين عمليات النشر حتى يستطيع المستخدمون الطباعة مباشرةً من تطبيقات العمل على أجهزة الشبكة.

### <a name="application-printing-scenarios"></a>سيناريوهات الطباعة في التطبيق 

يصف الجدول التالي سيناريوهات الطباعة الثلاثة الأساسية.

| سيناريو                        | الهدف                                                      | الحل |
|---------------------------------|-----------------------------------------------------------|----------|
| 1. طباعة ما تشاهده        | قم بطباعة ما يظهر في المستعرض حاليًا.             | يتم إنشاء إصدار "تسهل طباعته" من صفحة ويب للمستعرض. |
| 2. الطباعة التفاعلية         | قم بطباعة مستند دقة على جهاز متصل محليًا. | يمكنك تصدير نسخة PDF من التقرير وتنزيلها إلى المستعرض. |
| 3. الطباعة على جهاز شبكة | أرسل مستند دقة إلى جهاز طابعة مجال.     | يتم إرسال مستند دقة إلى تطبيق عميل يتم تشغيله على خادم تتم استضافته في المجال الخاص بالعميل. |

نظراً لأن الحل يختلف، استنادًا التي السيناريو، توفر التطبيقات الخدمات المضمنة والأدوات لمساعدة المستخدمين على تحقيق الأهداف الخاصة بها:

- **السيناريو 1** مدعوم بواسطة عرض المستعرض لعميل HTML5.
- **السيناريو 2** يستخدم تطبيقات العميل وخدمات Microsoft Office 365.
- **السيناريو 3** يحتاج إلى الدعم من تطبيقات العميل ومن الخدمات المستضافة في Microsoft Azure.

بالإضافة إلى النظام الأساسي الذي يتم نشره لاشتراك Azure، تزود تطبيقات Finance and Operations العملاء بتطبيق Azure متكامل وأصيل يساعدهم على استخدام الأجهزة المستضافة من قِبل المجال لطباعة المستندات بسهولة أكبر.

## <a name="service-overview"></a>نظرة عامة على الخدمة
بينما تنتظر المستندات التي يتم إنتاجها بواسطة التطبيقات المستضافة الطباعة على أحد الأجهزة المتصلة بشبكة، يتم تخزينها في تخزين Azure blob. يستخدم [تثبيت وكيل توجيه المستند لتمكين طباعة الشبكات](install-document-routing-agent.md) مصادقة Azure لتأسيس قناة آمنة لخدمات Azure.

**تسلسل عمليات التنفيذ**

1. يتم إنشاء التقرير بواسطة Microsoft SQL Server Reporting Services (SSRS) ويتم تخزينه في مخزن الكائن الثنائي كبير الحجم‬‬ من Azure. يتم تخزين إعدادات الطابعة التي تم توصيلها مع المستند.
2. يستعلم "وكيل توجيه المستند" قائمة انتظار ناقل خدمة Azure للحصول على الوظائف النشطة.
3. يتم تنزيل المستند بواسطة "وكيل توجيه المستند" وتخزينه في طابعة الشبكة.

يتيح الحل المستند إلى العميل للعملاء إدارة مقياس احتياجات الطباعة. يستطيع العملاء الذين لديهم أحمال عمل طباعة ثقيلة الحجم تثبيت العديد من "وكلاء توجيه المستندات" لزيادة عدد عمليات الطباعة المتزامنة. بدلاً من ذلك، يتطلب بعض العملاء عمليات تثبيت قليلة جداً لـ "وكيل توجيه المستند" لمعالجة احتياجات الطباعة المتوقعة.

### <a name="service-components-for-network-printing"></a>مكونات الخدمة للطباعة على الشبكة

يوضح المخطط التالي المكونات الأساسية التي تساعد في دعم عمليات الطباعة على الشبكة.

[![service-components-for-network-printing\_2016](./media/service-components-for-network-printing_2016.png)](./media/service-components-for-network-printing_2016.png)

لاحظ أنه يمكن تسجيل طابعة واحدة مع عدة وكلاء توجيه مستندات. لحل تفضيلات الطابعة، تستخدم الخدمة المستضافة مسار الشبكة الذي يحدد كل طابعة شبكة بشكل فريد. وكنتيجة لذلك، حتى في حالة تسجيل طابعة بواسطة العديد من العملاء، فإنها تظهر كتحديد واحد في قائمة الطابعات المتوفرة في التطبيقات.