--- 
title: "إنشاء كتالوج تدبير"
description: "يوضح هذا الدليل كيفية إنشاء كتالوج التدبير."
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 19d053a0bdbdcc764b3361fe5a326e8c68cdc682
ms.contentlocale: ar-sa
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-procurement-catalog"></a>إنشاء كتالوج تدبير

[!include[task guide banner](../../includes/task-guide-banner.md)]

يوضح هذا الدليل كيفية إنشاء كتالوج التدبير. يقوم أخصائي التدبير عادةً بتنفيذ هذه المهمة. ستتعلم أيضًا كيف يستخدم الموظفون الكتالوج عند إنشاء طلب. قبل إنشاء كتالوج، من الضروري وجود تدرج هرمي لفئات التدبير في النظام. يتوارث الكتالوج الجديد التدرج الهرمي، إلى جانب جميع المنتجات الموجودة في التدرج الهرمي. يمكن استخدام هذا الدليل في شركة بيانات العرض التوضيحي USMF حيث يتوفر التدرج الهرمي لفئات التدبير، بالإضافة إلى الأمثلة المستخدمة في خطوات الإجراء.


## <a name="ensure-that-a-procurement-category-hierarchy-exists"></a>التأكد من وجود تدرج هرمي لفئات التدبير
1. انتقل إلى التدبير والتوريد > فئات التدبير.
    * يتوفر التدرج الهرمي لفئات التدبير في شركة بيانات العرض التوضيحي USMF، وتمت إضافة المنتجات إلى فئة الأجهزة المكتبية/أجهزة الكمبيوتر. إذا كنت تنفذ هذا الإجراء كدليل مهمة، فستحتاج إلى إلغاء تأمين الدليل إذا أردت استعراض الفئة. إذا لم يتوفر التدرج هرمي، فيمكنك النقر فوق "جديد" لإنشائه. يمكن إجراء ذلك مرة واحدة فقط.  
2. قم بإغلاق الصفحة.

## <a name="create-a-catalog"></a>إنشاء كتالوج
1. انتقل إلى التدبير وتحديد الموارد > الكتالوجات > كتالوجات التدبير.
2. انقر فوق "كتالوج تدبير جديد" لفتح مربع حوار الإسقاط‬.
3. في حقل "الاسم"، اكتب قيمة.
4. انقر فوق موافق.
5. في الشجرة، قم بتوسيع "فئات التدبير للشركة".
6. في الشجرة، قم بتوسيع "أجهزة المكتب".
7. في الشجرة ، حدد "أجهزة الكمبيوتر"
    * يتم عرض المنتجات من فئة التدبير في القائمة. إذا أردت إضافة منتج إلى الفئة، فستحتاج إلى القيام بذلك على صفحة "التدرج الهرمي لفئات التدبير‬" أو صفحة "تفاصيل الصنف‬".  
    * يحدد نوع التحديث الافتراضي ما إذا كانت المنتجات الجديدة المضافة إلى التدرج الهرمي لفئات التدبير تكون مرئية على الفور في الكتالوج. إذا تم تعيين نوع التحديث إلى "ديناميكي"، فستكون التغييرات مرئية على الفور. إما إذا كان نوع التحديث "ثابت"، فستكون المنتجات الجديدة مرئية فقط للأشخاص الذين يستخدمون الكتالوج بعد إعادة نشر الكتالوج. يتوفر "إجراء النشر" في جزء الإجراءات في أعلى الصفحة. في حالة إزالة منتجات من التدرج الهرمي لفئات التدبير، سيكون التغيير مرئيًا على الفور، بغض النظر عن القيمة الموجودة في حقل نوع التحديث الافتراضي.  
8. في القائمة، قم بالبحث عن السجل المطلوب وحدده.
9. انقر فوق "إخفاء".
10. في جزء الإجراءات، انقر فوق "تنقل الفئة‬".
11. انقر فوق "تعطيل".
12. في جزء الإجراءات، انقر فوق "تنقل الفئة‬".
13. انقر فوق "تمكين".
14. انقر فوق "تنشيط الكتالوج".
15. قم بإغلاق الصفحة.

## <a name="make-the-catalog-visible"></a>جعل الكتالوج مرئيًا
1. انتقل إلى التدبير وتحديد الموارد > إعداد > السياسات > سياسات الشراء.
2. حدد "USMF لسياسة التدبير".
    * يتعينّ عليك تحديد سياسة الشراء للكيان القانوني الذي يُسمح للعامل المرتبط بملف تعريف المستخدم الخاص بك بطلب المنتجات فيه. في بيانات العرض التوضيحي USMF، المستخدم المسؤول مرتبط بالعاملة جوليا فونديربورك، وهي تطلب المنتجات في USMF بشكل افتراضي.  
3. في القائمة، انقر فوق الارتباط في الصف المحدد.
4. حدد الكتالوج الذي قمت بإنشائه للتوّ.
5. انقر فوق "موافق".
6. قم بإغلاق الصفحة.
7. قم بإغلاق الصفحة.

## <a name="use-the-catalog"></a>استخدام الكتالوج
1. انتقل إلى التدبير وتحديد الموارد > طلبات الشراء > كافة طلبات الشراء.
2. انقر فوق "جديد".
3. في حقل "الاسم"، اكتب قيمة.
4. انقر فوق "موافق".
5. انقر فوق "إضافة المنتجات".
6. في القائمة، قم بالبحث عن السجل المطلوب وحدده.
    * يمكنك استخدام التدرج الهرمي للفئات إلى اليمين أو عامل التصفية في أعلى القائمة لتصفية المنتجات.  
7. انقر فوق "إضافة إلى البنود".
8. في القائمة، قم بالبحث عن السجل المطلوب وحدده.
9. انقر فوق "إضافة إلى البنود".
10. انقر فوق "موافق".

