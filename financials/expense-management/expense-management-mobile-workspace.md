---
title: "مساحة العمل المحمولة لإدارة المصروفات"
description: "يوفر هذا الموضوع معلومات حول مساحة العمل المحمولة لإدارة المصروفات التي تتوفر في تطبيق Microsoft Dynamics 365 for Finance and Operations للأجهزة المحمولة. تسمح مساحة العمل هذه للمستخدمين بالتقاط إيصال وتحميله، مما يمكنهم من إرفاقه بتقرير مصروفات فيما بعد. وتسمح أيضًا مساحة العمل المحمولة للمستخدمين بإنشاء بند مصروفات باستخدام إيصال مرفق."
author: annbe
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: end user, IT Pro
ms.reviewer: annbe
ms.search.scope: Operations
ms.custom: 274023
ms.assetid: 3605eda1-a7ed-4675-8031-5279c5a8f5e4
ms.search.region: Global
ms.author: annbe
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 0e52d1c5dde7f79c4a8ac5ac2d9c3b25bba9c2cd
ms.contentlocale: ar-sa
ms.lasthandoff: 06/13/2017


---

# <a name="expense-management-mobile-workspace"></a>مساحة العمل المحمولة لإدارة المصروفات

[!include[banner](../includes/banner.md)]


يوفر هذا الموضوع معلومات حول مساحة العمل المحمولة لإدارة المصروفات التي تتوفر في تطبيق Microsoft Dynamics 365 for Finance and Operations للأجهزة المحمولة. تسمح مساحة العمل هذه للمستخدمين بالتقاط إيصال وتحميله، مما يمكنهم من إرفاقه بتقرير مصروفات فيما بعد. وتسمح أيضًا مساحة العمل المحمولة للمستخدمين بإنشاء بند مصروفات باستخدام إيصال مرفق.

<a name="overview-of-the-expense-management-mobile-workspace"></a>نظرة عامة على مساحة العمل المحمولة لإدارة المصروفات
---------------------------------------------------

يتطلب الكثير من المؤسسات إرفاق نسخة الإيصال بتقرير مصروفات يتعلق بالسفر أو العمل يقدمه الموظف للحصول على التعويض. تسمح مساحة العمل المحمولة **إدارة المصروفات** للمستخدمين بإنشاء بنود مصروفات جديدة بسرعة على جهاز محمول من اختيارهم باستخدام صورة إيصال مرفقة. بدلاً من ذلك، باستطاعة المستخدمين التقاط صورة لإيصال المستخدمين ثم إرفاقه بتقرير مصروفات فيما بعد. تتيح مساحة العمل المحمولة **إدارة المصروفات** للمستخدم القيام بما يلي:

-   التقاط صورة للإيصال وتحميلها إلى Microsoft Dynamics 365 for Finance and Operations. باستطاعة المستخدم عندئذٍ إرفاق هذه الصورة بتقرير مصروفات فيما بعد.
-   تحميل ملف كإيصال تم التقاطه. باستطاعة المستخدم عندئذٍ إرفاق هذا الملف بتقرير مصروفات فيما بعد.
-   إنشاء بند مصروفات جديد باستخدام إيصال مرفق. باستطاعة المستخدم عندئذٍ إضافة البند إلى تقرير مصروفات فيما بعد، وإرساله فيما بعد للموافقة والتعويض.

توضح المقاطع المتبقية من هذا الموضوع كيفية تنفيذ واستخدام مساحة العمل المحمولة **إدارة المصروفات**.

## <a name="prerequisites"></a>المتطلبات الأساسية
قبل تنفيذ مساحة العمل المحمولة **إدارة المصروفات**، تأكد من أن مسؤول النظام استكمل المتطلبات الأساسية التالية.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>المتطلب الأساسي</th>
<th>الدور</th>
<th>‏‏الوصف</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>يجب تطبيق الإصدار 1611 من Microsoft Dynamics 365 for Operations مع تحديث النظام الأساسي 3 أو إصدار أحدث.</td>
<td>مسؤول النظام</td>
<td>في حال عدم نشر Dynamics 365 for Operations في المؤسسة، يجب على مسؤول النظام الاطلاع على <a href="/dynamics365/unified-operations/dev-itpro/deployment/deploy-demo-environment">نشر بيئة عرض توضيحي Microsoft Dynamics 365 for Finance and Operations</a>.</td>
</tr>
<tr class="even">
<td>يجب أن يتم تطبيق KB 4019015.</td>
<td>مسؤول النظام</td>
<td>تحتوي مقالة قاعدة المعارف KB 4019015 (تحديث X + + أو إصلاح عاجل لبيانات التعريف) على أربع مساحات عمل محمولة لإدارة سلسلة التوريد. لتطبيق KB 4019015، يجب أن يتبع مسؤول النظام الخطوات التالية:
<ol>
<li>تنزيل KB 4019015 من Microsoft Dynamics Lifecycle Services (LCS).</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/migration-upgrade/install-metadata-hotfix-package">تثبيت الإصلاح العاجل لبيانات التعريف</a>.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/deployment/create-apply-deployable-package">إنشاء حزمة قابلة للنشر</a> تحتوي على نموذج <strong>‎ApplicationSuite</strong> و<strong>ExpenseMobile</strong>، ثم تحميل الحزمة القابلة للنشر إلى LCS.</li>
<li><a href="/dynamics365/unified-operations/dev-itpro/deployment/apply-deployable-package-system">تطبيق الحزمة القابلة للنشر</a> على نظام Finance and Operations.</li>
</ol></td>
</tr>
<tr class="odd">
<td>يجب نشر مساحة العمل المحمولة <strong>إدارة المصروفات</strong> إلى تطبيق Finance and Operations للأجهزة المحمولة.</td>
<td>مسؤول النظام</td>
<td><ol>
<li>بدء تشغيل تطبيق Finance and Operations في المستعرض.</li>
<li>في صفحة <strong>محددات النظام</strong>، حدد <strong>إدارة مساحات العمل المحمولة</strong>.</li>
<li>حدد مساحة العمل المحمولة <strong>إدارة المصروفات</strong>.</li>
<li>انقر فوق <strong>نشر مساحة العمل المحمولة</strong>.</li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-finance-and-operations-mobile-app"></a>تنزيل وتثبيت تطبيق Finance and Operations للأجهزة المحمولة.
يمكنك تنزيل وتثبيت تطبيق Finance and Operations للأجهزة المحمولة من متجر تطبيقات المحمول.

-   لـ Android: [Finance and Operations على Google Play Store](https://play.google.com/store/apps/details?id=com.microsoft.dynamics365.operations.mobile)
-   لـ iPhone: [Finance and Operations على iTunes apps store](https://itunes.apple.com/us/app/dynamics-365-for-operations/id1180836730?mt=8)

## <a name="sign-in-to-the-finance-and-operations-mobile-app"></a>تسجيل الدخول إلى تطبيق Finance and Operations للأجهزة المحمولة
1.  ابدأ تشغيل التطبيق على جهازك المحمول.
2.  أدخل عنوان URL لتطبيق Finance and Operations.
3.  أدخل الشركة لتسجيل الدخول إلى. على سبيل المثال، أدخل **USMF**.
4.  في المرة الأولى التي تقوم بتسجيل الدخول فيها، تتم مطالبتك باسم المستخدم وكلمة المرور الخاصة بحسابك في تطبيق Finance and Operations. أدخل بيانات اعتمادك.
5.  بعد تسجيل الدخول، يمكنك رؤية مساحات العمل المتوفرة لشركتك. تجدر الإشارة إلى أنه في حال قيام مسؤول النظام بنشر مساحة عمل جديدة في وقت لاحق، يمكنك السحب لتحديث قائمة مساحات العمل المحمولة. 

[![سحب للتحديث](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="capture-a-receipt-by-using-the-expense-management-mobile-workspace"></a>التقاط إيصال باستخدام مساحة العمل المحمولة لإدارة المصروفات
1.  على جهازك المحمول، حدد مساحة عمل **إدارة المصروفات**.
2.  حدد **التقاط الإيصال**.
3.  حدد **التقاط صورة‬** أو **اختيار صورة**.
4.  إذا حددت **التقاط صورة‬**، فاتبع الخطوات التالية:
    1.  يتم نقلك إلى الكاميرا على جهازك المحمول، بحيث يمكنك التقاط صورة للإيصال. عند الانتهاء من التقاط صورة، انقر فوق **موافق** للموافقة على الصورة.
    2.  اختياري: أدخل اسمًا للصورة، ثم أدخل أية ملاحظات.

     **أو:**  إذا حددت **اختيار صورة**، فاتبع الخطوات التالية:
    1.  حدد صورة في القائمة.
    2.  اختياري: أدخل اسمًا للصورة، ثم أدخل أية ملاحظات.

5.  حدد **تم**.

## <a name="quick-expense-entry-by-using-the-expense-management-mobile-workspace"></a>إدخال مصروفات سريعة باستخدام مساحة العمل المحمولة لإدارة المصروفات
1.  على جهازك المحمول، حدد مساحة عمل **إدارة المصروفات**.
2.  حدد **إدخال مصروفات سريعة**.
3.  حدد فئة المصروفات. يمكن الآن رؤية قائمة بفئات المصروفة تم تحميلها على تطبيقك للاستخدام دون اتصال. بشكل افتراضي، تم تحميل 50 صنف كحدٍ أقصى، ولكن باستطاعة المطور تغيير هذا الرقم. للحصول على مزيد من المعلومات، يجب على المطورين الاطلاع على [النظام الأساسي للمحمول Finance and Operations](/dynamics365/unified-operations/dev-itpro/mobile-apps/mobile-platform). إذا لم تكن الفئة المطلوبة في القائمة، فحدد **بحث** للقيام ببحث عبر الإنترنت في Finance and Operations. ابحث حسب فئة المصروفات، أو قم بالتبديل إلى البحث حسب نوع المصروفات.
4.  أدخل تاريخ الحركة للمصروفات.
5.  اختياري: أدخل التاجر للمصروفات.
6.  أدخل مبلغ المصروفات.
7.  حدد عملة المصروفات. يمكن الآن رؤية قائمة بأكواد العملات التي تم تحميلها على تطبيقك للاستخدام دون اتصال. بشكل افتراضي، تم تحميل 400 عملة كحدٍ أقصى، ولكن باستطاعة المطور تغيير هذا الرقم. للحصول على مزيد من المعلومات، يجب على المطورين الاطلاع على [النظام الأساسي للمحمول Finance and Operations](/dynamics365/unified-operations/dev-itpro/mobile-apps/mobile-platform). إذا لم تكن العملة المطلوبة في القائمة، فحدد **بحث** للقيام ببحث عبر الإنترنت في Finance and Operations. ابحث حسب العملة أو قم بالتبديل إلى البحث حسب الاسم.
8.  حدد **التقاط صورة‬** أو **اختيار صورة**.
9.  إذا حددت **التقاط صورة**، فسيتم نقلك إلى الكاميرا على جهازك المحمول، بحيث يمكنك التقاط صورة للإيصال. عند الانتهاء من التقاط صورة، انقر فوق **موافق** للموافقة على الصورة.  أو إذا حددت **اختيار صورة**، فحدد صورة في القائمة.
10. حدد **تم**.





