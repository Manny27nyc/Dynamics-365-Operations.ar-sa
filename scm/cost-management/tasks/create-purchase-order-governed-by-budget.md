--- 
title: "إنشاء أمر شراء تحكمه الموازنة"
description: "استخدم هذا الإجراء لإنشاء أمر شراء يتم التحقق منه للموازنة المتوفرة."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: f9b82db94d98fb19c67888a1f8a35b2fe62c98fe
ms.contentlocale: ar-sa
ms.lasthandoff: 07/28/2017

---
# <a name="create-a-purchase-order-governed-by-budget"></a>إنشاء أمر شراء تحكمه الموازنة

[!include[task guide banner](../../includes/task-guide-banner.md)]

استخدم هذا الإجراء لإنشاء أمر شراء يتم التحقق منه للموازنة المتوفرة. يستخدم هذا التسجيل شركة بيانات العرض التوضيحي USMF.


## <a name="review-the-budget-control-configuration"></a>مراجعة تكوين رقابة الموازنة
1. انتقل إلى إعداد الموازنة > الإعداد > رقابة الموازنة > تكوين رقابة الموازنة.
2. انقر فوق علامة التبويب "أموال الموازنة المتاحة‬".
3. انقر فوق علامة التبويب "المستندات ودفاتر اليومية".
4. انقر فوق علامة التبويب "تحديد قواعد التحكم في الموازنة‬".
5. انقر فوق علامة التبويب "تعريف مجموعات الموازنة‬‬".
6. قم بإغلاق الصفحة.

## <a name="create-the-purchase-order-header"></a>قم بإنشاء عنوان أمر الشراء
1. انتقل إلى التدبير وتحديد الموارد > أوامر الشراء > كل أوامر الشراء.
2. انقر فوق "جديد".
3. في الحقل "حساب المورد"، أدخل قيمة أو حددها.
4. قم بتوسيع القسم "عام".
5. في حقل "التاريخ المحاسبي‬"، قم بتعيين التاريخ إلى "2016-01-01".
6. انقر فوق "موافق".

## <a name="add-a-purchase-order-line"></a>إضافة بند أمر شراء
1. في الحقل "فئة التدبير"، أدخل قيمة أو حددها.
2. قم بتعيين الكمية على "2".
3. في الحقل "وحدة"، أدخل قيمة أو حددها.
4. قم بتعيين سعر الوحدة إلى "10000".
5. انقر فوق "الماليات‬".
6. انقر فوق "توزيع المبالغ".
7. في حقل "‏‫حساب دفتر الأستاذ‬"، حدد القيمة "601300-001-023--".
8. قم بإغلاق الصفحة.

## <a name="perform-budget-checking"></a>تنفيذ التحقق من الموازنة
1. انقر فوق "الماليات‬".
2. انقر فوق "تنفيذ التحقق من الموازنة".
3. انقر فوق "الماليات‬".
4. انقر فوق "أخطاء فحص الموازنة أو التحذيرات".
5. انقر فوق "إغلاق".

