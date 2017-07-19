---
title: "إدارة مخزون المتجر"
description: "توضح هذه المقالة أنواع المستندات التي يمكنك استخدامها لإدارة المخزون."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail Version
ms.translationtype: Human Translation
ms.sourcegitcommit: 59b51840c05fe649cf322bfa64737a321728a5aa
ms.openlocfilehash: 1a5f2cd60e09b67cee4bab211bba4e07e9ef181f
ms.contentlocale: ar-sa
ms.lasthandoff: 06/20/2017


---

# <a name="manage-store-inventory"></a>إدارة مخزون المتجر

[!include[banner](includes/banner.md)]


توضح هذه المقالة أنواع المستندات التي يمكنك استخدامها لإدارة المخزون.

يمكنك استخدام الأنواع التالية من المستندات لإدارة المخزون الخاصة بمؤسستك.

## <a name="purchase-orders"></a>أوامر الشراء
يتم إنشاء أوامر الشراء في المقر الرئيسي. ‏‫وإذا تم تضمين مستودع البيع بالتجزئة في رأس أمر الشراء، فيمكن تلقي الأمر في المتجر باستخدام نقاط البيع الحديثة أو نقاط بيع المجموعة في Microsoft Dynamics 365 for Retail. وبعد أن يتم إدخال الكميات التي يتم تلقيها في المتجر، يمكن حفظها محلياً لتعديلات إضافية.‬ وبدلاً من ذلك، يمكن تنفيذ الكميات وإرسالها إلى المكتب الرئيسي. وفي المقر الرئيسي، يتم عرض الكميات التي تم تلقيها في المتجر في Dynamics 365 for Retail، في حقل **تلقي الآن** في أمر الشراء.

## <a name="transfer-orders"></a>أوامر التحويل
يمكن لأمر تحويل تحديد أن متجر معين هو موقع يمكن شحن الأصناف منه. في هذه الحالة، يظهر أمر التحويل في المتجر كطلب انتقاء في نقطة البيع الحديثة أو نقطة بيع المجموعة. وبعد أن يتم انتقاء الكميات المطلوبة، يتم الالتزام بها وإرسالها إلى المقر الرئيسي.‬ في المقر الرئيسي، يتم انتقاء الكميات التي تم تلقيها في المتجر في Dynamics 365 for Retail، في حقل **شحن الآن** في أمر التحويل. ويمكن لأمر تحويل تحديد أن متجر معين هو موقع يمكن شحن الأصناف إليه. في هذه الحالة، يظهر أمر التحويل في المتجر كطلب تلقي في نقطة البيع الحديثة أو نقطة بيع المجموعة. وبعد أن يتم إدخال الكميات التي يتم تلقيها في المتجر، يمكن حفظها محلياً لتعديلات إضافية.‬ وبدلاً من ذلك، يمكن تنفيذ الكميات وإرسالها إلى المكتب الرئيسي. وفي المقر الرئيسي، يتم عرض الكميات التي تم تلقيها في المتجر في Dynamics 365 for Retail، في حقل **تلقي الآن** في أمر التحويل.

## <a name="stock-counts"></a>عمليات جرد المخزون
قد تكون عمليات جرد المخزون مجدولة أو غير مجدولة. يتم البدء في جرد المخزون المجدول في المكتب الرئيسي، الذي يحدد الأصناف التي يجب جردها. يُنشئ المكتب الرئيسي مستند جرد يمكن استلامه في المتجر، حيث يتم إدخال كميات المخزون الفعلي المتوفر في نقطة البيع الحديثة أو نقطة بيع المجموعة. ويتم البدء في عمليات جرد المخزون غير المجدولة في المتجر، ويتم تحديث كميات المخزون الفعلي المتوفر في نقطة البيع الحديثة أو نقاط بيع المجموعة. وعلى عكس الجرد المجدول، لا تحتوي عمليات جرد المخزون غير المجدولة على قائمة بالأصناف محددة مسبقاً.‬ وعند اكتمال عملية جرد مخزون من أي نوع، فإنه يتم الالتزام بها وإرسالها إلى المكتب الرئيسي. وفي المكتب الرئيسي، يتم التحقق من صحة الجرد وترحيله.

## <a name="inventory-lookup"></a>البحث في المخزون
كمية المنتجات الحالية الفعلية للعديد من المتاجر والمستودعات التي يمكنك عرضها في صفحة البحث في المخزون. بالإضافة إلى الكمية الحالية الفعلية، يمكن عرض الكميات المستقبلية المتاحة للتعهد (ATP) لكل متجر فردي. للقيام بذلك، حدد المتجر الذي ترغب في عرض كمية ATP الخاصة به، ثم انقر فوق **إظهار توافر المتجر‬**.




