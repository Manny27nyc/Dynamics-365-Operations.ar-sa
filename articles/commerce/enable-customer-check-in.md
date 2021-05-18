---
title: تمكين إعلامات إيداع العملاء في نقطة البيع (POS)
description: يوضح هذا الموضوع كيفيه تمكين إعلامات إيداع العملاء في نقطة بيع Microsoft Dynamics 365 Commerce (POS).
author: bicyclingfool
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: e4defc15d9ef198a361934d51e31016747dbb5ab
ms.sourcegitcommit: 593438a145672c55ff6a910eabce2939300b40ad
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/23/2021
ms.locfileid: "5937558"
---
# <a name="enable-customer-check-in-notifications-in-point-of-sale-pos"></a>تمكين إعلامات إيداع العملاء في نقطة البيع (POS)

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

يوضح هذا الموضوع كيفيه تمكين إعلامات إيداع العملاء في نقطة بيع Microsoft Dynamics 365 Commerce (POS).

في رسائل البريد الإلكتروني الخاصة بـ "الطلب جاهز للاستلام"، يمكن للمؤسسات توفير رابط أو زر يسمح للعملاء بإخطار المتجر بأنهم موجودون في المبنى وينتظرون إحضار الحزمة الخاصة بهم إليهم. يتلقى العملاء بعد ذلك تأكيدًا لتسجيل الوصول، ويتلقى المتجر إشعارًا كمهمة في تطبيق نقطة البيع الخاص به. تعمل هذه المهمة كمطالبة بمساعد المبيعات لتسليم الأمر إلى سيارة العميل. لذلك، لا يتعين على العميل الدخول إلى المتجر.

يمكن أيضًا تكوين سير عمل تسجيل وصول العميل لجمع معلومات إضافية من العملاء، مثل رقم مكان وقوف السيارات الخاص بهم، والنوع، والطراز، ولون سيارتهم، وتعليمات التسليم. يمكن لصاحب متجر البيع بالتجزئة استخدام هذه المعلومات لتسهيل تنفيذ الطلب.

## <a name="enable-customer-check-in"></a>تمكين إيداع العملاء

عند تشغيل ميزة إيداع العميل، تنشئ التجارة معرف تأكيد الطلب (المعروف أيضًا باسم معرف مرجع القناة). كما يقوم أيضًا بإنشاء معرفات تأكيد الطلب للأوامر التي تم إنشاؤها من خلال نقاط البيع (POS) أو قنوات مركز الاتصال. 

لتشغيل ميزة إيداع العميل في المقر الرئيسي للتجارة، اتبع هذه الخطوات.

1. انتقل إلى **مساحات العمل \> إدارة الميزات**.
2. ابحث عن ميزة **إنشاء تنسيق معرف مرجعي ثابت للقناة عبر القنوات**. 
3. حدد الميزة، ثم حدد **تمكين الآن** في جزء الخصائص. 

## <a name="create-a-check-in-confirmation-page"></a>إنشاء صفحة تأكيد الإيداع

على موقع التجارة الإلكترونية الخاص بك، يجب عليك إنشاء صفحة جديدة ستكون بمثابة تجربة تأكيد الإيداع. من خلال التكوين الإضافي، يمكن أن تتضمن الصفحة أيضًا نموذجًا يجمع معلومات إضافية من العملاء لتسهيل تنفيذ الطلبات. للحصول على معلومات حول كيفية إعداد الصفحة والوحدة، راجع [وحدة إيداع العميل](check-in-pickup-module.md).

## <a name="configure-the-transactional-email-template"></a>تكوين قالب البريد الإلكتروني للحركات

يجب عليك إضافة زر أو ارتباط **أنا هنا** إلى نموذج البريد الإلكتروني للحركات الذي يتلقاه العملاء عندما يكون طلبهم جاهزًا للاستلام. سيستخدم العملاء هذا الرابط أو الزر لإخطار المتجر بوصولهم لاستلام طلباتهم. 

أضف الارتباط أو الزر إلى القالب الذي تم تعيينه إلى نوع إعلام **اكتملت التعبئة** وطريقة التسليم التي تستخدمها لتنفيذ الطلبات على جانب الطريق. في القالب، قم بإنشاء ارتباط HTML أو زر يشير إلى عنوان URL لصفحة تأكيد الإيداع التي قمت بإنشائها. فيما يلي مثال على ذلك.

```
<a href="https://[YOUR_SITE_DOMAIN]/[CHECK-IN_CONFIRMATION_PAGE]?channelReferenceId=%channelreferenceid%&channelId=%channelid%&packingSlipId=%packingslipid%" target="_blank">I am here!</a>
```
لمزيد من المعلومات حول كيفية تكوين قوالب البريد الإلكتروني، راجع [تخصيص رسائل البريد الإلكتروني للحركات حسب طريقة التسليم](customize-email-delivery-mode.md). 

## <a name="a-check-in-confirmation-task-is-created-in-pos"></a>تم إنشاء مهمة تأكيد الإيداع في نقطة البيع

بعد أن يقوم العميل بإخطار المتجر بأنه موجود للاستلام، يتلقى إشعارًا بتأكيد تسجيل الوصول، ويتم إنشاء مهمة في قائمة المهام في نقطة البيع للمخزن حيث يقوم العميل باستلام الطلب. تحتوي المهمة على كافة معلومات العميل والأمر المطلوبة لاستيفاء الطلب. في المهمة، يُظهر حقل التعليمات أي معلومات تم جمعها من العميل من خلال نموذج المعلومات الإضافية. 

## <a name="additional-resources"></a>الموارد الإضافية

[وحدة الإيداع للتسليم](check-in-pickup-module.md)