---
title: تحميل الملفات الثابتة وخدمتها
description: يوضح هذا الموضوع كيفية تحميل ملف ثابت إلى منشئ موقع Microsoft Dynamics 365 Commerce ، وكيفية إنشاء عنوان URL مخصص واسم ملف يمكن استخدامه لطلب هذا الملف.
author: StuHarg
manager: annbe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 981bbf03480abfd812b4020173b7acfdad0fef14
ms.sourcegitcommit: 597476103bb695e3cbe6d9ffcd7a466400346636
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/20/2020
ms.locfileid: "4594940"
---
# <a name="upload-and-serve-static-files"></a>تحميل الملفات الثابتة وخدمتها

[!include [banner](../includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

يوضح هذا الموضوع كيفية تحميل ملف ثابت إلى منشئ موقع Microsoft Dynamics 365 Commerce ، وكيفية إنشاء عنوان URL مخصص واسم ملف يمكن استخدامه لطلب هذا الملف.

تتطلب بعض موصلات الجهات الخارجية استضافة ملف وعرضه من موقع التجارة الإلكترونية. وتتوقع هذه الموصلات أنه سيتم إرجاع الملف عن طريق الطلبات إلى مسار URL واسم الملف لرد الاتصال. لذلك، يشرح هذا الموضوع كيفية تحميل وتقديم ملف ثابت يحتوي على عنوان URL واسم ملف يمكن تعريفهما بواسطة المستخدم على موقع التجارة الإلكترونية لـ Dynamics 365 Commerce .

## <a name="create-a-site-url-that-returns-a-static-file"></a>إنشاء عنوان URL لموقع يقوم بإرجاع ملف ثابت

لإنشاء عنوان URL لموقع يقوم بإرجاع ملف ثابت في منشئ موقع التجارة، اتبع الخطوات التالية.

1. انتقل إلى مكتبة الوسائط الخاصة بموقعك، وقم بتحميل الملف الذي يجب أن تقدمه بواسطة الطلبات إلى عنوان URL الذي ستقوم بتعريفه. إذا قمت بالفعل بتحميل الملف، يمكنك تخطي هذه الخطوة.
1. انتقل إلى **عناوين URL** لموقعك.
1. حدد **جديد \> عنوان URL جديد**.
1. في مربع الحوار **عنوان URL جديد** ، حدد **أصول مكتبة الوسائط**.
1. في الحقل **مسار URL** ، أدخل مسار URL. قم بتضمين اسم الملف في المسار.
1. حدد **التالي**. يتم فتح مكتبة الوسائط وعرض جميع أصول الوسائط من نوع **المستند** الذي تم تحميله.
1. حدد الملف الذي يجب تقديمه للطلبات إلى عنوان URL الذي حددته في الخطوة 5.
1. حدد **حفظ**.

وفي هذه المرحلة، يكون عنوان URL الذي قمت بإنشائه في حالة المسودة. لن يتم إرجاع الملف الذي يشير إليه عنوان URL حتى تقوم بنشر عنوان URL. قبل نشر عنوان URL، يمكنك التحقق من أنه يقوم بإرجاع البيانات الصحيحة.

## <a name="validate-and-publish-a-url"></a>تحقق من صحة عنوان URL وانشره

للتحقق من صحة عنوان URL قبل نشره، اتبع هذه الخطوات.

1. انتقل إلى **عناوين URL** لموقعك، وحدد عنوان URL لمعاينته.
2. في جزء الخصائص على اليمين، أسفل الزر **تحرير** ، حدد ارتباط عنوان URL الصحيح. يتم فتح نافذة متصفح جديدة، ويتعين أن تتلقى خطأ 404.
3. قم بإلحاق سلسلة الاستعلام **?preview=inprogress** بعنوان URL (على سبيل المثال، `https://yoursite.com/callback.html?preview=inprogress`)، وأعد تحميل الصفحة. يجب إرجاع الملف الذي قمت بتحميله إلى مكتبة الوسائط في الاستجابة.

بعد التحقق من صحة عنوان URL، يمكنك نشره.

1. انتقل إلى **عناوين URL** لموقعك، وحدد عنوان URL.
2. في شريط الأوامر، حدد **نشر** .

## <a name="update-the-file-that-a-url-points-to"></a>قم بتحديث الملف الذي يشير إليه عنوان URL

بعد نشر عنوان URL، يمكنك تحديثه بحيث يشير إلى ملف مختلف. بدلاً من ذلك، يمكنك تحديث عنوان URL بحيث يشير إلى نوع مختلف من الموارد، كما هو موضح في القسم التالي. على سبيل المثال، يمكنك توجيه عنوان URL إلى صفحة داخلية أو إعادة توجيه.

لتحديث الملف الذي يشير إليه عنوان URL، اتبع هذه الخطوات.

1. انتقل إلى **عناوين URL** لموقعك، وحدد عنوان URL لتحديثه.
1. في جزء الخصائص على اليمين، حدد **تحرير**.
1. ضمن **تعيين عنوان URL**، حدد المربع **الخطوة 2** ، ثم حدد مستندًا جديدًا من مكتبه الوسائط.
1. حدد **تطبيق**.

## <a name="update-the-asset-type-that-a-url-points-to"></a>قم بتحديث نوع الأصل الذي يشير إليه عنوان URL

يمكنك أيضًا تحديث عنوان URL بحيث يشير إلى نوع مختلف من الأصول (الموارد)، مثل صفحة داخلية أو إعادة توجيه.

لتحديث نوع الأصل الذي يشير إليه عنوان URL، اتبع هذه الخطوات.

1. انتقل إلى **عناوين URL** لموقعك، وحدد عنوان URL لتحديثه.
1. في جزء الخصائص على اليمين، حدد **تحرير**.
1. ضمن **تعيين عنوان URL** ، ضمن **الخطوة 1**، حدد نوع أصل مختلف.
1. حدد المربع **الخطوة 2** ، ثم حدد الأصل الجديد.
1. حدد **تطبيق**.

## <a name="change-the-url-path"></a>تغيير مسار URL

بعد إنشاء عنوان URL، لا يمكن تغيير مساره. إذا كان يجب عليك تغيير مسار عنوان URL الذي يخدم ملفًا أو أي نوع آخر من الموارد، فيتعين عليك إنشاء عنوان URL جديد، وتعيينه إلى الملف الموجود أو مورد آخر، ثم إلغاء نشر عنوان URL القديم وحذفه.

لتغيير مسار عنوان URL، اتبع هذه الخطوات.

1. لإنشاء عنوان URL جديد وتعيينه إلى الملف الحالي أو مورد آخر، اتبع التعليمات الواردة في القسم [‏‫إنشاء عنوان URL لموقع يقوم بإرجاع ملف ثابت](#create-a-site-url-that-returns-a-static-file) سابقًا في هذا الموضوع.
1. حدد عنوان URL الجديد، وحدد **نشر** في شريط الأوامر. يتم نشر عنوان URL الجديد.
1. لإلغاء نشر عنوان URL القديم، حدده ، ثم حدد **إلغاء النشر** في شريط الأوامر. يمكنك الآن حذف عنوان URL القديم إذا كنت تري ذلك.

## <a name="additional-resources"></a>الموارد الإضافية

[نظرة عامة على إدارة الأصول الرقمية](dam-overview.md)

[تحميل صور](dam-upload-images.md)

[تحميل مقاطع فيديو](dam-upload-video.md)

[تحميل ملفات غير الصور ومقاطع الفيديو](dam-upload-files.md)

[اقتصاص الصور](dam-crop-images.md)

[تخصيص نقاط تركيز الصورة](dam-custom-focal-point.md)