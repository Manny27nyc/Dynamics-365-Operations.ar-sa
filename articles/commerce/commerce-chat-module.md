---
title: محادثه تجاره مع أومنيتشانيل للوحدة النمطية لخدمه العملاء
description: توضح هذه المقالة محادثه التجارة مع أومنيتشانيل للوحدة النمطية لخدمه العملاء في Microsoft Dynamics 365 Commerce
author: gvrmohanreddy
ms.date: 08/23/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-07-20
ms.openlocfilehash: b8eaed3eb015e96b1db6fa2297c341ea9d3ff8ad
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473799"
---
# <a name="commerce-chat-with-omnichannel-for-customer-service-module"></a>محادثه تجاره مع أومنيتشانيل للوحدة النمطية لخدمه العملاء

[!include [banner](includes/banner.md)]

توضح هذه المقالة *محادثه التجارة مع أومنيتشانيل للوحدة النمطية* لخدمه العملاء في Microsoft Dynamics 365 Commerce.

في الإصدار 10.0.29 إصدار التجارة ، تمت أضافه محادثه تجاره جديده مع أومنيتشانيل الخاصة بالوحدة النمطية لخدمه العملاء إلى مكتبه الوحدة النمطية التجارية. وتوفر ميزه المحادثة التجارية للعملاء التجاريين الكترونيين الذين لديهم إمكانيات المحادثة من أجل Dynamics 365 أومنيتشانيل لخدمه العملاء ، والتي تتضمن دعم العامل النشط للمساعدة في عناوين استعلامات العملاء ، وتوفير خدمه العملاء ، وتسهيل المبيعات للعملاء التجاريين.

تعمل ميزه المحادثة التجارية علي تمكين البائعين من التجزئة لتحقيق هذه الأهداف:

- قم بزيادة التفاوض المخصص مع العملاء للمساعدة علي تحسين استبقاء العميل.
- تحسين خدمه العملاء من خلال تكامل تشاتبوتس العاملين البشرية والخدمات الذاتية.
- تقوم عوامل التعليمات بالحصول علي خبره من خلال ملف تعريف العملاء في الوقت الحقيقي والأمر وبيانات الشراء التي تعمل علي تشغيل تحسينات ومفاوضات تشغيليه.
- قم بتحسين رضا العميل الكلي للمساعدة في زيادة المبيعات.

تتوفر الإمكانات التالية كجزء من ميزة الدردشة التجارية:

- محادثة التجارة مع Omnichannel لخدمة العملاء
- أضافه مركز **الاتصال** التجاري كعلامة تبويب تطبيق في أسلوب عمل العميل في Dynamics 365 أومنيتشانيل لخدمه العملاء

## <a name="prerequisites-for-omnichannel-for-customer-service"></a>المتطلبات الاساسيه لأومنيتشانيل لخدمه العملاء

وكمتطلب أساسي ، يجب تكوين المحادثة في أومنيتشانيل لواجهه مستخدم خدمه العملاء ، والحصول علي بعض المحددات لتكوين تجربه المحادثة التجارية. للحصول على إرشادات، راجع [تكوين قناة دردشة](/dynamics365/customer-service/set-up-chat-widget).

بعد تكوين المحادثة في أومنيتشانيل لواجهه مستخدم أداره خدمه العملاء ، ستحصل علي برنامج نصي يشبه المثال التالي.

`<script id="Microsoft_Omnichannel_LCWidget" src="https://oc-cdn-ocprod.azureedge.net/livechatwidget/scripts/LiveChatBootstrapper.js" data-app-id="xxxx-xxx-4be7-bcd5-1d118ecffe1f" data-org-id="5a0e73c0-xxxx-xxxxx-xxx- 76df135f375d" data-org-url="https://xxsxxxxssdb348f-crm.omnichannelengagementhub.com"></script>`

انسخ هذا البرنامج النصي ، لأنك ستحتاج إلى القيم الموجودة فيه لتكوين الوحدة النمطية للمحادثة.

### <a name="commerce-chat-with-omnichannel-for-customer-service-mandatory-fields"></a>الحقول الإلزامية الدردشة التجارية مع Omnichannel لخدمة العملاء

يعرض الجدول التالي قيم البرامج النصية من أومنيتشانيل لواجهه مستخدم أداره خدمه العملاء المطلوبة لتكوين محادثه التجارة مع أومنيتشانيل النمطية لخدمه العملاء.

| خاصيه Widget | ‏‏الوصف‬ |
| ------------- |--------------|
| مصدر البرنامج النصي | قيمه **src** في البرنامج النصي لعنصر واجهه مستخدم المحادثة. |
| معرف تطبيق البيانات | قيمه **معرّف تطبيق البيانات** في البرنامج النصي لأداة الدردشة. |
| معرف منظمة البيانات | قيمه **معرّف مؤسسة البيانات** في البرنامج النصي لأداة الدردشة. |
| عنوان URL لتنظيم البيانات | قيمه **بيانات-org-url** في البرنامج النصي لأداة الدردشة. |

## <a name="configure-the-commerce-chat-experience-for-your-e-commerce-site"></a>تكوين تجربه المحادثة التجارية لموقع التجارة الكترونيه لديك

أحدي الطرق الموصي بها لتطبيق تجربه المحادثة لموقع التجارة الكترونيه هي أضافه المحادثة التجارية مع أومنيتشانيل للوحدة النمطية لخدمه العملاء إلى جزء الراس المشترك المستخدم في صفحات موقع التجارة الكترونيه.

لإضافة وحدة الدردشة إلى جزء رأس موقعك في Commerce Site Builder ، اتبع هذه الخطوات.

1. في موقع البناء لموقعك ، انتقل إلى **Fragments**.
1. حدد **جديد**.
1. في مربع الحوار **تحديد جزء** ، حدد المحادثة التجارية **مع أومنيتشانيل للوحدة النمطية لخدمه** العملاء ، وادخل اسما لجزء ، ثم حدد **موافق**.
1. في عرض المخطط التفصيلي ، حدد **فتحه موصل** المحادثة cs Msdyn365.
1. في جزء **خصائص الدردشة** على اليمين، اتبع هذه الخطوات:

    1. في الحقل مصدر **البرنامج النصي** ، ادخل **قيمه src** التي حصلت عليها من أومنيتشانيل لبرنامج العميل النصي لخدمه العملاء.
    1. في **معرف تطبيق البيانات** ، ادخل **تطبيق البيانات ط** التي حصلت عليها من أومنيتشانيل لبرنامج العميل النصي لخدمه العملاء.
    1. في حقل **معرف منظمة البيانات** ، **القيمة data-org-id** التي حصلت عليها من أومنيتشانيل لبرنامج العميل النصي لخدمه العملاء.
    1. في حقل **عنوان URL لتنظيم البيانات** ،أدخل **القيمة data-org-url** التي حصلت عليها من أومنيتشانيل لبرنامج العميل النصي لخدمه العملاء.

    ![إنشاء جزء وحده محادثه تجاريه في منشئ مواقع التجارة.](media/Commerce-chat-creating-new-fragment.png)

1. حدد **حفظ**، وحدد **إنهاء التحرير** لإيداع الجزء، ثم حدد **نشر** لنشره.
1. انتقل إلى **أجزاء** ، وافتح جزء الراس الخاص بموقعك.
1. في فتحة **الحاوية الافتراضية‬‬‏‫** ، حدد علامة القطع (**...**)، ثم حدد **إضافة جزء**.
1. في مربع الحوار **تحديد الوحدات** ، حدد جزء المحادثة الذي قمت بإنشائه مسبقًا ، ثم حدد **موافق**.
1. حدد **حفظ**، وحدد **إنهاء التحرير** لإيداع الجزء، ثم حدد **نشر** لنشره.

## <a name="add-commerce-headquarters-as-an-application-tab-for-omnichannel-for-customer-service"></a>أضافه Commerce headquarters كتبويب تطبيق لأومنيتشانيل لخدمه العملاء

يمكنك إضافة علامة تبويب تطبيق لCommerce headquarters في Omnichannel لخدمة العملاء. يمكن للعاملين المباشرين بعد ذلك استخدام واجهه المستخدم الخاصة بأومنيتشانيل لتجربه عميل خدمه العملاء للوصول بسهوله إلى الوحدة النمطية Dynamics 365 Commerce لخدمه العملاء والتي تحتوي علي معلومات سياقيه للعميل مع معلومات أوامر التوريد الخاصة بهم. بالاضافه إلى ذلك ، يمكن لعوامل خدمه العملاء وضع أوامر جديده وبدء المرتجعات والتحقق من معلومات حاله الطلب.

### <a name="create-a-new-application-tab-that-loads-commerce-headquarters-in-an-iframe-module"></a>إنشاء علامة تبويب تطبيق جديده تقوم بتحميل Commerce headquarters في iFrameوحده نمطيه 

لإنشاء علامة تبويب تطبيق جديده تقوم بتحميل Commerce headquartersفي iFrame الوحدة النمطية، اتبع هذه الخطوات.

1. افتح [Power Apps بوابة المنشئ](https://make.powerapps.com).
1. في جزء التنقل علي اليسار، حدد **التطبيقات**.
1. حدد **مركز** أداره خدمه العملاء.
1. انتقل إلى تجربه **الوكيل**.
1. لقوالب **علامة** التبويب التطبيق ، حدد **أداره**.
1. قم بإنشاء علامة تبويب تطبيق جديد لنوع **موقع** الجهة الخارجية. للحصول على التعليمات ، انظر [إدارة قوالب علامة تبويب التطبيق](/dynamics365/app-profile-manager/application-tab-templates?tabs=customerserviceadmincenter).
1. ضمن **المعلمات** ، في الحقل **القيمة** لمعلمه **url** ، ادخل عنوان url التالي ، حيث `<YourOrganizationHeadquartersURL>` يتم استبدال و `<LegalEntityname>` بالقيم المناسبة. أومنيتشانيل خدمه العملاء بالقراءة **{AccountNumber}** من سياق المحادثة. ولذلك ، اترك **{AccountNumber}** كما هو.

    `https://<YourOrganizationHeadquartersURL>/?mi=MCRCustomerService&cmp=<LegalEntityName>&embedded=true&customerId={AccountNumber}`

1. اترك **حقل القيمة** الخاص بمعلمه **البيانات** فارغا.

![إنشاء علامة تبويب تطبيق في Dynamics 365 أومنيتشانيل Service.](media/OC-CS-Admin-Application-Tab-Parameters.png)

## <a name="enable-a-new-application-tab-for-customer-agents-in-dynamics-365-omnichannel-for-customer-service"></a>تمكين علامة تبويب تطبيق جديد لعوامل العملاء في Dynamics 365 أومنيتشانيل لخدمه العملاء

لتمكين علامة تبويب تطبيق جديدة لوكلاء العملاء في Dynamics 365 Omnichannel لخدمة العملاء، اتبع هذه الخطوات.
    
1. افتح [Power Apps بوابة المنشئ](https://make.powerapps.com).
1. في جزء التنقل علي اليسار، حدد **التطبيقات**.
1. حدد **مركز** أداره خدمه العملاء.
1. انتقل إلى **دعم العميل \> مسارات العمل**.
1. افتح ووركستريم الذي قمت بإنشاءه لوكلاءك ، ثم ضمن **إعدادات** متقدمة ، حدد **افتراضيات** جلسات العمل.
1. ضمن **علامات تبويب** التطبيق ، حدد **علامة التبويب** أضافه تطبيق موجود ، ثم أضف علامة التبويب التطبيق الجديد التي قمت بإنشاءها سابقا. تضمن هذه الخطوة انه ستظهر علامة التبويب التطبيق التي تقوم بتحميل Commerce headquarters في iFrame وحده نمطيه عندما يتلقى أحد الوكلاء مكالمة محادثه وارده من موقع الويب الخاص بالتجارة الكترونيه.

## <a name="add-context-variables-in-dynamics-365-omnichannel-for-customer-service"></a>أضافه متغيرات السياق في Dynamics 365 أومنيتشانيل لخدمه العملاء

لإضافة متغيرات السياق في Dynamics 365 Omnichannel لخدمة العملاء ، اتبع هذه الخطوات.

1. افتح [Power Apps بوابة المنشئ](https://make.powerapps.com).
1. في جزء التنقل علي اليسار، حدد **التطبيقات**.
1. حدد **مركز** أداره خدمه العملاء.
1. انتقل إلى **دعم العميل \> مسارات العمل**.
1. افتح ووركستريم الذي قمت بإنشاءه لوكلاءك ، ثم ضمن **إعدادات** متقدمة ، انتقل إلى جزء **متغير السياق**.
1. حدد **تحرير** ، ثم قم باضافه **AccountNumber** كمتغير سياق لنوع **النص**. سيساعد هذا المتغير Commerce headquarters في تحميل معلومات العميل بأرقام الحسابات المطابقة.

> [!NOTE]
> إذا كنت ترغب في قراءه عناوين البريد الكتروني وأسماء المستخدمين المسجلين الدخول من أحدي قنوات التجارة الكترونيه ، فيمكنك أضافه البريد الكتروني **والاسم** كمتغيرات السياق الخاصة بنوع **النص** ، بالاضافه إلى **متغير** السياق **AccountNumber**.