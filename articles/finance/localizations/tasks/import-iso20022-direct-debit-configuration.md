---
title: استيراد تكوين الدين المباشر ISO20022
description: يوضح هذا الإجراء كيفية استيراد تكوين التقارير الإلكترونية لمدفوعات العميل.‬
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e5d4256b155d3e06d63e425fab63b4025ef2577f
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140008"
---
# <a name="import-iso20022-direct-debit-configuration"></a>استيراد تكوين الدين المباشر ISO20022

[!include [banner](../../includes/banner.md)]

يوضح هذا الإجراء كيفية استيراد تكوين التقارير الإلكترونية لمدفوعات العميل.‬ يستخدم هذا الإجراء تنسيق الدين المباشر ISO 20022 كمثال. 



تم إنشاء هذا الإجراء باستخدام شركة بيانات العرض التوضيحي DEMF، ولكن يمكنك استخدام أي من شركات بيانات العرض التوضيحي لهذا الغرض.



هذا هو الإجراء الأول من ضمن خمسة إجراءات هدفها توضيح عملية معالجة مدفوعات العميل باستخدام تكوينات التقارير الإلكترونية.

1. انتقل إلى إدارة المؤسسة > مساحات العمل‬ > إعداد التقارير الإلكتروني‬.
2. في قائمة "موفرو التكوين‬" المتوفرون، حدد Microsoft.
3. انقر فوق "تعيين كنشط".
4. انقر فوق "المستودعات".
5. انقر فوق "فتح".
6. انقر فوق "إظهار عوامل التصفية".
7. طبّق عوامل التصفية التالية: أدخل قيمة عامل التصفية "الدين المباشر ISO20022 (DE)" في حقل "اسم التكوين" باستخدام مشغل عامل التصفية "يبدأ بـ".
    * بشكل اختياري، يمكنك العثور على التكوين في القائمة، وتحديده ثم تخطي هذه الخطوة.  
8. انقر فوق "استيراد".
    * إذا لم يتوفر الزر "استيراد"، فهذا يعني أن التكوين قد تم استيراده.  
9. انقر فوق نعم.
