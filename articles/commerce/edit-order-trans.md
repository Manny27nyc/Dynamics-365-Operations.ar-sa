---
title: تحرير وتدقيق الأوامر عبر الإنترنت وحركات أوامر العميل غير المتزامنة
description: يوضح هذا المقال كيفية تحرير وتدقيق الأوامر عبر الإنترنت وحركات أوامر العميل غير المتزامنة في Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.industry: Retail
ms.openlocfilehash: dac7ffe6d62aaea11f2f5af0476db446b091938b
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287666"
---
# <a name="edit-and-audit-online-order-and-asynchronous-customer-order-transactions"></a>تحرير وتدقيق الأوامر عبر الإنترنت وحركات أوامر العميل غير المتزامنة

[!include [banner](../includes/banner.md)]

يوضح هذا المقال كيفية تحرير وتدقيق الأوامر عبر الإنترنت وحركات أوامر العميل غير المتزامنة في Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>نظرة عامة

بين الإصدارين التجاريين 10.0.5 و10.0.6، تمت إضافة الدعم لتحرير حركات الدفع نقدًا والاستلام فورًا‬‬‏‫ (مثل المبيعات والمرتجعات) وحركات إدارة النقد (مثل إدخال معوم وإزالة العطاء). في Commerce الإصدار 10.0.7، تمت إضافة الدعم لتحرير معاملات الأوامر عبر الإنترنت ومعاملات أوامر العميل غير المتزامنة.

## <a name="edit-and-audit-order-transactions"></a>تحرير معاملات الأمر وتدقيقها

لتحرير حركات الأمر وتدقيقها في المركز الرئيسي لـ Commerce، اتبع هذه الخطوات.

1. قم بتثبيت [Microsoft Dynamics Office Add-in](https://appsource.microsoft.com/product/office/WA104379629?tab=Overview).
1. في صفحة **معلمات البيع بالتجزئة** ، في علامة التبويب **أوامر العملاء** ، في علامة التبويب السريعة **الأمر** ، حدد كود الاحتجاز لـ **كود الاحتجاز لأخطاء مزامنة الأمر**.
1. افتح مساحة العمل **ماليات المتجر**. يوفر الإطارين المتجانبين **أخطاء مزامنة الأمر عبر الإنترنت** و **أخطاء مزامنة أمر العميل** عرضًا مُصفى مسبقًا لصفحة حركة البيع بالتجزئة. يعرض كل منها سجلات المعاملات التي تحتوي علي مزامنة فاشلة لنوع الأمر المطابق.
1. افتح صفحة **أخطاء مزامنة الأوامر عبر الإنترنت** أو صفحة **أخطاء مزامنة أوامر العميل**. حدد سجلاً لعرض تفاصيل خطأ المزامنة. توفر علامة التبويب السريعة **حالة المزامنة** تفاصيل الخطأ التالية:

    - حالة أمر معلق
    - تفاصيل خطأ الأمر
    - تاريخ ووقت التعديل
    - عدد مرات إعادة المحاولة

1. إذا كانت تشير تفاصيل الخطأ إلى وجوب إصلاح السجل، فحدد **وظيفة Office الإضافية**، ثم حدد **تحرير المعاملة المحددة**. يتم فتح ملف Excel يعرض تفاصيل المعاملة المحددة.

    - إذا كانت المعاملة التي يتم تحريرها هي معاملة أمر عبر الإنترنت، سيحتوي ملف Excel علي أوراق العمل التالية:

        - **المعاملة**: تحتوي ورقة العمل هذه على تفاصيل الرأس الخاصة بالمعاملة.
        - **معاملة المبيعات**: تحتوي ورقة العمل هذه على تفاصيل بنود المعاملة.
        - **معاملات الدفع**: تتضمن ورقة العمل هذه تفاصيل بنود الدفع الخاصة بالمعاملة.
        - **معاملات الخصم** - تتضمن ورقة العمل هذه تفاصيل تتعلق بالخصومات الخاصة بالمعاملة.
        - **المعاملات الضريبية** : تتضمن ورقة العمل هذه تفاصيل تتعلق بالضريبة ذات الصلة بالمعاملة.
        - **معاملات المصروفات**: تتضمن ورقة العمل هذه ببيانات المصاريف ذات الصلة بالمعاملة.

    - إذا كانت الحركة التي يتم تحريرها هي معاملة لأمر العميل غير متزامنة‬، سيحتوي ملف Excel علي أوراق العمل التالية:

        - **البنود**: تحتوي ورقة العمل هذه على الرأس وتفاصيل بنود المعاملة.
        - **المدفوعات**: تتضمن ورقة العمل هذه تفاصيل بنود الدفع الخاصة بالمعاملة.
        - **الخصومات**: تتضمن ورقة العمل هذه تفاصيل تتعلق بالخصومات الخاصة بالمعاملة.
        - **الضرائب**: تتضمن ورقة العمل هذه تفاصيل تتعلق بالضرائب الخاصة بالمعاملة.
        - **المصاريف**: تتضمن ورقة العمل هذه بيانات تتعلق بمصاريف المعاملة.

1. في ملف Excel، في الحقل **حالة الأمر المعلق** ، ادخل **تحرير**، ثم قم بنشر التغيير. وبهذه الطريقة، تمنع مهمة **مزامنة الأمر** التي تعمل في وضع الدُفعات من تخطي هذا السجل أثناء المعالجة.
1. في ملف Excel، قم بتعديل الحقول المناسبة، ثم قم بتحميل البيانات مرة أخرى إلى المركز الرئيسي لـ Commerce باستخدام وظيفة النشر الخاصة بالوظيفة الإضافية Dynamics Excel. ستنعكس التغييرات في النظام بعد نشر البيانات. أثناء عملية النشر، لا يتم إجراء عملية التحقق من صحة التغييرات التي يُجريها المستخدمون.
1. يمكنك عرض مسار تدقيق كامل للتغييرات عن طريق تحديد **عرض مسار التدقيق** في عنوان **معاملة البيع بالتجزئة** للتغييرات على مستوى الرأس، وفي القسم والسجل ذي الصلة في صفحة المعاملة المناسبة. علي سبيل المثال، سيتم عرض كافة التغييرات المرتبطة ببنود المبيعات في صفحة **معاملات المبيعات** ، وسيتم عرض كافة التغييرات المرتبطة بالمدفوعات في صفحة **معاملات الدفع**. يتم الاحتفاظ بتفاصيل التدقيق للتغييرات على النحو التالي:

    - تاريخ ووقت التعديل
    - الحقل
    - قيمة قديمة
    - قيمة جديدة
    - تعديل بواسطة

1. بعد اجراء التغييرات ونشرها، حدد **مزامنة الأمر** لبدء عملية المزامنة علي الفور. وبدلاً من ذلك، يمكنك انتظار عملية المزامنة التي تعمل في الوضع الدفعي لإتمام المعاملة.

وبشكل افتراضي، بعد مزامنة الأوامر بنجاح، يتم وضعها في حاله التعليق، وذلك استنادًا إلى كود التعليق المحدد في محددات Commerce. يتعين إزالة التعليق على الأوامر قبل أن تتم معالجة الأوامر بشكل أكبر للوفاء بها أو عمليات أخرى.

## <a name="additional-resources"></a>الموارد الإضافية

[تحرير وتدقيق معاملات الدفع نقدًا والاستلام فورًا وإدارة النقد](edit-cash-trans.md)

[تحرير الأبعاد المالية لحركات البيع بالتجزئة](edit-financial-dim.md)

[إنشاء دفتر عمل Excel لتحرير معاملات البيع بالتجزئة](create-excel-edit.md)

[إضافة الحقول إلى دفتر عمل Excel لتحرير معاملات البيع بالتجزئة](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
