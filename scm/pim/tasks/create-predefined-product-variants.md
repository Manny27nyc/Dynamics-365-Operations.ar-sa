--- 
title: "إنشاء متغيرات المنتج المعرفة مسبقًا"
description: "يتناول هذا الإجراء إنشاء متغيرات المنتجات لأصل المنتج باستخدام مجموعات أبعاد المنتجات."
author: BibiSp
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: fd6e6844b5920ba1364fa0fd5865d89d83789973
ms.contentlocale: ar-sa
ms.lasthandoff: 07/28/2017

---
# <a name="create-predefined-product-variants"></a>إنشاء متغيرات المنتج المعرفة مسبقًا

[!include[task guide banner](../../includes/task-guide-banner.md)]

يتناول هذا الإجراء إنشاء متغيرات المنتجات لأصل المنتج باستخدام مجموعات أبعاد المنتجات. شركة بيانات العرض التوضيحي المُستخدمة لإنشاء هذا الإجراء هي USMF.


## <a name="create-a-product-master"></a>إنشاء أصل منتج
1. ‏‫انتقل إلى إدارة معلومات المنتج‬ > المنتجات > أصول المنتجات‬‬.
2. انقر فوق "جديد".
3. في الحقل "رقم المنتج"، اكتب قيمة.
    * يجب إدخال رقم منتج يدويًا فقط إذا لم يتم إعداد تسلسل رقمي للحقل "رقم المنتج". بمعنى آخر، تجاوز الخطوة إذا تم تعيين تسلسل الرقم للحقل.  
4. في الحقل "اسم المنتج"، اكتب قيمة.
5. في الحقل "مجموعة بُعد المنتج"، أدخل قيمة أو حددها.
    * حدد مجموعة بُعد المنتج SizeCol (الحجم واللون).  
6. انقر فوق "موافق".

## <a name="add-product-dimensions"></a>إضافة أبعاد المنتجات
1. انقر فوق "أبعاد المنتجات".
    * يوضح هذا المثال كيفية إدخال أبعاد المنتجات يدويًا. يمكنك كذلك اختيار تحديد الحجم أو اللون أو مجموعة النمط التي تتضمن قيم بُعد المنتج الذي تريد استخدامه.  
2. انقر فوق "جديد".
3. في القائمة، قم بوضع علامة للصف المحدد.
4. في حقل "الحجم"، أدخل قيمة أو حددها.
5. في حقل "الاسم"، اكتب قيمة.
6. انقر فوق جديد.
7. في القائمة، قم بوضع علامة للصف المحدد.
8. في حقل "الحجم"، أدخل قيمة أو حددها.
9. في حقل "الاسم"، اكتب قيمة.
10. انقر فوق علامة التبويب "الألوان".
11. انقر فوق "جديد".
12. في القائمة، قم بوضع علامة للصف المحدد.
13. في الحقل "اللون"، أدخل قيمة أو حددها.
14. في حقل "الاسم"، اكتب قيمة.
15. انقر فوق جديد.
16. في القائمة، قم بوضع علامة للصف المحدد.
17. في الحقل "اللون"، أدخل قيمة أو حددها.
18. في حقل "الاسم"، اكتب قيمة.
19. انقر فوق "حفظ".
20. قم بإغلاق الصفحة.

## <a name="generate-product-variants"></a>إنشاء متغيرات المنتج
1. انقر فوق "متغيرات المنتج".
2. انقر فوق "اقتراحات المتغيرات".
3. انقر فوق "تحديد الكل".
    * في هذا المثال، يتم تحديد كافة المتغيرات الممكنة. في حالة استخدام مجموعة فرعية محتملة من مجموعات أبعاد المنتجات لإنشاء متغيرات، فإنه يمكنك تحديد الإدخالات الفردية.  
4. انقر فوق "إنشاء".
    * يمكنك إنشاء أوصاف لكافة المتغيرات التي تعتمد على مجموعة قيم أبعاد المنتجات. الأوصاف اختيارية.  
5. انقر فوق "حفظ".

