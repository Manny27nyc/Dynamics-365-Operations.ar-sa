---
title: مستويات خدمة الأصول
description: يشرح هذا الموضوع مستويات الأصول في إدارة الأصول.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 35e7a55b1ba230be6bb72b20fcd805ea061b648e
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/02/2020
ms.locfileid: "3216560"
---
# <a name="asset-service-levels"></a>مستويات خدمة الأصول

[!include [banner](../../includes/banner.md)]

 

يشرح هذا الموضوع مستويات الأصول في إدارة الأصول. ترتبط مستويات خدمة الأصول بالأصول، ويتم نقلها إلى طلبات الصيانة وأوامر العمل. وتُستخدم لحساب أولوية أوامر العمل أثناء جدولة أوامر العمل. يمكن تغيير مستويات خدمة الأصول، إذا كانت التغييرات مطلوبة.

لمزيد من المعلومات حول الإعداد المرتبط بحساب درجات التقييم لجدولة أمر العمل، راجع [معلمات إدارة الأصول](../setup-for-objects/enterprise-asset-management-parameters.md). يجب إعداد سجل افتراضي واحد على الأقل لمستوى خدمة الأصول. يتم استخدام هذا السجل الافتراضي في حالة عدم العثور على تطابق آخر أثناء جدولة أمر العمل.

**مثال 1:** مستوى الخدمة الافتراضي المستخدم في حالة عدم العثور على تطابق آخر. في هذا السجل، تحدد مستوى خدمة واحدًا فقط.

**مثال 2:** مستوى خدمة عالٍ يُستخدم لجدولة مهام محرك شاحنة Volvo. في هذا السجل، تحدد نوع أصل ذا صلة (مثل **محرك شاحنة**) وشركة مصنعة (**Volvo**) ومستوى خدمة.

## <a name="set-up-asset-service-levels"></a>إعداد مستويات خدمة الأصول

1. حدد **إدارة الأصول** \> **إعداد** \> **مستويات خدمة الأصول**.
2. حدد **جديد** لإنشاء سجل.
3. وفقًا لمستوى التفاصيل المطلوب لمستوى خدمة الأصول، قم بإجراء تحديدات ذات صلة في الحقول التالية **موقع العمل** و**نوع الأصل** و**الشركة المصنعة** و**النموذج** و**الأصل‏‎** و**نوع أمر العمل** و**مستوى الخدمة**.

    > [!NOTE]
    > عند استخدام مستوى خدمة الأصول لطلبات الصيانة وأوامر العمل، تجري إدارة الأصول مراجع لجميع سجلات مستوى خدمة الأصول للتحقق من وجود تطابق محتمل. وهي تتحقق دائمًا من المجموعة الأكثر تحديدًا أولاً. وبعبارة أخرى، تقوم إدارة الأصول أولاً بالتحقق من تطابق في حقل **نوع أمر العمل**. إذا لم يتم العثور على تطابق، فهي تتحقق من وجود تطابق لحقل **الأصل**. كما ترى في تخطيط الصفحة **مستويات خدمة الأصول**، يعني هذا السلوك أنه، للعثور على المجموعة الأكثر تحديدًا، تقوم إدارة الأصول بالتحقق من كل سجل من اليسار إلى اليمين للحصول على تطابق. إذا لم يتم العثور على تطابق، يتم استخدام السجل الافتراضي الذي لا يحتوي على تحديدات في هذه الحقول.

4. في الحقل‏‎ **مستوى الخدمة**، حدد رقمًا يشير إلى مستوى الخدمة (أولوية).


> [!NOTE]
> إذا قمت بتغيير سجل مستوى الخدمة في صفحة **مستويات خدمة الأصول** بعد استخدامه في أمر عمل، فلن يتم تحديث مستوى الخدمة في طلبات الصيانة وأوامر العمل وفقًا لذلك.