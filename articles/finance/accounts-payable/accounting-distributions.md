---
title: التوزيعات المحاسبية
description: توفر هذه المقالة معلومات عن التوزيعات المحاسبية، ويصف الخيارات المتاحة لمعالجتها.
author: sunfzam
ms.date: 09/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AccountingDistribution
audience: Application User
ms.reviewer: twheeloc
ms.custom: 17231
ms.assetid: 9030355d-8e6e-408b-9e7d-7b346eaa652c
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0d5930ca2ce2bb1ae534f7e2b434836c3a4adeba
ms.sourcegitcommit: cf27cf277b37666c838043e0695d39d52be5dcdd
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588943"
---
# <a name="accounting-distributions"></a>التوزيعات المحاسبية

[!include [banner](../includes/banner.md)]

توفر هذه المقالة معلومات حول التوزيعات المحاسبية وتصف الخيارات المتاحة لمعالجتها. يتم استخدام التوزيعات المحاسبية لتوزيع مبالغ نقدية لمستند مصدر إلى حسابات دفتر أستاذ محددة. 

التوزيع المحاسبية عبارة عن قدرة على مستوى البرنامج يتم استخدامها وتوسيعها بواسطة كل مستند مصدر، مثل أمر الشراء، وفاتورة المورد، وتقرير المصروفات، وفاتورة النص الحر. وبشكل افتراضي، يتم إنشاء توزيع المحاسبة الافتراضية لكل بند مستند مصدر والمبلغ النقدي، ويتم تمكينه للتعديل بشروط. 

> [!NOTE] 
> تدعم بعض المستندات أيضًا المبالغ النقدية في مستند الرأس، مثل المصاريف لأوامر الشراء والفواتير. 

توفر قدرات التوزيع المحاسبية العامة الخيارات التالية لمعالجة التوزيعات المحاسبية:

-   **توزيع المبالغ** – عرض وتعديل التوزيعات المحاسبية لرأس أو بند مستند فردي وأي بنود فرعية، مثل الضرائب أو التكاليف.
    -   بالنسبة لتوزيعات المبالغ النقدية العليا (توزيعات الأصل)، وقد يكون الحساب الرئيسي والأبعاد المالية قابلة للتحرير مباشرةً في عنصر التحكم في الإدخال المقسم في الشبكة. السعر الممتد هو مثال نموذجي على توزيع الأصل.
    -   تستند مبالغ التوزيعات على عملة المدة للمستند. وبشكل عام، هذه العملة هي عملة الحركة. ويتم إنشاء مبالغ عملية المحاسبة والتقارير كجزء من محاسبة دفتر الأستاذ الفرعي.
    -   تعرض التوزيعات تاريخ المحاسبة وحدث المحاسبة. ويتم عادةً تعيين الحدث المحاسبي إلى **لا شيء** حتى يتم ترحيل المستند أو تسجيله في دفتر اليومية. وعند هذه النقطة، يصبح حدث المحاسبة **أصليًا**. وبعد ترحيل عمليات التوزيع، لا يمكنك تعديل عمليات التوزيع.
    -   قد يتم تمكين زر **التقسيم** لتوزيعات الأصل. يعمل **التقسيم** على إنشاء التوزيعات المحاسبية الجديدة، ويمكن أن يعتمد التقسيم على النسبة المئوية أو المبلغ أو الكمية.
    -   يمكن استخدام الزر **‏‫توزيع بشكل متساو‬** بالاشتراك مع **التقسيم** لتوزيع المبلغ بالتساوي عبر جميع التوزيعات تلقائيًا.
    -   قد يتم تمكين الزر **إعادة تعيين** للتوزيعات الأصل عند وجود أكثر من توزيع. يعمل الزر **إعادة تعيين** إلى عكس أي تعديل يدوي في التوزيع عن طريق حذف كافة التوزيعات الموجودة وإعادة إنشاء التوزيعات الافتراضية.
    -   يتبع أي توزيع فرعي، مثل الخصم، والرسم، وضريبة المبيعات، التوزيع الأصل دائمًا. يمكنك عرض علاقة الأصل/الفرع في **المرجع** &gt; **معلومات الأصل**.
    -   الحساب الرئيسي والبعد المالي قد يكونا قابلين للتحرير للفروع أيضًا.
    -   تتبع الأبعاد المالية في التوزيعات المحاسبية نمط التعيين الافتراضي الذي يمكن توسيع المستند له.
    -   قد يتم إنشاء توزيعات الفرق في مطابقة السيناريوهات، مثل المطابقة بين أمر شراء وفاتورة مورد. يمكنك عرض علاقات المطابقة بين التوزيع المحاسبي في **المرجع** &gt; **معلومات المستند**.
    -   يظهر الزر **صحيح** ويتم تمكينه للمستندات التي تدعم التصحيحات. يُنشئ الزر **صحيح** توزيعات جديدة. أولاً، يتم إنشاء عمليات التوزيع التي تعكس التوزيعات الأصلية.‬ لا يمكن تعديل هذه التوزيعات. في الخطوة التالية، يتم إنشاء التوزيعات المحاسبية الصحيحة الجديدة.‬ ويمكن تعديل هذه التوزيعات إذا كان يمكن تعديل عمليات التوزيع الأصلية.
    -   يتم تمكين الزر **تفاصيل المشروع** كملحق عندما ريتم ربط بند بمشروع. تتيح لك توزيعات محاسبة المشروع إمكانية تعديل تفاصيل مثل خاصية البند ومصدر التمويل.
    -   يمكنك عرض حالة محاسبة المستند الحالي في **مرجع**. الحالة مخصصة للمستند بأكمله، وتشير إلى ما إذا كان المستند قيد التنفيذ أو مكتمل.‬
-   **عرض التوزيعات** – عرض التوزيعات المحاسبية لكافة البنود والمبالغ النقدية في المستند. لا يمكنك تعديل التوزيعات المحاسبية من طريقة العرض هذه.

في الإصدار 10.0.13، تمت إضافة ميزة تتحقق من صحة جدول التوزيع المحاسبي لضمان إعداد الحقول الجديدة بشكل صحيح. تسمى هذه الميزة **تمكين التحقق من صحة البيانات الإضافي للمستندات باستخدام إطار عمل محاسبة المستند المصدر**. سيتم تشغيل هذه الميزة افتراضيًا في الإصدار 10.0.29. 

‏‫لمزيد من المعلومات، راجع [التوزيعات المحاسبية وإدخالات دفتر اليومية بدفتر الأستاذ الفرعي لفواتير الموردين](accounting-distributions-subledger-journal-entries-vendor-invoices.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
