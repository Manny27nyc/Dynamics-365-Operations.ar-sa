---
title: FIRSTORNULL ER وظيفة
description: 'يشرح هذا الموضوع كيفية استخدام وظيفة التقارير الإلكترونية FIRSTORNULL (ER) '
author: NickSelin
manager: kfend
ms.date: 11/29/2019
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
ms.openlocfilehash: 86c8a0ae21ffeb6268efbbd198f7c709c2ad54f6
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042103"
---
# <a name="FIRSTORNULL">FIRSTORNULL ER وظيفة</a>

[!include [banner](../includes/banner.md)]

تُعيد الوظيفة `FIRSTORNULL` السجل الأول من القائمة المُحددة كقيمة *حاوية (سجل)*، إذا لم يكن هذا السجل فارغًا. إذا كان السجل فارغًا، تُرجع هذه الوظيفة قيمة *حاوية (سجل)* فارغة.

## <a name="syntax"></a>بناء الجملة

```vb
FIRSTORNULL (list)
```

## <a name="arguments"></a>الوسائط

`list`: *قائمة السجلات*

مسار صالح لمصدر بيانات من نوع البيانات *قائمة السجلات*.

## <a name="return-values"></a>إرجاع القيم

*حاوية (سجل)*

قيمة السجل الناتجة.

## <a name="example"></a>مثال

يُرجع التعبير `FIRSTORNULL(SPLIT("",1)).Value` سلسلة فارغة (**""**).

## <a name="additional-resources"></a>الموارد الإضافية

[دالات القائمة](er-functions-category-list.md)