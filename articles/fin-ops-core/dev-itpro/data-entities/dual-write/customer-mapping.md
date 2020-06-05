---
title: أصل العميل المتكامل
description: يوضح هذا الموضوع تكامل بيانات العملاء بين Finance and Operations وCommon Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
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
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 977b74b10b4549d09a8816264f9ff603fa86e91c
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172821"
---
# <a name="integrated-customer-master"></a>أصل العميل المتكامل

[!include [banner](../../includes/banner.md)]


يمكن إدارة بيانات العملاء في أكثر من تطبيق Dynamics 365 واحد. علي سبيل المثال، يمكن أن ينشأ سجل العميل إذا كان نشاط المبيعات في Dynamics 365 Sales (تطبيق يستند إلى النموذج في Dynamics 365)، أو يمكن أن سجل من خلال نشاط بيع بالتجزئة في Dynamics 365 Commerce (تطبيق Finance and Operations). بغض النظر عن المكان الذي تنشأ فيه البيانات الخاصة بالعميل، فإنها تتكامل خلف المشاهد. يوفر أصل العميل المتكامل المرونة لبيانات العميل الرئيسية في أي تطبيق Dynamics 365 ويوفر طريقة عرض شاملة للعميل عبر مجموعة تطبيقات Dynamics 365.

## <a name="customer-data-flow"></a>تدفق بيانات العميل

*العميل* هو مفهوم معرف بشكل دقيق في التطبيقات. ولذلك، فإن تكامل بيانات العميل ينطوي فقط على مواءمة مفهوم العميل بين التطبيقين. يبين الرسم التوضيحي التالي تدفق بيانات العميل.

![تدفق بيانات العميل](media/dual-write-customer-data-flow.png)

يمكن تصنيف العملاء على نطاق واسع في نوعين: العملاء التجاريين/المؤسسيين والمستهلكين/المستخدمين النهائيين. يتم تخزين هذين النوعين من العملاء والتعامل معهما بطريقة مختلفة في Finance and Operations وCommon Data Service.

في Finance and Operations، تتم إدارة العملاء التجاريين/المؤسسيين والمستهلكين/المستخدمين النهائيين في جدول واحد يسمى **CustTable** (CustomerCustomerV3Entity)، ويتم تصنيفهم استنادًا إلى سمة **النوع**. (إذا تم تعيين **النوع** إلى **مؤسسة**، فسيكون العميل تجاريًا/مؤسسيًا، وإذا تم تعيين **النوع** إلى **شخص**، فسيكون العميل مستهلكًا/مستخدمًا نهائيًا.) يتم التعامل مع معلومات جهة الاتصال الرئيسية عبر الكيان SMMContactPersonEntity.

في Common Data Service، تتم إدارة العملاء التجاريين/المؤسسيين في كيان الحساب، ويتم تعريفهم كعملاء عند تعيين سمة **RelationshipType** إلى **عميل**. يتم تمثيل المستهلكين/المستخدمين النهائيين وشخص جهة الاتصال بواسطة كيان جهة الاتصال. للفصل بشكل واضح بين المستهلك/المستخدم النهائي وشخص جهة الاتصال، يتضمن كيان **جهة الاتصال** علامة منطقية تسمى **قابل للبيع**. عندما تكون قيمة **قابل للبيع** **صواب**، تكون جهة الاتصال عبارة عن عميل مستهلك/مستخدم نهائي، ولا يمكن إنشاء الأوامر وعروض الأسعار لجهة الاتصال هذه. عندما تكون قيمة **قابل للبيع** **خطأ**، تكون جهة الاتصال مجرد جهة اتصال رئيسية للعميل.

عندما تشارك جهة اتصال غير قابلة للبيع في عملية عرض أسعار أو أمر، يتم تعيين قيمة **قابل للبيع** إلى **صواب** لوضع علامة على جهة الاتصال كجهة اتصال قابلة للبيع. جهة الاتصال التي أصبح جهة اتصال قابلة للبيع تبقى جهة اتصال قابلة للبيع.

## <a name="templates"></a>القوالب

تتضمن بيانات العميل كافة المعلومات المتعلقة بالعميل، مثل مجموعة العملاء والعناوين ومعلومات الاتصال وملف تعريف الدفع وملف تعريف الفاتورة وحالة الولاء. تعمل مجموعة من مخططات الكيانات معًا أثناء تفاعل بيانات العميل، كما هو موضح في الجدول التالي.

تطبيقات Finance and Operations | تطبيقات Dynamics 365 الأخرى         | ‏‏الوصف
----------------------------|---------------------------------|------------
جهات اتصال CDS V2             | جهات الاتصال                        | يقوم هذا القالب بمزامنة كافة معلومات جهات الاتصال الاساسيه والثانوية والثلاثية لكل من العملاء والموردين.
مجموعات العملاء             | msdyn_customergroups            | يقوم هذا القالب بمزامنة معلومات مجموعة العملاء.
طريقة دفع العميل     | msdyn_customerpaymentmethods    | يقوم هذا القالب بمزامنة معلومات طرق دفع العملاء.
العملاء V3                | الحسابات                        | يقوم هذا القالب بمزامنة المعلومات الرئيسية للعميل للعملاء التجاريين والمؤسسين.
العملاء V3                | جهات الاتصال                        | يقوم هذا القالب بمزامنة البيانات الرئيسية للعميل للعملاء والمستخدمين النهائيين.
ملحقات الاسم                | msdyn_nameaffixes               | يقوم هذا القالب بمزامنة البيانات المرجعية لملصقات الأسماء، لكلٍّ من العملاء والموردين.
بنود يوم الدفع CDS V2    | msdyn_paymentdaylines           | يقوم هذا القالب بمزامنة البيانات المرجعية لأسطر أيام الدفع لكلٍّ من العملاء والموردين.
أيام الدفع CDS            | msdyn_paymentdays               | يقوم هذا القالب بمزامنة البيانات المرجعية لأيام الدفع لكلٍّ من العملاء والموردين.
بنود جدول الدفع      | msdyn_paymentschedulelines      | مزامنة البيانات المرجعية لأسطر جداول الدفع لكلٍّ من العملاء والموردين.
جدول الدفع            | msdyn_paymentschedules          | يقوم هذا القالب بمزامنة البيانات المرجعية لجدول الدفع لكلٍّ من العملاء والموردين.
شروط الدفع            | msdyn_paymentterms              | يقوم هذا القالب بمزامنة البيانات المرجعية لمدد الدفع (مدد الدفع) لكلٍّ من العملاء والموردين.

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping contacts contacts](includes/CDSContactsV2-contacts.md)]

[!include [mapping customer group](includes/CustCustomerGroup-msdyn-customergroups.md)]

[!include [mapping customer payment method](includes/CustomerPaymentMethod-msdyn-customerpaymentmethods.md)]

[!include [mapping customer accounts](includes/CustomersV3-accounts.md)]

[!include [mapping customer contacts](includes/CustomersV3-contacts.md)]

[!include [mapping name affixes](includes/NameAffixes-msdyn-nameaffixes.md)]

[!include [mapping payment day lines](includes/PaymentDayLinesCdsV2-msdyn-paymentdaylines.md)]

[!include [mapping payment days](includes/PaymentDaysCds-msdyn-paymentdays.md)]

[!include [mapping payment schedule lines](includes/PaymentScheduleLines-msdyn-paymentschedulelines.md)]

[!include [mapping payment schedules](includes/PaymentSchedules-msdyn-paymentschedules.md)]

[!include [mapping terms of payment](includes/TermsofPayment-msdyn-paymentterms.md)]