---
title: "تضمين تطبيقات PowerApps في Core HR"
description: "يشرح هذا المقال كيفية حل هذه المشكلة التي يختفي فيها عنصر قائمة PowerApps من الوحدة النمطية لإدارة النظام."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 197b553f0b202ee29ad42274e2c0e03446ec782c
ms.contentlocale: ar-sa
ms.lasthandoff: 12/04/2018

---

# <a name="embed-powerapps-apps-in-core-hr"></a>تضمين تطبيقات PowerApps في Core HR

[!include [banner](includes/banner.md)]

**المشكلة**

اختفي عنصر قائمة**PowerApps** من الوحدة النمطية لـ **إدارة النظام**.

**السبب**

تم تغيير تصميم واجهة المستخدم، ويتم الآن تضمين Microsoft PowerApps في نموذج التخصيص القياسي.

**‏‏الدقة**

تم تغيير الطريقة التي يتم من خلالها تضمين تطبيقات PowerApps. تتم الآن إضافة تطبيقات PowerApps من خلال نموذج التخصيص. يمكنك إضافة تطبيقات PowerApps إلى كافة الصفحات الموجودة في Microsoft Dynamics 365 for Talent تقريبًا.

للحصول على معلومات تفصيلية حول كيفية تضمين تطبيقات PowerApps في Talent، راجع [تضمين تطبيقات PowerApps](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/embed-power-apps).

يجب أن تتم ترقية أي عميل من عملاء PowerApps الذي قام بتضمين التطبيقات قبل التغيير إلى النموذج الجديد.

يوجد زر **PowerApps**في الزاوية اليسرى العليا في كل صفحة من صفحات Talent تقريبًا. يمكنك استخدام هذا الزر لإدراج تطبيق PowerApps.

فيما يلي مثال على ذلك.

1. انتقل إلى **إدارة العاملين \> الارتباطات \> العاملون \> الموظفون**.
2. حدد زر **PowerApps**، ثم قم بتحديد **إدراج PowerApp**.

    ![زر PowerApps](media/png.png)

3. أكمل الحقول في مربع حوار **إدراج PowerApp**.

    ![إدراج مربع حوار PowerApp](media/insert-powerapp.png)

بدلًا من ذلك، اتبع الخطوات التالية.

1. في صفحة جزء الإجراءات، في علامة التبويب **خيارات**، في مجموعة **تخصيص**، حدد **تخصيص هذا النموذج**

    ![تخصيص مجموعة في علامة التبويب خيارات](media/options.png)

    يظهر شريط أدوات التخصيص.

2. على شريط الأدوات، حدد **إدراج \> PowerApp**.

    ![إدراج تطبيق PowerApps باستخدام شريط أدوات التخصيص](media/powerapp-bar.png)
