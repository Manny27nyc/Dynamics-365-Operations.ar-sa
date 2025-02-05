---
title: إعدادات التغطية
description: يوفر هذا المقال معلومات حول إعدادات التغطية التي تستخدمها الجدولة الرئيسية لحساب متطلبات الصنف.
author: t-benebo
ms.date: 09/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard, ReqItemTableSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1218c447a18f79f9a44bfa413a0414d6926d7499
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871938"
---
# <a name="coverage-settings"></a>إعدادات التغطية

[!include [banner](../includes/banner.md)]

تستخدم الجدولة الرئيسية إعدادات التغطية لحساب متطلبات الصنف.

يمكنك تحديد إعدادات التغطية بعدة طرق:

- حدد إعدادات التغطية لمجموعة تغطية.

    يمكنك إنشاء مجموعة تغطية تحتوي على إعدادات لكل المنتجات المرتبطة بمجموعة التغطية. لإنشاء مجموعة تغطية، انتقل إلى **التخطيط الرئيسي &gt; الإعداد &gt; التغطية &gt; مجموعات التغطية**. يمكن ربط مجموعة تغطية لأحد المنتجات. إذا كان الارتباط خاصًا بموقع أو مستودع أو بُعد منتج، فاستخدم حقل **مجموعة التغطية** في صفحة **تغطية الصنف**. إذا كان الارتباط عامًا، وبغض النظر عن أبعاد المنتج، فاستخدم حقل **مجموعة التغطية** في علامة التبويب السريعة **خطة** في صفحة **تفاصيل المنتج**. بشكل افتراضي، إذا لم تربط مجموعة تغطية بمنتج، يستخدم التخطيط الرئيسي مجموعة التغطية العامة المحددة في صفحة **معلمات التخطيط الرئيسي**.

- تحديد إعدادات التغطية لمنتج.

    يمكنك إنشاء إعدادات التغطية لمنتج محدد. انتقل إلى **إدارة معلومات المنتج‬ &gt; المنتجات &gt; المنتجات الصادرة**. حدد المنتج، ثم في جزء الإجراءات، علامة التبويب **خطة**، في مجموعة **التغطية‏‎**، حدد **تغطية الصنف** لفتح صفحة **تغطية الصنف**. إذا تم ربط المنتج بمجموعة تغطية بالفعل، فيمكنك تجاوز إعدادات مجموعة التغطية باستخدام حقل **التجاوز**. تأخذ إعدادات التغطية في صفحة **تغطية الصنف** الأسبقية على الإعدادات في صفحة **مجموعة التغطية**.

- تحديد إعدادات التغطية لمنتج باستخدام معالج.

    يقوم المعالج بإرشادك خطوة بخطوة خلال عملية إعداد معلمات تغطية الصنف الرئيسية.‬ في صفحة **تغطية الصنف**، على جزء الإجراءات، حدد **معالج** لفتح **معالج تغطية الصنف**.

- تحديد إعدادات تغطية لمجموعة أبعاد.

    انتقل إلى **إدارة معلومات المنتج‬ &gt; المنتجات &gt; المنتجات الصادرة**. في صفحة **تفاصيل المنتجات الصادرة‬**، في علامة التبويب السريعة **عام**، في القسم **الإدارة**، حدد الارتباط في الحقل **مجموعة أبعاد التخزين**. في صفحة **مجموعات أبعاد التخزين**، حدد خانة الاختيار **خطة التغطية حسب البعد** لإنشاء إعدادات التغطية لبُعد في مجموعة أبعاد التخزين. يجب تحديد الحقل **خطة التغطية حسب البُعد** لجميع أبعاد المنتج، مثل التكوين واللون والحجم والنمط.


## <a name="coverage-codes"></a>أكواد التغطية

يمكن تكوين التخطيط الرئيسي لاستخدام أساليب تزويد مختلفة. تعتبر أساليب التزويد أو أساليب تغيير حجم الدفعة التقنيات التي يستخدمها النظام لتحديد حجم الدفعة للأصناف التي تم شراؤها أو إنتاجها. 

يتم تعيين أحد أكواد التغطية التالية لكل أسلوب تزويد:

- **يدوي** -أسلوب تغيير حجم الدفعة حيث لا يقترح النظام أوامر الشراء أو التحويل أو الإنتاج الخاصة بالصنف. سيكون مخطط الصنف مسؤولاً عن إنشاء الأوامر المطلوبة لتزويد الصنف.
- **لكل متطلب** - أسلوب تغيير حجم الدفعة حيث يقوم النظام بإنشاء أمر شراء أو تحويل أو أمر إنتاج مخطط لكل واحد من المتطلبات الخاصة بالصنف. ويستخدم هذا بشكل عام في الأصناف المكلفة ذات طلب متقطع عليها.  
- **لكل فتره** -أسلوب تغيير حجم الدفعة الذي يضم كافة الطلبات لفترة ما في أمر واحد للصنف. سيتم التخطيط للأمر لأول يوم من الفترة، وستستوفي كميته صافي المتطلبات خلال الفترة التي تم تعيينها. تبدأ الفترة مع الطلب الأول للصنف وتغطي المدة المحددة. ستبدأ الفترة التالية مع المتطلبات التالية للصنف.
- **الحد الأدنى/الحد الأقصى** -أسلوب تغيير حجم الدفعة الذي يحتوي على تزويد المخزون حتى مستوى معين عندما يكون التوقع الفعلي اقل من الحد المعين. ستكون كمية التزويد الفرق بين الحد الأقصى لمستوى المخزون والمستوى الفعلي المتوقع.


## <a name="additional-resources"></a>الموارد الإضافية

[نظرة عامة على الخطط الرئيسية](master-plans.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]