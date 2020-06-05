---
title: إنشاء أصول استنادًا إلى أوامر الشراء
description: يشرح هذا الموضوع كيفية إنشاء قائمة تتضمن أصناف الأصول التي يمكن استخدامها كأساس لإنشاء أصول لمهام الصيانة في إدارة الأصول.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8dd52d877ee7f862577d8bfea113f22eca03c597
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/02/2020
ms.locfileid: "3209871"
---
# <a name="create-assets-based-on-purchase-orders"></a>إنشاء أصول استنادًا إلى أوامر الشراء

[!include [banner](../../includes/banner.md)]

 

يشرح هذا الموضوع كيفية إنشاء قائمة تتضمن أصناف الأصول التي يمكن استخدامها كأساس لإنشاء أصول لمهام الصيانة في إدارة الأصول. استنادًا إلى أصناف الأصول، يمكنك عرض قائمة ببنود أوامر الشراء التي تم إنشاؤها على هذه الأصناف. الغرض من هذه الوظيفة هو إنشاء أصل بسهولة في إدارة الأصول استنادًا إلى أمر شراء.

أولاً، يمكنك إعداد الأصناف المراد استخدامها لإنشاء أصول من أمر شراء في **أصناف الأصول**. بعد إنشاء بند أمر شراء، يمكنك إنشاء الأصول في **الأصول المعلقة**. من الممكن تحديد المرحلة في بند الشراء التي يجب فيها إنشاء الأصل.


## <a name="select-asset-items"></a>تحديد أصناف الأصول

1. انقر فوق **إدارة الأصول** > **الإعداد** > **الأصول‏‎** > **الأصناف**.
2. انقر فوق **جديد** لإنشاء صنف أصل جديد.
3. في الحقل **رقم الصنف**، حدد الصنف. عندما تغدر هذا الحقل، يتم إدراج اسم الصنف بشكل تلقائي في حقل **اسم المنتج**.
4. على علامة التبويب السريعة **عام** حدد نوع أصل للصنف.
5. حدد الشركة المصنعة للأصل ونموذج الصنف.
6. احفظ الصنف.


## <a name="create-assets-from-pending-assets"></a>إنشاء أصول من أصول معلقة

1. انقر فوق **إدارة‏‎ الأصول‏‎** > **عام** > **الأصول‏‎** > **الأصول‏‎ المعلقة**.
2. سترى قائمة محدثة بأوامر الشراء استنادًا إلى الأصناف المحددة في **أصناف الأصول**.
3. يمكنك تصفية حالة أوامر الشراء لتحديد حالة دورة الحياة التي يجب إنشاء الأصل عندها. على سبيل المثال، قد ترغب فقط في إنشاء أصول عند ترحيل إيصال منتج في أمر شراء.
4. حدد الارتباط‏‎ **رقم المرجع** في بند أمر شراء لعرض معلومات مفصلة حول الصنف.
5. إذا كنت ترغب في تحرير الأبعاد التي تظهر على علامة التبويب السريعة **أبعاد المخزون**، فانقر فوق الزر **عرض الأبعاد**، وبعد ذلك يمكنك إجراء تحديداتك.
6. إذا كنت ترغب في إنشاء أصل استنادًا إلى بند أمر شراء، فحدد خانة الاختيار في العمود **علامة** لهذا البند في صفحة القائمة، وانقر فوق **إنشاء أصول**. ستظهر رسالة تعلمك بمعرف الأصل.
7. حدد الأصل في قائمة **كل الأصول** وانقر فوق **تحرير** لإضافة مزيد من المعلومات إلى الأصل.
8. في **الأصول‏‎ المعلقة**، إذا أردت حذف بند لأنك لا تريد إنشاء أصل، فحدد خانة الاختيار في العمود **علامة** لهذا البند، وانقر فوق **تجاهل الأصول المعلقة**. ستظهر رسالة تعلمك بمعرف الأصل. أنت لا تحذف أمر الشراء أو أمر المبيعات، بل فقط السجل الذي كان بإمكانك إنشاء أصل منه في **إدارة الأصول**.

>[!NOTE]
>يتم نقل جميع أبعاد المنتج (الحجم واللون والتكوين وما إلى ذلك) تلقائيًا إلى سمات الأصول. يتم تخزين أبعاد التتبع (الرقم التسلسلي) مباشرة ً على الأصل عند إنشاء الأصل.


## <a name="find-pending-assets"></a>البحث عن الأصول المعلقة

يمكنك تشغيل عملية **تعداد الأصول المعلقة** للتحقق من الأصول المعلقة. على سبيل المثال، يمكن استخدام هذه الوظيفة لتلقي إشعار في كل مرة يكون فيها الأصل المعلق جاهزًا لإنشائه كأصل.

1. انقر فوق **إدارة‏‎ الأصول‏‎** > **دوري** > **الأصول‏‎** > **تعداد الأصول‏‎ المعلقة**.
2. انقر فوق **موافق** لتشغيل الوظيفة وتحديث القائمة في **الأصول المعلقة**.
3. يمكنك إعداد هذه الوظيفة لتشغيلها وظيفة دفعية، على سبيل المثال، مرة كل يوم.

**تحذير:** إذا تغيرت البيانات في أمر شراء *بعد* إنشاء أصل استنادًا إلى الصنف المتعلق به، لن تظهر هذه التغييرات في الأصل.