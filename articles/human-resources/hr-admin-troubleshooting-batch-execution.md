---
title: إعادة تعيين وظائف الدُفعات المتوقفة
description: يشرح هذا الموضوع كيفية حل المشكلات المتعلقة بوظائف الدفعات المتوقفة.
author: andreabichsel
ms.date: 03/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: Platform update 42
ms.openlocfilehash: 01ef0bf8ccc486614eec42d3fb6f0b2941fc47c0
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794939"
---
# <a name="reset-stuck-batch-jobs"></a>إعادة تعيين وظائف الدُفعات المتوقفة

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="issue"></a>إصدار

يمكن أن يواجه Microsoft Dynamics 365 Human Resources مشكلات في وظائف الدفعات المتوقفة إما في حالة **قيد التنفيذ** أو **قيد الإلغاء** ولم تكتمل.

## <a name="resolution"></a>الدقة

عندما تكون وظيفة الدفعة متوقفة في حالة **قيد التنفيذ** أو **قيد إلغاء**، يمكنك إعادة تعيين الحالة من خلال فرض إلغاء الوظيفة. وبعد إلغائها، يمكنك إعادة تعيين وظيفة الدفعة عن طريق تعيينها على حالة **قيد الانتظار**. سيتم بعد ذلك انتقاؤها مرة أخرى للتنفيذ في تشغيل الدُفعة المجدولة التالي.

1. في مساحة عمل **إدارة النظام**، حدد صفحة **الارتباطات**، وحدد **وظائف الدفعات**.

2. في صفحة قائمة **وظيفة الدفعة**، حدد الوظيفة التي تحتاج إلى إعادة التعيين.

3. على شريط الاجراء، حدد **فرض الإلغاء**، وقم بتأكيد الإجراء.

   > [!NOTE]
   > يتوفر إجراء **فرض الإلغاء** فقط عندما تكون حالة وظيفة الدفعة المحددة هي إما **قيد التنفيذ** أو **قيد الإلغاء**، ولا يتم تشغيل عمليات تنفيذ الدفعة أو إلغائها للوظيفة.

4. على شريط الإجراء، حدد **تغيير الحالة**.

5. في صفحة **تحديد الحالة الجديدة**، حدد **قيد الانتظار**، ثم حدد **موافق**.

   ![تحديد حالة وظيفة دفعة جديدة](./media/hr-admin-reset-batch-job-status.png)

## <a name="see-also"></a>راجع أيضًا

[تحسين الأداء عن طريق جدولة الوظائف الدُفعية بعد الساعات](hr-admin-troubleshooting-batch-jobs.md)<br>
[تحسين الأداء باستخدام مهام التنظيف التلقائية](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]