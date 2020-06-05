---
title: إعداد التكامل المالي لقنوات Commerce
description: يوفر هذا الموضوع إرشادات لإعداد وظيفة التكامل المالي لقنوات Commerce.
author: josaw
manager: annbe
ms.date: 02/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: v-kikozl
ms.search.validFrom: 2018-11-1
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: b221bfede5d1db8d7970e1efede85e8dba7fe017
ms.sourcegitcommit: 1d5a4f70a931e78b06811add97c1962e8d93689b
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/13/2020
ms.locfileid: "3124372"
---
# <a name="set-up-the-fiscal-integration-for-commerce-channels"></a>إعداد التكامل المالي لقنوات Commerce

[!include [banner](../includes/banner.md)]

## <a name="introduction"></a>مقدمة

يوفر هذا الموضوع إرشادات لإعداد وظيفة التكامل المالي لقنوات Commerce. للحصول على مزيد من المعلومات حول التكامل المالي، راجع [نظرة عامة على التكامل المالي لقنوات Commerce](fiscal-integration-for-retail-channel.md).

تتضمن عملية إعداد التكامل المالي المهام التالية:

1. تكوين الموصلات المالية التي تمثل أجهزة أو خدمات مالية يتم استخدامها لأغراض التسجيل المالي، مثل طابعات الضرائب المحصلة .
2. تكوين موفري المستندات الذين يعملون على إنشاء المستندات المالية التي سيتم تسجيلها في الأجهزة أو الخدمات المالية بواسطة الموصلات المالية.
3. تكوين عملية التسجيل المالي التي تحدد يعرف تسلسل خطوات التسجيل المالي والموصلات المالية وموفري المستندات المالية المستخدمة لكل خطوة.
4. تعيين عملية التسجيل المالي إلى ملفات وظائف نقطة البيع.
5. تعيين ملفات التعريف التقنية للموصلات إلى ملفات تعريف الأجهزة.

## <a name="set-up-a-fiscal-registration-process"></a>إعداد عملية التسجيل المالي

قبل استخدام وظيفة التكامل المالي، يجب تكوين الإعدادات التالية.

1. يمكنك تحديث محددات Commerce.

    1. في صفحة **معلمات Commerce المشتركة‬**، على علامة التبويب **عام**، عيّن الخيار **تمكين التكامل المالي** إلى **نعم**. على علامة التبويب **التسلسلات الرقمية‬‬**، حدد التسلسلات الرقمية‬ للمراجع التالية:

        - رقم ملف التعريف التقني المالي
        - رقم مجموعة الموصل المالي
        - رقم عملية التسجيل

    2. في صفحة **معلمات Commerce‬**، حدد التسلسل الرقمي لرقم ملف تعريف الوظائف المالية.

    > [!NOTE]
    > التسلسلات الرقمية اختيارية. يمكن إنشاء أرقام كافة الكيانات التكامل المالي من التسلسلات الرقمية أو يدويًا.

2. تحميل تكوينات الموصلات المالية وموفري المستندات المالية.

    يعتبر موفر المستندات المالية مسؤولاً عن إنشاء المستندات المالية التي تمثل أحداث وحركات والأحداث المسجلة في نقطة البيع بتنسيق يُستخدم أيضًا للتفاعل مع جهاز أو خدمة مالية. على سبيل المثال، بإمكان موفر المستندات المالية إنشاء تمثيل لإيصال مالي بتنسيق XML.

    يعتبر الموصل المالي مسؤولاً عن الاتصال بجهاز مالي أو خدمة مالية. على سبيل المثال، بإمكان الموصل المالي إرسال إيصال مالي أنشأه موفر المستندات المالية بتنسيق XML إلى طابعة الضرائب المحصلة. لمزيد من التفاصيل حول مكونات التكامل المالي، راجع [عملية التسجيل المالي ونماذج التكامل المالي للأجهزة المالية](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices).

    1. في صفحة **الموصلات المالية** (**البيع بالتجزئة والتجارة \> إعداد القناة \> التكامل المالي \> الموصلات المالية**)، قم بتحميل تكوين XML لكل جهاز أو خدمة تخطط لاستخدامها لأغراض تتعلق بالتكامل المالي.

        > [!TIP]
        > عن طريق تحديد **عرض**، يمكنك عرض كافة ملفات التعريف الوظيفية والتقنية التي ترتبط بالموصل المالي الحالي.

    2. في صفحة **موفرو المستندات المالية** (**البيع بالتجزئة والتجارة \> إعداد القناة \> التكامل المالي \> موفرو المستندات المالية**)، قم بتحميل تكوين XML لكل جهاز أو خدمة تخطط لاستخدامها لأغراض تتعلق بالتكامل المالي.

        > [!TIP]
        > عن طريق تحديد **عرض**، يمكنك عرض كافة ملفات التعريف الوظيفية والتقنية التي ترتبط بموفر المستندات المالية الحالي.

    للحصول على أمثلة حول تكوينات الموصلات المالية وموفري المستندات المالية، راجع [نماذج التكامل المالي في Retail SDK‬](fiscal-integration-for-retail-channel.md#fiscal-integration-samples-in-the-retail-sdk).

    > [!NOTE]
    > يعتبر تعيين البيانات جزءًا من موفر المستندات المالية. لإعداد تعيينات بيانات مختلفة للموصل نفسه (على سبيل المثال، القواعد الخاصة بالولاية)، يجب عليك إنشاء موفرين مختلفين للمستندات المالية.

3. إنشاء ملفات تعريف وظيفية وملفات تعريف تقنية للموصلات‬‏‎.

    1. في صفحة **ملفات التعريف الوظيفية للموصلات‬** (**البيع بالتجزئة والتجارة \> إعداد القناة \> التكامل المالي \> ملفات التعريف الوظيفية للموصلات**)، أنشئ ملف تعريف وظيفيًا لكل مجموعة مكونة من موصل مالي وموفر مستندات مالية مرتبطة بهذا الموصل المالي.

        1. حدد اسم موصل.
        2. حدد موفر المستندات.

        يمكنك تغيير معلمات تعيين البيانات في ملف التعريف الوظيفي للموصل. لاستعادة المعلمات الافتراضية التي تم تعريفها في تكوين موفر المستندات المالية، حدد **تحديث**.

        **أمثلة**

        |   | التنسيق | مثال |
        |---|--------|---------|
        | **إعدادات معدلات ضريبة القيمة المضافة** | القيمة: VATrate | 1 : 2000, 2 : 1800 |
        | **تعيين أكواد ضريبة القيمة المضافة** | VATcode : القيمة | vat20 : 1, vat18 : 2 |
        | **تعيين أنواع طرق الدفع** | TenderType: قيمة | النقد : 1، البطاقة : 2 |

        > [!NOTE]
        > تعتبر ملفات التعريف الوظيفية للموصلات خاصة بالشركة. إذا كنت تخطط لاستخدام المجموعة نفسها لموصل مالي وموفر مستندات مالية في شركات مختلفة، فيجب إنشاء ملف تعريف وظيفي للموصل لكل شركة.

    2. في صفحة **ملفات التعريف التقنية للموصلات‬** (**البيع بالتجزئة والتجارة \> إعداد القناة \> التكامل المالي \> ملفات التعريف التقنية للموصلات‬**)، أنشئ ملف تعريف تقنيًا للموصل لكل موصل مالي.

        1. حدد اسم موصل.
        2. حدد نوع موصل. بالنسبة إلى الأجهزة المتصلة بمحطة أجهزة، حدد **محلي**.

            > [!NOTE]
            > الموصلات المحلية هي وحدها المدعومة في الوقت الحالي.

        يمكن تغيير المعلمات على علامتي التبويب **الجهاز** و**الإعدادات** في ملف تعريف تقني للموصل. لاستعادة المعلمات الافتراضية التي تم تعريفها في تكوين الموصل المالي، حدد **تحديث**. بينما يتم تحميل إصدار جديد لتكوين XML، تتلقى رسالة تفيد بأن الموصل المالي الحالي أو موفر المستندات المالية الحالي قيد الاستخدام. لا يتجاوز هذا الإجراء التغييرات اليدوية التي تم إدخالها في وقت سابق على ملفات التعريف الوظيفية أو التقنية للموصلات. لتطبيق المجموعة الافتراضية للمعلمات من تكوين جديد، انقر فوق **تحديث** في صفحة **ملفات التعريف الوظيفية للموصلات‬** أو صفحة **ملفات التعريف التقنية للموصلات‬**.

4. أنشئ مجموعات موصلات مالية.

    تضم مجموعة الموصلات المالية ملفات التعريف الوظيفية للموصلات المالية التي تؤدي وظائف مماثلة وتُستخدم في الخطوة نفسها في عملية التسجيل المالي. على سبيل المثال، إذا كان استخدام نماذج متعددة لطابعات الضرائب المحصلة في متجر، فيمكن دمج الموصلات المالية لطابعات الضرائب المحصلة هذه في مجموعة موصلات مالية.

    1. في صفحة **مجموعة الموصلات المالية** (**البيع بالتجزئة والمتجر \> إعداد القناة \> التكامل المالي \> مجموعة الموصلات المالية**)، أنشئ مجموعة موصلات مالية جديدة.
    2. أضف ملفات تعريف وظيفية إلى مجموعة الموصلات. حدد **إضافة** في صفحة **ملفات التعريف الوظيفية** وحدد رقم ملف تعريف. ضمن مجموعة موصلات، يتوفر ملف تعريف وظيفي واحد لكل موصل مالي في مجموعة موصلات.
    3. لتعليق استخدام ملف التعريف الوظيفي، عيّن الخيار **تعطيل** إلى **نعم**. يؤثر هذا التغيير على مجموعة الموصلات الحالية فقط. يمكنك متابعة استخدام ملف التعريف الوظيفي نفسه في مجموعات موصلات أخرى.

5. إنشاء عملية تسجيل مالي.

    يتم تعريف عملية التسجيل بواسطة تسلسل خطوات التسجيل ومجموعة الموصلات المستخدمة لكل خطوة.

    1. في صفحة **عملية التسجيل المالي** (**البيع بالتجزئة والمتجر \> إعداد القناة \> التكامل المالي \> عمليات التسجيل المالي**)، أنشئ سجلاً جديدًا لكل عملية تسجيل مالي فريدة.
    2. إضافة خطوات التسجيل للعملية:

        1. حدد **إضافة**.
        2. حدد نوع موصل مالي.
        3. في حقل **رقم المجموعة**، حدد مجموعة الموصلات المالية المناسب.

6. تعيين كيانات عملية التسجيل المالي إلى ملفات تعريف نقطة البيع.

    1. في صفحة **ملفات تعريف وظائف نقطة البيع** (**البيع بالتجزئة والمتجر \> إعداد القناة \> إعداد نقطة البيع \> ملفات تعريف نقطة البيع \> ملفات تعريف الوظائف**)، عيّن عملية تسجيل مالي إلى ملف تعريف وظائف نقطة البيع. حدد **تحرير**، ثم، على علامة تبويب **عملية التسجيل المالي**، في حقل **رقم العملية**، حدد عملية.
    2. في صفحة **ملف تعريف أجهزة نقطة البيع** (**البيع بالتجزئة والمتجر \> إعداد القناة \> إعداد نقطة البيع \> ملفات تعريف نقطة البيع \> ملفات تعريف الأجهزة**)، عيّن ملفات التعريف التقنية للموصلات إلى ملف تعريف الأجهزة‏‎. حدد **تحرير**، وأضف سطرًا في علامة التبويب **الأجهزة الطرفية المالية‬**، ثم في حقل **رقم ملف التعريف**، حدد ملف تعريف تقنيًا للموصل.

    > [!NOTE]
    > يمكنك إضافة العديد من ملفات التعريف التقنية إلى ملف تعريف الأجهزة نفسه. ومع ذلك، يجب أن يتضمن ملف تعريف الأجهزة أو ملف تعريف وظائف نقطة البيع تقاطعًا واحدًا فقط مع أي مجموعة موصلات مالية.

    يتحدد سير عمل التسجيل المالي بواسطة عملية التسجيل المالي وأيضًا بواسطة بعض معلمات مكونات التكامل المالي: ملحق وقت التشغيل التجاري لموفر المستندات المالية وملحق محطة الأجهزة للموصل المالي.

    - يتم تعريف اشتراك الأحداث والحركات في التسجيل المالي بواسطة موفر المستندات المالية بشكل مسبق.
    - يتحمل موفر المستندات المالية أيضًا مسؤولية تعريف الموصل المالي المستخدم لعملية التسجيل المالي. وهو يعمل على مطابقة ملفات التعريف الوظيفية للموصلات المضمنة في مجموعة الموصلات المالية المحددة للخطوة الحالية في عملية التسجيل المالي مع ملف التعريف التقني للموصل المعيّن إلى ملف تعريف الأجهزة في محطة الأجهزة التي تقترن بها نقطة البيع.
    - يستخدم موفر المستندات المالية إعدادات تعيين البيانات من تكوين موفر المستندات المالي لتحويل بيانات الحركة/الحدث مثل الضرائب والدفعات بينما يتم إنشاء مستند مالي.
    - عندما ينشئ موفر المستندات المالية مستندًا ماليًا، بإمكان الموصل المالي إرساله إلى الجهاز المالي كما هو، أو تحليله وتحويله إلى تسلسل أوامر لواجهة برمجة التطبيقات في الجهاز، بحسب التعامل مع الاتصال.

7. في صفحة **عملية التسجيل المالي** (**البيع بالتجزئة والمتجر \> إعداد القناة \> التكامل المالي \> عمليات التسجيل المالي**)، حدد **التحقق من الصحة** للتحقق من صحة عملية تسجيل المالي.

    من المستحسن تشغيل عملية تحقق من الصحة من هذا النوع في الحالات التالية:

    - بعد استكمال جميع إعدادات عملية تسجيل جديدة، بما في ذلك عندما تعين عمليات التسجيل إلى ملفات تعريف وظائف نقطة البيع وملفات تعريف الأجهزة.
    - بعد إدخال تغييرات على عملية تسجيل مالي موجودة، وقد تتسبب هذه التغييرات في تحديد موصل مالي مختلف في وقت التشغيل (على سبيل المثال، إذا قمت بتغيير مجموعة الموصلات لخطوة معينة في عميلة تسجيل مالي، يمكنك تمكين ملف تعريف وظيفي للموصل في مجموعة موصلات، أو إضافة ملف تعريف وظيفي جديد للموصل إلى مجموعة موصلات).
    - بعد إدخال تغييرات في تعيين ملفات التعريف التقنية للموصلات إلى ملفات تعريف الأجهزة.

8. في صفحة **جدول التوزيع**، شغّل المهمتين **1070** و**1090** لنقل البيانات إلى قاعدة بيانات القناة.

## <a name="set-up-fiscal-texts-for-discounts"></a>إعداد النصوص المالية للخصومات

في بعض الحالات، يجب طباعة نص خاص على إيصال مالي عند تطبيق خصم. يمكنك إعداد النصوص المالية للخصومات في صفحة **مجموعة الموصلات المالية** (**البيع بالتجزئة والتجارة \> إعداد القناة \> التكامل المالي \> مجموعة الموصلات المالية**).

- بالنسبة إلى الخصومات اليدوية المطبقة على نقطة البيع، يمكنك تكوين نص مالي لكود المعلومات أو مجموعة أكواد المعلومات المحدد في كود المعلومات **خصم المنتج** في ملف تعريف وظائف نقطة البيع.

    1. في صفحة **مجموعة الموصلات المالية**، حدد **نص للإيصال المالي**.
    2. في صفحة **أكواد المعلومات**، حدد **إضافة**، وحدد كود معلومات أو مجموعة أكواد معلومات.
    3. في **كود المعلومات**، حدد قيمة.
    4. في الحقل **رقم الكود الفرعي‬**، حدد قيمة إذا كان الكود الفرعي مطلوبًا لكود المعلومات المحدد.
    5. في حقل **نص الإيصال المالي**، حدد نصًا ماليًا يجب طباعته على إيصال مالي.
    6. عيّن الخيار **طباعة إدخال المستخدم على الإيصال المالي** إلى **نعم** لتجاوز النص الموجود على إيصال مالي بالمعلومات التي يدخلها المستخدم يدويًا في نقطة البيع. ينطبق هذا الخيار فقط على أكواد المعلومات التي تحتوي على إدخال من نوع **النص**.

    > [!NOTE]
    > يمكنك تحديد نص مالي لعدة أكواد معلومات لدعم السيناريوهات التي يتم فيها استخدام مجموعات أكواد معلومات وأكواد معلومات مرتبطة وأكواد معلومات تم تشغيلها. في هذه السيناريوهات، سوف يحتوي الإيصال المالي على النصوص المالية من جميع أكواد المعلومات المرتبطة ببند الحركة حيث تم تطبيق الخصم.

- بالنسبة إلى الخصومات الخاصة بالقناة، يجب تحديد نص مالي لمعرّف الخصم.

    1. في صفحة **مجموعة الموصلات المالية**، حدد **نص للإيصال المالي**.
    2. على علامة تبويب **الخصومات**، حدد **إضافة**، وحدد معرّف خصم.
    3. في حقل **نص الإيصال المالي**، حدد نصًا ماليًا يجب طباعته على إيصال مالي.

    > [!NOTE]
    > إذا تم تطبيق خصومات متعددة على بند الحركة نفسه، فسيحتوي الإيصال المالي على نصوص مالية من جميع الخصومات المرتبطة ببند الحركة هذا.

## <a name="set-error-handling-settings"></a>تعيين إعدادات معالجة الأخطاء‬

يتم تعيين خيارات معالجة الأخطاء المتوفرة في التكامل المالي في عملية التسجيل المالية. للحصول على مزيد من المعلومات حول معالجة الأخطاء في التكامل المالي، راجع [معالجة الأخطاء](fiscal-integration-for-retail-channel.md#error-handling).

1. في صفحة **عملية التسجيل المالي** (**البيع بالتجزئة والتجارة \> إعداد القناة \> التكامل المالي \> عمليات التسجيل المالي**)، يمكنك تعيين المعلمات التالية لكل خطوة في عملية التسجيل المالي.

    - **السماح بالتخطي‬** – هذه المعلمة تمكّن الخيار **تخطي** في مربع حوار معالجة الأخطاء.
    - **السماح بوضع علامة كمسجل** – تمكّن هذه المعلمة الخيار **وضع علامة كمسجل** في مربع حوار معالجة الأخطاء.
    - **المتابعة مع وجود الخطأ‬** - إذا تم تمكين هذه المعلمة، فبإمكان عملية التسجيل المالي المتابعة على سجل نقطة البيع إذا فشل التسجيل المالي لحركة أو حدث. وبخلاف ذلك، لتشغيل التسجيل المالي للحركة التالية أو الحدث التالي، يجب على المشغّل إعادة تجربة التسجيل المالي الفاشل أو تخطيه أو وضع علامة على الحركة أو الحدث كمسجل. للحصول على مزيد من المعلومات، راجع [التسجيل المالي الاختياري](fiscal-integration-for-retail-channel.md#optional-fiscal-registration).

    > [!NOTE]
    > إذا تم تمكين المعلمة **المتابعة مع وجود الخطأ**، فسيتم تعطيل المعلمتين **السماح بالتخطي** و**السماح بوضع علامة كمسجل‬‏‫** بشكل تلقائي.

2. يحتاج الخياران **تخطي** و**وضع علامة كمسجل** في مربع حوار معالجة الأخطاء إلى الإذن **السماح بتخطي التسجيل أو وضع علامة كمسجل**. وبالتالي، في الصفحة **مجموعات الأذونات** (**البيع بالتجزئة والتجارة \> الموظفون \> مجموعات الأذونات**)، يمكنك تمكين الإذن **السماح بتخطي التسجيل أو وضع علامة كمسجل**.
3. يسمح الخياران **تخطي** و**وضع علامة كمسجل** للعاملين بإدخال معلومات إضافية عند فشل التسجيل المالي. لإتاحة هذه الوظيفة، يجب تحديد أكواد معلومات **تخطي** و**وضع علامة كمسجل** على مجموعة موصلات مالية. يتم عندئذٍ حفظ المعلومات التي قام العاملون بإدخالها كحركة أكواد معلومات مرتبطة بالحركة المالية. للحصول على مزيد من التفاصيل حول أكواد المعلومات، راجع [أكواد المعلومات وأكواد مجموعات المعلومات‬](../info-codes-retail.md).

    > [!NOTE]
    > لم تعد وظيفة المشغل **المنتج** مدعومة لأكواد المعلومات المستخدمة للخيارين **تخطي** و**وضع علامة كمسجل** في مجموعات الموصلات المالية.

    - في صفحة **مجموعة الموصلات المالية**، على علامة التبويب **أكواد المعلومات**، حدد أكواد المعلومات أو مجموعات أكواد المعلومات في الحقلين **تخطي** و**وضع علامة كمسجل**.

    > [!NOTE]
    > يمكن إنشاء مستند مالي ومستند آخر غير مالي في أي خطوة في عملية التسجيل المالي. يحدد ملحق موفر المستندات المالية كل نوع من حركة أو حدث يرتبط بالمستندات المالية أو غير المالية. وتنطبق ميزة معالجة الأخطاء على المستندات المالية فقط.
    >
    > - **مستند مالي** - مستند إلزامي يجب تسجيله بنجاح (على سبيل المثال، إيصال مالي).
    > - **مستند غير مالي** - مستند مكمّل للحركة أو الحدث (على سبيل المثال، قسيمة بطاقة هدايا).

4. إذا كان من الضروري أن يكون المشغّل قادرًا على متابعة معالجة العملية الحالية (على سبيل المثال، إنشاء حركة أو إنجازها) بعد حدوث خطأ في فحص الصحة، يجب تمكين الإذن **السماح بتخطي خطأ فحص الصحة** في صفحة **مجموعات الأذونات** (**البيع بالتجزئة والتجارة \> الموظفون \> مجموعات الأذونات‏‎**). للحصول على مزيد من المعلومات حول إجراء فحص الصحة، راجع [فحص صحة التسجيل المالي](fiscal-integration-for-retail-channel.md#fiscal-registration-health-check).

## <a name="set-up-fiscal-xz-reports-from-the-pos"></a>إعداد التقارير المالية X/Z من نقطة البيع

لتمكين تشغيل التقارير المالية X/Z من نقطة البيع، يجب إضافة أزرار جديدة إلى تخطيط نقطة البيع.

- في صفحة **شبكات الأزرار**، اتبع الإرشادات في [إضافة عمليات نقطة البيع إلى مخططات نقطة البيع باستخدام مصمم شبكة الأزرار](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters) لتثبيت المصمم وتحديث تخطيط نقطة البيع.

    1. حدد التخطيط الذي تريد تحديثه. 
    2. أضف زرًا جديدًا، وعيّن خاصية الزر **طباعة X المالي**.
    3. أضف زرًا جديدًا، وعيّن خاصية الزر **طباعة Z المالي**.
    4. في صفحة **مجدول التوزيع**، شغّل المهمة **1090** لنقل التغييرات إلى قاعدة بيانات القناة.

## <a name="enable-manual-execution-of-postponed-fiscal-registration"></a>تمكين التنفيذ اليدوي للتسجيل المالي المؤجل

لتمكين التنفيذ اليدوي لتسجيل مالي مؤجل، يجب إضافة زر جديد إلى مخطط نقطة البيع.

- في صفحة **شبكات الأزرار**، اتبع الإرشادات في [إضافة عمليات نقطة البيع إلى مخططات نقطة البيع باستخدام مصمم شبكة الأزرار](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters) لتثبيت المصمم وتحديث تخطيط نقطة البيع.

    1. حدد التخطيط الذي تريد تحديثه.
    2. أضف زرًا جديدًا، وعيّن خاصية الزر **إكمال عملية التسجيل المالي**.
    3. في صفحة **جدول التوزيع**، شغّل المهمة **1090** لنقل التغييرات إلى قاعدة بيانات القناة.