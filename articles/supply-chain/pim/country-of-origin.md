---
title: بلد المنشأ
description: تصدر العديد من المؤسسات شهادات إلى الموردين الخاصين بهم لضمان أن المنتجات تفي بمعايير الشهادة المحددة. وغالبًا ما تعتمد هذه الشهادات على بلد المنشأ. يوفر هذا الموضوع معلومات حول الميزة "بلد المنشأ"، والتي تتيح لك ربط منتج ببلد المنشأ الخاص به وتعقب شهادات المنتج الخاصة به.
author: dasani-madipalli
manager: tfehr
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: COOVendorCerts
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 0471785991a307de11147e9773d9abe1e02941d6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 10/13/2020
ms.locfileid: "4421032"
---
# <a name="country-of-origin"></a>بلد المنشأ

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

تصدر العديد من المؤسسات شهادات إلى الموردين الخاصين بهم لضمان أن المنتجات تفي بمعايير الشهادة المحددة. وغالبًا ما تعتمد هذه الشهادات على بلد المنشأ. تتيح لك ميزة "بلد المنشأ" ربط منتج ببلد المنشأ الخاص به وتعقب شهادات المنتج الخاصة به.

## <a name="turn-on-the-country-of-origin-feature"></a>تشغيل ميزة بلد المنشأ

قبل أن تتمكن من استخدام هذه الميزة، يجب تشغيلها في النظام. بإمكان المسؤولين استخدام إعدادات [دارة الميزات](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) للتحقق من حالة الميزة وتشغيلها. في مساحة عمل **إدارة الميزات**، تكون هذه الميزة مدرجة بالطريقة التالية:

- **الوحدة النمطية** *إدارة معلومات المنتج*
- **اسم الميزة:** *ميزة إدارة بلد المنشأ*

## <a name="configure-source-and-destination-countries"></a>تكوين البلدان المصدر والوجهة

قبل إصدار شهادة لمنتج ما، يجب ربط المنتج بالبلد الوجهة الخاصة به وبلده الأصلي.

1. الانتقال إلى **إدارة معلومات المنتج \>إعداد \>توافق المنتجات \> بلد المنشأ \> قواعد بلد المنشأ**.
2. حدد إعداد بلد موجود لتحريره، أو حدد **جديد** في جزء الإجراءات لإنشاء إعداد بلد جديد.
3. عيِّن القيم التالية للبلد المحدد أو البلد الجديد.

    | الحقل | ‏‏الوصف |
    |---|---|
    | رقم العنصر | أدخل عدد أصناف المنتج. |
    | بلد الوجهة | حدد البلد الذي تقوم بإرسال المنتج إليه. |
    | بلد المنشأ | حدد البلد الذي تقوم بإرسال المنتج منه. |

والغرض من هذا الإعداد هو مساعدتك في إنشاء تقرير شجره المواد (BOM) حيث يمكنك تضمين البلد الخاص بالأصل لكل جزء من الأجزاء التي يتم تحديد المصدر والوجهة لها. يساعدك هذا التقرير في الحصول على صوره شاملة للمكان الذي تأتي إليه الأجزاء والمكان التي سيتم نقلها إليه.

## <a name="keep-track-of-vendor-certificates"></a>تتبع شهادات الموردين

يمكنك استخدام الصفحة **شهادات الموردين للبلد المنشأ** لتعقب الشهادات التي تصدرها إلى الموردين.

يجب تحديد مستندات الشهادة التي تقوم بإصدارها وكيف ستقوم بالإبلاغ عنها للعملاء. تساعدك هذه الميزة في متابعة تعقب الشهادات. كما تتيح لك إمكانية اختيار ما إذا كانت تظهر أرقام الشهادات ذات الصلة في الفواتير وكشوف التعبئة و/أو تأكيدات الأوامر.

لإعداد معلومات الشهادة‬، اتبع هذه الخطوات:

1. الانتقال إلى **إدارة معلومات المنتج \>إعداد \>توافق المنتجات \> بلد المنشأ \> شهادات الموردين لبلد المنشأ**.
2. حدد إعداد شهادة موجودة لتحريره، أو حدد **جديد** في جزء الإجراءات لإنشاء شهادة جديدة.
3. عيِّن الإعدادات التالية للشهادة المحددة أو الجديدة.

    | الحقل | ‏‏الوصف |
    |---|---|
    | حساب المورد | حدد المورد الذي قمت بإصدار الشهادة له. |
    | رقم العنصر | حدد البند الذي قمت بإصدار الشهادة له. |
    | البلد/المنطقة | البلد أو المنطقة الوجهة التي يجب استخدام هذه الشهادة فيها. |
    | رقم الشهادة | أدخل رقم تعريف الشهادة الذي قمت بإصداره. |
    | ساري المفعول | حدد التاريخ الأول لصلاحية الشهادة الحالية.|
    | انتهاء الصلاحية | حدد التاريخ الأخير لصلاحية الشهادة الحالية. |
    | الطباعة في فاتورة | حدد خانة الاختيار هذه لطباعة رقم الشهادة في الفواتير الموجهة إلى البلد المحدد أثناء نطاق التاريخ المحدد. |
    | الطباعة في إيصال تعبئة | حدد خانة الاختيار هذه لطباعة رقم الشهادة في إيصالات التعبئة الموجهة إلى البلد المحدد أثناء نطاق التاريخ المحدد. |
    | الطباعة في أمر مبيعات | حدد خانة الاختيار هذه لطباعة رقم الشهادة في أوامر المبيعات الموجهة إلى البلد المحدد أثناء نطاق التاريخ المحدد. |

## <a name="include-the-country-of-origin-on-bom-reports"></a>تضمين بلد المنشأ في تقارير قائمة مكونات الصنف

عند إنشاء تقرير شجرة مواد، يمكنك تضمين بلد المنشأ لكل جزء من الأجزاء التي قمت بتحديدها وبلدان الوجهة والخاصة بها في الصفحة **قواعد بلد المنشأ**.

1. انتقل إلى **إدارة معلومات المنتج‬ \> المنتجات \> المنتجات الصادرة**.
1. حدد منتجًا أو قم بإنشائه لفتح صفحة **تفاصيل المنتج الصادر** له.
1. في جزء الإجراءات، في علامة تبويب **المهندس** في مجموعة **قائمة مكونات الصنف‏‎‬**، حدد **المصمم**.
1. في صفحة القائمة التي تظهر، في جزء الإجراءات، حدد **قائمة مكونات الصنف \> طباعة**.
1. في مربع الحوار **بنود قائمة مكونات الصنف**، قم بتعيين حقل **البلد الوجهة** إلى البلد الوجهة التي ترغب في عرضها في التقرير.
1. حدد **موافق**.

ويتم إنشاء تقرير يعرض معلومات حول بلد المنشأ لكل جزء ويتم إظهاره. فيما يلي مثال التقرير.

![تقرير بلد المنشأ](media/country-of-origin-report.png "تقرير بلد المنشأ")