---
title: الشروع في العمل في ‏‫محاسبة المخزون العالمي
description: يصف هذا الموضوع كيفية الشروع في العمل مع محاسبة المخزون العالمي.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 59f9db309312bbbc88b4fa47c12c4c02f09e7c6d
ms.sourcegitcommit: cbbb35c71ab4ff1ae08fa4f7cc97019b207246be
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301688"
---
# <a name="get-started-with-global-inventory-accounting"></a>الشروع في العمل في ‏‫محاسبة المخزون العالمي

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

تتيح لك محاسبة المخزون العالمي إجراء محاسبات متعددة للمخزون في دفاتر الأستاذ العام لمحاسبة المخزون العالمي التي قمت بإعدادها. يمكنك إقران كل دفتر أستاذ لمحاسبة المخزون العالمي بـ *اصطلاح*. والاصطلاح هو مجموعة من الأنواع التالية من سياسات المحاسبة:

- كائن التكلفة
- أساس قياس الإدخال
- افتراض تدفق التكلفة
- عنصر التكلفة

> [!NOTE]
> حتى بعد تشغيل خدمة محاسبة المخزون العالمي، ما يزال بإمكانك إجراء محاسبة المخزون في Microsoft Dynamics 365 Supply Chain Management كما هو معتاد.

تُعد محاسبة المخزون العالمي وظيفة إضافية. ولجعل ميزاتها متوفرة، يجب أن تثبتها من Microsoft Dynamics Lifecycle Services (LCS). يمكنك اختيار تقييمها في بيئة اختبار قبل تشغيلها في بيئات التشغيل.

لا تدعم محاسبة المخزون العالمي حاليًا كافة ميزات إدارة التكلفة المضمنة في Supply Chain Management. بالتالي، من المهم أن تجري تقييمًا بشأن ما إذا كانت مجموعة الميزات المتوفرة حاليًا ستلبي متطلباتك أم لا.

## <a name="how-to-get-the-global-inventory-accounting-public-preview"></a><a name="sign-up"></a>كيفية الحصول على إصدار أولي للاستخدام العام لمحاسبة المخزون العالمي

> [!IMPORTANT]
> لاستخدام محاسبة المخزون العام، يجب أن يكون لديك بيئة عالية التوفر ممكن بها LCS (ليس بيئة OneBox). بالإضافة إلى ذلك، يجب تشغيل Supply Chain Management الإصدار 10.0.19 أو إصدار لاحق.

للتسجيل في الإصدار الأولي للاستخدام العام لمحاسبة المخزون العالمي، قم بإرسال معرف بيئة LCS الخاص بك بالبريد الإلكتروني إلى [فريق محاسبة المخزون العالمي](mailto:GlobalInventoryAccounting@service.microsoft.com). وبعد الموافقة على البرنامج، سيقوم الفريق بإرسال بريد إلكتروني للمتابعة يحتوي على مفتاح بيتا لمحاسبة المخزون العالمي ونقاط نهاية الخدمة. بعد استلام مفتاح بيتا، يمكنك [تثبيت الوظيفة الإضافية](#install).

## <a name="licensing"></a>الترخيص

يجري ترخيص محاسبة المخزون العالمي معًا مع الميزات القياسية لمحاسبة المخزون المتوفرة لـ Supply Chain Management. لا يتعين عليك شراء ترخيص إضافي لاستخدام محاسبة المخزون العالمي.

## <a name="prerequisites"></a>المتطلبات الأساسية

### <a name="set-up-microsoft-power-platform-integration"></a>إعداد تكامل Microsoft Power Platform

قبل تمكين وظيفة الوظيفة الإضافية، فإنه يجب التكامل مع Microsoft Power Platform باتباع الخطوات التالية.

1. افتح بيئة LCS حيث تريد إضافة الخدمة بها.
1. انتقل إلى **التفاصيل الكاملة**.
1. في القسم **تكامل Power Platform**، حدد **إعداد**.
1. في مربع الحوار **إعداد بيئة Power platform**، حدد خانة الاختيار، ثم حدد **إعداد** وعادةً، يستغرق الإعداد بين 60 و90 دقيقة.
1. بعد اكتمال الإعداد الخاص بالبيئة Microsoft Power Platform، تعرض الصفحة اسم البيئة الخاصة بك. بالإضافة إلى ذلك، يعرض القسم تكامل **Power Platform** الكشف و"تم إكمال إعداد البيئة Power Platform". لا تتطلب محاسبة المخزون العالمي تطبيقًا ثنائي الكتابة.

لمزيد من المعلومات، راجع [الإعداد بعد نشر البيئة](../../fin-ops-core/dev-itpro/power-platform/overview.md#set-up-after-environment-deployment).

### <a name="set-up-dataverse"></a>إعداد Dataverse

قبل إعداد Dataverse، قم بإضافة مبادئ خدمة محاسبة المخزون العالمي إلى المستأجر باتباع الخطوات التالية.

1. قم بتثبيت وحدة Azure AD النمطية لـ Windows PowerShell الإصدار 2 كما هو موضح في [تثبيت Azure Active Directory PowerShell للرسم البياني](/powershell/azure/active-directory/install-adv2).
1. قم بتشغيل الأمر PowerShell التالي.

    ```powershell
    Connect-AzureAD # (open a sign in window and sign in as a tenant user)

    New-AzureADServicePrincipal -AppId "7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9" -DisplayName "d365-scm-costaccountingservice"

    New-AzureADServicePrincipal -AppId "5f58fc56-0202-49a8-ac9e-0946b049718b" -DisplayName "d365-scm-operationdataservice"
    ```

بعد ذلك، قم بإنشاء مستخدمي التطبيق لمحاسبة المخزون العالمي في Dataverse باتباع الخطوات التالية.

1. افتح عنوان URL الخاص ببيئة Dataverse الخاصة بك.
1. انتقل إلى **إعدادات متقدمة \> النظام \> الأمان \> المستخدمين**، وقم بإنشاء مستخدم تطبيق. استخدم الحقل **عرض** لتغيير طريقة عرض الصفحة إلى *مستخدمي التطبيق*.
1. حدد **جديد**.
1. عيّن الحقل **معرف التطبيق** إلى *7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9*.
1. حدد **تعيين دور**، ثم حدد *مسؤول النظام*. إذا كان هناك دور يسمي *مستخدم Common Data Service*، فحدده أيضًا.
1. كرر الخطوات السابقة، ولكن قم بتعيين الحقل **معرف التطبيق** إلى *5f58fc56-0202-49a8-ac9e-0946b049718b*.

لمزيد من المعلومات، راجع [إنشاء مستخدم تطبيق](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).

إذا لم تكن اللغة الإنجليزية لتثبيت Dataverse هي اللغة الافتراضية، اتبع الخطوات التالية.

1. انتقل إلى **إعداد متقدم \> الإدارة \> اللغات**.
1. حدد *الإنجليزية* (*LanguageCode=1033*)، ثم حدد **تطبيق**.

## <a name="install-the-add-in"></a><a name="install"></a>تثبيت الوظيفة الإضافية

اتبع هذه الخطوات لتثبيت الوظيفة الإضافية بحيث يمكنك استخدام محاسبة المخزون العالمي.

1. [التسجيل](#sign-up) إصدار أولي للاستخدام العام لمحاسبة المخزون العالمي.
1. سجل الدخول إلى [LCS](https://lcs.dynamics.com/Logon/Index).
1. انتقل إلى **إدارة ميزة المعاينة**.
1. حدد علامة الزائد (**+**).
1. في حقل **الرمز**، أدخل مفتاح بيتا للوظيفة الإضافية لمحاسبة المخزون العالمي. (يجب أن تكون قد حصلت على مفتاح بيتا الخاص بك عبر البريد الإلكتروني عند التسجيل الاشتراك.)
1. حدد **إلغاء الحظر**.
1. افتح بيئة LCS حيث تريد إضافة الخدمة بها.
1. انتقل إلى **التفاصيل الكاملة**.
1. انتقل إلى **تكامل Power Platform**، وحدد **إعداد**.
1. في مربع الحوار **إعداد بيئة Power platform**، حدد خانة الاختيار، ثم حدد **إعداد** وعادةً، يستغرق الإعداد بين 60 و90 دقيقة.
1. بعد إكمال إعداد بيئة Microsoft Power Platform، في علامة التبويب السريعة **الوظائف الإضافية للبيئة**، حدد **تثبيت وظيفة إضافية جديدة**.
1. حدد **محاسبة المخزون العالمي**.
1. اتبع دليل التثبيت، ووافق على البنود والشروط.
1. حدد **تثبيت**.
1. في علامة التبويب السريعة **الوظائف الإضافية للبيئة**، يجب أن تشاهد محاسبة المخزون العالمي قد تم تثبيتها. بعد بضع دقائق، يجب أن تغير الحالة من *قيد التثبيت* إلى *مثبت*. (قد تحتاج إلى تحديث الصفحة لعرض هذا التغيير.) في تلك النقطة، تكون محاسبة المخزون العالمي جاهزة للاستخدام.

## <a name="set-up-the-integration"></a>إعداد التكامل

اتبع هذه الخطوات لإعداد التكامل بين محاسبة المخزون العالمي وSupply Chain Management.

1. سجل دخولك إلى Supply Chain Management.
1. انتقل إلى **إدارة النظام \> إدارة الميزات**.
1. حدد **التحقق من وجود تحديثات**.
1. في علامة التبويب **الكل**، ابحث عن الميزة التي تسمي *محاسبة المخزون العالمي*.
1. حدد **تمكين الآن**.
1. انتقل إلى **محاسبة المخزون العالمي \> الإعداد \> معلمات محاسبة المخزون العالمي \> معلمات التكامل**.
1. في الحقلين **نقطة نهاية خدمة البيانات** و **نقطة نهاية محاسبة المخزون العالمي**، أدخل عناوين URL من البريد الإلكتروني الذي أرسله فريق محاسبة المخزون العالمي عند التسجيل في الإصدار الأولي.

محاسبة المخزون العالمي جاهزة الآن للاستخدام.