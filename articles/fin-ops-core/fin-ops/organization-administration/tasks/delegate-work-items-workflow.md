---
title: تفويض عناصر العمل في سير عمل
description: إذا كنت تخطط للتواجد خارج المكتب مما يعني أنك لن تكون متاحًا لاتخاذ الإجراءات اللازمة على عناصر العمل، فيمكنك تفويض عناصر العمل أو إعادة تعيينها إلى مستخدمين آخرين.
author: jasongre
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserSetup, WorkflowDelegationUserListLookup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: aceafbe8dfcdac2ac7b97a4f77a9a30599c60c51
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140572"
---
# <a name="delegate-work-items-in-a-workflow"></a>تفويض عناصر العمل في سير عمل

[!include [banner](../../includes/banner.md)]

## <a name="manually-delegate-a-work-item"></a>تفويض عنصر عمل يدويًا

تفويض عنصر عمل فردي، حدد الخيار **تفويض** في قائمة **سير العمل**، ثم أدخل المستخدم الذي تريد تفويضه لسير العمل مع إضافة تعليق. سيؤدي ذلك إلى إعادة تعيين عنصر العمل إلى هذا المستخدم لتمكينه من إتمامه.

## <a name="automatically-delegate-work-items"></a>تفويض عناصر العمل تلقائيًا

إذا كنت تخطط للبقاء خارج المكتب أو بشكل آخر غير متوفر للعمل على عناصر عمل لفترة من الوقت، فيمكنك تفويض عناصر العمل الجديدة بشكل تلقائي لمستخدمين آخرين باستخدام صفحة **خيارات المستخدم**.

### <a name="set-up-automatic-delegation"></a>إعداد تفويض تلقائي
1. انتقل إلى **عام > الإعداد > خيارات المستخدم**.
2. انقر فوق علامة‏‎ التبويب **سير العمل**. تأكد من توسيع قسم "التفويض". لتكوين النظام بحيث يقوم النظام بتفويض عناصر عملك إلى مستخدمين الآخرين بشكل تلقائي، يجب إنشاء قواعد تفويض تحدد متى يتم تفويض أنواع معينة من عناصر العمل. اتبع هذه الخطوات لإنشاء قاعدة تفويض.  
3. انقر فوق **إضافة**.
4. في حقل **النطاق**، حدد خيارًا.
    - الكل - تفويض كل عناصر العمل المعينة لك.
    - وحدة نمطية - تفويض فقط عناصر العمل المرتبطة بنوع سير عمل معين. إذا قمت بتحديد هذا الخيار، فيجب تحديد نوع سير العمل في حقل "الاسم".
    - سير العمل - تفويض فقط عناصر العمل المرتبطة بنوع سير عمل معين. إذا قمت بتحديد هذا الخيار، فيجب تحديد سير العمل في حقل "الاسم".  
5. في حقل **التفويض**، حدد المستخدم الذي تريد تفويض عناصر العمل إليه. استخدم الحقلين "تاريخ/وقت البدء" و"تاريخ/وقت الانتهاء" لتحديد متى تريد تفويض عناصر العمل تلقائيًا.  
6. في الحقل **تاريخ/وقت البدء**، أدخل تاريخًا ووقتًا.
7. في الحقل **‏‫تاريخ/وقت الانتهاء**، أدخل تاريخًا ووقتًا.
8. حدد خانة الاختيار **ممكّن‬** لتنشيط قاعدة التفويض. إذا حددت **وحدة نمطية** كنطاق، فيجب عندئذٍ تحديد الوحدة النمطية في حقل "الاسم". إذا حددت **سير العمل** كنطاق، فيجب عندئذٍ سير العمل المحدد الذي تريد تفوضه في حقل "الاسم".  
9. في حقل **التعليق**، أدخل تعليقًا يوضح سبب تفويض عناصر العمل.
