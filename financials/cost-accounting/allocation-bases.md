---
title: "أسس التوزيع"
description: "يقدم هذا الموضوع معلومات حول أسس التوزيع. تمثل أسس التوزيع المكونات الأساسية في محاسبة التكاليف، وتستخدم غالبًا لتخصيص التكاليف الزائدة."
author: YuyuScheller
manager: AnnBe
ms.date: 05/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMDimensionMember
audience: Application User
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 223174
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: YuyuScheller
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: 74a3033ffbdba2efc6c5ecd6c55019898751a146
ms.contentlocale: ar-sa
ms.lasthandoff: 06/20/2017


---

# <a name="allocation-bases"></a>أسس التوزيع 

[!include[banner](../includes/banner.md)]

يمثل أساس التخصيص ذلك الأساس الذي تقوم محاسبة التكاليف بتخصيص التكاليف الإضافية على أساسه. يمكن أن يكون أساس التخصيص كمية، مثل ساعات الأجهزة المستخدمة، أو ساعات الكيلووات (كيلووات) التي يتم استهلاكها، أو القدم المربع الذي يتم شغله. غالبًا ما تستخدم أسس التوزيع لتعيين التكاليف الإضافية إلى المخزون الذي يتم إنتاجه. على سبيل المثال، يخصص قسم تكنولوجيا المعلومات نفقاته وفقًا لعدد أجهزة الكمبيوتر التي يستخدمها كل قسم.

يوجد ثلاثة أنواع من أسس التوزيع في محاسبة التكاليف:

- أسس التوزيع لعضو البُعد المعرف مسبقًا
- أسس التوزيع للتدرج الهرمي
- أسس التوزيع للمعادلة

## <a name="predefined-dimension-member-allocation-bases"></a>أسس التوزيع لعضو البُعد المعرف مسبقًا

يتم إنشاء قواعد توزيع أعضاء الأبعاد المُعرفة مسبقًا تلقائيًا عندما يتم إنشاء عضو البعد لأحد الأنواع التالية:

- أعضاء الأبعاد الإحصائية
- أعضاء أبعاد عنصر التكلفة

> [!NOTE]
> تراعي قواعد توزيع أعضاء الأبعاد المُعرفة مسبقًا التي تستند على عضو بُعد عنصر التكلفة، القيم فقط من موفر مصدر البيانات، مثل دفتر الأستاذ العام أو الموازنة.

### <a name="example-1-use-a-cost-element-dimension-member-as-the-allocation-base"></a>مثال 1: استخدام عضو بعد عنصر تكلفة كأساس للتوزيع
يوضح هذا المثال كيفية إنشاء قاعدة توزيع تكلفة لتخصيص عنصر التكلفة 10002 (تأمين الموظف) للرصيد المُسجل في عنصر التكلفة 10001 (رواتب). يتم تحديد قاعدة التخصيص استناداً إلى النسبة الخاصة برواتب كل قسم إلى إجمالي الرواتب. (مراجعة البيانات مطلوبة!)

في دفتر الأستاذ العام، يتم تعريف مخطط الحساب على النحو التالي.

| مخطط الحساب | الحساب الرئيسي | ‏‏الوصف        | نوع الحساب الرئيسي |
|------------------|--------------|--------------------|-------------------|
| مشترك           | 10001        | الرواتب           | المصروفات           |
| مشترك           | 10002        | تأمين الموظف | المصروفات           |

تحديد بُعد عنصر التكلفة، وتكوين موصل البيانات. بعد استيراد البيانات، يتم إنشاء الإدخالات التالية في محاسبة التكاليف.

**أعضاء أبعاد عنصر التكلفة**

| اسم بُعد عنصر التكلفة | عنصر التكلفة |  ‏‏الوصف       | النوع    |
|-----------------------------|--------------|--------------------|---------|
| عناصر التكلفة               | 10001        | الرواتب           | أساسي |
| عناصر التكلفة               | 10002        | تأمين الموظف | أساسي |

**أسس التوزيع لعضو البُعد المعرف مسبقًا** 

| الاسم  | ‏‏الوصف        | بُعد عنصر التكلفة |
|-------|--------------------|------------------------|
| 10001 | الرواتب           | عناصر التكلفة          |
| 10002 | تأمين الموظف | عناصر التكلفة          |

في دفتر الأستاذ العام، تم ترحيل الإدخالات التالية:

- الإدخالات التي تعرض الحساب الرئيسي للرواتب تأتي من نظام الرواتب، وتُرحل إلى مراكز التكلفة.
- يتم ترحيل مصروفات تأمين الموظف يدويًا إلى مركز التكلفة الافتراضي.

| التاريخ المحاسبي | مركز التكلفة |  ‏‏الوصف        | الحساب الرئيسي |  ‏‏الوصف       | المبلغ بعملة المحاسبة |
|-----------------|-------------|---------------------|--------------|--------------------|-------------------------------|
| 03-01-2017      | CC001       | الموارد البشرية                  | 10001        | الرواتب           | 2,000.00                      |
| 03-01-2017      | CC002       | FI                  | 10001        | الرواتب           | 5,000.00                      |
| 03-01-2017      | CC003       | تكنولوجيا المعلومات                  | 10001        | الرواتب           | 3,000.00                      |
| 03-01-2017      | CC099       | مركز التكلفة الافتراضي | 10002        | تأمين الموظف | 1000.00                      |

بعد معالجة بيانات مصدر دفتر الأستاذ العام، يتم إنشاء الإدخالات التالية في محاسبة التكاليف.

**إدخالات التكلفة**

| كائن التكلفة |  ‏‏الوصف        | عنصر التكلفة  |  ‏‏الوصف       | سلوك التكلفة   |المبلغ|التاريخ المحاسبي|
|-------------|---------------------|---------------|--------------------|-----------------|------|---------------|
| CC001       | الموارد البشرية                  | 10001         | الرواتب           | غير مصنف    |2,000.00|  03-01-2017    |
| CC002       | FI                  | 10001         | الرواتب           | غير مصنف    |5,000.00|     03-01-2017         |
| CC003       | تكنولوجيا المعلومات                  | 10001         | الرواتب           | غير مصنف    |3,000.00|      03-01-2017        |
| CC099       | مركز التكلفة الافتراضي | 10002         | تأمين الموظف | غير مصنف    |1000.00|      03-01-2017       |

في هذا المثال المبسط، يتم إنشاء قاعدة توزيع التكلفة لتخصيص عنصر التكلفة 10002 (تأمين الموظف) بالتناسب مع الرصيد المُسجل في عنصر التكلفة 10001 (الرواتب).

**قاعدة توزيع التكلفة**

| عقدة التدرج الهرمي لبُعد كائن التكلفة | عقدة التدرج الهرمي لبُعد عنصر التكلفة | سلوك التكلفة | أساس التوزيع |
|--------------------------------------|---------------------------------------|---------------|-----------------|
| CC099                                | 10002                                 | غير مصنف  | 10001           |

**إجراء حسابات المصروفات الإضافية**

بعد تطبيق عنصر التكلفة 10001 (رواتب) كأساس التوزيع، تكون نتيجة حساب المصروفات الإضافية على النحو التالي.

| كائن التكلفة | ‏‏الوصف | المقدار |   عامل التوزيع         | المبلغ |
|-------------|-------------|-----------|-----------------------------|--------|
| CC001       | الموارد البشرية          | 2,000     | (2,000 ÷ 10,000) × 1,000.00 | 200.00 |
| CC002       | FI          | 5,000     | (5,000 ÷ 10,000) × 1,000.00 | 500.00 |
| CC003       | تكنولوجيا المعلومات          | 3,000     | (3,000 ÷ 10,000) × 1,000.00 | 300.00 |

**دفتر اليومية**

| دفتر يومية | نوع دفتر اليومية                          | فترة التقويم المالي | السنة | الفترة   | ‏‏الإصدار                                                                 |
|---------|---------------------------------------|------------------------|------|----------|-------------------------------------------------------------------------|
| 00001   | دفتر يومية حساب توزيع التكلفة | مالي                 | 2017 | الفترة 1 | حساب المصروفات الزائدة / 01-02-2017 11:51:00 م / دفتر الأستاذ العام /2017 / الفترة 1 |

**إدخالات دفتر اليومية لرصيد كائن التكلفة**

| التاريخ المحاسبي | كائن التكلفة | ‏‏الوصف         | عنصر التكلفة | ‏‏الوصف        | سلوك التكلفة |  المبلغ  |
|-----------------|-------------|---------------------|--------------|--------------------|---------------|----------|
| 31-01-2017      | CC099       | مركز التكلفة الافتراضي | 10002        | تأمين الموظف | غير مصنف  | 1000.00 |

**إدخالات التكلفة**

| كائن التكلفة |  ‏‏الوصف        | عنصر التكلفة |    ‏‏الوصف     | سلوك التكلفة | المبلغ    | التاريخ المحاسبي |
|-------------|---------------------|--------------|--------------------|---------------|-----------|-----------------|
| CC099       | مركز التكلفة الافتراضي | 10002        | تأمين الموظف | غير مصنف  | -1000.00 | 31-01-2017      |
| CC001       | الموارد البشرية                  | 10002        | تأمين الموظف | غير مصنف  | 200.00    | 31-01-2017      |
| CC002       | FI                  | 10002        | تأمين الموظف | غير مصنف  | 500.00    | 31-01-2017      |
| CC099       | تكنولوجيا المعلومات                  | 10002        | تأمين الموظف | غير مصنف  | 300.00    | 31-01-2017      |

### <a name="example-2-use-a-statistical-dimension-member-as-the-allocation-base"></a>مثال 2: استخدام عضو البُعد الإحصائي كأساس للتوزيع

يمكن استخدام أعضاء البُعد الإحصائي كأسس توزيع لتحديد سياسات أو تقارير الاستهلاك غير النقدي حسب كائنات التكلفة. يمكن إنشاء أعضاء البُعد الإحصائية يدويًا أو استيرادها من الملف باستخدام أداة إدارة استيراد/تصدير البيانات.

**أعضاء الأبعاد الإحصائية**

| اسم البُعد الإحصائي | العنصر الإحصائي | ‏‏الوصف               | الوحدة |
|----------------------------|---------------------|---------------------------|------|
| العناصر الإحصائية       | FTE                 | موظفو الدوام الكامل       | وحدة   |
| العناصر الإحصائية       | الكهرباء         | استهلاك الكهرباء   | كيلووات في الساعة  |

عندما يتم حفظ عضو بعد إحصائي، يتم إنشاء سجل مقابل له في أسس توزيع عضو البعد المُعرف مسبقًا.

**أسس التوزيع لعضو البُعد المعرف مسبقًا**

| الاسم        | ‏‏الوصف             | بعد العنصر الإحصائي |
|-------------|-------------------------|-------------------------------|
| FTE         | موظفو الدوام الكامل     | العناصر الإحصائية          |
| الكهرباء | استهلاك الكهرباء | العناصر الإحصائية          |

يمكن أن تأتي الإجراءات الإحصائية من مصادر متعددة:

- يتم قياس استهلاك الكهرباء حسب العدادات التي تم تركيبها في مناطق مختلفة من الشركة.
- الجداول التي تحتفظ بالقياسات الإحصائية. على سبيل المثال، يحتفظ جدول HcmEmployment بقائمة بكافة الموظفين ومراكز التكلفة التي يعملون عليها.

| الاسم       | مركز التكلفة |  ‏‏الوصف  | نوع العامل |
|------------|-------------|----|-------------|
| الموظف أ | CC001       | الموارد البشرية | الموظف    |
| الموظف ب | CC002       | FI | الموظف    |
| الموظف ج | CC002       | FI | الموظف    |
| الموظف د | CC003       | تكنولوجيا المعلومات | الموظف    |
| الموظف و | CC003       | تكنولوجيا المعلومات | الموظف    |

> [!NOTE]
> يمكن استخدام كافة الجداول التي تحتوي على الأبعاد المالية كمصادر للإجراءات الإحصائية.

تدعم محاسبة التكاليف مجموعة من الإجراءات الإحصائية باستخدام اتصالات البيانات التالية:

- أداة استيراد/تصدير إدارة البيانات
- القياسات الإحصائية

لسحب الإجراءات الإحصائية من النظام، يلزم وجود قالب موفر قياس إحصائي. للمزيد من المعلومات، يُرجى الاطلاع على قالب موفر القياسات الإحصائية. (سيتم إضافة ارتباط بمجرد أن تتم كتابة هذا الموضوع.)

**قوالب موفري القياسات الإحصائية**

| الاسم  | الوظيفة | جدول المصدر  | حقل المجموع      | حقل التاريخ     |
|-------|----------|---------------|----------------|----------------|
| FTE’s | جرد    | HcmEmployment | غير قابل للتطبيق | غير قابل للتطبيق |

بعد معالجة بيانات مصدر القياس الإحصائي، سوف يتم إنشاء الإدخالات التالية في محاسبة التكاليف.

**الإدخالات الإحصائية**

| كائن التكلفة | ‏‏الوصف      | التاريخ المحاسبي | عضو البُعد الإحصائي | ‏‏الوصف         | المقدار |
|-------------|------------------|-----------------|------------------------------|---------------------|-----------|
| CC001       | الموارد البشرية               | 31-01-2017      | FTE’s                        | موظفو الدوام الكامل | 1.00      |
| CC002       | FI               | 31-01-2017      | FTE’s                        | موظفو الدوام الكامل | 2.00      |
| CC003       | تكنولوجيا المعلومات               | 31-01-2017      | FTE’s                        | موظفو الدوام الكامل | 2.00      |

وفيما يلي مثالًا على قاعدة توزيع التكلفة إذا ما تم تعيين أساس توزيع عضو بُعد مُعرف مسبقًا لـ FTE كأساس توزيع فيه.

| كائن التكلفة | ‏‏الوصف  | المقدار | عامل التوزيع |
|-------------|------|-----------|-------------------|
| CC001       | الموارد البشرية   | 1.00      | (1/5) × المبلغ    |
| CC002       | FI   | 2.00      | (2/5) × المبلغ    |
| CC003       | تكنولوجيا المعلومات   | 2.00      | (2/5) × المبلغ    |

يمكنك استخدام كيان بيانات القياسات الإحصائية المستوردة لاستيراد القياسات الإحصائية في محاسبة التكاليف. يمكنك أيضًا استخدام أداة استيراد/تصدير إدارة البيانات. في Excel، يتم تسجيل استهلاك الكهرباء على النحو التالي.

| التاريخ المحاسبي | عضو البُعد | المقدار | ‏‏معرف المصدر |
|-----------------|------------------|-----------|-------------------|
| 31-01-2017      | CC001            | 2,450.00  | الكهرباء       |
| 31-01-2017      | CC002            | 4,100.00  | الكهرباء       |
| 31-01-2017      | CC003            | 15,000.00 | الكهرباء       |

بعد معالجة بيانات مصدر القياس الإحصائي، سوف يتم إنشاء الإدخالات التالية في محاسبة التكاليف.

**الإدخالات الإحصائية**

| كائن التكلفة |    | التاريخ المحاسبي | عضو البُعد الإحصائي |    ‏‏الوصف          | المقدار |
|-------------|----|-----------------|------------------------------|-------------------------|-----------|
| CC001       | الموارد البشرية | 31-01-2017      | الكهرباء                  | استهلاك الكهرباء | 2,450.00  |
| CC002       | FI | 31-01-2017      | الكهرباء                  | استهلاك الكهرباء | 4,100.00  |
| CC003       | تكنولوجيا المعلومات | 31-01-2017      | الكهرباء                  | استهلاك الكهرباء | 15,000.00 |

وفيما يلي مثالًا على قاعدة توزيع التكلفة إذا ما تم تعيين أساس توزيع عضو بُعد مُعرف مسبقًا للكهرباء كأساس توزيع فيه.

| كائن التكلفة | ‏‏الوصف  | المقدار | عامل التوزيع          |
|-------------|------|-----------|----------------------------|
| CC001       | الموارد البشرية   | 2,450.00  | (2,450 ÷ 21,550) × المبلغ  |
| CC002       | FI   | 4,100.00  | (4,100 ÷ 21,550) × المبلغ  |
| CC003       | تكنولوجيا المعلومات   | 15,000.00 | (15,000 ÷ 21,550) × المبلغ |

## <a name="hierarchy-allocation-bases"></a>أسس التوزيع للتدرج الهرمي

يمكن لمحاسبي التكاليف إنشاء التدرج الهرمي لأسس التوزيع يدويًا عن طريق تطبيق عقد التدرج الهرمي لبعد كائن التكلفة على أساس التوزيع الموجود. وبهذه الطريقة، يمكنك تحديد نطاق أساس توزيع عضو البُعد الأصلي المُعرف مسبقًا. يمكن استخدام أساس توزيع عضو بُعد واحد مُحدد مسبقًا لإنشاء أسس توزيع تدرجات هرمية متعددة. يمكن الاحتفاظ بالنطاقات في التدرج الهرمي لبُعد كائن التكلفة المُقترن مع أسس توزيع التدرج الهرمي.

### <a name="example-hierarchy-allocation-bases-that-are-based-on-full-time-employees-in-the-organization"></a>على سبيل المثال: أسس التوزيع الهرمي التي تستند على موظفي الدوام الكامل في المؤسسة
وفيما يلي مثالًا للتدرج الهرمي لبعد كائن التكلفة الذي يمكن إنشاؤه لوصف مؤسسة بسيطة.

| اسم التدرج الهرمي | مستوى العقدة 0 | مستوى العقدة 1 | مستوى العقدة 2 | أعضاء الأبعاد |
|----------------|--------------|--------------|--------------|-------------------|
| المؤسسة   | رئيس تنفيذي          | ‏‫المدير المالي‬          | FICO         | CC001             |
| المؤسسة   | رئيس تنفيذي          | ‏‫المدير المالي‬          | الموارد البشرية           | CC002             |
| المؤسسة   | رئيس تنفيذي          | مدير الإعلام          | تكنولوجيا المعلومات           | CC003             |

تحتفظ أسس توزيع عضو البُعد المُعرف مسبقًا لـ FTE الذي تم إنشاؤه في السابق بالإدخالات التالية.

**الإدخالات الإحصائية**

| كائن التكلفة | ‏‏الوصف  | التاريخ المحاسبي | عضو البُعد الإحصائي | ‏‏الوصف | المقدار |
|-------------|------|-----------------|------------------------------|---------------------|-----------|
| CC001       | الموارد البشرية   | 31-01-2017      | FTE’s                        | موظفو الدوام الكامل | 1.00      |
| CC002       | FI   | 31-01-2017      | FTE’s                        | موظفو الدوام الكامل | 2.00      |
| CC003       | تكنولوجيا المعلومات   | 31-01-2017      | FTE’s                        | موظفو الدوام الكامل | 2.00      |

يجب توزيع التكلفة بين مراكز التكلفة التي تقوم بتقديم التقارير إلى المدير المالي للمؤسسة (المدير المالي). من المتفق عليه أن نسبة التوزيع الصحيحة هي عدد موظفي الدوام الكامل (FTEs) بحسب مركز التكلفة.

**أسس التوزيع للتدرج الهرمي**

| الاسم                  | أساس التوزيع | تدرج بُعد كائن التكلفة | عقدة التدرج الهرمي لبُعد كائن التكلفة |
|-----------------------|-----------------|---------------------------------|--------------------------------------|
| عدد الـ FTEs في المدير المالي | FTE’s           | المؤسسة                    | ‏‫المدير المالي‬                                  |

تسمح لك وظيفة المعاينة بالتحقق من صحة أسس توزيع التدرج الهرمي التي تم إنشاؤها، بناءً على الإدخالات الإحصائية في النظام.

**تفاصيل أساس التوزيع**

| كائن التكلفة | ‏‏الوصف  |  المقدار |
|-------------|------|------------|
| CC001       | الموارد البشرية   | 1.00       |
| CC002       | FI   | 2.00       |

وفيما يلي مثالًا على قاعدة توزيع التكلفة إذا كان عدد FTEs في أسس توزيع التدرج الهرمي للمدير المالي قد تم تعيينها كأساس توزيع فيها.

| كائن التكلفة | ‏‏الوصف  | المقدار | عامل التوزيع |
|-------------|------|-----------|-------------------|
| CC001       | الموارد البشرية   | 1.00      | (1/3) × المبلغ    |
| CC002       | FI   | 2.00      | (2/3) × المبلغ    |

## <a name="formula-allocation-bases"></a>أسس التوزيع للمعادلة

تسمح لك أسس توزيع المعادلة بتحديد المعادلات المتقدمة لتحقيق أساس التوزيع الصحيح. يمكنك إنشاء أسس توزيع المعادلة يدوياً.

عندما تقوم بإنشاء أساس توزيع معادلة، تقوم بتحديد أي بُعد إحصائي وأي بُعد لعنصر التكلفة يجب أن يكون الأساس لهذه المعادلة. يمكن استخدام كافة أسس التوزيع التي تأتي من الأبعاد المُحددة مُسبقًا في أساس توزيع المعادلة.

> [!NOTE]
> يمكن استخدام أسس توزيع المعادلة المحددة مسبقًا لتحديد أساس توزيع معادلة جديد.

في معاملات أساس توزيع المعادلة، يمكنك إنشاء أسماء مستعارة وربطها إما بقاعدة التوزيع أو بأحد الثوابت. بعد ذلك، يتم استخدام الأسماء المستعارة لتحديد المعادلة.

يمكنك استخدام عوامل التشغيل التالية لتحديد المعادلة الخاصة بك.

| الرموز | النص           |
|---------|----------------|
| ( )     | الأقواس    |
| \<      | أصغر من   |
| \>      | أكبر من    |
| +       | الجمع       |
| -       | الطرح    |
| \*      | الضرب |

العبارات التقليدية **IF** غير مدعومة. ومع ذلك، يمكنك إنشاء العبارات والتحقق مما إذا كانت صحيحة.

| كشف الحساب | التحقق من الصحة | النتيجة |
|-----------|------------|--------|
| أ \> ب    | صحيح       | 1      |
| أ \> ب    | خطأ      | 0      |

### <a name="example-1-a-simple-formula"></a>مثال 1: معادلة بسيطة

عادة ما تتكون فواتير الكهرباء من جزئين:

- رسوم ثابتة متصلة بالشبكة
- تكلفة مرتبطة بالاستهلاك لكل كيلووات

تم تحديد أساس توزيع عضو بُعد الكهرباء المُعرف مسبقًا، ويحتفظ بهذه القيم.

**الإدخالات الإحصائية**

| كائن التكلفة | الاسم | التاريخ المحاسبي | عضو البُعد الإحصائي | ‏‏الوصف             | المقدار |
|-------------|------|-----------------|------------------------------|-------------------------|-----------|
| CC001       | الموارد البشرية   | 31-01-2017      | الكهرباء                  | استهلاك الكهرباء | 2,450.00  |
| CC002       | FI   | 31-01-2017      | الكهرباء                  | استهلاك الكهرباء | 4,100.00  |
| CC003       | تكنولوجيا المعلومات   | 31-01-2017      | الكهرباء                  | استهلاك الكهرباء | 15,000.00 |

إذا كانت الرسوم الثابتة يجب نشرها بالتساوي على كائنات التكلفة التي تستهلك الكهرباء، فمن ثم لديك خياران لتخصيص التكاليف:

- إنشاء أساس توزيع جديد مُعرف مسبقًا، وأساس كهرباء ثابت، ثم تطبيق إجراء إحصائي 1.00 لكل كائن تكلفة يستهلك الكهرباء.
- قم بإنشاء أساس توزيع معادلة، ورسوم كهرباء ثابتة، والتي تستفيد من أساس التوزيع المُعرف مُسبقًا للكهرباء والمحدد بالفعل في النظام. وتعتبر الميزة من هذا الخيار أنه يجب تحميل البيانات إلى محاسبة التكاليف الخاصة لعضو بعد كهرباء إحصائي واحد فقط.

**أساس توزيع المعادلة** 

| الاسم              | بُعد عنصر التكلفة | البُعد الإحصائي | المعادلة |
|-------------------|------------------------|-----------------------|---------|
| الكهرباء ثابتة |                        | العناصر الإحصائية  |         |

قبل ملء حقل **المعادلة**، يجب تحديد الاسم المستعار الذي يجب استخدامه في المعادلة.

**عوامل أساس توزيع المعادلة**

| الاسم المستعار | ثابت | أساس التوزيع |
|-------|----------|-----------------|
| أ     |          | الكهرباء     |
| ب     | 0.01     |                 |

لاحظ أنه 0 (صفر) غير مدعوم كثابت.

**أساس توزيع المعادلة**

| الاسم              | بُعد عنصر التكلفة | البُعد الإحصائي | المعادلة |
|-------------------|------------------------|-----------------------|---------|
| الكهرباء ثابتة |                        | العناصر الإحصائية  | أ \> ب  |

تسمح لك وظيفة المعاينة بالتحقق من صحة أساس توزيع المعادلة التي تم إنشاؤها، بناءً على الإدخالات الإحصائية في النظام.

**تفاصيل أساس التوزيع**

| كائن التكلفة | ‏‏الوصف  | المعادلة           | المقدار |
|-------------|------|-------------------|-----------|
| CC001       | الموارد البشرية   | 2,450.00 \> 0.01  | 1.00      |
| CC002       | FI   | 4,100.00 \> 0.01  | 1.00      |
| CC003       | تكنولوجيا المعلومات   | 15,000.00 \> 0.01 | 1.00      |

وفيما يلي مثالًا على قاعدة توزيع التكلفة إذا ما تم تعيين أساس توزيع معادلة الكهرباء كأساس توزيع فيها.

**عامل توزيع مقدار كائن التكلفة**

| كائن التكلفة | الاسم | المقدار |  عامل التوزيع |
|-------------|------|-----------|--------------------|
| CC001       | الموارد البشرية   | 1.00      | (1/3) × المبلغ     |
| CC002       | FI   | 1.00      | (1/3) × المبلغ     |
| CC003       | تكنولوجيا المعلومات   | 1.00      | (1/3) × المبلغ     |

### <a name="example-2-an-advanced-formula"></a>مثال 2: معادلة متقدمة
على سبيل المثال، يجب أن تتبع تكلفة الكهرباء الكهرباء الفعلية المستهلكة بالكيلووات. تريد الإدارة دمج المكافأة لتقليل استخدام الكهرباء. 

| القاعدة              | المعدل | 
|-------------------|------|
| أ < = 10000,00 كيلووات | 0.75 |
| أ < = 10000,00 كيلووات  | 1.15 |

يتم إنشاء أساس توزيع معادلة جديد، استخدام الكهرباء.

**أساس توزيع المعادلة**

| الاسم              | بُعد عنصر التكلفة | البُعد الإحصائي | المعادلة |
|-------------------|------------------------|-----------------------|---------|
| استخدام الكهرباء |                        | العناصر الإحصائية  |         |

قبل ملء حقل **المعادلة**، يجب تحديد الاسم المستعار الذي يجب استخدامه في المعادلة.

**عوامل أساس توزيع المعادلة**

| الاسم المستعار | ثابت  | أساس التوزيع |
|-------|-----------|-----------------|
| أ     |           | الكهرباء     |
| ب     | 10,000.00 |                 |
| ج     | 0.75      |                 |
| د     | 1.15      |                 |

**أساس توزيع المعادلة**

| الاسم              | بُعد عنصر التكلفة | البُعد الإحصائي | المعادلة                                                    |
|-------------------|------------------------|-----------------------|------------------------------------------------------------|
| الكهرباء ثابتة |                        | العناصر الإحصائية  | ((a \> b) × ((b × c) + (a – b) × d)) + ((a \<= b] × a × c) |

تسمح لك وظيفة المعاينة بالتحقق من صحة أساس توزيع المعادلة التي تم إنشاؤها، بناءً على الإدخالات الإحصائية في النظام.

**تفاصيل أساس التوزيع**

| كائن التكلفة |    | المعادلة                                                                                                                             | المقدار |
|-------------|----|-------------------------------------------------------------------------------------------------------------------------------------|-----------|
| CC001       | الموارد البشرية | ((2,450.00 \> 10.000.00) × ((10,000.00 × 0.75) + (2,450.00 – 10,000.00) × 1.15)) + ((2,450.00 \<= 10,000.00) × 2,450.00 × 0.75)     | 1,837.50  |
| CC002       | FI | ((4,100.00 \> 10.000.00) × ((10,000.00 × 0.75) + (4,100.00 – 10,000.00) × 1.15)) + ((4,100.00 \<= 10,000.00) × 4,100.00 × 0.75)     | 3,075.00  |
| CC003       | تكنولوجيا المعلومات | ((15,000.00 \> 10.000.00) × ((10,000.00 × 0.75) + (15,000.00 – 10,000.00) × 1.15)) + ((15,000.00 \<= 10,000.00) × 15,000.00 × 0.75) | 1,3250.00 |

وإليك على نظرة دقيقة على المعادلة لـ CC003 "(تكنولوجيا المعلومات):

((15,000.00 \> 10,000.00) × ((10,000.00 × 0.75) + (15,000.00 – 10,000.00) × 1.15)) + ((15,000.00 \<= 10,000.00) × 15,000.00 × 0.75) = 13,250.00

(1 × (7,500.00 + 5,000.00 × 1.15)) + (0 × 15,000.00 × 0.75)            

1 × 7,500.00 + 5,750.00 + 0 

وفيما يلي مثالًا على قاعدة توزيع التكلفة إذا ما تم تعيين أساس توزيع معادلة كهرباء ثابتة كأساس توزيع فيها.

| كائن التكلفة |  ‏‏الوصف  | المقدار | عامل التوزيع                |
|-------------|----|-----------|----------------------------------|
| CC001       | الموارد البشرية | 1,837.50  | (1,837.50 ÷ 18,162.50) × المبلغ  |
| CC002       | FI | 3,075.00  | (3,075.00 ÷ 18,162.50) × المبلغ  |
| CC003       | تكنولوجيا المعلومات | 13,250.00 | (13,250.00 ÷ 18,162.50) × المبلغ |
