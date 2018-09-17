---
title: "إنشاء شجرة مواد قالب"
description: "يمكنك إنشاء قائمة مكونات الصنف القالب باستخدام طرق متنوعة."
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMATemplateBOMTable
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
ms.openlocfilehash: a80cf596a3e7c7f08d493a0fb7350fad62d38c3e
ms.contentlocale: ar-sa
ms.lasthandoff: 05/08/2018

---

# <a name="create-a-template-bom"></a>إنشاء شجرة مواد قالب   

[!include [banner](../includes/banner.md)]


يمكنك إنشاء شجرة مواد قالب باستخدام الطرق التالية. بالنسبة لجميع الطرق، يعد حقلا **من تاريخ** و **إلى تاريخ** اختياريين وللمعلومات فقط.

## <a name="create-a-template-bom-manually"></a>إنشاء شجرة مواد قالب يدويًا

1.  انقر فوق **إدارة الخدمة** \> **الإعداد‏‎** \> **كائنات الخدمة** \> **قوائم مكونات الصنف القالب**.

2.  اضغط على CTRL+N لفتح نموذج **إنشاء قائمة مكونات صنف قالب**.

3.  تحت **نسخ بنود قائمة مكونات الصنف من المرجع**، حدد خيار **يدوي**.

4.  في حقل **رقم الصنف**، أدخل صنفًا من نوع **قائمة مكونات الصنف**.

5.  في الحقل **الاسم**، أدخل اسمًا للقالب.

6.  في الحقلين **من تاريخ** و**إلى تاريخ**، أدخل فترة تاريخ تكون فيها قائمة مكونات الصنف القالب نشطة.

7.  وانقر فوق **موافق**.

يتم إنشاء شجرة مواد قالب فارغة جديدة.

## <a name="create-a-template-bom-based-on-another-template-bom"></a>إنشاء شجرة مواد قالب تستند إلى شجرة مواد قالب أخرى

1.  انقر فوق **إدارة الخدمة** \> **الإعداد‏‎** \> **كائنات الخدمة** \> **قوائم مكونات الصنف القالب**.

2.  اضغط على CTRL+N لفتح نموذج **إنشاء قائمة مكونات صنف قالب**.

3.  تحت **نسخ بنود قائمة مكونات الصنف من المرجع**، حدد خيار **قائمة مكونات الصنف القالب**.

4.  في الحقل **رقم المرجع**، حدد قائمة مكونات صنف قالب موجودة لنسخها إلى قائمة مكونات الصنف القالب الخاص بك.

5.  في الحقل **الاسم**، أدخل اسمًا للقالب.

6.  في الحقلين **من تاريخ** و**إلى تاريخ**، أدخل فترة تاريخ تكون فيها قائمة مكونات الصنف القالب نشطة.

7.  وانقر فوق **موافق**.

يتم إنشاء شجرة مواد قالب جديدة باستخدام بنود تتطابق مع البنود الموجودة في شجرة مواد القالب الأصلية.

## <a name="create-a-template-bom-based-on-an-item-bom"></a>إنشاء شجرة مواد قالب تستند إلى شجرة مواد صنف

1.  انقر فوق **إدارة الخدمة** \> **الإعداد‏‎** \> **كائنات الخدمة** \> **قوائم مكونات الصنف القالب**.

2.  اضغط على CTRL+N لفتح نموذج **إنشاء قائمة مكونات صنف قالب**.

3.  تحت **نسخ بنود قائمة مكونات الصنف من المرجع**، حدد **قائمة مكونات الصنف**.

4.  في **رقم المرجع** ، حدد إصدار قائمة مكونات الصنف. يتم نسخ صنف من نوع قائمة مكونات الصنف إلى **رقم الصنف**.

5.  في الحقل **الاسم**، أدخل اسمًا للقالب.

6.  في الحقلين **من تاريخ** و**إلى تاريخ**، أدخل فترة تاريخ تكون فيها قائمة مكونات الصنف القالب نشطة.

7.  وانقر فوق **موافق**.

يتم إنشاء قائمة مكونات صنف قالب جديدة باستخدام البنود المتوافقة مع البنود الموجودة في قائمة مكونات الصنف المدرجة في **قائمة مكونات الصنف**.

## <a name="create-a-template-bom-based-on-a-production-bom"></a>إنشاء شجرة مواد قالب تستند إلى شجرة مواد إنتاج

1.  انقر فوق **إدارة الخدمة** \> **الإعداد‏‎** \> **كائنات الخدمة** \> **قوائم مكونات الصنف القالب**.

2.  اضغط على CTRL+N لفتح نموذج **إنشاء قائمة مكونات صنف قالب**.

3.  تحت **نسخ بنود قائمة مكونات الصنف من المرجع**، حدد **الإنتاج**.

4.  في حقل **رقم المرجع**، حدد قائمة مكونات الصنف للإنتاج.

5.  في الحقل **الاسم**، أدخل اسمًا للقالب.

6.  في الحقلين **من تاريخ** و**إلى تاريخ**، أدخل فترة تاريخ تكون فيها قائمة مكونات الصنف القالب نشطة.

7.  وانقر فوق **موافق**.

يتم إنشاء قائمة جديدة من قوائم مكونات الصنف القالب باستخدام البنود المتوافقة مع البنود الموجودة في قائمة مكونات الصنف المدرجة في **قائمة مكونات الصنف**.

## <a name="see-also"></a>راجع أيضًا

[شجرة المواد القالب ](template-boms.md)

  


