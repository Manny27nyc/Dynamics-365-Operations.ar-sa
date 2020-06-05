---
title: تمكين مصادقة Azure Active Directory لتسجيل الدخول إلى نقطة البيع
description: يشرح هذا الموضوع كيفية تكوين تجربة تسجيل الدخول إلى نقطة البيع (POS) في Microsoft Dynamics 365 Commerce بحيث تستخدم مصادقة Azure Active Directory.
author: boycezhu
manager: annbe
ms.date: 03/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: boycezhu
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: dfc49585434383385b6b993893d93b95ef888384
ms.sourcegitcommit: ff6dde637d2f5d2bd18a582eb41573d4c69acdd6
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/08/2020
ms.locfileid: "3248930"
---
# <a name="enable-azure-active-directory-authentication-for-pos-sign-in"></a>تمكين مصادقة Azure Active Directory لتسجيل الدخول إلى نقطة البيع
[!include [banner](includes/banner.md)]


عدد كبير من العملاء ممن يستخدمون Microsoft Dynamics 365 Commerce يستخدمون أيضًا خدمات سحابية أخرى من Microsoft، وقد يستخدمون Azure Active Directory (Azure AD) لإدارة بيانات اعتماد المستخدم لهذه الخدمات. وفي هذه الحالات، قد يرغب العملاء في استخدام حساب Azure AD نفسه عبر التطبيقات. يشرح هذا الموضوع كيفية تكوين تجربة تسجيل الدخول إلى نقطة البيع (POS) في Commerce لاستخدام مصادقة Azure AD.

## <a name="configure-azure-ad-authentication"></a>تكوين مصادقة Azure AD

لجعل Azure AD متوفرًا كأسلوب مصادقة لتسجيل الدخول إلى نقطة البيع في متجر ما، يجب تكوين إعدادات ملف تعريف الوظائف الخاصة بالمتجر ثم تطبيق هذه الإعدادات على عملاء نقطه البيع.

لتكوين ملف تعريف الوظائف، اتبع هذه الخطوات.

1. انتقل إلى **Retail and Commerce** \> **إعداد القناة** \> **إعداد نقطة البيع** \> **ملفات تعريف نقاط البيع** \> **ملفات تعريف الوظائف**.
1. حدد ملف تعريف الوظائف لتغييره.
1. على علامة التبويب السريعة **الوظائف**، في القسم **تسجيل دخول الموظفين إلى نقطة البيع**، قم بتغيير قيمة الحقل **أسلوب مصادقة تسجيل الدخول** من **معرف الموظف وكلمة المرور** إلى **Azure Active Directory**.

بشكل افتراضي، تستخدم جميع ملفات تعريف الوظائف **معرف الموظف وكلمة المرور** كأسلوب مصادقة نقطة البيع. وبالتالي، يجب تغيير قيمة حقل **أسلوب مصادقة تسجيل الدخول** إذا أردت استخدام Azure AD. سيتأثر كل متجر للبيع بالتجزئة مرتبط بملف تعريف الوظائف المحددة بهذا التغيير.

لتطبيق الإعدادات على عملاء نقطة البيع، اتبع الخطوات التالية.

1. انتقل إلى **Retail and Commerce** \> **تكنولوجيا معلومات البيع بالتجزئة والتجارة** \> **جدول التوزيع**.
1. شغّل جدول توزيع **1070** (**تكوين قناة**).

> [!NOTE]
> تتطلب مصادقة Azure AD اتصال إنترنت. ولن تعمل عندما تكون نقطة البيع في وضع عدم الاتصال.

## <a name="associate-an-azure-ad-account-with-a-worker"></a>ربط حساب Azure AD بعامل

قبل أن يتمكن عامل المتجر من استخدم حساب Azure AD لتسجيل الدخول إلى تطبيق نقطة البيع، يجب ربط حساب Azure AD بهذا العامل.

لربط حساب Azure AD بعامل، اتبع الخطوات التالية.

1. انتقل إلى **البيع بالتجزئة والتجار** \> **الموظفون** \> **العاملون**.
1. افتح صفحة تفاصيل العامل.
1. في جزء الإجراءات، في علامة تبويب **Commerce**، في مجموعة **الهوية الخارجية**، حدد **إقران هوية موجودة**.
1. في مربع الحوار **استخدام هوية خارجية موجودة**، حدد **البحث باستخدام البريد الإلكتروني**، وأدخل عنوان بريد إلكتروني في Azure AD، ثم حدد **بحث**.
1. حدد حساب Azure AD المرتجع، ثم حدد **موافق**.

ستتم تعبئة حقول **الاسم المستعار** و**UPN** و**المعرف الفرعي الخارجي** على علامة تبويب **Commerce** في صفحة تفاصيل العامل.

## <a name="additional-resources"></a>الموارد الإضافية

[إعداد وظيفة تسجيل الدخول الموسع لـ MPOS وCloud POS](extended-logon.md)

[إنشاء ملف تعريف وظائف البيع بالتجزئة](retail-functionality-profile.md)

[ تكوين عامل](https://docs.microsoft.com/dynamics365/commerce/tasks/worker)