---
title: تثبيت الوظيفة الإضافية لرؤية المخزون
description: يوضح هذا الموضوع كيفيه تثبيت الوظيفة الإضافية لرؤية المخزون لـ Microsoft Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: eb17f24b90933dac0f875bb0ef2d5039a240b197
ms.sourcegitcommit: 1ca4ad100f868d518f3634dca445c9878962108e
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 09/01/2022
ms.locfileid: "9388530"
---
# <a name="install-and-set-up-inventory-visibility"></a>تثبيت Inventory Visibility وإعداده

[!include [banner](../includes/banner.md)]

يوضح هذا الموضوع كيفيه تثبيت الوظيفة الإضافية لرؤية المخزون لـ Microsoft Dynamics 365 Supply Chain Management.

يجب عليك استخدام Microsoft Dynamics Lifecycle Services (LCS) لتثبيت الوظيفة الإضافية لرؤية المخزون. LCS عبارة عن مدخل تعاون يوفر بيئة ومجموعه من الخدمات المحدثة بشكل منتظم والتي تساعدك علي أداره دوره حياه التطبيقات الخاصة بتطبيقات finance and operations الخاصة بك. للحصول على مزيد من المعلومات، راجع [موارد Lifecycle Services](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).

> [!TIP]
> نوصي بالانضمام إلى مجموعة مستخدمي الوظيفة الإضافية لرؤية المخزون، حيث يمكنك العثور على أدلة مفيدة، والحصول على آخر التحديثات الخاصة بنا، ونشر أية أسئلة قد تكون لدينا بشأن استخدام رؤية المخزون. للانضمام، الرجاء إرسال بريد إلكتروني إلى رؤية المخزون فريق المنتجات على [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) وتضمين معرف بيئة Supply Chain Management.

## <a name="inventory-visibility-prerequisites"></a>المتطلبات الأساسية لرؤية المخزون

قبل تثبيت رؤية المخزون، يجب عليك إكمال المهام التالية:

- احصل على مشروع تنفيذ LCS حيث يتم نشر بيئة واحدة على الأقل.
- تأكد من أن المتطلبات الأساسية لإعداد الوظائف الإضافية قد اكتملت. للحصول على معلومات حول هذه المتطلبات الأساسية، راجع [نظرة عامة على الوظائف الإضافية](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). لا تتطلب رؤية المخزون ارتباطًا ثنائي الكتابة.

> [!NOTE]
> تشمل البلدان والمناطق المدعومة حاليًا كندا (CCA، ECA)، والولايات المتحدة (WUS، EUS)، والاتحاد الأوروبي (NEU، WEU)، والمملكة المتحدة (SUK، WUK)، وأستراليا (EAU، SEAU) واليابان (EJP, WJP)، والبرازيل (SBR, SCUS).

إذا كانت لديك أي أسئلة حول هذه المتطلبات الأساسية، فاتصل بفريق منتج رؤية المخزون على [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com).

## <a name="install-the-inventory-visibility-add-in"></a><a name="install-add-in"></a>تثبيت الوظيفة الإضافية لرؤية المخزون

قبل تثبيت الوظيفة الإضافية، قم بتسجيل تطبيق وإضافة سر عميل إلى Azure Active Directory (Azure AD) ضمن اشتراك Azure. للحصول على إرشادات، راجع [تسجيل تطبيق](/azure/active-directory/develop/quickstart-register-app) و[إضافة سر عميل](/azure/active-directory/develop/quickstart-register-app#add-a-certificate). تأكد من تدوين ملاحظة بشأن قيم **معرف التطبيق (العميل)** ، و **سر العميل** ، و **معرف المستأجر** ، لأنك ستحتاج إليها لاحقًا.

> [!IMPORTANT]
> إذا كان لديك أكثر من بيئة LCS، فقم بإنشاء تطبيق Azure AD مختلف لكل منهم. في حالة استخدام نفس معرف التطبيق ومعرف المستاجر لتثبيت الوظيفة الإضافية لرؤية المخزون لبيئات مختلفة، ستحدث مشكلة في الرمز المميز للبيئات الأقدم. نتيجة لذلك، سيكون التثبيت الأخير فقط صالحًا.

بعد تسجيل تطبيق وإضافة سر عميل إلى Azure AD، اتبع الخطوات التالية لتثبيت الوظيفة الإضافية "رؤية المخزون".

1. سجل الدخول إلى [LCS](https://lcs.dynamics.com/Logon/Index).
1. في الصفحة الرئيسية ، حدد المشروع حيث يتم نشر البيئة الخاصة بك.
1. في الصفحة المشروع ، حدد البيئة التي ترغب في تثبيت الوظيفة الإضافية بها.
1. في الصفحة البيئة، قم بالتمرير لأسفل حتى تعثر على قسم **الوظائف الإضافية الخاصة بالبيئة** في قسم **تكامل Power Platform**. هناك، يمكنك العثور على اسم بيئة Dataverse. تأكد من أن اسم بيئة Dataverse هو الاسم الذي ترغب في استخدامه لرؤية المخزون.

    > [!NOTE]
    > حاليا، يتم اعتماد بيئات Dataverse التي تم إنشاؤها باستخدام LCS فقط. إذا كنت Dataverse تم إنشاء البيئة بطريقة أخرى (على سبيل المثال ، باستخدام PowerApps مركز المشرف) ، وإذا كان مرتبطًا ببيئة Supply Chain Management الخاصة بك ، فيجب عليك أولاً إصلاح مشكلة التعيين قبل تثبيت الوظيفة الإضافية.
    >
    > من الممكن أن تكون بيئة الكتابة المزدوجة الخاصة بك مرتبطة بمثيل Dataverse بينما لم يتم إعداد LCS لتكامل Power Platform. يمكن أن يتسبب عدم تطابق الارتباط هذا في حدوث سلوك غير متوقع. نوصي بان تكون تفاصيل بيئة LCS مطابقه لما تتصل به في الكتابة المزدوجة حتى يمكن استخدام نفس الاتصال بواسطة احداث الاعمال والجداول الظاهرية والوظائف الاضافيه. راجع [ربط عدم التوافق](../../fin-ops-core/dev-itpro/data-entities/dual-write/lcs-setup.md#linking-mismatch) للحصول علي معلومات حول كيفيه حل مشكله التعيين. وبمجرد حل مشكله التعيين ، يمكنك الاستمرار في تثبيت رؤية المخزون.

1. في قسم **الوظائف الإضافية للبيئة**، حدد **تثبيت وظيفة إضافية جديدة**.

    ![صفحة البيئة في LCS](media/inventory-visibility-environment.png "صفحة البيئة في LCS")

1. حدد الرابط **تثبيت وظيفة إضافية جديدة**. تظهر قائمة بالوظائف الإضافية المتاحة.
1. في القائمة، حدد **رؤية المخزون**.
1. قم بتعيين الحقول التالية لبيئتك:

    - **معرف تطبيق AAD (العميل)** – أدخل معرف تطبيق Azure AD الذي أنشأته ودونت ملاحظة عنه سابقًا.
    - **معرف مستأجر AAD** – أدخل معرف المستأجر الذي دونت ملاحظة عنه في وقت سابق.

    ![صفحة إعداد الوظيفة الإضافية](media/inventory-visibility-setup.png "صفحة إعداد الوظيفة الإضافية")

1. الموافقة علي البنود والشروط عن طريق تحديد خانه الاختيار **البنود والشروط**.
1. حدد **تثبيت**. تظهر حاله الوظيفة الإضافية باعتبارها **قيد التثبيت**. عند اكتمال التثبيت، قم بتحديث الصفحة. يجب تغيير الحالة إلى **تم التثبيت**.
1. في Dataverse، حدد قسم **التطبيقات** في جزء التنقل الأيمن، وتحقق من تثبيت **رؤية المخزون** في Power Apps بطريقة ناجحة. إذا لم يظهر قسم **التطبيقات**، فاتصل بفريق منتج رؤية المخزون على [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com).

> [!NOTE]
> وفي حاله استغراق أكثر من ساعة للتثبيت من الصفحة LCS ، فمن المحتمل ان يكون حساب المستخدم الخاص بك يفتقد اذن لتثبيت حلول في البيئة Dataverse. اتبع هذه الخطوات لحل المشكلة:
>
> 1. قم بإلغاء عملية تثبيت الوظيفة الإضافية لرؤية المخزون من صفحة LCS.
> 1. قم بتسجيل الدخول إلى مركز [Microsoft 365الاداره ](https://admin.microsoft.com)والتاكد من ان حساب المستخدم الذي تريد استخدامه لتثبيت الوظيفة الاضافيه تم تعيين ترخيص " Dynamics 365 Unified Operationsالخطة" له. قم بتعيين الترخيص إذا لزم الأمر.
> 1. تسجيل الدخول إلى [Power Platformمركز ](https://admin.powerplatform.microsoft.com)الاداره باستخدام حساب المستخدم ذي الصلة. ثم قم بتثبيت الوظيفة الإضافية لرؤية المخزون عن طريق القيام بالخطوات التالية:
>     1. حدد البيئة التي تريد تثبيت الوظيفة الإضافية فيها.
>     1. حدد **تطبيقات Dynamics 365**.
>     1. حدد **تثبيت التطبيق**.
>     1. حدد **رؤية المخزون**
>
> 1. بعد اكتمال التثبيت ، انتقل إلى صفحه LCS وحاول أعاده تثبيت الوظيفة الاضافيه لرؤية **المخزون**.

## <a name="set-up-inventory-visibility-in-supply-chain-management"></a><a name="setup-dynamics-scm"></a>إعداد رؤية المخزون في Supply Chain Management

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a>توزيع حزمة تكامل رؤية المخزون

إذا كنت تقوم بتشغيل Supply Chain Management الإصدار 10.0.17 أو إصدار سابق عنه، فتواصل بفريق دعم رؤية المخزون على [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) للحصول علي ملف الحزمة. ثم قم بنشر الحزمة في LCS.

> [!NOTE]
> إذا حدث خطأ عدم تطابق في الإصدار أثناء التوزيع، يجب عليك استيراد مشروع X++ يدويًا إلى بيئة التطوير الخاصة بك. ثم قم بإنشاء الحزمة القابلة للنشر في بيئة التطوير الخاصة بك، ثم قم بنشرها في بيئة الإنتاج الخاصة بك.
>
> يتم تضمين الكود Supply Chain Management في الإصدار 10.0.18. إذا كنت تقوم بتشغيل هذا الإصدار أو الأحدث، فإن عملية النشر تكون غير ضرورية.

تأكد من أنه يتم تشغيل الميزات التالية في بيئة Supply Chain Management. (بشكل افتراضي، يتم تشغيلها.)

| وصف الميزة | إصدار الكود | تبديل الفئة |
|---|---|---|
| تمكين أو تعطيل استخدام أبعاد المخزون في جدول InventSum      | 10.0.11 | InventUseDimOfInventSumToggle      |
| تمكين أو تعطيل استخدام أبعاد المخزون في جدول InventSumDelta | 10.0.12 | InventUseDimOfInventSumDeltaToggle |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a>إعداد تكامل رؤية المخزون

بمجرد تثبيت الوظيفة الإضافية، قم بتحضير نظام Supply Chain Management الخاص بك للعمل معها عن طريق إجراء الخطوات التالية.

1. في Supply Chain Management، افتح مساحة عمل **[إدارة الميزات](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)**، وقم بتشغيل الميزات التالية:
    - *تكامل رؤية المخزون* - مطلوب.
    - *تكامل رؤية المخزون مع إزاحة الحجز* - موصي به لكنه اختياري. يتطلب الإصدار 10.0.22 أو إصدار لاحق. لمزيد من المعلومات، راجع [حجوزات رؤية المخزون](inventory-visibility-reservations.md).

1. انتقل إلى **إدارة المخزون \> الإعداد \> معلمات تكامل رؤية المخزون**.
1. افتح علامة التبويب **عام** وقم بإجراء الإعدادات التالية:
    - **نقطه نهاية رؤية المخزون** – أدخل عنوان URL الخاص بالبيئة التي تقوم فيها بتشغيل رؤية المخزون. للحصول على مزيد من المعلومات، راجع [البحث عن نقطة نهاية الخدمة](inventory-visibility-configuration.md#get-service-endpoint).
    - **الحد الأقصى لعدد السجلات في طلب مفرد** - يتم تعيينه إلى الحد الأقصى لعدد السجلات المطلوب تضمينها في طلب واحد. يجب إدخال عدد صحيح موجب أقل من أو يساوي 1000. القيمة الافتراضية هي 512. نوصي بشدة بالاحتفاظ بالقيمة الافتراضية إلا إذا كنت قد تلقيت نصيحة من دعم Microsoft أو أنك متأكد من أنك تحتاج إلى تغييرها.

1. إذا قمت بتمكين ميزة *تكامل رؤية المخزون مع إزاحة الحجز*، افتح علامة التبويب **إزاحة الحجز** ثم قم بإجراء الإعدادات التالية:
    - **تمكين إزاحة الحجز** - قم بتعيينها إلى *نعم* لتمكين هذه الوظيفة.
    - **معدل إزاحة الحجز** – حدد حالة حركة المخزون التي ستقوم بازاحة عمليات الحجز التي تم إجراؤها في رؤية المخزون. يحدد هذا الإعداد مرحلة معالجة الأمر التي تشغل الإزاحات. يتم تتبع المرحلة حسب حالة حركة المخزون الخاصة بالأمر. اختيار واحد من الخيارات التالية:
        - *في أمر* – بالنسبة لحالة *في الحركة*، سيقوم أمر بإرسال طلب إزاحة عند إنشائه. ستكون كمية الإزاحة هي الكمية الخاصة بالأمر الذي تم إنشاؤه.
        - *الحجز* – بالنسبة لحالة *الحركة المطلوبة للحجز*، سيقوم أمر بإرسال طلب تعويض عند حجزه أو انتقاؤها أو ترحيل كشف التعبئة أو فوترتها. سيتم تشغيل الطلب مرة واحدة فقط، للخطوة الأولى عند حدوث العملية المذكورة. ستكون كمية الإزاحة هي الكمية التي تغيرت فيها حالة حركة المخزون من *تحت الطلب* إلى *مطلوب محجوز* (أو لاحقًا الحالة) في بند الأمر المقابل.

1. انتقل إلى **إدارة المخزون \> دوري \> تكامل رؤية المخزون**، وقم بتمكين الوظيفة. سيتم الآن ترحيل كافة أحداث تغيير المخزون من Supply Chain Management إلى رؤية المخزون.

## <a name="uninstall-the-inventory-visibility-add-in"></a><a name="uninstall-add-in"></a>إزالة تثبيت الوظيفة الإضافية لرؤية المخزون

لإلغاء تثبيت الوظيفة الإضافية "رؤية المخزون" ، اتبع الخطوات التالية:

1. سجل دخولك إلى Supply Chain Management.
1. انتقل إلى **إدارة المخزون \> دوري \> تكامل رؤية المخزون** ، وقم بإلغاء تمكين الوظيفة.
1. انتقل إلى LCS وافتح الصفحة الخاصة بالبيئة التي ترغب في أزاله تثبيت الوظيفة الاضافيه فيها (راجع أيضا [تثبيت الوظيفة الاضافيه](#install-add-in)لرؤية المخزون).
1. حدد **إلغاء تثبيت**.
1. تقوم عملية إلغاء التثبيت الآن بإنهاء الوظيفة الإضافية رؤية المخزون ، وإلغاء تسجيل الوظيفة الإضافية من LCS ، وحذف أي بيانات مؤقتة مخزنة في ذاكرة التخزين المؤقت لبيانات الجرد الإضافية. ومع ذلك ، فإن بيانات المخزون الأولية التي تمت مزامنتها مع Dataverse الاشتراك لا يزال مخزنا هناك. لحذف هذه البيانات، أكمل باقي هذا الإجراء.
1. افتح [Power Apps](https://make.powerapps.com).
1. تحديد **البيئة** علي شريط التنقل
1. حدد البيئة Dataverse البونديده ببيئة الLCS الخاصة بك.
1. ثم انتقل إلى **الحلول** ، واحذف الحلول التالية بالترتيب التالي:
    1. رؤية مخزون Dynamics 365 - مرساة
    1. رؤية مخزون Dynamics 365 - التطبيق
    1. رؤية مخزون Dynamics 365 - عناصر التحكم
    1. رؤية مخزون Dynamics 365 - المكونات الإضافية
    1. رؤية مخزون Dynamics 365 - القاعدة

    بعد حذف هذه الحلول، سيتم حذف البيانات المخزنة في الجداول أيضا.

> [!NOTE]
> إذا قمت باستعادة قاعده بيانات Supply Chain Management بعد إلغاء تثبيت الوظيفة الاضافيه لرؤية المخزون ، ثم أردت أعاده تثبيت الوظيفة الاضافيه ، فتاكد من حذف بيانات رؤية المخزون القديمة التي تم تخزينها في Dataverse الاشتراك (كما هو موضح في الاجراء السابق) قبل أعاده تثبيت الوظيفة الاضافيه. سيؤدي ذلك إلى منع مشكلات عدم اتساق البيانات التي قد تحدث.

## <a name="clean-inventory-visibility-data-from-dataverse-before-restoring-the-supply-chain-management-database"></a><a name="restore-environment-database"></a>بيانات رؤية الجرد النظيفة من Dataverse قبل استعادة قاعدة بيانات Supply Chain Management.

إذا كنت تستخدم رؤية المخزون ثم استعدت قاعدة بيانات Supply Chain Management ، فقد تحتوي قاعدة البيانات المستعادة على بيانات لم تعد متوافقة مع البيانات التي تمت مزامنتها مسبقًا بواسطة Inventory Visibility إلى Dataverse. يمكن ان يتسبب عدم اتساق البيانات في حدوث أخطاء في النظام والمشكلات الأخرى. لذلك ، فانه من المهم ان تقوم دائما بتنظيف كافة بيانات Dataverse رؤية المخزون قبل استعاده قاعده بيانات Supply Chain Management.

إذا كنت بحاجه إلى استعاده قاعده بيانات Supply Chain Management ، فاستخدم الاجراء التالي:

1. قم بإلغاء تثبيت الوظيفة الإضافية Inventory Visibility Add-in وقم بإزالة جميع البيانات ذات الصلة بتنسيق Dataverseكما هو موصوف في [قم بإلغاء تثبيت الوظيفة الإضافية رؤية المخزون](#uninstall-add-in)
1. قم باستعادة قاعده بيانات Supply Chain Management، علي سبيل المثال ، الموصوفة في [استعاده استعاده قاعده بيانات نقطه النهاية (بيتر)](../../fin-ops-core/dev-itpro/database/database-point-in-time-restore.md) أو [المرحلة الزمنيه لقاعده بيانات الإنتاج إلى بيئة](../../fin-ops-core/dev-itpro/database/database-pitr-prod-sandbox.md) اليه تحديد الصلاحيات.
1. إذا كنت لا تزال ترغب في استخدامها ، فقم بعد ذلك باعاده تثبيت الوظيفة الاضافيه لرؤية المخزون واعدادها كما هو موضح في [تثبيت الوظيفة الاضافيه](#install-add-in) لرؤية المخزون واعداد [تكامل رؤية المخزون](#setup-inventory-visibility-integration)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
