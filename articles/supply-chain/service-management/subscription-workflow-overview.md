---
title: "نظرة عامة على سير عمل الاشتراك"
description: "يقدم هذا الموضوع نظرة عامة على سير عمل الاشتراك."
author: ShylaThompson
manager: AnnBe
ms.date: 05/07/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMASubscriptionGroup, SMASubscriptionCreateDialog
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: b4872c0753b54bdddf2c7778a13819726eea4a90
ms.contentlocale: ar-sa
ms.lasthandoff: 05/08/2018

---


# <a name="subscription-workflow-overview"></a>نظرة عامة على سير عمل الاشتراك 

[!include [banner](../includes/banner.md)]


تعمل كمسؤول عن الاشتراكات لدى شركة إضاءة والتي تقدم اشتراكات لصيانة معدات الإضاءة. ويتصل أحد العملاء بشركتك لشراء اشتراك سنوي للحصول على صيانة معدات الإضاءة.

## <a name="setting-up-subscriptions"></a>إعداد الاشتراكات

لإعداد اشتراك، يجب عليك أولا إنشاء مجموعة مشتركين لاتفاقية الخدمة الجديدة أو التحقق من وجود مجموعة مشتركين. في حالة وجود مجموعة مشتركين، يجب إعدادها لإرسال فواتير للعميل سنويًا واستحقاق إيرادات المبيعات في كل شهر على مدار السنة. للحصول على مزيد من المعلومات حول كيفية إعداد الاشتراكات، راجع [إعداد مجموعات الاشتراك](set-up-subscription-groups.md).

يُمكنك إنشاء الاشتراك بعد إنشاء مجموعة المشتركين. للحصول على مزيد من المعلومات حول كيفية إنشاء اشتراكات الخدمة، راجع [إنشاء اشتراكات خدمة من مجموعة اشتراك](create-service-subscriptions-from-subscription-group.md).

## <a name="create-and-modify-subscription-transactions"></a>إنشاء حركات المشتركين وتعديلها

بعد إنشاء الاشتراك، يمكنك إنشاء حركة رسوم اشتراك لفترة الفوترة الأولى، والتي تبلغ عام واحد. تكون الحركات من نوع **عادي**. لذلك، يمكنك فقط إنشاء حركات الاشتراك التي يتوافق فيها من تاريخ والي تاريخ مع الفترات التي تم إنشاؤها مسبقاً في النموذج **أنواع الفترات**. لمزيد من المعلومات حول حركات الرسوم، راجع [إنشاء حركات رسوم الاشتراك](create-subscription-fee-transactions.md).

بعد قيامك بإعداد اشتراك لعميلك، تتذكر أنه تفاوض للحصول على خصم يصل إلى 10 في المائة على كافة أسعار عروض الخدمة بالقائمة. وبالتالي، يجب عليك تخفيض سعر رسوم الحركة التي قمت بإنشائها.

في وقت لاحق من اليوم، تتصل جهة الاتصال الخاصة بالعميل لتضيف أنه رغم احتياجهم إلى اتفاقية الخدمة الخاصة بمعدات الإضاءة، فهم يخططون لتقديم معدات إضاءة جديدة فيما بعد خلال العام. بالتالي، فهم بحاجة فقط إلى تغطية الصيانة حتى أكتوبر 2013. لتخفيض عدد أشهر اشتراك العميل، قمت بإنشاء حركة رسوم اشتراك جديدة من النوع **أيام التخفيض**. للحصول على مزيد من المعلومات حول كيفية تقليل الأيام، راجع [تقليل الأيام على رسوم الاشتراك](reduce-the-days-on-subscription-fees.md).

## <a name="invoice-and-accrue-subscription-transactions"></a>فوترة حركات الاشتراك واستحقاقها

لقد انتهيت الآن من إعداد الاشتراك، وأنت مستعد الآن لإرسال الفواتير للعميل مقابله. للحصول على مزيد من المعلومات حول كيفية فوترة الاشتراكات، راجع [حركات اشتراك الفاتورة](invoice-subscription-transactions.md).

يتصل العميل بعد مرور يومين ليذكر بأنه يجب فوترة الاشتراك بالدولار الأمريكي، وليس باليورو. بالتالي، عليك إنشاء إشعار دائن، وعليك إنشاء حركة اشتراك جديدة بالعملة الصحيحة. للحصول على مزيد من المعلومات حول كيفية ائتمان حركات الاشتراكات، راجع [ائتمان حركات اشتراك](credit-subscription-transactions.md).

في نهاية كل شهر، يمكن استحقاق إيراد شهر واحد من اشتراك العميل لحساب الربح والخسارة وحسابات الأعمال تحت التنفيذ. للحصول على مزيد من المعلومات عن كيفية استحقاق الإيراد للاشتراكات، راجع [إيراد اشتراك مستحق ](accrue-subscription-revenue.md).

  


