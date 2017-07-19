---
title: "مساحة العمل المحمولة للمخزون الفعلي"
description: "يوفر هذا الموضوع معلومات حول مساحة العمل المحمولة \"المخزون الفعلي‬\". تساعدك مساحة العمل هذه في الحصول على معلومات دقيقة على جهازك المحمول تتعلق بالمخزون المحجوز والمتوفر في أي وقت وفي أي مكان.‬"
author: Mirzaab
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 267094
ms.assetid: 3fa385ba-894d-4a9e-b394-ef3697abf895
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mirzaab
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: a0edbad63c51d111d7c8985aa7fdf7312da6149d
ms.openlocfilehash: d14f3510df45169e3b77ee9c4f3d0d9d389e6036
ms.contentlocale: ar-sa
ms.lasthandoff: 06/13/2017


---

# <a name="inventory-on-hand-mobile-workspace"></a>مساحة العمل المحمولة للمخزون الفعلي

[!include[banner](../includes/banner.md)]

يوفر هذا الموضوع معلومات حول مساحة العمل المحمولة **المخزون الفعلي**. تساعدك مساحة العمل هذه في الحصول على معلومات دقيقة تتعلق بالمخزون المحجوز والمتوفر في أي وقت وفي أي مكان.‬

تهدف مساحة العمل المحمولة هذه إلى استخدامها بواسطة تطبيق المحمول Microsoft Dynamics 365 for Unified Operations.

## <a name="overview"></a>نظرة عامة
عادةً، يكون للشركات شحنات متعددة وإيصالات مخزون متعددة يوميًا. تغير هذه الحركات باستمرار حالة المخزون الفعلي. تسمح لك مساحة العمل المحمولة **المخزون الفعلي** برؤية حالة المخزون الفعلي عبر الشركة، حتى يتسنى لك الحصول على آخر المعلومات الدقيقة حول بيانات المخزون على جهاز محمول من اختيارك. بغض النظر عن ما إذا كان عملك في المخزن أو في المشتريات أو المبيعات أو التصنيع أو الإدارة، أو كان لديك أدوار أخرى، يمكنك الوصول إلى بيانات المخزون الفعلي في أي وقت وفي أي مكان. 

توفر مساحة العمل المحمولة عرضًا فوريًا لحالة المخزون الفعلي عبر المرافق. إنها تسمح لك بعرض المخزون الفعلي عبر المرافق وعمليات حجز المواد الحالية والمخزون الفعلي غير المحجوز. ويمكنك أيضًا إدخال أرقام الأصناف للاستعلام عن المخزون الفعلي، ويمكنك إجراء بحث مُصفى عن المنتجات أو المتغيرات الفعلية. 

وبوجه خاص، توفر مساحة العمل المحمولة هذه الميزات:

-   يمكنك البحث حسب رقم المنتج أو اسم المنتج للعثور على منتجات لعرض حالة المخزون الفعلي لها.
-   بالنسبة للمنتجات المحددة، يمكنك عرض المعلومات التالية:

    -   المخزون الفعلي لكل موقع
    -   المخزون الفعلي لكل مستودع
    -   المخزون الفعلي لكل موقع
    -   المخزون الفعلي لكل دفعة (للمنتجات الخاضعة لسيطرة الدفعة)
    -   المخزون الفعلي لكل حالة مخزون
    
-   يتم عرض منتجات المخزون الفعلي بالطريق التالية:

    -   حسب المخزون الفعلي (يمثل هذا العرض المبلغ الإجمالي.)
    -   حسب المخزون الفعلي (يمثل هذا العرض المبلغ المحجوز.)
    -   حسب المخزون الفعلي المتوفر (يمثل هذا العرض المبلغ المتاح والذي لا تنطبق عليه أي حجوزات.)

## <a name="prerequisites"></a>المتطلبات الأساسية
تختلف المتطلبات الأساسية، بناءً على إصدار Microsoft Dynamics 365 الذي تم نشره لمؤسستك.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-july-2017-update"></a>يلزم وجود المتطلبات الأساسية إذا كنت تستخدم Microsoft Dynamics 365 for Finance and Operations, Enterprise edition تحديث يوليو 2017 
إذا تم نشر Microsoft Dynamics 365 for Finance and Operations, Enterprise edition، تحديث يوليو 2017 لمؤسستك، يتعين على مسؤول النظام نشر مساحة العمل المحمولة **المخزون الفعلي**. للاطلاع على الإرشادات، راجع [نشر مساحة العمل المحمولة ](/dynamics365/unified-operations/dev-itpro/mobile-apps/publish-mobile-workspace).

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>المتطلبات الأساسية إذا كنت تستخدم الإصدار 1611 من Microsoft Dynamics 365 for Operations مع تحديث النظام الأساسي 3 أو إصدار أحدث
إذا تم نشر الإصدار 1611 من Microsoft Dynamics 365 for Operations مع تحديث النظام الأساسي 3 أو إصدار أحدث لمؤسستك، فيجب على مسؤول النظام إكمال المتطلبات الأساسية التالية. 

<table>
<thead>
<tr class="header">
<th>المتطلب الأساسي</th>
<th>الدور</th>
<th>‏‏الوصف</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>تطبيق قاعدة المعارف 4013633.</td>
<td>مسؤول النظام</td>

<td>إن KB 4013633 عبارة عن تحديث X++ أو إصلاح عاجل لبيانات التعريف يحتوي على مساحة العمل المحمولة <strong>المخزون الفعلي</strong>. لتطبيق KB 4013633، يجب أن يتبع مسؤول النظام الخطوات التالية.
<ol>
<li><a href="/dynamics365/unified-operations/dev-itpro/migration-upgrade/download-hotfix-lcs">تنزيل الإصلاح العاجل لبيانات التعريف من Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">تثبيت الإصلاح العاجل لبيانات التعريف</a>.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/deployment/create-apply-deployable-package">إنشاء حزمة قابلة للنشر</a> تحتوي على نموذج <strong>SCMMobile</strong>، ثم تحميل الحزمة القابلة للنشر إلى LCS.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/deployment/apply-deployable-package-system">تطبيق الحزمة القابلة للنشر</a>.</li>

</ol></td>
</tr>
<tr class="even">
<td>نشر مساحة العمل المحمولة <strong>المخزون الفعلي</strong>.</td>
<td>مسؤول النظام</td>
<td>راجع <a href="/dynamics365/unified-operations/dev-itpro/mobile-apps/publish-mobile-workspace">نشر مساحة عمل محمولة</a></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-mobile-app"></a>تحميل وتثبيت تطبيق الجوال

تنزيل وتثبيت تطبيق Dynamics 365 for Unified Operations للأجهزة المحمولة:

-   [لهواتف Android](https://go.microsoft.com/fwlink/?linkid=850662)
-   [لهواتف iPhone](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>تسجيل الدخول إلى تطبيق الهاتف الجوال

1.  ابدأ تشغيل التطبيق على جهازك المحمول.
2.  أدخل عنوان URL لـ Dynamics 365.
3.  في المرة الأولى التي تقوم بتسجيل الدخول فيها، تتم مطالبتك باسم المستخدم وكلمة المرور الخاصة بك. أدخل بيانات اعتمادك.
4.  بعد تسجيل الدخول، تظهر مساحات العمل المتوفرة لشركتك. تجدر الإشارة إلى أنه في حال قيام مسؤول النظام بنشر مساحة عمل جديدة في وقت لاحق، فسوف يكون عليك تحديث قائمة مساحات العمل المحمولة.

    [![سحب للتحديث](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="view-the-on-hand-inventory-for-a-product-by-using-the-inventory-on-hand-mobile-workspace"></a>عرض المخزون الفعلي لمنتج باستخدام مساحة العمل المحمولة "المخزون الفعلي"

1.  على جهازك المحمول، حدد مساحة العمل **المخزون الفعلي‬**.

2.  حدد **تحديد المخزون الفعلي لصنف معين**. يمكن الآن رؤية قائمة المنتجات المُحمّلة على تطبيقك للاستخدام دون اتصال. بشكل افتراضي، تم تحميل 50 صنف، ولكن باستطاعة المطور تغيير هذا الرقم. للحصول على مزيد من المعلومات، يجب على المطورين الاطلاع على [النظام الأساسي للمحمول](/dynamics365/unified-operations/dev-itpro/mobile-apps/mobile-platform).
3.  إذا لم يكن صنفك موجودًا في القائمة، فحدد **بحث عن المزيد‬**. البحث حسب رقم المنتج، أو قم بالتبديل إلى بحث حسب اسم المنتج.

4.  حدد منتجًا. إذا كان الصنف يحتوي على صورة، فسوف تظهر الصورة.
5.  حدد أحد الخيارات التالية لعرض حالة المخزون الفعلي:

    -   عرض الكمية الحالية لكل موقع
    -   عرض الكمية الحالية لكل مستودع
    -   عرض الكمية الحالية لكل موقع
    -   عرض الكمية الحالية لكل دفعة (ينطبق ذلك على المنتجات الخاضعة للدفعة)
    -   عرض الكمية الحالية لكل حالة مخزون

    يتم عرض منتجات المخزون الفعلي بالطرق التالية:
    -   حسب المخزون الفعلي (يمثل هذا العرض المبلغ الإجمالي.)
    -   حسب المخزون الفعلي (يمثل هذا العرض المبلغ المحجوز.)
    -   حسب المخزون الفعلي المتوفر (يمثل هذا العرض المبلغ المتاح والذي لا تنطبق عليه أي حجوزات.)
