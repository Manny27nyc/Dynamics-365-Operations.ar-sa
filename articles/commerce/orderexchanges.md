---
title: تكوين ومعالجة عملية استبدال في أمر إرجاع
description: يشرح هذا الموضوع كيفية تكوين عملية استبدال في أمر إرجاع في Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 11/12/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: a6d7688e78a375bc262b1156c5439c0fff7cd1f0
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004425"
---
# <a name="configure-and-process-an-exchange-on-a-return-order"></a>تكوين ومعالجة عملية استبدال في أمر إرجاع

[!include [banner](includes/banner.md)]

في الإصدارات السابقة من Dynamics 365 Commerce، كانت معالجة المرتجعات في مقابل أوامر العملاء تتم باستخدام مستند أمر الإرجاع في Headquarters. ومع ذلك، يمكن استخدام مستند أمر الإرجاع لمعالجة المنتجات المرتجعة فقط. يُشار إلى المنتجات المرتجعة بكمية سالبة في بنود أمر الإرجاع. وبطريقة مغايرة، يُشار إلى المبيعات بكمية موجبة. ومع ذلك، لا يدعم مستند أمر الإرجاع الكميات الموجبة. وبسبب هذا القيد، لم تدعم الإصدارات السابقة من التطبيق السيناريوهات حيث كانت عمليات الاستبدال تتم فقط باستخدام مستند أمر الإرجاع.

ومع ذلك، تمت إضافة وظيفة لدعم السيناريوهات حيث تتم عمليات الاستبدال على الأوامر المرتجعة. يستخدم Commerce الآن مستند أمر المبيعات بدلاً من مستند أمر الإرجاع لمعالجة هذه الأنواع من الحركات.

## <a name="configure-commerce-to-support-exchanges-on-return-orders"></a>تكوين Commerce لدعم عمليات الاستبدال على أوامر الإرجاع

اتبع هذه الخطوات لتكوين النظام لدعم عمليات الاستبدال على أوامر الإرجاع.

1. انتقل إلى **Retail and Commerce \> إعداد Headquarters \> المعلمات \> معلمات Commerce**. على علامة التبويب السريعة **أوامر العملاء‬**، عيّن الخيار **معالجة أوامر الإرجاع كأوامر مبيعات** إلى **نعم**.
2. شغّل وظيفة **جدول توزيع التكوين العمومي** (**1110**).

## <a name="make-an-exchange"></a>إجراء عملية استبدال

بعد أن يتم تكوين النظام كما ورد في المقطع السابق، سيحدد مستخدم نقطة البيع (POS) أمر مبيعات أو فاتورة مبيعات لمعالجة عملية إرجاع، كما هو الحال في إصدارات سابقة من التطبيق. ومع ذلك، بعد إضافة الأصناف المرتجعة إلى سلة التسوق، سيتمكن المستخدم من إضافة بنود مبيعات جديدة إلى سلة التسوق.

بالنسبة إلى بنود المبيعات الجديدة هذه، يجب على المستخدم تحديد كافة السمات المطلوبة لمعالجة بند في أمر العميل. تتضمن هذه السمات أسلوب التسليم وموقع التنفيذ. سيكون الدفع المستحق للحركة عبارة عن قيمة صافية لبنود أمر الإرجاع وبنود أمر المبيعات. عند تقديم الدفع للحركة، سيتم ترحيل أمر الإرجاع كمستند أمر مبيعات في Headquarters، وسيقوم النظام بفوترة بنود الإرجاع على الفور.

لتوفير رؤية أفضل لمختلف المبالغ في سلة التسوق، تمت إضافة ثلاثة حقول مبالغ جديدة إلى سلة التسوق. ويمكنك استخدام مصمم الشاشة لجعل كافة هذه الحقول الجديدة متوفرة في واجهة مستخدم (UI) نقطة البيع.

- **‏‫تم استخدام الإيداع‬** – مبلغ الإيداع المطبق على حركة عندما يقوم المستخدم بانتقاء أمر العميل‬. إذا لم يكن هناك أي مبلغ تجاوز الإيداع، وإذا تم تكوين إيداع بنسبة 10 بالمئة، سيكون المبلغ في هذا الحقل 90 بالمئة من المبلغ الإجمالي لأمر العميل.
- **تنفيذ المبلغ** – المبلغ الإجمالي للبنود حيث تم تعيين وضع التسليم إلى **تنفيذ** عندما تم إنشاء أمر العميل أو تحريره، أو خلال استبدال أمر العميل. يتضمن المبلغ الموجود في هذا الحقل الضرائب والمصاريف.
- **المبلغ المرتجع‬** – المبلغ الإجمالي للبنود ذات الكميات السالبة أثناء استبدال أمر العميل. يتضمن المبلغ الموجود في هذا الحقل الضرائب والمصاريف.