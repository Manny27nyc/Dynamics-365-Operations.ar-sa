---
title: "تزويد فوري"
description: "يصف هذا الموضوع كيف يمكنك استخدام التزويد الفوري لتزويد المخزون عند فشل توجيه موقع في تخصيص المخزون."
author: Mirzaab
manager: AnnBe
ms.date: 03/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSLocDirTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: a11a26df85647aa36cd30c42f81be4ec2af4409b
ms.contentlocale: ar-sa
ms.lasthandoff: 04/13/2018

---

# <a name="immediate-replenishment"></a>تزويد فوري

[!include [banner](../includes/banner.md)]

يتيح لك التزويد الفوري تزويد المخزون مباشرةً بعد فشل بند توجيه موقع في تخصيص المخزون. يعتمد التزويد على بند واحد في إعداد توجيه الموقع. إذا لم يكن المخزون متوفرًا في وحدة القياس المحددة بواسطة هذا البند، يحدث تزويد وحدة القياس هذه مباشرةً.

يوفر التزويد الفوري بديلاً للطريقة التي يستند فيها تخصيص المخزون يستند إلى بنود إضافية في توجيه الموقع، ويتم فيها تجميع المطلب في نهاية التخصيص وتزويده في وحدة القياس المحددة بواسطة البند الأخير في توجيه الموقع.

تتمثل مزايا استخدام التزويد الفوري في أن التزويد يمكن أن محدودًا بواسطة وحدات محددة ويمكن توجيه الكمية إلى مواقع محددة.

## <a name="business-scenario"></a>سيناريو الأعمال

على سبيل المثال، لديك مستودع يحتوي على مناطق انتقاء منفصلة لـ "المربع" و"كل" وحدة من وحدات القياس. تحتاج أنت إلى تحسين عملية الانتقاء من خلال انتقاء أكبر عدد ممكن من المربعات ثم انتقاء أي كمية متبقية أقل من مربع من منطقة "كل".

في هذه الحالة، يمكنك استخدام التزويد الفوري. في توجيه الموقع، يمكنك إعداد تزويد فوري للمربعات حتى يتم استخدام تزويد الطلب بمجرد وجود نقص في المربعات التي يمكن انتقاؤها لكمية الطلب. وبهذه الطريقة، تقوم بتحسين عملية الانتقاء حتى يشتمل الانتقاء على أكبر عدد من المربعات. سيُنشئ التزويد الفوري تزويدًا للمربعات، ولن يتم تمرير الطلب حتى يتم انتقاء الكميات في وحدة القياس "كل". بمعنى آخر، سيتم انتقاء الكميات التي يجب انتقاؤها في وحدة القياس "كل" (يعني الكميات الأقل من مربع) من المنطقة "كل". في حالة حدوث نقص في منطقة "المربع"، يمكنك انتقاء أكبر عدد من المربعات من الطلب الإجمالي. سيتم بعد ذلك انتقاء الكميات المتبقية من المنطقة "كل".

## <a name="where-it-applies"></a>أين يتم التطبيق

يتم استخدام التزويد الفوري أثناء تنفيذ موجة إذا فشل تخصيص لبند توجيه موقع تم تعيين قالب تزويد له.

## <a name="set-up-immediate-replenishment"></a>إعداد التزويد الفوري

- انتقل إلى **إدارة المستودعات**\>**الإعداد**\>**توجيهات موقع**، ثم في علامة التبويب **بنود**، في قائمة **قالب التزويد الفوري**، حدد قالب تزويد لطلب الموجة.

يتم استخدام قالب التزويد في حالة فشل بند توجيه الموقع في تخصيص وحدة قياس مخصصة.

## <a name="troubleshooting"></a>استكشاف الأخطاء وإصلاحها

إذا تم تحديد التزويد الفوري لبند توجيه موقع، ولكن لم يتم إنشاء أي عمل تزويد عند استخدامك قوالب تزويد طلبات لبند توجيه الموقع هذا، فيجب التحقيق في نوعين من الأسباب الرئيسية:

- تأكد من إعداد قالب تزويد الطلب التي يتم تطبيقه لاستخدام قوالب المواقع وقوالب العمل الصحيحة من نوع **التزويد**.
- تأكد من وجود مخزون فعلى كافٍ في المواقع التي يبحث فيها قالب تزويد الطلب عن مخزون فعلي للتزويد.
