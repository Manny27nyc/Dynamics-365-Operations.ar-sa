---
title: استكشاف أخطاء أوامر الشراء وإصلاحها
description: يوضح هذا الموضوع كيفية إصلاح المشكلات التي قد تواجهها أثناء العمل مع أوامر الشراء.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 234458f865e37a2d962aee8ab218b9521847081d
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 10/16/2020
ms.locfileid: "4421791"
---
# <a name="troubleshoot-purchase-orders"></a>استكشاف أخطاء أوامر الشراء وإصلاحها

يوضح هذا الموضوع كيفية إصلاح المشكلات التي قد تواجهها أثناء العمل مع أوامر الشراء.

## <a name="an-action-can-be-completed-only-after-the-line-number-is-fully-distributed"></a>يمكن إكمال الإجراء فقط بعد توزيع رقم البند بشكل كامل.

قد تحدث هذه المشكلة بسبب عدم الاتساق في توزيعات أمر الشراء.

لحل هذه المشكلة وإعادة تعيين أمر الشراء إلى الحالة *مسودة*، انتقل إلى **التدبير والتوريد \> المهام الدورية \> تنظيف \> إعادة تعيين توزيع أمر الشراء**. لمزيد من المعلومات، راجع منشور المدونة التالي: [حل أخطاء توزيع أمر الشراء في Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="when-purchase-orders-are-imported-through-data-management-purchase-order-line-numbers-dont-follow-the-increment-that-defined-in-system-parameters"></a>عند استيراد أوامر الشراء من خلال إدارة البيانات، لن تتبع بنود أمر الشراء الزيادة التي تم تحديدها في معلمات النظام.

### <a name="issue-description"></a>وصف المشكلة

بشكل افتراضي، لا تستخدم أرقام البنود المُنشأة بشكل تلقائي لبنود أوامر الشراء المستوردة عبر كيان البيانات *بنود أمر الشراء V2* زيادة رقم بند النظام المحددة في معلمات النظام. إذا أنشأت أمر شراء بشكل يدوي وأضفت البنود عبر واجهة المستخدم (UI)، يتم زيادة أرقام البنود بشكل صحيح. ومع ذلك، إذا كنت تستخدم إطار عمل إدارة البيانات (DMF)، فإنها لن تزداد بشكل صحيح.

تحدث هذه المشكلة لأن النظام يستخدم أسلوب إطار عمل إدارة البيانات (DMF) لتعيين أرقام البنود إذا لم تكن أرقام البنود معينة في الكيان المستورد، وذلك عند استيراد البنود عبر DMF. تقوم هذه الطريقة دائمًا بزيادة أرقام البنود بمقدار رقم واحد.

### <a name="issue-workaround"></a>حل المشكلة

تأكد من أن أرقام البنود المطلوبة معطاة بالفعل في حقول أرقام بنود كيان البيانات عندما تستورد بنود أمر الشراء. في هذه الحالة، لن يستبدل DMF أرقام البنود.

## <a name="a-default-tax-group-and-a-default-cash-discount-arent-filled-in-from-the-invoice-account"></a>لا يتم ملء مجموعة الضرائب الافتراضية والخصم النقدي الافتراضي من حساب الفاتورة.

إذا كنت تستخدم حساب فاتورة يختلف عن حساب العميل، فلن يتم ملء مجموعة الضرائب الافتراضية والخصم النقدي الافتراضي من حساب الفاتورة عند إنشاء أمر شراء.

يتم هذا السلوك بسبب التصميم. تعتمد القيم الافتراضية لمجموعة الضرائب والخصومات النقدية ومعلومات السعر الأخرى إلى حساب العميل، وليس حساب الفاتورة.

## <a name="i-receive-an-object-reference-not-set-error-during-purchase-order-confirmation-or-an-exception-has-been-thrown-by-the-target-of-an-invocation-exception-occurs-during-vendor-invoice-posting"></a>أتلقى الخطأ "لم يتم تعيين مرجع الكائن" أثناء تأكيد أمر الشراء، أو حدث الاستثناء "تم طرح استثناء بواسطة هدف استدعاء أثناء ترحيل فواتير المورّد.

قد تحدث هذه المشكلة بسبب عدم الاتساق في توزيعات أمر الشراء.

لحل هذه المشكلة وإعادة تعيين أمر الشراء إلى الحالة *مسودة*، انتقل إلى **التدبير والتوريد \> المهام الدورية \> تنظيف \> إعادة تعيين توزيع أمر الشراء**. لمزيد من المعلومات، راجع منشور المدونة التالي: [حل أخطاء توزيع أمر الشراء في Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="one-or-more-accounting-distributions-are-either-over-distributed-or-under-distributed"></a>هناك زيادة أو نقص في التوزيع في توزيع محاسبي واحد أو أكثر.

### <a name="issue-description"></a>وصف المشكلة

تتلقي رسالة الخطأ التالية: "هناك زيادة أو نقص في التوزيع في توزيع محاسبي واحد أو أكثر."

### <a name="issue-resolution"></a>حل المشكلة

قد تحدث هذه المشكلة بسبب عدم الاتساق في توزيعات أمر الشراء.

لحل هذه المشكلة وإعادة تعيين أمر الشراء إلى الحالة *مسودة*، انتقل إلى **التدبير والتوريد \> المهام الدورية \> تنظيف \> إعادة تعيين توزيع أمر الشراء**. لمزيد من المعلومات، راجع منشور المدونة التالي: [حل أخطاء توزيع أمر الشراء في Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).

## <a name="can-i-show-only-purchase-orders-that-i-created"></a>هل يمكنني إظهار فقط أوامر الشراء التي قمت بإنشائها؟

هذه الوظيفة غير متوفرة حاليًا.

## <a name="can-i-reserve-inventory-and-create-transactions-against-registered-inventory-on-a-purchase-order"></a>هل يمكنني حجز المخزون وإنشاء حركات مقابل مخزون مسجل في أمر شراء؟

### <a name="issue-description"></a>وصف المشكلة

حتى عندما تكون حالة الأصناف *مسجلة* على أمر شراء، لا يزال بإمكانك حجز المخزون. بمعنىً آخر، يمكنك إنشاء حركات في مقابل المخزون المسجل.

### <a name="reproduce-the-issue"></a>إعادة إنتاج المشكلة

يعرض الإجراء التالي إحدى الطرق لإعادة إنتاج المشكلة.

1. إنشاء أمر شراء.
2. تسجيل بند أمر الشراء.
3. لاحظ أنه يمكنك إنشاء حجوزات أو حركات في مقابل المخزون المسجل.

### <a name="issue-resolution"></a>حل المشكلة

يتم هذا السلوك بسبب التصميم. الأمر المتوقع هو ان الأصناف المسجلة قد وصلت فعليًا إلى المستودع أو المخزون، وأنها بالتالي متاحة للحجز.

## <a name="purchase-orders-dont-reflect-the-language-settings-of-the-legal-entity"></a>لا تعكس أوامر الشراء إعدادات اللغة الخاصة بالكيان القانوني.

### <a name="issue-description"></a>وصف المشكلة

يظهر اسم المنتج في أمر الشراء بلغة النظام بدلاً من اللغة التي تم تعيينها للكيان القانوني حيث تم إنشاء أمر الشراء.

### <a name="reproduce-the-issue"></a>إعادة إنتاج المشكلة

يعرض الإجراء التالي إحدى الطرق لإعادة إنتاج المشكلة.

1. قم بتعيين لغة النظام إلى *EN-US* (US English).
1. تأكد من وجود منتج حيث تتم المحافظة على اللغتين *EN-US* و *DE* (German) للترجمات واسم المنتج.
1. قم بتغيير لغة الكيان القانوني إلى *DE*.
1. في الكيان القانوني حيث تم تعيين *DE‎* كلغة، أنشئ أمر شراء يتضمن المنتج.
1. لاحظ استمرار ظهور اسم المنتج باللغة US English (لغة النظام).

### <a name="issue-resolution"></a>حل المشكلة

يتم هذا السلوك بسبب التصميم. على أوامر الشراء، يظهر المنتج دائمًا بلغة النظام. يتم استخدام لغة أمر الشراء عند إنشاء دفتر يومية التأكيد.

## <a name="the-approved-vendor-list-by-product-entity-doesnt-allow-the-effective-date-to-be-changed"></a>لا تسمح قائمة المورّدين المعتمدين حسب كيان المنتج بتغيير تاريخ السريان.

### <a name="issue-description"></a>وصف المشكلة

هناك منتج لديه مورّد معتمد لديه، على سبيل المثال، تاريخ السريان 11 يناير 2018 (*01/11/2018*)، وتاريخ انتهاء الصلاحية *إطلاقًا*. إذا حاولت تغيير تاريخ السريان إلى 10 يناير 2018 (*01/10/2018*)، أو 12 يناير 2018 (*01/12/2018*)، تتلقى رسالة الخطأ التالية:

> لا يمكن إنشاء سجل في قائمة المورّدين المعتمدين (PdsApproveVendorList). يجب أن تكون قيمة "انتهاء الصلاحية" أكبر من قيمة "ساري المفعول‬" أو مساوية لها.

### <a name="issue-resolution"></a>حل المشكلة

يمكنك فقط تمديد الفترة التي تم خلالها الموافقة على المورّد. تطبيق القواعد التالية:

- لتغيير تاريخ السريان بحيث يقع قبل أي من السجلات الموجودة (الفترات) الخاصة بمورّد الصنف، يجب أن يكون تاريخ انتهاء صلاحية الفترة الجديدة قبل كافة تواريخ انتهاء الصلاحية في السجلات الموجودة.
- لتغيير تاريخ انتهاء الصلاحية بحيث يقع بعد أي من الفترات الموجودة، يجب أن يقع تاريخ السريان بعد تاريخ انتهاء الصلاحية الأخير في أي سجل موجود.
- لتقليل الفترة الإجمالية التي تمت الموافقة على المورّد خلالها، يجب حذف السجلات الموجودة أو تعديلها. أو، يمكنك استخدام مفتاح **الاقتطاع** خلال عملية الاستيراد. يقوم هذا المفتاح بحذف كافة السجلات الموجودة في الجدول للمورّدين المعتمدين حسب الصنف.

بالنسبة لسيناريو المثال الموضح في وصف المشكلة، حيث للسجل تاريخ السريان *01/11/2018* وتاريخ انتهاء الصلاحية *إطلاقًا*، يمكنك استيراد سجل جديد لديه تاريخ السريان *01/10/2018* وتاريخ انتهاء الصلاحية *إطلاقًا‏‎*. ومع ذلك، لا يمكنك تقليل الفترة بحيث يتم تحديث تاريخ السريان إلى *01/12/2018* عبر إدارة البيانات. يجب إجراء هذا التغيير من خلال واجهة المستخدم.

## <a name="after-i-change-the-delivery-address-on-a-purchase-order-header-the-delivery-nameisnt-synced"></a>بعد قيامي بتغيير عنوان التسليم على رأس أمر الشراء، لا تتم مزامنة اسم التسليم.

### <a name="issue-description"></a>وصف المشكلة

يتم تحديث العنوان الموجود على رأس أمر الشراء إلى عنوان ليس عنوان تسليم. علي الرغم من تحديث العنوان على أمر الشراء، لا يتم تحديث اسم التسليم استنادًا إلى العنوان المحدّث.

### <a name="issue-resolution"></a>حل المشكلة

يتم هذا السلوك بسبب التصميم. يجب تصنيف العنوان المحدد كعنوان تسليم. وبخلاف ذلك، لا يتم تحديث اسم التسليم استنادًا إلى العنوان المحدد.

## <a name="can-i-find-the-user-who-canceled-a-purchase-order"></a>هل يمكنني العثور على المستخدم الذي قام بإلغاء أمر الشراء؟

يتم تعقب هذه المعلومات فقط إذا كان أمر الشراء يخضع لإدارة التغيير. إذا كنت تستخدم إدارة التغيير، فيمكنك معرفة من هي الجهة التي أرسلت التغيير (الإلغاء) ووافقت عليه.