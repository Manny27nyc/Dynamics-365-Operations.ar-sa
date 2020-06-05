---
title: إنشاء مستندات تتضمن بيانات التطبيق
description: لإكمال الخطوات المذكورة في هذا الإجراء، يجب عليك أولاً إكمال الإجراء، "التقارير الإلكترونية - إنشاء مستندات بواسطة تحديث بيانات التطبيق (الجزء 4 - تعديل التنسيق)‬".
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dcc00bba4aa92ad089bcab83ee22f79c21ccc252
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141846"
---
# <a name="generate-documents-that-have-application-data"></a>إنشاء مستندات تتضمن بيانات التطبيق

[!include [banner](../../includes/banner.md)]

لإكمال الخطوات المذكورة في هذا الإجراء، يجب عليك أولاً إكمال الإجراء، "التقارير الإلكترونية - إنشاء مستندات بواسطة تحديث بيانات التطبيق (الجزء 4 - تعديل التنسيق)‬".



توضح الخطوات الواردة في هذا الإجراء كيفية تصميم تكوينات التقارير الإلكترونية لإنشاء مستند إلكتروني وتحديث بيانات التطبيق. في هذا الإجراء، يمكنك تنفيذ تكوين تنسيق التقارير الإلكترونية لإنشاء تقرير نظام جمع المعلومات التجارية وتحديث بيانات التطبيق لأرشفة التفاصيل الخاصة بعملية إعداد التقارير.



تم إنشاء هذا الإجراء للمستخدمين الذين لديهم دور مسؤول النظام أو مطور التقارير الإلكترونية. يمكن إتمام هذه الخطوات باستخدام مجموعة بيانات DEMF. قبل أن تبدأ، تأكد من أن سياق البلد الخاص بالشركة DEMF هو BEL (بلجيكا).


## <a name="set-up-foreign-trade-parameters"></a>إعداد محددات التجارة الخارجية
1. انتقل إلى الضريبة > الإعداد > التجارة الخارجية > معلمات التجارة الخارجية.
2. انقر فوق علامة التبويب "التسلسلات الرقمية".

    لأرشفة التفاصيل الخاصة بعملية إعداد تقارير نظام جمع المعلومات التجارية، نحتاج إلى تحديد السجلات لكل أرشيف قمنا بإنشائه. يجب تكوين تسلسلي رقمي خاص لذلك.  

3. حدد المرجع "معرف أرشيف نظام جمع المعلومات التجارية بين دول الاتحاد الأوروبي‬".
4. في الحقل "كود تسلسل الرقم"، اكتب قيمة.

    في حقل "كود التسلسل الرقمي"، أدخل قيمة "Fore_2" أو حددها.  

5. كود التسلسل الرقمي ResolveChanges.
6. انقر فوق حفظ.
7. قم بإغلاق الصفحة.

## <a name="run-modified-er-format"></a>تشغيل تنسيق التقارير الإلكترونية المعدّل
1. انتقل إلى إدارة المؤسسة >إعداد التقارير الإلكتروني >التكوينات.
2. في الشجرة، قم بتوسيع "نظام جمع المعلومات التجارية بين دول الاتحاد الأوروبي (نموذج)".
3. في الشجرة، حدد "نظام جمع المعلومات التجارية بين دول الاتحاد الأوروبي (نموذج)\نظام جمع المعلومات التجارية بين دول الاتحاد الأوروبي (تنسيق)".
4. انقر فوق "تشغيل".
5. في الحقل "إدخال اسم الملف"، اكتب "intrastat2.xml".
6. انقر فوق موافق.

## <a name="review-er-format-executions-results"></a>مراجعة نتائج تنفيذ تنسيق التقارير الإلكترونية
راجع ملف XML المنشأ.  
1. قم بإغلاق الصفحة.
2. انتقل إلى الضريبة > الإقرارات‬ > التجارة الخارجية > نظام جمع المعلومات التجارية بين دول الاتحاد الأوروبي.

    افتح هذا النموذج الذي يحتوي على حركات نظام جمع المعلومات التجارية بين دول الاتحاد الأوروبي المضمنة في المستند الإلكتروني المنشأ.  

3. انقر فوق أرشيف نظام جمع المعلومات التجارية بين دول الاتحاد الأوروبي.

    نظرًا لاحتواء تنسيق التقارير الإلكترونية الذي تم تنفيذه الآن على إعدادات خاصة بتحديث بيانات التطبيق، تمت أرشفة تفاصيل تقرير نظام جمع المعلومات التجارية بين دول الاتحاد الأوروبي المكتمل. في هذا النموذج، يمكنك رؤية سجل الرأس للأرشيف الذي تم إنشاؤه.  

4. انقر فوق "تفاصيل".

    في هذا النموذج، يمكنك رؤية تفاصيل الأرشيف الذي تم إنشاؤه.  

5. قم بإغلاق الصفحة.
6. قم بإغلاق الصفحة.
7. قم بإغلاق الصفحة.
