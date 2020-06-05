---
title: إهلاك الاستهلاك
description: توفر هذه المقالة نظرة عامة على أسلوب الاستهلاك للإهلاك.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13751
ms.assetid: d25a681f-49a5-4bfc-aa76-1c6373e35dd8
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2c9d95a7a45ed99c63516749285126c786685c87
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187304"
---
# <a name="consumption-depreciation"></a>إهلاك الاستهلاك

[!include [banner](../includes/banner.md)]

توفر هذه المقالة نظرة عامة على أسلوب الاستهلاك للإهلاك.

عند إعداد ملف تعريف إهلاك للأصول الثابتة وتحديد **استهلاك** في حقل **الطريقة** في صفحة **ملفات تعريف الإهلاك**، تستند الأصول الثابتة المعيَّنة إلى ملف تعريف الإهلاك إلى استخدامها. ولا يلزمك إعداد النسب المئوية والفترات في صفحة **ملفات تعريف الإهلاك**. وبعد قيامك بإنشاء ملف تعريف إهلاك يستخدم طريقة الاستهلاك، يمكنك إعداد الطريقة بطرق متعددة.

## <a name="set-up-and-use-consumption-depreciation"></a>إعداد واستخدام إهلاك الاستهلاك
1.  في صفحة **ملفات تعريف الإهلاك**، قم بإنشاء ملف تعريف الإهلاك. بالنسبة لحسابات الاستهلاك، يجب أن يتضمن ملف تعريف الإهلاك معرفًا واسمًا، ويجب تحديد **الاستهلاك** في حقل **الطريقة**.
2.  في صفحة **معامِلات الاستهلاك**، قم بإعداد معامِلات الاستهلاك. يجب أن يشتمل كل معامِل استهلاك على معرف واسم، ومعامل استهلاك تم تحديده كنسبة مئوية أو كمية.
3.  في صفحة **وحدات الاستهلاك**، قم بإعداد وحدات الاستهلاك. يجب أن تشتمل كل وحدة استهلاك على معرف واسم. ويتم استخدام وحدات الاستهلاك لحساب إهلاك الاستهلاك في صفحة **إهلاك الاستهلاك**. ومن أمثلة الوحدات الكيلومتر (كم) والكيلوجرام (كجم) والساعة.
4.  في صفحة **الأصول الثابتة**، قم بإعداد الأصول الثابتة الفردية. وللحصول على كل أصل ثابت، حدد نماذج القيم ودفاتر الإهلاك التي تشتمل على ملفات تعريف الإهلاك. ويجب عليك إعداد نماذج القيم أو دفاتر لإهلاك الاستهلاك، في حالة قيام أي أصول من أصولك الثابتة باستخدام ملف تعريف الإهلاك المستند إلى طريقة الاستهلاك. ويتم إجراء هذا الإعداد في علامة التبويب **الإهلاك** في صفحة **نماذج القيم** الصفحة أو في علامة التبويب السريعة **عام** في صفحة **ملف تعريف الإهلاك**. ويمكنك استخدام نفس نموذج القيمة للعديد من الأصول الثابتة. تعد ملفات تعريف الإهلاك جزءًا من نموذج القيمة أو دفتر الإهلاك المحدد لكل أصل ثابت. لا يمكنك إضافة أو تعديل ملفات تعريف الإهلاك مباشرةً في صفحة **الأصول الثابتة**. ويمكنك تعديل ملفات تعريف الإهلاك في صفحة **دفاتر الإهلاك**.
5.  في صفحة **نماذج القيم** أو صفحة **دفاتر الإهلاك** في مجموعة حقول **إهلاك الاستهلاك**، أدخل المعلومات في الحقول التالية:
    -   معامل الاستهلاك
    -   الوحدة
    -   إهلاك الوحدة
    -   الاستهلاك المقدر

    يقوم حقل **الاستهلاك المرّحل** بعرض إهلاك الاستهلاك، بالوحدات، الذي تم ترحيله بالفعل لمجموعة من الأصل الثابت ونموذج القيمة، أو لدفتر الإهلاك. لا يمكنك تحديث القيمة الموجودة في هذا الحقل يدوياً.

## <a name="examples"></a>أمثلة
### <a name="example-1"></a>مثال 1

تم إعداد معامل الاستهلاك التالي لتاريخ 31 يناير:

-   الكمية تساوي 1,000.
-   سعر إهلاك الوحدة المحدد للأصل الثابت المحدد هو 1.5.

فيما يلي مقترح الإهلاك في 31 يناير: الكمية × إهلاك الوحدة 1,000 × 1.5 = 1,500 إذا كان المعامِل الذي تم تحديده للأصل الثابت هو معامل نسبة مئوية، ويتم ضرب الكمية المقدرة في حقل **الاستهلاك المقدر** لنموذج قيمة الأصل الثابت في النسبة المئوية التي تم إعدادها لتاريخ الانتهاء المحدد. يتم فيما بعد اقتراح الكمية الناتجة باعتبارها كمية الإهلاك للفترة.

### <a name="example-2"></a>مثال 2

تم إعداد معامل إهلاك الاستهلاك التالي لتاريخ 31 يناير:

-   النسبة المئوية هي 10 في المائة.
-   سعر إهلاك الوحدة المحدد للأصل الثابت المحدد هو 1.5.
-   الكمية المقدرة للأصل الثابت هي 2,000.

فيما يلي مقترح الإهلاك في 31 يناير: الكمية المقدرة × النسبة المئوية × إهلاك الوحدة 2,000 × 10 × 1.5 = 300


