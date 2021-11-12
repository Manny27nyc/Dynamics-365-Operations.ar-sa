---
title: تكوين منتج ليتم شراؤه مجانًا
description: يوضح هذا الموضوع كيفيه تكوين منتج بحيث يمكن شراؤه مجانا في Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 10/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 2ad96a3dde93a48694aee418ecfbbd33dc9830d6
ms.sourcegitcommit: 6bf9e18989e6d77497a9dda1c362f324b3c2fbf2
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 10/27/2021
ms.locfileid: "7713875"
---
# <a name="configure-a-product-to-be-purchased-for-free"></a>تكوين منتج ليتم شراؤه مجانًا

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

يوضح هذا الموضوع كيفيه تكوين منتج بحيث يمكن شراؤه مجانا في Microsoft Dynamics 365 Commerce.

## <a name="configure-the-product"></a>تكوين المنتج

لبيع منتج مجانا في Dynamics 365 Commerce ، يجب تعيين السعر الخاص به إلى 0 (صفر). بالاضافه إلى ذلك ، يجب ان تقوم بتكوين الاعداد **صالح سعر صفري** للمنتج.

لتكوين إعداد **صالح لسعر صفري** في المراكز الرئيسية للتجارة، اتبع هذه الخطوات.

1. انتقل إلى **Retail and Commerce \> المنتجات والفئات \> المنتجات الصادرة حسب الفئة**.
1. انتقل إلى المنتج الذي ترغب في بيعه مجانا. 
1. في المقطع **التجارة** من الصفحة المنتج، قم بتعيين الخيار **صالح للسعر الصفري** إلى **نعم**.

يبين الرسم التوضيحي التالي مثالا لأحد المنتجات التي تم تعيين الخيار **صالح للسعر الصفري** الخاص بها إلى **نعم**.

![مثال لمنتج تم فيه تعيين الخيار الصالح لسعر الصفر إلى نعم.](./media/Zero-price.png)

## <a name="configure-the-online-stores-functionality-profile"></a>تكوين ملف تعريف وظائف المتجر عبر الإنترنت

قبل التمكن من معالجه الحركات المجانية ، يجب تكوين اعداد **السماح بالسحب بدون مدفوعات** لملف تعريف الوظائف الخاص بالمتجر الموجود علي الإنترنت بحيث يتم السماح بالحركات التي ليس لها مدفوعات. للحصول علي معلومات حول كيفيه إنشاء ملفات تعريف الوظائف ، راجع [إنشاء ملف تعريف الوظائف عبر الإنترنت](online-functionality-profile.md).

لتكوين إعداد **السماح بالسحب بدون مدفوعات** في المراكز الرئيسية للتجارة، اتبع هذه الخطوات.

1. انتقل إلى **Retail وCommerce \> إعداد القناة \> إعداد متجر على الإنترنت**.
1. في الصفحة الخاصة بملف تعريف وظائف المتجر ، ضمن **السحب** ، قم بتعيين خيار **السماح بالسحب بدون مدفوعات** إلى **نعم**.

يبين الرسم التوضيحي التالي مثالا لملف تعريف المتجر الفوري حيث يتم تعيين **خيار السماح بالسحب بدون مدفوعات** إلى **نعم**.

![مثال لملف تعريف المتجر الفوري حيث يتم تعيين خيار السماح بالسحب بدون مدفوعات إلى نعم.](./media/Zero-price-profile.png)

## <a name="additional-resources"></a>الموارد الإضافية

[إدارة أسعار مبيعات البيع بالتجزئة](price-management.md)

[إنشاء ملف تعريف وظائف على الإنترنت](online-functionality-profile.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]