---
title: علامات المخزون مع تحسين التخطيط
description: يوفر هذا الموضوع معلومات حول الخيارات المتاحة لتمييز المخزون في الأوامر المؤكدة عند استخدام تحسين التخطيط.
author: ChristianRytt
manager: tfehr
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 99a52c03e519384955d68d7101a7b73b7e9a7af6
ms.sourcegitcommit: fe21a3a98dcf6fe4eb9351941493f2c0443d8696
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 12/04/2020
ms.locfileid: "4672169"
---
# <a name="inventory-marking-with-planning-optimization"></a>علامات المخزون مع تحسين التخطيط

[!include [banner](../../includes/banner.md)]

يوفر هذا الموضوع معلومات حول الخيارات المتاحة لتمييز المخزون في الأوامر المؤكدة عند استخدام تحسين التخطيط.

تستخدم *العلامة* لربط التوريد والطلب. وهو يمثل *تثبيت* السعر، والذي يشير إلى الطريقة التي يتوقع بها التخطيط الرئيسي تغطيه الطلب. من وجهه لعرض التخطيط ، فان الفرق الأساسي هو ان وضع العلامة يعد أكثر نهائيه من تثبيت السعر.

وقد تم تقديم علامة لدعم سيناريوهات التكاليف الخاصة لأول مره داخل ، ما يرد أولا يصرف أولا وأخيرا ما يرد أخيرا يصرف أولا. ومع ذلك ، فهي الآن تستخدم أيضا لبعض السيناريوهات غير الخاصة بالتكاليف. وضع علامة علي التوريد والطلب يكون اختياريا ودائما في الغالب. يمكن أزاله التمييز يدويا بواسطة مستخدم ، أو يمكن ازالته عن طريق تشغيل عمليه تحديد إجماليات بند أمر التوريد حيث يتم تحديد خيار **أزاله العلامات**.

يتم التحكم في تثبيت السعر بواسطة التخطيط الرئيسي اثناء التغطية لربط الطلب بالتوريد المطلوب. يمكن تحديث تثبيت السعر لكل تشغيل تخطيط لتحسين التوريد المطلوب لتغطيه الطلب. عندما يقوم التخطيط الرئيسي بتحديث معلومات التثبيت المسبق ، فانه يتقيد بآيه تعليمات موجودة.

ويبدا التثبيت من خلال تضمين العلامات ذات الصلة وعمليات الحجز الفعلية وعمليات الحجز علي الطلب ، بالتسلسل التالي:

1. وضع علامة علي الطلب والتوريد
1. عمليات الحجز الفعلية
1. حجز الأمر

عند تاكيد أمر مخطط ، يوفر مربع الحوار **التاكيد** حقل **تحديث التعليم** الذي تستخدمه لتعيين خيارات وضع العلامات للأوامر التي تم إنشاؤها اثناء التاكيد. حدد إحدى القيم التالية:

- **لا** – لم يتم تطبيق إيه علامات مخزون.
- ‎**قياسي‎** - يتم تحديث علامات المخزون وفقًا لتثبيت السعر. ويتم وضع علامة على أحد أوامر المتطلبات (الطلب) على أساس أمر استيفاء (العرض). في حاله بقاء بعض الكمية علي أمر الاستيفاء ، فلن يتم تمييزها ، ويتم ترك المعلومات المرجعية فارغه. علي سبيل المثال ، إذا كان أمر التوريد الخاص ب 100 ea بيجيد في مقابل أمر شراء ل 150 ea ، سيتم تعيين معلومات مرجعيه لأمر المبيعات فقط.
- **مفصل** - يتم وضع علامة على كل من أمر المتطلب (الطلب) وأمر الاستيفاء (العرض)، بغض النظر عما إذا كانت هناك أية كمية متبقية في أمر الاستيفاء أم لا. علي سبيل المثال ، إذا كان أمر التوريد الخاص ب 100 ea بيجيد في مقابل أمر شراء ل 150 ea ، سيتم تعيين معلومات مرجعيه لأمر المبيعات وأمر الشراء.