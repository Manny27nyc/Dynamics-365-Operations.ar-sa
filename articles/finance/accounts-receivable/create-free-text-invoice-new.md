---
title: إنشاء فاتورة نص حر
description: توضح هذه المقالة كيفية إنشاء فواتير النص الحر‬.
author: abruer
ms.date: 02/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 87dc6334baa83ace23b77d94da4d1e464cb0b574
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878149"
---
# <a name="create-a-free-text-invoice"></a>إنشاء فاتورة نص حر

[!include [banner](../includes/banner.md)]

توضح هذه المقالة كيفية إنشاء فواتير النص الحر‬. بالنسبة إلى هذا الإجراء، استخدم شركة بيانات العرض التوضيحي **USMF**.

## <a name="create-a-free-text-invoice"></a>إنشاء فاتورة نص حر

1. انتقل إلى **الحسابات المدينة (أو دفتر أستاذ المبيعات) \> الفواتير \> جميع الفواتير ذات نص حر‬**.
2. حدد **جديد**.
3. في الحقل **حساب العميل**، حدد قيمة.

    * بشكل افتراضي، يُستخدم الحساب المحدد على أنه حساب العميل كحساب فاتورة.
    * إذا لم يتم ترحيل الفاتورة، فستبدأ حالة المحاسبة مع **قيد التنفيذ‬**.
    * سوف يتم تعيين رقم الفاتورة عند ترحيل الفاتورة.
    * إذا كنت تستخدم تفويضات منطقة التداول باليورو (SEPA) فسيتم إدخال تفويض الخصم المباشر‬ تلقائيًا عند تحديد حساب العميل.

4. في حقل **الوصف**، أدخل قيمة.
5. في الحقل **الحساب الرئيسي**، حدد رقم حساب من دون أبعاد. ستقوم بإدخال الأبعاد لاحقًا في هذه المقالة.

    يمكنك أيضًا إدخال حرف واحد أو أكثر للحساب الرئيسي، واستخدام خاصية البحث للعثور على الحساب.

6. حدد علامة التبويب السريعة **تفاصيل البند** لإضافة الأبعاد إلى الحساب الرئيسي.
7. حدد علامة تبويب **بند الأبعاد المالية**.

    * تتعلق الأبعاد بالبند المحدد فقط.
    * يتم ملء مجموعة ضريبة المبيعات من العميل. إذا لم يكن لدى العميل مجموعة ضريبة مبيعات، فسوف تستخدم مجموعة ضريبة المبيعات من الحساب الرئيسي.
    * يتم ملء مجموعة ضريبة مبيعات الأصناف من الحساب الرئيسي. إذا لم يتوافر للحساب الرئيسي مجموعة ضريبة مبيعات أصناف، فسيتم استخدام مجموعة ضريبة مبيعات الأصناف المحددة في معلمات ضريبة المبيعات في دفتر الأستاذ العام.

8. اختياري: في حقل **الكمية**، أدخل رقمًا.
9. اختياري: في حقل **سعر الوحدة**، أدخل رقمًا.

    يتم حساب المبلغ بضرب الكميات في سعر الوحدة. ومع ذلك، يمكنك تجاوز هذا الحساب من خلال إدخال مبلغ.

10. حدد **ضريبة المبيعات** لعرض ضريبة المبيعات التي تم حسابها لفاتورتك.

    يمكنك عرض مبالغ ضريبة المبيعات في هذه الصفحة، أو يمكنك تجاوز المبالغ في علامة تبويب **التسوية**.

11. حدد **موافق**.
12. حدد **التكاليف** لإضافة تكلفة إلى فاتورتك.
13. في حقل **كود التكاليف‬**، أدخل قيمة.
14. في حقل **قيمة التكاليف**، أدخل رقمًا.
15. قم بإغلاق الصفحة.
16. حدد **الإجماليات** لعرض ملخص تفاصيل الفاتورة والإجماليات.
17. حدد **إغلاق**.
18. حدد **ترحيل** لترحيل الفاتورة. تبقى لديك فرصة لإلغاء قبل ترحيل الفاتورة فعليًا.

    * يمكنك تغيير توقيت طباعة الفواتير. حدد **الحالية** لطباعة كل فاتورة عند تحديثها. حدد **بعد** لطباعة جميع الفواتير بعد تحديثها.
    * لتغيير كيفية التحقق من حد الائتمان الخاص بالعميل قبل أن يتم ترحيل الفاتورة، قم بتغيير القيمة في الحقل **نوع حد الائتمان**.
    * يمكنك تحديد إيقاف ترحيل فاتورة النص الحر عند حدوث خطأ في علامة التبويب **تحديثات** في صفحة **معلمات الحسابات المدينة** (**الحسابات المدينة > الإعداد > معلمات الحسابات المدينة**). حدد **نعم** للمعلمة **إيقاف ترحيل الفواتير ذات النص الحر عند حدوث الخطأ الأول‬** لإيقاف ترحيل فواتير النص الحر عند حدوث خطأ. إذا كان الترحيل يتم على دُفعات، فسيوقف خطأ عملية الترحيل وسيتم تعيين حاله الدُفعة إلى **خطأ**. إذا لم يتم تحديد هذا الخيار، فستتخطى عملية الترحيل فاتورة بها خطأ ترحيل وستستمر في ترحيل فواتير إضافية. إذا كان الترحيل يتم على دُفعات، فلن يؤدي خطأ ترحيل إلى منع ترحيل فواتير أخرى. ستكون حالة الدُفعة **منتهية**. سيتوفر تقرير مفصل عن عملية الترحيل للمراجعة في سجل الوظائف الدُفعية.
    * لطباعة الفاتورة، عيّن الخيار إلى **نعم**.
    * لترحيل الفاتورة، عيّن الخيار إلى **لا**. يمكنك طباعة الفاتورة من دون ترحيلها.

19. حدد **موافق**.

## <a name="copy-lines"></a>نسخ السطور
لنسخ البنود في فاتورة نص حر، حدد بندًا واحدًا أو أكثر، ثم حدد **نسخ البنود المحددة**. يمكنك تحديد عدد النسخ التي ترغب في إنشائها، ويمكنك أيضًا نسخ الملاحظات والمرفقات. يمكنك إما نسخ التوزيعات أو السماح بإعادة إنشائها عند إجراء الترحيل.

بعد نسخ البنود، يمكنك تحرير المعلومات حسب الحاجة.

## <a name="create-a-free-text-invoice-from-a-template"></a>إنشاء فاتورة نص حر من قالب
يمكنك إنشاء فاتورة نص حر من قالب. عندما تحدد **جديد من قالب** من علامة تبويب **الفاتورة**، يمكنك تحديد اسم قالب وحساب العميل لفاتورة النص الحر الجديدة. يمكن ملء القيم الافتراضية، مثل شروط الدفع وطريقة الدفع، من العميل بشكل تلقائي، أو يمكنك استخدام القيم التي تم حفظها مع القالب.

يتم إنشاء فاتورة نص حر جديدة ويمكنك تحرير القيم حسب الحاجة.

## <a name="resetting-the-workflow-status-for-free-text-invoices-from-unrecoverable-to-draft"></a>إعادة تعيين حالة سير العمل للفواتير ذات النص الحر من "غير قابل للاسترداد" إلى "مسودة"
سيكون لمثيل سير العمل الذي توقف بسبب خطأ لا يمكن إصلاحه حالة سير العمل **غير قابل للاسترداد**. عندما تكون حالة سير عمل فاتورة النص الحر للعميل **غير قابلة للاسترداد**، يمكنك إعادة تعيينها إلى **مسودة** عن طريق تحديد **استدعاء** من إجراءات سير العمل. يمكنك بعد ذلك تحرير فاتورة النص الحر للعميل. تتوفر هذه الميزة في حالة تشغيل المعلمة **إعادة تعيين حالة سير العمل للفواتير ذات النص الحر من "غير قابل للاسترداد" إلى "مسودة"‬** في صفحة **إدارة الميزات**.

يمكنك استخدام صفحة **محفوظات سير العمل** لإعادة تعيين حالة سير العمل إلى **مسودة**. يمكنك فتح هذه الصفحة من **فاتورة النص الحر** أو من جزء التنقل **عام > استعلامات > سير العمل**. لإعادة تعيين حالة سير العمل إلى **مسودة**، حدد **استدعاء**. يمكنك أيضًا إعادة تعيين حالة سير العمل إلى **مسودة** عن طريق تحديد الإجراء **استدعاء** في صفحة **فاتورة النص الحر** أو صفحة **جميع الفواتير ذات نص حر**. بعد إعادة تعيين حالة سير العمل إلى **مسودة**، تصبح متوفرة للتحرير في صفحة **فاتورة النص الحر**.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
