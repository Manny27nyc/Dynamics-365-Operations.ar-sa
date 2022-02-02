---
title: عينة تكامل طابعة الضرائب المحصلة لإيطاليا
description: يقدم هذا الموضوع نظرة عامة على عينة التكامل المالي لإيطاليا في Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2018-11-1
ms.openlocfilehash: 592cecff5b6179e7afd1bacb25beda277dfb8fa3
ms.sourcegitcommit: 0d2de52e12fdb9928556d37a4813a67b303695dc
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 12/21/2021
ms.locfileid: "7944624"
---
# <a name="fiscal-printer-integration-sample-for-italy"></a>عينة تكامل طابعة الضرائب المحصلة لإيطاليا

[!include[banner](../includes/banner.md)]

يقدم هذا الموضوع نظرة عامة على عينة التكامل المالي لإيطاليا في Microsoft Dynamics 365 Commerce.

تتضمن وظيفة Commerce لإيطاليا نموذجًا لتكامل نقطة البيع (POS) مع طابعة مالية. يقوم النموذج بتوسيع [وظيفة التكامل المالي](fiscal-integration-for-retail-channel.md) بحيث يعمل مع طابعات [سلسلة Epson FP-90III](https://www.epson.it/products/sd/pos-printer/epson-fp-90iii-series) من Epson، وهو يتيح الاتصال بطابعة مالية في وضع خادم الويب عبر خدمة الويب EpsonFPMate باستخدام Fiscal ePOS-Print API. تدعم العينة وضع Registratore Telematico (RT) فقط. يتم توفير العينة في شكل كود المصدر وهي جزء من مجموعة تطوير برامج البيع بالتجزئة (SDK).

لا تصدر Microsoft إيه أجهزه أو برامج أو وثائق من Epson. للحصول على معلومات حول كيفية الحصول على الطابعة المالية وتشغيلها، اتصل بشركة [Epson Italia S.p.A](https://www.epson.it).

## <a name="scenarios"></a>السيناريوهات

يتم تغطية السيناريوهات التالية بواسطة عينة تكامل الطابعة المالية لإيطاليا:

- سيناريوهات المبيعات:

    - اطبع إيصالًا ماليًا للمبيعات والمرتجعات نقدًا وبالاستلام.
    - قم بالتقاط استجابه من الطابعة المالية، ثم قم بتخزينها في قاعده بيانات القناة.
    - الضرائب:

        - تعيين إلى أكواد الضريبة للطابعة المالية (الأقسام).
        - تحويل بيانات الضريبة المعينة إلى الطابعة المالية.
        - طباعة الضرائب على إيصال مالي.

    - المدفوعات:

        - تعيين إلى طرق الدفع الخاصة بالطابعة المالية.
        - طباعة المدفوعات على إيصال مالي.
        - طباعه معلومات التغيير.

    - طباعة خصومات البند.
    - بطاقات الهدايا:

        - استبعاد بند بطاقة الهدايا الذي تم إصداره/أعاده تحميله من إيصال مالي للبيع.
        - يستخدم هذا الزر في طباعه عمليه دفع تستخدم بطاقة الهدايا كطريقه دفع دوريه.

    - طباعه عمليات الاستلام المالية لعمليات أمر العميل:

        - لا تتم طباعه إيصال مالي لإيداع أمر العميل.
        - اطبع إيصالًا ماليًا للبنود المرحلة لأمر عميل مختلط.
        - يستخدم في طباعه إيصال مالي لعمليه الانتقاء الخاصة بامر العميل.
        - طباعه إيصال مالي لأمر إرجاع.

    - اطبع رمز شريطي لرقم الإيصال في إيصال مالي.
    - اطبع [معلومات العميل](emea-ita-customer-information.md) المحددة لحركة مبيعات في إيصال مالي. مثال على هذه المعلومات هو رمز يانصيب العميل. 

- كشوفات نهاية اليوم (تقارير X المالية وتقارير Z المالية).
- معالجه الأخطاء، مثل الخيارات التالية:

    - أعد محاولة التسجيل المالي إذا كانت إعادة المحاولة ممكنة، على سبيل المثال إذا كانت الطابعة المالية غير متصلة أو غير جاهزة أو لا تستجيب أو نفد الورق من الطابعة أو حدث انحشار للورق.
    - تأجيل عملية التسجيل المالي.
    - يستخدم لتخطي التسجيل المالي أو وضع علامة علي الحركة كمسجله، وتضمين رموز المعلومات للتقاط سبب الفشل والمعلومات الاضافيه.
    - تحقق من توفر الطابعة المالية قبل فتح معاملة مبيعات جديدة أو إنهاء معاملة المبيعات.

### <a name="gift-cards"></a>بطاقات الهدايا

تطبق عينة تكامل الطابعة المالية القواعد التالية المتعلقة ببطاقات الهدايا:

- استبعاد سطور المبيعات ذات الصلة بعمليتي *إصدار بطاقة الهدايا* و *إضافة إلى بطاقة الهدايا* من الإيصال الضريبي.
- لا تطبع إيصالًا ماليًا إذا كان يتكون من خطوط بطاقة هدايا فقط.
- قم بخصم المبلغ الإجمالي لبطاقات الهدايا التي تم إصدارها أو إعادة تحصيلها في معاملة من سطور الدفع الخاصة بالإيصال المالي.
- حفظ التسويات المحسوبة لبنود الدفع في قاعده بيانات القناة مع وجود مرجع لحركه مالية مقابله.
- ويعتبر الدفع حسب بطاقة الهدايا دفعا منتظما.

### <a name="customer-deposits-and-customer-order-deposits"></a>ودائع العملاء وودائع أوامر العملاء

يطبق نموذج تكامل الطابعة المالية القواعد التالية المتعلقة بإيداعات العملاء وإيداعات أوامر العميل:

- لا تقم بطباعه إيصال مالي إذا كانت الحركة عبارة عن إيداع للعميل.
- لا تطبع إيصالًا ماليًا إذا كانت المعاملة تحتوي فقط على إيداع طلب العميل أو استرداد إيداع طلب العميل.
- قم بطباعه مبلغ الإيداع السابق الذي تم دفعه في إيصال مالي لعمليه انتقاء أمر العميل.
- خصم مبلغ إيداع أمر العميل من بنود الدفع عند إنشاء أمر عميل مختلط.
- احفظ التعديلات المحسوبة لبنود الدفع في قاعدة بيانات القناة بمرجع إلى حركة مالية لأمر زبون مختلط.

### <a name="limitations-of-the-sample"></a>قيود العينة

- تدعم الطابعة المالية فقط السيناريوهات التي يتم فيها تضمين ضريبة المبيعات في السعر. لذلك، يجب تعيين خيار **السعر شامل ضريبة المبيعات** إلى **نعم** لكل من المتاجر والعملاء.
- تتم طباعة التقارير اليومية (المالية X و المالية Z) باستخدام التنسيق المضمن في البرنامج الثابت للطابعة المالية.
- الطابعة المالية لا تدعم الحركات المختلطة. يجب تعيين خيار **منع خلط المبيعات والإرجاع في إيصال واحد** إلى **نعم** في ملفات تعريف وظائف نقطة البيع.
- يدعم النموذج التكامل فقط مع الطابعة المالية التي تعمل في وضع Registratore Telematico (RT)).

## <a name="set-up-fiscal-integration-for-italy"></a>إعداد التكامل المالي لإيطاليا

تعتمد عينة تكامل الطابعة المالية لإيطاليا على [وظيفة التكامل المالي](fiscal-integration-for-retail-channel.md) وهي جزء من Retail SDK. النموذج موجود في مجلد **src\\FiscalIntegration\\EpsonFP90IIISample** لمستودع [حلول Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (على سبيل المثال، [النموذج في إصدار/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/EpsonFP90IIISample)). يتكون [النموذج](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices) من موفر المستند المالي، وهو امتداد لCommerce Runtime (CRT)، والموصل المالي، وهو امتداد لمحطة أجهزة Commerce. لمزيد من المعلومات حول كيفيه استخدام Retail SDK، راجع [هندسة Retail SDK](../dev-itpro/retail-sdk/retail-sdk-overview.md)و[قم بإعداد تدفق البناء لمجموعة SDK المستقلة](../dev-itpro/build-pipeline.md).

> [!WARNING]
> وبسبب قيود [التعبئة المستقلة الجديدة ونموذج التوسيع](../dev-itpro/build-pipeline.md)، لا يمكن استخدامها حاليًا لنموذج التكامل المالي هذا. يجب استخدام الإصدار السابق من Retail SDK على الجهاز الظاهري (VM) للمطور في Microsoft Dynamics Lifecycle Services (LCS). لمزيد من المعلومات، راجع [إرشادات التوزيع الخاصة بنموذج تكامل الطابعة المالي لإيطاليا (قديم)](emea-ita-fpi-sample-sdk.md).
>
> يتم تخطيط الدعم الخاص بالتعبئة المستقلة الجديدة ونموذج الملحق الخاص بنماذج التكامل المالي للإصدارات اللاحقة.

قم بإكمال خطوات اعداد التكامل المالي كما هو موضح في [اعداد التكامل المالي لقنوات Commerce](setting-up-fiscal-integration-for-retail-channel.md).

1. [إعداد عملية التسجيل المالي](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). وكذلك قم بتسجيل الإعدادات الخاصة بعمليه التسجيل المالي [الخاصة بنموذج تكامل الطابعة المالية هذه](#set-up-the-registration-process).
1. [إعداد النصوص المالية للخصومات](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-texts-for-discounts).
1. [تعيين إعدادات معالجة الأخطاء‬](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [إعداد التقارير المالية X/Z من نقطة البيع](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).
1. [تمكين التنفيذ اليدوي للتسجيل المالي المؤجل](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).
1. [إعداد وظيفة إدارة معلومات العملاء في نقاط البيع](emea-ita-customer-information.md#setup).
1. [تكوين مكونات القناة](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>إعداد عملية التسجيل

لتمكين عملية التسجيل، اتبع هذه الخطوات لإعداد مقر Commerce الرئيسي. لمزيد من المعلومات، راجع [إعداد التكامل المالي لقنوات Commerce](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. تنزيل ملفات التكوين لموفر المستند المالي والموصل المالي:

    1. افتح مستودع [حلول Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. حدد إصدار فرع إصدار صحيح وفقا لإصدار التطبيق أو SDK الخاص بك (علي سبيل المثال، **[إصدار/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**).
    1. افتح **src \> FiscalIntegration \> EpsonFP90IIISample**.
    1. قم بتنزيل ملف تكوين موفر المستند المالي في **CommerceRuntime \> DocumentProvider.EpsonFP90IIISample \> Configuration \> DocumentProviderEpsonFP90IIISample.xml** (على سبيل المثال، [ملف إصدار/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/EpsonFP90IIISample/CommerceRuntime/DocumentProvider.EpsonFP90IIISample/Configuration/DocumentProviderEpsonFP90IIISample.xml)).
    1. قم بتنزيل ملف تكوين الموصل المالي في **HardwareStation \> EpsonFP90IIIFiscalDeviceSample \> Configuration \> ConnectorEpsonFP90IIISample.xml** (على سبيل المثال، [ملف إصدار/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/EpsonFP90IIISample/HardwareStation/EpsonFP90IIIFiscalDeviceSample/Configuration/ConnectorEpsonFP90IIISample.xml).

    > [!WARNING]
    > وبسبب قيود [التعبئة المستقلة الجديدة ونموذج التوسيع](../dev-itpro/build-pipeline.md)، لا يمكن استخدامها حاليًا لنموذج التكامل المالي هذا. يجب استخدام الإصدار السابق من Retail SDK على الجهاز الظاهري (VM) للمطور في LCS. توجد ملفات التكوين لعينة التكامل المالي هذه في المجلدات التالية من Retail SDK على الجهاز الظاهري VM للمطور في LCS:
    >
    > - **ملف تكوين موفر المستندات المالية:** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extension.DocumentProvider.EpsonFP90IIISample\\Configuration\\DocumentProviderEpsonFP90IIISample.xml
    > - **ملف تكوين الموصل المالي:** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.EpsonFP90IIIFiscalDeviceSample\\Configuration\\ConnectorEpsonFP90IIISample.xml
    > 
    > يتم تخطيط الدعم الخاص بالتعبئة المستقلة الجديدة ونموذج الملحق الخاص بنماذج التكامل المالي للإصدارات اللاحقة.

1. انتقل إلى **Retail and Commerce \> إعداد Headquarters \> المعلمات \> معلمات Commerce المشتركة**. في علامة التبويب السريعة **عام**، عيّن خيار **تمكين التكامل المالي** إلى **نعم**.
1. انتقل إلى **Retail وCommerce \> إعداد القناة \> التكامل المالي \> موفري المستندات المالية**، وقم بتحميل ملف تكوين موفر المستندات المالية الذي قمت بتنزيله مسبقًا.
1. انتقل إلى **Retail وCommerce \> إعداد القناة \> التكامل المالي \> الموصلات المالية**، وقم بتحميل ملف تكوين موفر المستندات المالية الذي قمت بتنزيله مسبقًا.
1. انتقل إلى **Retail وCommerce \> إعداد القناة \> التكامل المالي \> ملفات تعريف الموصل الوظيفية**. أنشئ ملف تعريف الموصل الوظيفي الجديد. حدد موفر المستند والموصل الذي قمت بتحميله سابقًا. قم بتحديث [إعدادات تعيين البيانات](#default-data-mapping) كما هو مطلوب.
1. انتقل إلى **Retail وCommerce \> إعداد القناة \> التكامل المالي \> ملفات تعريف الموصل الفنية**. قم بإنشاء ملف تعريف فني جديد للموصل، وحدد الرابط المالي الذي قمت بتحميله مسبقًا. قم بتحديث [إعدادات الموصل](#fiscal-connector-settings) كما هو مطلوب.
6. انتقل إلى **Retail وCommerce \> إعداد القناة \> التكامل المالي \> مجموعات الموصلات المالية**. قم بإنشاء مجموعة رابط مالي جديدة لملف التعريف الوظيفي للموصل الذي قمت بإنشائه مسبقًا.
7. انتقل إلى **Retail وCommerce \> إعداد القناة \> التكامل المالي \> عمليات التسجيل المالي**. قم بإنشاء عملية تسجيل مالي جديد وخطوة عملية تسجيل مالي، وحدد مجموعة الرابط المالي الذي قمت بإنشائه مسبقًا.
8. انتقل إلى **البيع بالتجزئة والتجارة \> إعداد القناة \> إعداد قناة البيع \> ملفات تعريف نقطة البيع \> ملفات تعريف الوظائف**. حدد ملف تعريف وظائف مرتبط بالمتجر حيث يجب تنشيط عمليه التسجيل. في علامة التبويب السريعة **عملية التسجيل المالي**، حدد عملية التسجيل المالي التي قمت بإنشائها مسبقًا.
9. انتقل إلى **Retail وCommerce \> إعداد القناة \> إعداد نقطة البيع \> ملفات تعريف نقطة البيع \> ملفات تعريف الأجهزة**. حدد ملف تعريف الجهاز المرتبط بمحطة الأجهزة التي سيتم توصيل الطابعة المالية بها. في علامة التبويب السريعة **الأجهزة الطرفية المالية**، حدد ملف التعريف الفني للموصل الذي قمت بإنشائه مسبقًا.
10. افتح جدول التوزيع (**Retail وCommerce \>تكنولوجيا معلومات Retail وCommerce\> جدول التوزيع**)، وحدد الوظيفتين **1070** و **1090** لنقل البيانات إلى قاعدة بيانت القناة.

#### <a name="default-data-mapping"></a>تعيين البيانات الافتراضي

يتم تضمين تعيين البيانات الافتراضي التالي في تكوين موفر المستندات المالية الذي يتم توفيره كجزء من نموذج التكامل المالي:

- **تعيين نوع طريقة الدفع** - تعيين طرق الدفع التي تم تكوينها للمتجر لأنواع الدفع التي تعتمدها الطابعة المالية. يوضح المثال التالي التعيين الافتراضي.

    ```JSON
    {"PaymentMethods": [
        {"StorePaymentMethod":"1", "PrinterPaymentType":"0", "PrinterPaymentIndex":"00"},
        {"StorePaymentMethod":"3", "PrinterPaymentType":"2", "PrinterPaymentIndex":"00"},
        {"StorePaymentMethod":"4", "PrinterPaymentType":"2", "PrinterPaymentIndex":"01"},
        {"StorePaymentMethod":"6", "PrinterPaymentType":"0", "PrinterPaymentIndex":"01"},
        {"StorePaymentMethod":"8", "PrinterPaymentType":"6", "PrinterPaymentIndex":"01"}
        ],
        "DepositPaymentMethod": {"PrinterPaymentType":"2", "PrinterPaymentIndex":"00"}}
    ```

    فيما يلي شرح للسمات الموجودة في هذا التعيين:

    - إن **StorePaymentMethod** عبارة عن طريقة دفع تم إعدادها للمتجر في **Retail وCommerce \> إعداد القناة \> طرق الدفع \> طرق الدفع**.
    - إن **PrinterPaymentType** و **PrinterPaymentIndex** هما نوع الدفع المطابق والفهرس المحددين في وثائق طابعة Epson المالية.
    - يتم استخدام **DepositPaymentMethod** لتحديد نوع الدفع وفهرس الطابعة للجزء من مبلغ استلام طلب العميل الذي تمت تسويته مع إيداع أمر العميل.

    يوضح الجدول التالي كيف يتوافق تعيين نماذج طرق الدفع مع طرق دفع المتجر التي تم تكوينها في البيانات التجريبية القياسية.

    | طريقة الدفع | اسم طريقة الدفع |
    |----------------|---------------------|
    | 1              | نقدي                |
    | 3              | رقم البطاقة                |
    | 4              | حساب العميل    |
    | 6              | عملة            |
    | 8              | بطاقة الهدايا           |

    يجب تعديل تعيين النموذج وفقا لطرق الدفع التي تم تكوينها في التطبيق الخاص بك.

- **نوع الرمز الشريطي لرقم الإيصال** - نوع الكود الشريطي المستخدم لعرض رقم الإيصال في الإيصال المالي. التعيين الافتراضي هو **CODE128**.
- **طباعة البيانات المالية في رأس الإيصال** – إذا تم تشغيل هذه المعلمة، فستتم طباعة معلومات المخزن على الإيصال المالي. تتضمن هذه المعلومات اسم المتجر وعنوانه ورقم التعريف الضريبي واسم الكاشير.
- **تعيين قسم الطابعة المالية** – تعيين أقسام الطابعة المالية إلى معدلات القيمة المضافة (VAT) ومعدلات الاعفاء الضريبي وناتوريس الاعفاء من الضريبة المحصلة وأنواع المنتجات. يوضح المثال التالي التعيين الافتراضي.

    ```JSON
    {"Departments": [
        {"VATRate":"2200", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"01"},
        {"VATRate":"2200", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"02"},
        {"VATRate":"1000", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"03"},
        {"VATRate":"1000", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"04"},
        {"VATRate":"0500", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"05"},
        {"VATRate":"0500", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"06"},
        {"VATRate":"0400", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"07"},
        {"VATRate":"0400", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"08"},
        {"VATRate":"0000", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"09"},
        {"VATRate":"0000", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"10"},
        {"VATRate":"0000", "VATExemptNature":"NS", "ProductType":"0", "DepartmentNumber":"99"}]}
    ```

    فيما يلي شرح للسمات الموجودة في هذا التعيين:

    - **VATRate** هو معدل ضريبة القيمة المضافة المدعوم والذي تم تكوينه ككود ضريبة مبيعات. تحتوي القيمة الموجودة في التعيين علي منزلتين عشريتين ولكن لا يوجد فاصل عشري. على سبيل المثال، **2200** تمثل 22 بالمائة، و **1000** تمثل 10 بالمائة.
    - إن **VATExemptNature** ينطبق فقط في الحالات التي يكون فيها معدل ضريبة القيمة المضافة 0 (صفر)، بما في ذلك الحالات التي لا توجد فيها ضريبة. حاليًا، يتم دعم **VATExemptNature** فقط لبطاقات الهدايا، ويجب أن تتوافق القيمة في التعيين مع قيمة خاصية **VATExemptNatureForGiftCard** في ملف تكوين XML.
    - **ProductType** هو نوع منتج. تمثل قيمة **0** البضائع، وتمثل قيمة **1** الخدمات.
    - **DepartmentNumber** هو رقم القسم الذي تم تكوينه في الطابعة والذي يتوافق مع السمات الثلاث السابقة.

    يجب تعديل تعيين النموذج وفقا لمعدلات ضريبة القيمة المضافة التي تم تكوينها في التطبيق الخاص بك والأقسام المقابلة التي تم تكوينها في الطابعة المالية.

- **طبيعة معفاة من ضريبة القيمة المضافة لبطاقة الهدايا** – طبيعة الإعفاء من ضريبة القيمة المضافة التي يجب تطبيقها عند إصدار بطاقة الهدايا أو إعادة تعبئتها. يجب أن تتوافق القيمة مع بعض المدخلات في تعيين قسم الطابعة المالية. التعيين الافتراضي هو **NS**.
- **تمكين العناصر المجانية** – إذا تم تشغيل هذه المعلمة، فسيتم تمكين نوع تعديل الخصم *omaggio* الخاص للعناصر التي تحتوي على خصم بنسبة 100 بالمائة.
- **رمز المعلومات لأصل الإرجاع** – رمز المعلومات المستخدم لالتقاط أصل حركة الإرجاع إذا لم يتم توفير إيصال مبيعات أصلي. يتم استخدام هذه المعلمة مع معلمتي **كود المعلومات الخاص بتاريخ المبيعات الأصلي** و **تعيين أصل الإرجاع** لإنشاء رسالة صحيحه في الإيصال المالي حول أصل حركه الإرجاع في حاله عدم وجود حركه مبيعات أصليه. 

    يجب تكوين رمز المعلومات هذا لتمكين المستخدم من تحديد أو إدخال أحد الأصول المحتملة لعمليات الإرجاع في المتاجر الخاصة بك. علي سبيل المثال، يمكن تكوينه كقائمه بالرموز التالية (مثل **الإرجاع من الموقع** أو **الإرجاع من الكشك**). عندئذ يتم استخدام معلمه **تعيين أصل الإرجاع** لترجمه قيمه التعليمات البرمجية للمعلومات إلى أمر خاص بطابعه المالية.

    يجب تكوين كود المعلومات الذي تم تحديده لـ **كود المعلومات لأصل الإرجاع** ككود معلومات إلزامي يتم تشغيله مره واحده لكل حركه مبيعات. يجب تعيينه على أنه رمز معلومات **إرجاع المنتج** في ملف تعريف وظائف نقطة البيع، بحيث يتم تشغيله عند تشغيل عملية **إرجاع المنتج**.

    لم يتم تحديد قيمه افتراضيه لهذا التعيين. يجب عليك تحديد رمز معلومات تم تكوينه في التطبيق الخاص بك.

- **رمز المعلومات لتاريخ المبيعات الأصلي** – رمز المعلومات المستخدم لالتقاط تاريخ المبيعات الأصلي لحركة المرتجعات إذا لم يتم توفير إيصال مبيعات أصلي. يتم استخدام هذه المعلمة مع معلمتي **كود المعلومات لأصل الإرجاع** و **تعيين أصل الإرجاع** لإنشاء رسالة صحيحه في الإيصال المالي حول أصل حركه الإرجاع في حاله عدم وجود حركه مبيعات أصليه.

    يجب تكوين التعليمات البرمجية للمعلومات بحيث يتم تعيين حقل **نوع الإدخال** إلى **التاريخ**. يجب تكوينه كرمز معلومات إلزامي يتم إطلاقه مرة واحدة لكل معاملة مبيعات. ويجب أيضا تعيينه باعتباره **كود المعلومات المرتبط** لكود المعلومات الذي تم تحديده لمعلمة **كود المعلومات لأصل الإرجاع**، بحيث يتم تشغيل رمزي المعلومات الاثنين واحدًا بعد الآخر.

    لم يتم تحديد قيمه افتراضيه لهذا التعيين. يجب عليك تحديد رمز معلومات تم تكوينه في التطبيق الخاص بك.

- **تعيين أصل الإرجاع** – تعيين أصول المرتجعات المستخدم لطباعة أصل حركة المرتجعات إذا لم يتم توفير إيصال مبيعات أصلي. يتم استخدام هذه المعلمة مع معلمتي **كود المعلومات لأصل لإرجاع** و **كود معلومات تاريخ المبيعات الأصلي** لإنشاء رسالة صحيحه في الإيصال المالي حول أصل حركه الإرجاع في حاله عدم وجود حركه مبيعات أصليه. يوضح المثال التالي التعيين الافتراضي.

    ```JSON
    {"ReturnOrigins": [
        {"ReturnOrigin":"1", "PrinterReturnOrigin":"POS"},
        {"ReturnOrigin":"2", "PrinterReturnOrigin":"ND"}
        ],
        "PrinterReturnOriginWithoutFiscalData":"POS"}
    ```

    فيما يلي شرح للسمات الموجودة في هذا التعيين:

    - **ReturnOrigin** هي أحد الأصول المحتملة للعائدات في متاجرك. يجب ان تكون القيمة مطابقه لقيمه معلمة **كود المعلومات لأصل الإرجاع**.
    - **PrinterReturnOrigin** هو أحد أصول المرتجعات التي تقبلها الطابعة المالية (**POS** أو **VR** أو **ND**).
    - إن **PrinterReturnOriginWithoutFiscalData** هو أصل الإرجاع الذي تقبله الطابعة المالية والذي يتوافق مع حركة إرجاع مرتبطة بحركة مبيعات أصلية لا تحتوي على بيانات مالية مرتبطة، لأنها لم يتم تسجيلها من خلال طابعة مالية. وفي هذه الحالة، يتم تحديد تاريخ المبيعات الأصلي علي انه تاريخ حركه المبيعات الاصليه.

ان تعيينات البيانات الافتراضية التالية قديمه ويتم الاحتفاظ بها فقط للتوافق مع الإصدارات السابقة:

- تعيين أكواد ضريبة القيمة (VAT)
- نوع دفع الإيداع

#### <a name="fiscal-connector-settings"></a>إعدادات الموصل المالي

يتم تضمين الإعدادات التالية في تكوين الرابط المالي الذي يتم توفيره كجزء من نموذج التكامل المالي:

- **عنوان نقطة النهاية** – عنوان URL الخاص بالطابعة.
- **مزامنة التاريخ والوقت** - قيمه تحدد ما إذا كان يجب مزامنة تاريخ الطابعة ووقتها مع محطه الاجهزه المتصلة.

### <a name="configure-channel-components"></a>تكوين مكونات القناة

> [!WARNING]
> وبسبب قيود [التعبئة المستقلة الجديدة ونموذج التوسيع](../dev-itpro/build-pipeline.md)، لا يمكن استخدامها حاليًا لنموذج التكامل المالي هذا. يجب استخدام الإصدار السابق من Retail SDK على الجهاز الظاهري (VM) للمطور في LCS. لمزيد من المعلومات، راجع [إرشادات التوزيع الخاصة بنموذج تكامل الطابعة المالي لإيطاليا (قديم)](emea-ita-fpi-sample-sdk.md).
>
> يتم تخطيط الدعم الخاص بالتعبئة المستقلة الجديدة ونموذج الملحق الخاص بنماذج التكامل المالي للإصدارات اللاحقة.

#### <a name="set-up-the-development-environment"></a>إعداد بيئة التطوير

لإعداد بيئة تطوير لاختبار العينة وتوسيعها، اتبع هذه الخطوات.

1. قم بنسخ مستودع [حلول Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions) أو تنزيله. حدد إصدار فرع إصدار صحيح وفقا لإصدار التطبيق أو SDK الخاص بك. لمزيد من المعلومات، راجع [تنزيل نماذج Retail SDK والحزم المرجعية من GitHub وNuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. افتح حل تكامل الطابعة المالي على **Dynamics365Commerce.Solutions\\FiscalIntegration\\EpsonFP90IIISample\\EpsonFP90IIISample.sln**، وقم بإنشائه.
1. تثبيت ملحقات CRT:

    1. ابحث عن مثبت ملحق CRT:

        - **Commerce Scale Unit:** في مجلد **EpsonFP90IIISample\\ScaleUnit\\ScaleUnit.EpsonFP90III.Installer\\bin\\Debug\\net461**، ابحث عن مثبت **ScaleUnit.EpsonFP90III.Installer**.
        - **CRT المحلي على نقطة البيع الحديثة:** في مجلد **EpsonFP90IIISample\\ModernPOS\\ModernPOS.EpsonFP90III.Installer\\bin\\Debug\\net461**، ابحث عن مثبت **ModernPOS.EpsonFP90III.Installer**.

    1. ابدأ مثبت ملحق CRT من سطر الأوامر:

        - **Commerce Scale Unit:**

            ```Console
            ScaleUnit.EpsonFP90III.Installer.exe install --verbosity 0
            ```

        - **CRT المحلي في نقطة البيع الحديثة:**

            ```Console
            ModernPOS.EpsonFP90III.Installer.exe install --verbosity 0
            ```

1. تثبيت ملحقات محطة الأجهزة:

    1. في مجلد **EpsonFP90IIISample\\HardwareStation\\HardwareStation.EpsonFP90III.Installer\\bin\\Debug\\net461**، ابحث عن مثبت **HardwareStation.EpsonFP90III.Installer**.
    1. أبدا بتشغيل مثبت الملحق من سطر الأوامر:

        ```Console
        HardwareStation.EpsonFP90III.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>بيئة الإنتاج

اتبع الخطوات الواردة في [إعداد تدفق البناء لنموذج تكامل مالي](fiscal-integration-sample-build-pipeline.md) لإنشاء وإصدار وحده مقياس السحابة وحزم الخدمة الذاتية القابلة للنشر لنموذج التكامل المالي. يمكن العثور على ملف YAML لقالب **EpsonFP90III build-pipeline.yml** في مجلد **Pipeline\\YAML_Files** الخاص بمستودع [حلول Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions).

## <a name="design-of-extensions"></a>تصميم الملحقات

تعتمد عينة تكامل الطابعة المالية لإيطاليا على [وظيفة التكامل المالي](fiscal-integration-for-retail-channel.md) وهي جزء من Retail SDK. النموذج موجود في مجلد **src\\FiscalIntegration\\EpsonFP90IIISample** لمستودع [حلول Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (على سبيل المثال، [النموذج في إصدار/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/EpsonFP90IIISample)). يتكون [النموذج](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices) من موفر المستند المالي، وهو ملحق لـ (CRT)، والموصل المالي، وهو ملحق لمحطة أجهزة Commerce. لمزيد من المعلومات حول كيفيه استخدام Retail SDK، راجع [هندسة Retail SDK](../dev-itpro/retail-sdk/retail-sdk-overview.md)و[قم بإعداد تدفق البناء لمجموعة SDK المستقلة](../dev-itpro/build-pipeline.md).

> [!WARNING]
> وبسبب قيود [التعبئة المستقلة الجديدة ونموذج التوسيع](../dev-itpro/build-pipeline.md)، لا يمكن استخدامها حاليًا لنموذج التكامل المالي هذا. يجب استخدام الإصدار السابق من Retail SDK على الجهاز الظاهري (VM) للمطور في LCS. لمزيد من المعلومات، راجع [إرشادات التوزيع الخاصة بنموذج تكامل الطابعة المالي لإيطاليا (قديم)](emea-ita-fpi-sample-sdk.md). يتم تخطيط الدعم الخاص بالتعبئة المستقلة الجديدة ونموذج الملحق الخاص بنماذج التكامل المالي للإصدارات اللاحقة.

### <a name="commerce-runtime-extension-design"></a>تصميم ملحق Commerce Runtime

الغرض من الملحق الذي يمثل موفر المستندات المالية هو إنشاء مستندات خاصة بالطابعة والتعامل مع الاستجابات من الطابعة المالية.

#### <a name="request-handler"></a>معالج الطلب

إن معالج طلب **DocumentProviderEpsonFP90III** هو نقطه الإدخال الخاصة بالطلب لإنشاء مستندات من الطابعة المالية.

المعالج موروث من واجهة **INamedRequestHandler**. طريقة **HandlerName** مسؤولة عن إرجاع اسم المعالج. يجب أن يتطابق اسم المعالج مع اسم موفر مستند الموصل المحدد في مقر Commerce الرئيسي.

يدعم الموصل الطلبات التالية:

- **GetFiscalDocumentDocumentProviderRequest** – يحتوي هذا الطلب على معلومات حول المستند الذي يجب إنشاؤه. تقوم بإرجاع مستند خاص بالطابعة يجب تسجيله في الطابعة المالية.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – يعيد هذا الطلب قائمة الأحداث للاشتراك فيها. حاليًا، يتم دعم الأحداث التالية: المبيعات وطباعة تقرير X وطباعة تقرير Z.

#### <a name="configuration"></a>تكوين

يوجد ملف التكوين لموفر المستند المالي في **src\\FiscalIntegration\\EpsonFP90IIISample\\CommerceRuntime\\DocumentProvider.EpsonFP90IIISample\\Configuration\\DocumentProviderEpsonFP90IIISample.xml** في مستودع [حلول Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). الغرض من الملف هو تمكين إعدادات موفر المستندات ليتم تكوينها من مقر Commerce الرئيسي. يتوافق تنسيق الملف مع متطلبات تكوين التكامل المالي.

### <a name="hardware-station-extension-design"></a>تصميم ملحقات محطة الأجهزة

الغرض من الملحق الذي يمثل رابطًا ماليًا هو الاتصال بالطابعة المالية. يستخدم هذا الملحق بروتوكول HTTP لإرسال المستندات التي ينشئها ملحق CRT للطابعة المالية. كما أنه يتعامل مع الاستجابات التي يتم تلقيها من الطابعة المالية.

#### <a name="request-handler"></a>معالج الطلب

معالج طلب **EpsonFP90IIISample** هو نقطه الإدخال لمعالجه الطلب إلى جهاز الاجهزه الطرفية المالية.

المعالج موروث من واجهة **INamedRequestHandler**. طريقة **HandlerName** مسؤولة عن إرجاع اسم المعالج. يجب أن يتطابق اسم المعالج مع اسم الموصل المالي المحدد في مقر Commerce الرئيسي.

يدعم الموصل الطلبات التالية:

- **SubmitDocumentFiscalDeviceRequest** – يرسل هذا الطلب المستندات إلى الطابعات ويعيد الاستجابة من الطابعة المالية.
- **IsReadyFiscalDeviceRequest** – يستخدم هذا الطلب لإجراء فحص سلامة الجهاز.
- **InitializeFiscalDeviceRequest** – يستخدم هذا الطلب لتهيئة الطابعة.

#### <a name="configuration"></a>تكوين

يوجد ملف التكوين للموصل المالي في **src\\FiscalIntegration\\EpsonFP90IIISample\\HardwareStation\\EpsonFP90IIIFiscalDeviceSample\\Configuration\\ConnectorEpsonFP90IIISample.xml** في مستودع [حلول Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). الغرض من الملف هو تمكين إعدادات الموصل ليتم تكوينه من مقر Commerce الرئيسي. يتوافق تنسيق الملف مع متطلبات تكوين التكامل المالي.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]