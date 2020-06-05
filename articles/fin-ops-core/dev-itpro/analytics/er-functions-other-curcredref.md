---
title: CURCREDREF ER وظيفة
description: يوفر هذا الموضوع معلومات حول كيفية استخدام وظيفة إعداد التقارير الإلكتروني CURCREDREF (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6e684a8e063cb3c049d13005cbcf6ebbe688af00
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041482"
---
# <a name="CURCREDREF">CURCREDREF ER وظيفة</a>

[!include [banner](../includes/banner.md)]

تُرجع الوظيفة `CURCREDREF` قيمة *سلسلة* تُمثل مرجع دائن، بناءً على أرقام رقم الفاتورة المُحددة.

## <a name="syntax"></a>بناء الجملة

```vb
CURCREDREF (invoice number digits)
```

## <a name="arguments"></a>الوسائط

`invoice number digits`: *السلسلة*

قيمة نصية تمثل الأرقام الخاصة برقم الفاتورة.

## <a name="return-values"></a>إرجاع القيم

*السلسلة*

القيمة النصية الناتجة.

## <a name="example"></a>مثال

يُرجع التعبير `CURCredRef ("VEND-200002")` **"2200002"**.

## <a name="additional-resources"></a>الموارد الإضافية

[دالات أخرى (خاصة بمجال الأعمال)](er-functions-category-other.md)