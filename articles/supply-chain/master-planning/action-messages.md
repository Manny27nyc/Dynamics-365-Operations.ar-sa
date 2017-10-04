---
title: "رسائل الإجراءات"
description: "رسالة الإجراء هي عبارة عن اقتراح منشأ بواسطة النظام بغرض تغيير أمر مخطط أو مؤكد موجود."
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19411
ms.assetid: 52b46d93-7d02-46b5-aad1-9fd08206bf9d
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: fbae19bd9699f17e7ce581415bf859cb87ebdb83
ms.contentlocale: ar-sa
ms.lasthandoff: 07/27/2017

---

# <a name="action-messages"></a>رسائل الإجراءات

[!include[banner](../includes/banner.md)]


رسالة الإجراء هي عبارة عن اقتراح منشأ بواسطة النظام بغرض تغيير أمر مخطط أو مؤكد موجود.

## <a name="introduction"></a>مقدمة

يتم إنشاء رسائل الإجراءات بواسطة حساب التخطيط الرئيسي في استجابة للمتطلبات المتغيرة. على سبيل المثال، ربما تم تغيير تاريخ الشحن أو الكمية في أمر مبيعات قمت بالفعل بإنشاء أمر شراء له لتلبية الطلب. وفي هذه الحالة، يتم إنشاء رسالة إجراء واحدة أو أكثر عن طريق حساب التخطيط الرئيسي لتحديث أمر الشراء. وتحدد ما إذا كان يتم إجراء التغييرات التي تم اقتراحها.

يمكن إعداد كيفية حساب رسائل الإجراءات لإحدى مجموعات التغطية، والتي يمكن إرفاقها بصنف.

## <a name="select-action-messages"></a>تحديد رسائل الإجراءات

في صفحة **مجموعات التغطية**، يمكنك تحديد رسائل الإجراء التي تريد أن يقوم النظام بإنشائها، ومجموعات التغطية أو الأصناف التي تُطبق عليها الرسائل. يمكنك تحديد رسائل الإجراءات التالية.

| رسالة             | الوصف                                                                                                                                                                                                                                              |
|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **مقدم**         | إذا قمت بتحديد هذه الرسالة، سيُنشئ النظام رسائل الإجراءات، عند الحاجة، لنقل أوامر إلى تاريخ سابق. وفي حقل **هامش التقدم**، يمكنك أيضًا تحديد الحد الأقصى لعدد الأيام بين الاستلام والإصدار دون إجراء مسبق. |
| **تأجيل**        | إذا قمت بتحديد هذه الرسالة، سيُنشئ النظام رسائل الإجراءات، عند الحاجة، لنقل أوامر إلى تاريخ سابق. وفي حقل **هامش التأجيل**، يمكنك تحديد الحد الأقصى لعدد الأيام بين الاستلام والإصدار دون إجراء تأجيل.       |
| **تخفيض**        | في حالة قيامك بتحديد هذه الرسالة، يجب إنقاص أوامر الإنتاج، وأوامر الشراء، وحركات الاستلام الأخرى لمنع حدوث زيادة في مستويات المخزون.                                                                                                   |
| **زيادة**        | في حالة قيامك بتحديد هذه الرسالة، يجب زيادة أوامر الإنتاج، وأوامر الشراء، وحركات الاستلام الأخرى لمنع حدوث حالات النقصان في المخزون.                                                                                                    |
| **الإجراءات المشتقة** | إذا قمت بتحديد هذه الرسالة، فإنه يتم إنشاء رسائل إجراءات للمتطلبات المشتقة، على سبيل المثال، إجراءات أوامر المكونات التي تستوفي الإنتاج.                                                                                                   |





