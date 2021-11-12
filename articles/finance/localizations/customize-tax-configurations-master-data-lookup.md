---
title: تخصيص تكوينات الضرائب للبحث عن البيانات الرئيسية
description: يوضح هذا الموضوع كيفيه تخصيص تكوينات الضريبة لتوسيع وظيفة بحث البيانات الرئيسية.
author: kai-cloud
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 498201d5c0377058e86b25953ebbe401ae1af9e3
ms.sourcegitcommit: ed43ceae9b2ef3f616b81127bcf4c4b0862e23f5
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 10/28/2021
ms.locfileid: "7714870"
---
# <a name="customize-tax-configurations-for-master-data-lookup"></a>تخصيص تكوينات الضرائب للبحث عن البيانات الرئيسية

[!include [banner](../includes/banner.md)]

اتبع هذه الخطوات في هذا الموضوع لتخصيص تكوينات الضريبة لتوسيع وظيفة بحث البيانات الرئيسية.

## <a name="import-a-tax-configuration-provided-by-microsoft"></a>استيراد تكوين الضريبة الذي يوفره Microsoft

1. في Regulatory Configuration Service (RCS)، في مساحة عمل **التقارير الإلكترونية**، حدد المستودعات لموفر تكوين **Microsoft** .
2. حدد **المستودعات**.
3. حدد **العمومي**، ثم حدد **فتح**.
4. حدد تكوين الضريبة ، مثل **تكوين حساب الضريبة** ، ثم في علامة التبويب **الإصدارات**، حدد إصدارًا.
5. حدد **استيراد**.

> [!NOTE]
> يتم استيراد تعيين نموذج Dataverse بشكل افتراضي. في حاله استلام رسائل تحذير اثناء عمليه استيراد التكوين ، قم بتمكين الكيانات الظاهرية في Dataverse. لمزيد من المعلومات، راجع [تمكين الكيانات الظاهرية Dataverse](../../fin-ops-core/dev-itpro/power-platform/enable-virtual-entities.md).

## <a name="create-a-customized-data-model-configuration"></a>إنشاء تكوين نموذج بيانات مخصص

1. في مساحة عمل **التقارير الإلكترونيه** ، حدد **تكوينات الضريبة** ، ثم حدد تكوين نموذج البيانات المراد توسيعه. علي سبيل المثال ، قم بتحديد **نموذج بيانات حساب الضريبة**.
2. حدد **إنشاء التكوين**.
3. حدد **نموذج المستند الخاضع للضريبة المشتق من الاسم: نموذج بيانات حساب الضريبة، Microsoft**.
4. في الحقل **الاسم**، أدخل **نموذج بيانات التخصيص**.
5. حدد **إنشاء التكوين**.

## <a name="create-customized-reference-models"></a>إنشاء نماذج مرجعيه مخصصه

1. في الصفحة **تكوينات الضريبة** ، حدد **نموذج بيانات التخصيص** ، ثم قم بتحديد **المصمم**.
2. حدد زر علامة الحذف (**...**)، ثم حدد طريقة العرض **نموذج المرجع**.

    [![نموذج المرجع.](./media/pic2.png)](./media/pic2.png)

3. إنشاء نموذج مرجع مخصص. الطراز المخصص هو نموذج جذر. الكيان المخصص عبارة عن قائمه سجلات. الحقل المخصص عبارة عن حقل السلسلة الذي تريد استخدامه في البحث. يمكنك إضافة المزيد من الحقول، إذا لزم الأمر.
4. حدد زر علامة الحذف (**...**)، ثم حدد طريقة العرض **المستند الخاضع للضريبة**.
5. حدد السمة لربطها بنموذج المرجع المخصص. علي سبيل المثال ، حدد **سمه مخصصه** ، ثم اتبع الخطوات التالية:

    1. حدد **تحديد نموذج المرجع**.
    2. حدد **نموذج مخصص** ، ثم حدد **موافق**. يتم تحديث اسم نموذج المرجع إلى قيمه حقل **مفتاح طبيعي**.

        [![حدد مربع الحوار نموذج المرجع.](./media/pic5.png)](./media/pic5.png)

    3. حدد **حفظ**، ثم قم بتحديد **إكمال**.

## <a name="create-a-customized-model-mapping-configuration"></a>إنشاء تكوين تعيين نموذج بيانات مخصص

1. في مساحة **عمل التقارير الإلكترونيه**، حدد **تكوينات الضريبة**، ثم حدد **تكوين تعيين نموذج Dataverse**.
2. في حقل **الإعداد الافتراضي لتعيين النموذج‬**، حدد **لا**.
3. حدد **إنشاء التكوين**.
4. حدد **نموذج المستند الخاضع للضريبة المشتق من الاسم: تعيين نموذج Dataverse، Microsoft**.
5. في الحقل **الاسم**، أدخل **تعيين نموذج التخصيص**.
6. في حقل **النموذج الهدف** ، حدد نموذج بيانات **نموذج بيانات التخصيص**.
7. حدد **إنشاء التكوين**.

    [![إنشاء مربع حوار القائمة المنسدلة للتكوين.](./media/pic6.png)](./media/pic6.png)

8. حدد **تعيين نموذج التخصيص** ، ثم قم بتعيين حقل **التطبيق المتصل** علي الاتصال الذي تم إنشاؤه في الخطوة 8 في [اعداد بيئة للبحث عن البيانات الرئيسية](tax-service-set-up-environment-master-data-lookup.md).
9. قم بتعيين الحقل **الاعداد الافتراضي لتعيين النموذج** إلى **نعم.**

## <a name="create-customized-model-mappings"></a>إنشاء تعيينات النماذج المخصصة

1. في الصفحة **تكوينات الضريبة** ، حدد **تعيين نموذج التخصيص**.
2. حدد **المصمم** ، ثم حدد **نموذج التخصيص**.

    [![نموذج التخصيص.](./media/pic8.png)](./media/pic8.png)

## <a name="map-a-model-mapping-to-a-dataverse-entity"></a>تعيين تعيين نموذج لكيان Dataverse

1. في الصفحة **مصمم تعيين النموذج** ، حدد **نموذج التخصيص** ، ثم قم بتحديد **المصمم**.
2. في شجرة **أنواع مصادر البيانات**، حدد **جدول Dataverse**.
3. حدد **إضافة جذر** في علامة التبويب **مصادر البيانات** .
4. في الحقل **الاسم**، أدخل ‏‫**Dataverse مخصصة**.
5. في الحقل **الاسم** الثاني، حدد كيانا.
6. حدد **موافق**.

    [![مربع حوار خصائص مصدر بيانات الجدول.](./media/pic9.png)](./media/pic9.png)

7. حدد **Dataverse مخصص** و **كيان مخصص** ، ثم حدد **ربط**.

    [![ربط الكيان المخصص وDataverse المخصص.](./media/pic10.png)](./media/pic10.png)

8. ضمن **Dataverse مخصص** و **حقل مخصص** ، حدد حقلاً، ثم حدد **ربط**.

    [![ربط الحقل المخصص وDataverse المخصص.](./media/pic11.png)](./media/pic11.png)

9. حدد **حفظ**، ثم قم بتحديد **إكمال**.

## <a name="create-a-customized-tax-configuration"></a>إنشاء تكوين ضريبة مخصص

1. في مساحة عمل **التقارير الإلكترونيه**، حدد **تكوينات الضريبة**، ثم حدد **تكوين تعيين نموذج**.
2. حدد **إنشاء التكوين**.
3. حدد **تكوين خدمه الضرائب المشتق من الاسم: تكوين حساب الضريبة ، Microsoft**.
4. في الحقل **الاسم**، أدخل **تكوين التخصيص**.
5. حدد **إنشاء التكوين**.
6. حدد **تكوين التخصيص** ، ثم حدد **المصمم**.
7. في حقل **نموذج البيانات** ، حدد **نموذج بيانات التخصيص**.
8. في حقل **إصدار نموذج البيانات**، حدد الإصدار المناسب لنموذج البيانات.

    [![قسم الخصائص.](./media/pic13.png)](./media/pic13.png)

9. حدد **مكتمل**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]