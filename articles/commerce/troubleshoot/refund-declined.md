---
title: رفض المبلغ المسترد في أمر الإرجاع
description: يوفر هذا الموضوع إرشادات استكشاف الأخطاء وإصلاحها والتي يمكن أن تساعد في حالة رفض المبلغ المسترد لأمر الإرجاع نظرا لأن بطاقة الائتمان المستخدمة للفوترة تختلف عن البطاقة التي تم استخدامها أثناء تفويض الدفع الأصلي.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: e202c6b4b9e025d5af1cd5eb6235884aab6444e6
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585183"
---
# <a name="refund-on-a-return-order-is-declined"></a>رفض المبلغ المسترد في أمر الإرجاع

[!include [banner](../../includes/banner.md)]

يوفر هذا الموضوع إرشادات استكشاف الأخطاء وإصلاحها والتي يمكن أن تساعد في حالة رفض المبلغ المسترد لأمر الإرجاع نظرا لأن بطاقة الائتمان المستخدمة للفوترة تختلف عن البطاقة التي تم استخدامها أثناء تفويض الدفع الأصلي.

## <a name="description"></a>الوصف

يتم رفض المبلغ المسترد عندما تختلف بطاقة الائتمان المستخدمة لفوترة أمر الإرجاع عن البطاقة التي تم استخدامها أثناء تفويض الدفع الأصلي. تظهر رسالة الخطا التالية: بعض المدفوعات ليست بالحالة الصحيحة للترحيل. الرجاء إعادة التحقق من صحة حالة كافة المدفوعات السابقة للفوترة."

ستتضمن تفاصيل تخويل الدفع رسالة الخطا التالية: "فشل SendRequest() في بوابة Adyen بالحالة'InternalServerError'.22144; تم إرجاع استجابة فارغة من Adyen.(22001);"

![خطأ رفض المبلغ المسترد في أمر الإرجاع](media/refund-order-decline.jpg)

## <a name="resolution"></a>الدقة

### <a name="enable-blind-returns-in-adyen"></a>تمكين المرتجعات المخفيه في Adyen

لتمكين المرتجعات المخفية، اتبع الخطوات الموجودة في [استكشاف الأخطاء وإصلاح مشكلات موصل الدفع Dynamics 365 لـ Adyen](adyen-support.md) للاتصال بفريق دعم Adyen وطلب أن يتم تمكين المرتجعات المخفية في حساب تاجر Adyen الخاص بك.

## <a name="additional-resources"></a>الموارد الإضافية

[موصل دفع Dynamics 365 لـ Adyen](../dev-itpro/adyen-connector.md)

[إعداد موصل دفع Adyen لـ Dynamics 365](https://docs.adyen.com/plugins/microsoft-dynamics)