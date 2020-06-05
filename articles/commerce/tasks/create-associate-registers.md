---
title: " إنشاء وربط سجلات"
description: يوضح هذا الإجراء كيفية إنشاء سجل نقطة البيع.
author: rubencdelgado
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailTerminalTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 001bdd61f9266798dadae2ac7c96a4f4c19dbb94
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141443"
---
# <a name="create-and-associate-registers"></a> إنشاء وربط سجلات

[!include [banner](../includes/banner.md)]

يوضح هذا الإجراء كيفية إنشاء سجل نقطة البيع. يستخدم هذا الإجراء شركة بيانات العرض التوضيحي USRT.

1. انتقل إلى البيع بالتجزئة والتجارة > إعداد القناة > إعداد نقطة البيع > السجلات.
2. انقر فوق جديد.
3. في الحقل "رقم السجل" اكتب معرف السجل الجديد.
    * يتضمن "معرف السجل" عادةً أكوادًا قد تساعد على تعيين السجل إلى المتجر الذي ينتمي إليه والموقع داخل المخزن.  
4. في حقل "الاسم"، اكتب اسمًا وصفيًا للسجل.
5. في الحقل "رقم المتجر"، أدخل قيمة أو حددها.
6. في الحقل "ملف تعريف الأجهزة"، أدخل قيمة أو حددها.
    * يتم استخدام ملفات تعريف الأجهزة لتحديد الأجهزة الطرفية التي سيتم توصيلها بالسجل، مثل درج الأوراق النقدية وطابعة الإيصالات.  
7. في حقل "ملف التعريف المرئي‬"، أدخل قيمة أو حددها.
    * يتم استخدام ملفات التعريف المرئية لتحديد الصور المستخدمة في خلفية نقطة البيع وصفحة تسجيل الدخول بالإضافة إلى نُسق نقطة البيع.  
8. في الحقل "رقم تسجيل نقطة بيع EFT"، اكتب قيمة.
    * يتم استخدام "رقم تسجيل نقطة بيع EFT" لإعلام معالج الدفع بمحطة الدفع الطرفية التي تُرسل طلبات التفويض. غالبًا ما تسمى هذه القيمة "معرف المحطة الطرفية" أو "TID". يمكن العثور على TID عادةً على ملصق على جهاز الدفع.  
9. انقر فوق "حفظ".
