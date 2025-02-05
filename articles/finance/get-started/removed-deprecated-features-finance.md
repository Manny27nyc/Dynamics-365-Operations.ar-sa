---
title: ميزات تمت إزالتها أو إهمالها في Dynamics 365 Finance
description: توفر هذه المقالة الميزات التي تمت إزالتها أو تلك المخطط لإزالتها من Dynamics 365 Finance.
author: kfend
ms.date: 06/29/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2020-03-02
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 070c61df14db4d2538b129b01defd4b82db0b8a7
ms.sourcegitcommit: 9c637bcf4e2eb8f711290a861492f038feaf1568
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 09/09/2022
ms.locfileid: "9462291"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-finance"></a>ميزات تمت إزالتها أو إهمالها في Dynamics 365 Finance

[!include [banner](../includes/banner.md)]

توفر هذه المقالة الميزات التي تمت إزالتها أو تلك المخطط لإزالتها من Dynamics 365 Finance.

- لم تعد ميزة *تمت الإزالة* متوفرة في المنتج.
- لا توجد ميزة *المهملة* في التطوير النشط وقد يتم إزالتها في تحديثات مستقبلية.

تهدف هذه القائمة إلى مساعدتك في مراعاة ميزات الإزالة وعمليات الإهلاك للتخطيط الخاص بك. 

> [!NOTE]
> يمكن العثور على معلومات مفصلة حول الكائنات في تطبيقات التمويل والعمليات في [التقارير المرجعية التقنية](/dynamics/s-e/global/axtechrefrep_61). يمكنك مقارنة إصدارات مختلفة من هذه التقارير لمعرفة المزيد حول الكائنات التي تم تغييرها أو التي تمت إزالتها من كل إصدار من تطبيقات التمويل والعمليات.

## <a name="features-removed-or-deprecated-in-the-finance-10030-release"></a>ميزات تمت إزالتها أو إهمالها في الإصدار 10.0.30 من Finance

### <a name="revenue-recognition"></a>إقرار الإيرادات

[إقرار الإيرادات](../../finance/accounts-receivable/revenue-recognition-overview.md)

| &nbsp;  | &nbsp;  |
|---|---|
| **سبب الإهلاك/الإزالة** |تم استبداله بوظائف محسنه ، أو [فوتره اشتراك](../../finance/accounts-receivable/subscription-billing-summary.md)
| **هل تم الاستبدال بميزة أخرى؟**   | ‏‏نعم‬ |
| **مناطق المنتجات المتأثرة** | استمارة التقديم |
| **خيارات النشر** | ‏‏الكل‬ |
| **Status** | مهمله: بعد 2023 ابريل ، لن تتلقي وظيفة إقرار الإيرادات في Dynamics 365 Finance الدعم مع إصلاحات الأخطاء. سيطلب من العملاء استخدام الوظائف المحسنة ، وهي [فواتير الاشتراك](../../finance/accounts-receivable/subscription-billing-summary.md). في 2023 أكتوبر ، لن تكون ميزه التعرف علي الإيرادات متوفرة بعد الآن. سيُطلب من العملاء الانتقال إلى وظيفة فواتير الاشتراك المحسّنة. لميزه المجموعة كجزء من إقرار الإيراد، لا توجد وظيفة بديله مخططه في هذا الوقت.|

## <a name="features-removed-or-deprecated-in-the-finance-10029-release"></a>ميزات تمت إزالتها أو إهمالها في الإصدار 10.0.29 من Finance

### <a name="stock-transfer-orders-that-have-tax-on-the-transfer-price"></a>أوامر تحويل المخزون التي تخضع لضريبة على سعر التحويل

[أوامر تحويل المخزون التي تخضع لضريبة على سعر التحويل](../../finance/localizations/apac-ind-gst-stock-transfer-transactions.md)

| &nbsp;  | &nbsp;  |
|---|---|
| **سبب الإهلاك/الإزالة** | تم استبداله بوظائف محسنه ، وهي [أوامر تحويل المخزون للهند.](../../finance/localizations/apac-ind-stock-transfer.md)|
| **هل تم الاستبدال بميزة أخرى؟**   | ‏‏نعم‬ |
| **مناطق المنتجات المتأثرة** | استمارة التقديم |
| **خيارات النشر** | ‏‏الكل‬ |
| **Status** | مهمل: بعد 2023 ابريل ، **لن تتلقي أوامر تحويل المخزون التي تحتوي علي ضريبة في وظيفة سعر** التحويل بعد الآن استقبال الدعم مع إصلاحات الأخطاء وإصلاحات الأمان. سيطلب من العملاء استخدام الوظائف المحسنة ، وهي [أوامر تحويل المخزون للهند](../../finance/localizations/apac-ind-stock-transfer.md). بعد 2023 أكتوبر ، لن تكون أوامر تحويل المخزون **التي تحتوي علي ضريبة في وظيفة سعر** التحويل متوفرة ، ستتم مطالبه العملاء بالانتقال إلى الوظيفة المحسنة. |

### <a name="bank-statement-import-and-export-of-positive-pay-file"></a>استيراد كشف حساب البنك وتصديره لملف الدفع الموجب

| &nbsp;  | &nbsp;  |
|---|---|
| **سبب الإهلاك/الإزالة** |ويتم استبدالها بوظائف محسنه ، واستيراد كشوف الحسابات البنكية وتصدير ملفات الدفع الايجابيه.| 
| **هل تم الاستبدال بميزة أخرى؟**   | ‏‏نعم‬ |
| **مناطق المنتجات المتأثرة**         | استمارة التقديم |
| **خيارات النشر**              | ‏‏الكل‬ |
| **Status**                         | تم إهماله: لن تتلقي وظيفة XSLT لاستيراد الملفات وتصديرها الدعم مع إصلاحات الأخطاء وإصلاحات الأمان. سيُطلب من العملاء استخدام الوظيفة المحسّنة: [قم بإعداد ملفات الدفع الإيجابية باستخدام التقارير الإلكترونية](../../finance/accounts-payable/set-up-positive-pay-er.md) و [قم بإعداد استيراد التسوية البنكية المتقدمة باستخدام التقارير الإلكترونية](../../finance/accounts-payable/import-bai2-er.md). بعد 2022 سبتمبر ، لن تعود وظيفة XSLT متاحه ، سيطلب من العملاء الانتقال إلى الوظيفة المحسنة.|


## <a name="features-removed-or-deprecated-in-the-finance-10026-release"></a>ميزات تمت إزالتها أو إهمالها في الإصدار 10.0.26 من Finance

### <a name="sales-tax-report-for-finland-design-based-on-reporting-codes"></a>تقرير ضريبة المبيعات لفنلندا (تصميم يستند إلى أكواد التقارير)

[تقرير ضريبة المبيعات لفنلندا](../localizations/emea-fin-sales-tax-payment-report-finland.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **سبب الإهلاك/الإزالة** | تم استبداله بتصميم إقرار ضريبة القيمة المضافة الجديد، [إقرار ضريبة القيمة المضافة لفنلندا](../localizations/emea-fin-vat-declaration.md) |
| **هل تم الاستبدال بميزة أخرى؟**   | ‏‏نعم‬ |
| **مناطق المنتجات المتأثرة**         | استمارة التقديم |
| **خيارات النشر**              | ‏‏الكل‬ |
| **Status**                         | مهمل: بحلول 1 مارس 2023، إننا لن نقوم بدعم تقرير ضريبة المبيعات لفنلندا (تخطيط التقرير الفنلندي) الآن. يتم تقديم تنسيقات التقارير الإلكترونية (ER) **إقرار TXT لضريبة القيمة المضافة (FI**) و **إقرار ضريبة القيمة المضافة Excel (FI)** الجديدة ضمن نموذج **إقرار الضريبة**. |

## <a name="features-removed-or-deprecated-in-the-finance-10024-release"></a>ميزات تمت إزالتها أو إهمالها في الإصدار 10.0.24 من Finance

### <a name="sales-tax-report-for-sweden-design-based-on-reporting-codes"></a>تقرير ضريبة المبيعات للسويد (تصميم يستند إلى أكواد التقارير)

[تقرير ضريبة المبيعات للسويد](../localizations/emea-swe-sales-tax-payment-report-sweden.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **سبب الإهلاك/الإزالة** | تم استبداله بتصميم إقرار ضريبة القيمة المضافة الجديد، [إقرار ضريبة القيمة المضافة للسويد](../localizations/emea-swe-vat-declaration-sweden.md) |
| **هل تم الاستبدال بميزة أخرى؟**   | ‏‏نعم‬ |
| **مناطق المنتجات المتأثرة**         | استمارة التقديم |
| **خيارات النشر**              | ‏‏الكل‬ |
| **Status**                         | مهمل: بحلول 1 ديسمبر 2022، إننا لن نقوم بدعم تقرير ضريبة المبيعات للسويد (تخطيط تقرير سويدي) الآن. يتم تقديم تنسيقات التقارير الإلكترونية (ER) **إقرار XML لضريبة القيمة المضافة (SE**) و **إقرار ضريبة القيمة المضافة Excel (SE)** الجديدة ضمن نموذج **إقرار الضريبة**. |

### <a name="vat-statement-for-austria-design-based-on-reporting-codes"></a>كشف ضريبة القيمة المضافة للنمسا (تصميم يستند إلى أكواد التقارير)

[تفاصيل كشف ضريبة القيمة المضافة للنمسا](../localizations/emea-aut-vat-statement-details.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **سبب الإهلاك/الإزالة** | تم استبداله بتصميم إقرار ضريبة القيمة المضافة الجديد، [إقرار ضريبة القيمة المضافة للنمسا](../localizations/emea-aut-vat-declaration-austria.md) |
| **هل تم الاستبدال بميزة أخرى؟**   | ‏‏نعم‬ |
| **مناطق المنتجات المتأثرة**         | استمارة التقديم |
| **خيارات النشر**              | ‏‏الكل‬ |
| **Status**                         | ‏‫مهمل: بحلول 1 ديسمبر، 2021، لن نقوم بعد الآن بتقديم الدعم لتنسيق التقارير الإلكترونية (ER) **إقرار ضريبة القيمة المضافة (AT)** ضمن **نموذج إقرار ضريبة القيمة المضافة**. يتم تقديم تنسيقات التقارير الإلكترونية (ER) **إقرار XML لضريبة القيمة المضافة (AT)** و **إقرار ضريبة القيمة المضافة Excel (AT)** الجديدة ضمن نموذج **إقرار الضريبة**. |

### <a name="elster-declaration-for-germany-design-based-on-reporting-codes"></a>إقرار ELSTER لألمانيا (تصميم يستند إلى أكواد التقارير)

[كشف حساب ضريبة القيمة المضافة](../localizations/emea-de-vat-declaration.md)</br>
[إعداد إقرار الضريبة الإلكترونية لألمانيا](../../fin-ops-core/dev-itpro/analytics/tasks/setup-electronic-tax-declaration-germany.md)</br>
[الإرسال الإلكتروني لإقرار ضريبة القيمة المضافة (ELSTER)](../localizations/tasks/de-00003-electronic-transmission-elster.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **سبب الإهلاك/الإزالة** | تم استبداله بتصميم إقرار ضريبة القيمة المضافة الجديد، [إقرار ضريبة القيمة المضافة لألمانيا](../localizations/emea-deu-vat-declaration-germany.md) |
| **هل تم الاستبدال بميزة أخرى؟**   | ‏‏نعم‬ |
| **مناطق المنتجات المتأثرة**         | استمارة التقديم |
| **خيارات النشر**              | ‏‏الكل‬ |
| **Status**                         | ‏‫مهمل: بحلول 1 ديسمبر، 2021، لن نقوم بعد الآن بتقديم الدعم لتنسيقات التقارير الإلكترونية (ER) لـ **Elster (DE)** و **نموذج Elster**. يتم تقديم تنسيقات التقارير الإلكترونية (ER) **إقرار XML لضريبة القيمة المضافة (DE)** و **إقرار ضريبة القيمة المضافة Excel (DE)** الجديدة ضمن نموذج **إقرار الضريبة**. |

### <a name="ob-declaration-for-netherlands-design-based-on-reporting-codes"></a>إقرار OB لهولندا (تصميم يستند إلى أكواد التقارير)

[إقرار OB](../localizations/emea-nl-vat-declaration.md)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **سبب الإهلاك/الإزالة** | تم استبداله بتصميم إقرار ضريبة القيمة المضافة الجديد، [إقرار ضريبة القيمة المضافة لهولندا](../localizations/emea-nl-vat-declaration-netherlands.md) |
| **هل تم الاستبدال بميزة أخرى؟**   | ‏‏نعم‬ |
| **مناطق المنتجات المتأثرة**         | استمارة التقديم |
| **خيارات النشر**              | ‏‏الكل‬ |
| **Status**                         | ‏‫مهمل: بحلول 1 ديسمبر، 2021، لن نقوم بعد الآن بتقديم الدعم لتنسيق التقارير الإلكترونية (ER) **إقرار OB (NL)** و **نموذج إقرار OB**. يتم تقديم تنسيقات التقارير الإلكترونية (ER) **إقرار XML لضريبة القيمة المضافة (NL)** و **إقرار ضريبة القيمة المضافة Excel (NL)** الجديدة ضمن نموذج **إقرار الضريبة**. |

## <a name="features-removed-or-deprecated-in-the-finance-10020-release"></a>ميزات تمت إزالتها أو إهمالها في الإصدار 10.0.20 من Finance

### <a name="rtir-query-invoice-data-request-hu-electronic-reporting-er-format-configuration"></a>تكوين تنسيق إعداد التقارير الإلكترونية‬ (ER) لطلب بيانات فاتورة الاستعلام RTIR (HU)

| &nbsp; | &nbsp; |
|------------|--------------------|
| **سبب الإهلاك/الإزالة** | مستثنى من معالجه المراسلة الإلكترونية للتشغيل المتبادل مع نظام الفوترة المجري عبر الإنترنت |
| **هل تم الاستبدال بميزة أخرى؟**   | لا |
| **مناطق المنتجات المتأثرة**         | استمارة التقديم |
| **خيارات النشر**              | ‏‏الكل |
| **الحالة**                         | ميزة مهملة: بحلول 15 أبريل 2022، نخطط لوقف دعم تكوين تنسيق "طلب بيانات فاتورة الاستعلام RTIR‬. |

### <a name="french-fec-audit-file-electronic-reporting-er-format-for-france-under-german-audit-file-output-format"></a>تنسيق التقارير الإلكترونية (ER) لفرنسا "بملف تدقيق FEC الفرنسي" ضمن تنسيق ‏‫إخراج ملف المراجعة الألماني

| &nbsp; | &nbsp; |
|------------|--------------------|
| **سبب الإهلاك/الإزالة** | تم استبداله بتنسيق (FR) "ملف تدقيق FEC" جديد |
| **هل تم الاستبدال بميزة أخرى؟**   | نعم |
| **مناطق المنتجات المتأثرة**         | استمارة التقديم |
| **خيارات النشر**              | ‏‏الكل |
| **الحالة**                         | تم إهماله: بحلول 1 مايو، 2022، لن نساعدك على دعم تنسيق إعداد التقارير الإلكترونية (ER) "بملف مراجعة FEC الفرنسي لفرنسا ضمن تنسيق "إخراج ملف مراجعة. يتم تقديم تنسيق (FR) ملف مراجعة (FR) جديد لـ FEC بدلاً من ذلك ضمن "نموذج تصدير البيانات". |

## <a name="features-removed-or-deprecated-in-the-finance-10017-release"></a>ميزات تمت إزالتها أو إهمالها في الإصدار 10.0.17 من Finance

### <a name="lcs-repository-as-a-storage-option-for-electronic-reporting-configurations"></a>مستودع LCS كخيار تخزين لتكوينات التقارير الإلكترونية

| &nbsp; | &nbsp; |
|------------|--------------------|
| **سبب الإهلاك/الإزالة** | تم استبداله بالمستودع العمومي لـ Regulatory Configuration Service (RCS) الجديد |
| **هل تم الاستبدال بميزة أخرى؟**   | ‏‏نعم‬ |
| **مناطق المنتجات المتأثرة**         | منتجات Dynamics 365 Finance وإدارة سلسلة التوريد وProject Operations|
| **خيارات النشر**              | ‏‏الكل |
| **الحالة**                         | مهمل: بحلول 01 أبريل، 2022، نخطط لإيقاف الدعم لمستودع Microsoft Dynamics Lifecycle Services (LCS) باعتباره خيار تخزين لتكوين التقارير الإلكترونية (ER). سيتم نشر تكوينات Microsoft ER الجديدة لتنزيلها حصريًا من المستودع العمومي. يمكن الوصول إلى المستودع العمومي من منتجات Dynamics 365 وRCS. لمزيد من المعلومات، راجع [استيراد تكوينات التقارير الإلكترونية من RCS](../../fin-ops-core/dev-itpro/analytics/tasks/import-configuration-rcs.md) و [إهلاك تخزين Regulatory Configuration Service - Lifecycle Services](../localizations/rcs-lcs-repo-dep-faq.md). |

## <a name="features-removed-or-deprecated-in-the-finance-10016-release"></a>ميزات تمت إزالتها أو إهمالها في الإصدار 10.0.16 من Finance

### <a name="vat-declaration-cz-and-control-statement-export-cz-electronic-reporting-formats-for-czech-republic"></a>تنسيقات التقارير الإلكترونية "إقرار ضريبة القيمة المضافة (CZ)" و"تصدير كشف حساب المراقبة (CZ)" لجمهورية التشيك

| &nbsp; | &nbsp; |
|------------|--------------------|
| **سبب الإهلاك/الإزالة** | تم استبدالها بتنسيقات جديدة |
| **هل تم الاستبدال بميزة أخرى؟**   | نعم |
| **مناطق المنتجات المتأثرة**         | استمارة التقديم |
| **خيارات النشر**              | ‏‏الكل |
| **الحالة**                         | مهمل: بحلول 22 يناير، 2022 ، فإننا نخطط لم دعم تنسيقات التقارير الإلكترونية (ER) لـ "إقرار ضريبة القيمة المضافة (CZ)" أو "تصدير كشف حساب المراقبة (CZ)". يتم تقديم تنسيقات إقرار XML لضريبة القيمة المضافة (CZ) ، وإقرار XML لضريبة القيمة المضافة Excel (CZ) ، وكشف التحكم XML لضريبة القيمة المضافة (CZ) بدلا من ذلك تحت نموذج "إقرار الضريبة". |

### <a name="ledger-transaction-export-format-be-electronic-reporting-format-and-respective-ledger-transaction-export-be-model-for-belgium"></a>"تنسيق تصدير حركة دفتر الأستاذ (BE)" تنسيق التقارير الإلكترونية ونموذج تصدير حركة دفتر الأستاذ (BE) "الخاص ببلجيكا

| &nbsp; | &nbsp; |
|------------|--------------------|
| **سبب الإهلاك/الإزالة** | تم استبداله بتنسيق جديد للتقارير الإلكترونية ضمن النموذج "ملف مراجعة قياسي (SAF-T)".  |
| **هل تم الاستبدال بميزة أخرى؟**   | نعم |
| **مناطق المنتجات المتأثرة**         | استمارة التقديم |
| **خيارات النشر**              | ‏‏الكل |
| **الحالة**                         | مهمل: بحلول 1 ديسمبر، 2021، إننا نخطط إلى عدم دعم "تنسيق تصدير حركة دفتر الأستاذ (BE)" وتنسيق التقارير الإلكترونية (ER) والنموذج المعني "تصدير حركة دفتر الأستاذ (BE)". يتم تقديم تنسيق "تصدير بيانات دفتر الأستاذ العام (BE)" الجديد مع "تعيين نموذج بيانات دفتر الأستاذ العام" بدلاً من النموذج "ملف مراجعة قياسي (SAF-T)". |

### <a name="vat-100-report-for-the-united-kingdom-in-ssrs-format"></a>تقرير "ضريبة القيمة المضافة 100" للمملكة المتحدة بتنسيق SSRS.

| &nbsp; | &nbsp; |
|------------|--------------------|
| **سبب الإهلاك/الإزالة** | تم استبداله بتنسيق ER الجديد - تنسيق Excel لإقرار ضريبة القيمة المضافة (المملكة المتحدة)" ضمن "نموذج إقرار الضريبة".  |
| **هل تم الاستبدال بميزة أخرى؟**   | نعم |
| **مناطق المنتجات المتأثرة**         | استمارة التقديم |
| **خيارات النشر**              | ‏‏الكل |
| **الحالة**                         | مهمل: بحلول 1 ديسمبر، 2021، لن نقوم بعد الآن بتقديم الدعم لإصدار "تقرير ضريبة القيمة المضافة 100" بتنسيق SSRS. تم تقديم التنسيق الجديد " Excel لإقرار بضريبة القيمة المضافة (المملكة المتحدة) ضمن "نموذج إقرار الضريبة" في [ميزة ضريبة القيمة المضافة لرقمنة الضرائب MTD](../localizations/emea-gbr-mtd-vat-integration.md). |

## <a name="features-removed-or-deprecated-in-the-finance-10015-release"></a>ميزات تمت إزالتها أو إهمالها في الإصدار 10.0.15 من Finance

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>تم إهمال دعم Internet Explorer 11 لـ Dynamics 365

| &nbsp; | &nbsp; |
|------------|--------------------|
| **سبب الإهلاك/الإزالة** | اعتبارًا من ديسمبر 2020، تم إهمال دعم Microsoft Internet Explorer 11 لجميع منتجات Dynamics 365، ولن يتم دعم Internet Explorer 11 بعد أغسطس 2021.<br><br>سيؤثر هذا الاجراء علي العملاء الذين يستخدمون منتجات Dynamics 365 التي تم تصميمها ليتم استخدامها من خلال واجهة Internet Explorer 11. بعد أغسطس 2021، لن يتم دعم Internet Explorer 11 لمنتجات Dynamics 365. |
| **هل تم الاستبدال بميزة أخرى؟**   | نوصي العملاء بالانتقال إلى Microsoft Edge.|
| **مناطق المنتجات المتأثرة**         | كافة منتجات Dynamics 365 |
| **خيارات النشر**              | ‏‏الكل|
| **الحالة**                         | مهملة. لن يتم دعم Internet Explorer 11 بعد (أغسطس) 2021.|

## <a name="features-removed-or-deprecated-in-the-finance-10012-release"></a>ميزات تمت إزالتها أو إهمالها في الإصدار 10.0.12 من Finance

### <a name="not-deprecated-polish-ssrs-reports-sales-vat-register-purchase-vat-register-eu-summary-vat-register--feature-reference-pl-00014"></a>غير مهلكة: تقارير SSRS البولندية: سجل ضريبة القيمة المضافة للإخراج، سجل ضريبة القيمة المضافة للإدخال، سجل تقرير ملخص ضريبة القيمة المضافة للاتحاد الأوروبي‬، مرجع الميزة PL-00014

| &nbsp; | &nbsp; |
|------------|--------------------|
| **سبب الإهلاك/الإزالة** | غير مطلوبة من الناحية القانونية.  |
| **هل تم الاستبدال بميزة أخرى؟**   | نعم (تنسيق Excel لملف المراجعة القياسي مع إقرار ضريبة القيمة المضافة - JPK_VDEK) |
| **مناطق المنتجات المتأثرة**         | استمارة التقديم |
| **خيارات النشر**              | ‏‏الكل |
| **الحالة**                         | غير مهمل: اعتبارًا من 27 أبريل 2021، نخطط لمواصلة دعم تقارير SSRS: **سجل ضريبة القيمة المضافة على المبيعات، سجل ضريبة القيمة المضافة للشراء، ملخص الاتحاد الأوروبي لسجل ضريبة القيمة المضافة - مرجع الميزة PL-00014**. كما تم تقديم مثال تنسيق Excel لملف التدقيق القياسي مع إقرار ضريبة القيمة المضافة (JPK_VDEK). |

## <a name="features-removed-or-deprecated-in-the-finance-10011-release"></a>ميزات تمت إزالتها أو إهمالها في الإصدار 10.0.11 من Finance

### <a name="norwegian-standard-main-accounts"></a>الحسابات النرويجية الرئيسية القياسية

| &nbsp; | &nbsp; |
|------------|--------------------|
| **سبب الإهلاك/الإزالة** | إعادة التصميم  |
| **هل تم الاستبدال بميزة أخرى؟**   | نعم (تم استبداله بالمعلمات الخاصة بتطبيق تنسيق التقارير الإلكترونية) |
| **مناطق المنتجات المتأثرة**         | التطبيق |
| **خيارات النشر**              | ‏‏الكل |
| **الحالة**                         | ميزة مهملة: بحلول 1 ابريل 2021، نخطط لإيقاف دعم الوظيفة ذات الصلة بالحسابات الرئيسية القياسية: حقل المرجع، الجدول ذو الصلة، كيان البيانات. |

## <a name="features-removed-or-deprecated-in-the-finance-1007-release"></a>ميزات تمت إزالتها أو إهمالها في الإصدار 10.0.7 من Finance

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a>لم يعد مربع حوار تغيير طلب سير العمل يتضمن القائمة المنسدلة لتحديد المستخدم

| &nbsp; | &nbsp; |
|------------|--------------------|
| **سبب الإهلاك/الإزالة** | يتم تغييرها إلى الميزة مع تحديد مجموعات الحساب.  |
| **هل تم الاستبدال بميزة أخرى؟**   | ‏‏نعم |
| **مناطق المنتجات المتأثرة**         | سير العمل |
| **خيارات النشر**              | ‏‏الكل |
| **الحالة**                         | مهمل: بحلول 1 ديسمبر 2020، لا نقدم خطط لدعم إعداد أنواع الإيصالات الصينية دون تحديد مجموعات الحساب. يمكنك العثور على مزيد من التفاصيل حول التصميم الجديد في [ما الجديد في الإصدار 10.0.7](whats-new-changed-10-0-7.md). |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>الإعلانات السابقة حول الميزات التي تمت إزالتها أو إهمالها
لمعرفه المزيد حول الميزات التي تمت إزالتها أو إهمالها في الإصدارات السابقة، راجع [‏‫الميزات التي تمت إزالتها أو إهمالها في الإصدارات السابقة‬](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

