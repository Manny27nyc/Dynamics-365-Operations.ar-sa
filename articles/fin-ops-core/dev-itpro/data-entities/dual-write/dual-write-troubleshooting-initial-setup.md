---
title: استكشاف المشاكل وإصلاحها أثناء الإعداد الأولي
description: يوفر هذا الموضوع استكشاف الأخطاء وإصلاحها الذي يمكن أن يساعدك في إصلاح المشكلات التي قد تحدث أثناء الإعداد الأولي لتكامل الكتابة الثنائية بين تطبيقات Finance and OperationsوCommon Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 76e104c9ebd7db7ebcbaf214e84be6c4353e8a73
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/21/2020
ms.locfileid: "3275431"
---
# <a name="troubleshoot-issues-during-initial-setup"></a>استكشاف المشاكل وإصلاحها أثناء الإعداد الأولي

[!include [banner](../../includes/banner.md)]



يوفر هذا الموضوع معلومات حول استكشاف أخطاء تكامل الكتابة الثنائية وإصلاحها بين تطبيقات Finance and Operations وCommon Data Service. على وجه التحديد، يوفر هذا الموضوع المعلومات التي يمكن أن تساعدك في إصلاح المشكلات التي قد تحدث أثناء الإعداد الأولي لتكامل الكتابة الثنائية.

> [!IMPORTANT]
> قد تتطلب بعض المشكلات التي يتناولها هذا الموضوع إما دور إدارة النظام أو بيانات اعتماد مسؤول مستأجر  Microsoft Azure Active Directory (Azure AD). يوضح القسم الخاص بكل مشكلة ما إذا كانت هناك حاجة إلى دور محدد أو بيانات اعتماد.

## <a name="you-cant-link-a-finance-and-operations-app-to-common-data-service"></a>لا يمكنك ربط تطبيق Finance and Operations بـ Common Data Service

**الدور المطلوب لتعيين الكتابة المزدوجة:** مسؤول النظام في تطبيقات Finance and Operations وCommon Data Service.

تحدث الأخطاء في صفحة **رابط الإعداد لـ Common Data Service** عادة بسبب وجود مشكلات الإعداد غير المكتمل أو المشكلات المتعلقة بالأذونات. تأكد من نجاح عملية التحقق من الصحة الكاملة في صفحة **رابط الإعداد لـ Common Data Service**، كما هو مبين في التوضيح التالي. لا يمكنك ربط الكتابة الثنائية إلا إذا نجحت عملية التحقق من الصحة الكاملة.

![عملية التحقق من السلامة الناجحة](media/health_check.png)

يجب أن يكون لديك بيانات اعتماد مسؤول مستأجر Azure AD لربط بيئات Finance and Operations وCommon Data Service بعد ربط البيئات، يمكن للمستخدمين تسجيل الدخول باستخدام بيانات اعتماد الحساب الخاص بهم وتحديث خريطة كيان موجودة.

## <a name="error-when-you-open-the-link-to-common-data-service-page"></a>حدث خطأ عند فتح الرابط المؤدي إلى صفحة Common Data Service

**بيانات الاعتماد المطلوبة لإصلاح المشكلة:** مسؤول مستأجر Azure AD

قد تظهر رسالة الخطأ التالية عندمت تفتح صفحة **الرابط لـ Common Data Service** في تطبيق Finance and Operations:

*لا يشير رمز حالة الاستجابة إلى النجاح: 404 (لم يتم العثور عليه).*

يحدث هذا الخطأ عند عدم إكمال خطوة الموافقة. للتحقق مما إذا كان قد تم إكمال خطوه الموافقة، قم بتسجيل الدخول إلى portal.Azure.com باستخدام حساب مسؤول مستأجر Azure AD، وراجع ما إذا كان التطبيق التابع للجهة الخارجية الذي يحتوي على المعرف **33976c19-1db5-4c02-810e-c243db79efde** في قائمة Azure AD**تطبيقات المرسسات**. وفي حالة عدم توفرها، يجب توفير موافقة للتطبيقات.

لتوفير الموافقة على التطبيق، اتبع الخطوات التالية.

1. افتح عنوان URL التالي باستخدام بيانات اعتماد المسؤول. يجب أن تكون مطالبًا بالموافقة.

    <https://login.microsoftonline.com/common/oauth2/authorize?client_id=33976c19-1db5-4c02-810e-c243db79efde&response_type=code&prompt=admin_consent>

2. حدد **قبول** للإشارة إلى أنك تقوم بمنح موافقتك لتثبيت التطبيق الذي يشتمل على المعرف **33976c19-1db5-4c02-810e-c243db79efde** الموجود في المستأجر الخاص بك.

    > [!TIP]
    > هذا التطبيق مطلوب لربط Common Data Service وتطبيقات Finance and Operations. إذا كانت لديك مشكلة في هذه الخطوة، فقم بفتح المستعرض في وضع التخفي (في Google Chrome) أو في وضع InPrivate (في Microsoft Edge).

## <a name="verify-that-company-data-and-dual-write-teams-are-set-up-correctly-during-linking"></a>تحقق من إعداد بيانات الشركة وفرق الكتابة الثنائية بشكل صحيح أثناء الربط

ولضمان عمل الكتابة الثنائية بشكل صحيح، يتم إنشاء الشركات التي تقوم بتحديدها أثناء التكوين في بيئة Common Data Service. وبشكل افتراضي، تكون هذه الشركات للقراءة فقط، ويتم تعيين الخاصية **IsDualWriteEnable** إلى **True**. بالإضافة إلى ذلك، يتم إنشاء مالك وحدةه الأعمال المالكة والفريق الافتراضي وتضمين اسم الشركة. قبل تمكين المخططات، تحقق من تحديد مالك الفريق الافتراضي. للبحث عن كيان **الشركات (CDM\_الشركة)**، اتبع الخطوات التالية.

1. في التطبيق المستند إلى النموذج في Dynamics 365، حدد عامل التصفية في الركن العلوي الأيمن.
2. من القائمة المنسدلة، حدد **الشركة**.
3. حدد **تشغيل** لعرض النتائج.
4. حدد الشركة التي تم ربطها عندما قمت بتكوين الكتابة الثنائية.
5. تحقق من أن حقل **الفريق المالك الافتراضي** يشتمل على قيمة. في التوضيح التالي، يتم تعيين حقل **الفريق المالك الافتراضي** إلى **الكتابة الثنائية لـ USMF**.

    ![التحقق من الفريق الافتراضي المالك](media/default_owning_team.png)

## <a name="find-the-limit-on-the-number-of-legal-entities-or-companies-that-can-be-linked-for-dual-write"></a>البحث عن الحد الخاص بعدد الكيانات القانونية أو الشركات التي يمكن ربطها للكتابة الثنائية

قد تظهر رسالة الخطأ التالية عندما تحاول تمكين المخططات:

*فشل الكتابة الثنائية - فشل تسجيل المكون الإضافي: \[(يتعذر الحصول على مخطط تقسيم لمشروع DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443eaللمشروع DWM--. يتجاوز الخطا الحد الأقصى للأقسام المسموح بها لتعيين DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)\]، حدث خطأ واحد أو أكثر.*

الحد الحالي عند ربط البيئات هو تقريبًا 40 كيانًا قانونيًا. يحدث هذا الخطأ إذا حاولت تمكين المخططات وكان أكثر من 40 كيانًا قانونيًا مرتبطًا بين البيئات.