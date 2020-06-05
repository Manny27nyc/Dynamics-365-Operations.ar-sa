---
title: أوامر الشراء لمشروع
description: توضح هذه المقالة مختف الأساليب التي يمكنك استخدامها لإنشاء أوامر شراء لمشروع. يتوقف الأسلوب الذي تستخدمه على غرض أمر الشراء، والوقت الذي يتم فيه استهلاك الأصناف التي تم شراؤها وتحميل المشروع تكاليفها.
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 83972
ms.assetid: 247e4d72-610b-4fa5-9873-601ed0f4b2d6
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a4975b9f9e20906fb1259e36a07d8ef3db4f4fee
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174548"
---
# <a name="purchase-orders-for-a-project"></a>أوامر الشراء لمشروع

[!include [banner](../includes/banner.md)]

توضح هذه المقالة مختف الأساليب التي يمكنك استخدامها لإنشاء أوامر شراء لمشروع. يتوقف الأسلوب الذي تستخدمه على غرض أمر الشراء، والوقت الذي يتم فيه استهلاك الأصناف التي تم شراؤها وتحميل المشروع تكاليفها.

### <a name="methods-for-creating-a-purchase-order"></a>أساليب لإنشاء أمر شراء

يمكنك استخدام أحد الأساليب التالية لإنشاء أمر شراء في المحاسبة وإدارة المشروع. يحدد غرض أمر الشراء الوقت الذي سيتم فيه استهلاك فيه أمر الشراء، وبالتالي إلى تحديد الوقت الذي سيتم فيه تحميل المشروع تكاليف الأصناف.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>الأسلوب</th>
<th>الغرض</th>
<th>استهلاك الأصناف</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>إنشاء أمر شراء مباشرةً من مشروع.</td>
<td>استخدم هذه الطريقة لشراء أصناف من مورد خارجي للاستهلاك في مشروع. يمكنك إنشاء أمر الشراء باستخدام طريقتين:
<ul>
<li>من المشروع نفسه. وفي هذه الحالة يكون المشروع معرفًا بالفعل لأمر الشراء.</li>
<li>عن طريق الانتقال إلى أمر شراء المشروع. يجب تحديد كل من المورد والمشروع المراد إنشاء أمر الشراء لهما.</li>
</ul></td>
<td>يتم استهلاك الأصناف عندما يتم تحديث فاتورة المورد.</td>
</tr>
<tr class="even">
<td>إنشاء أمر شراء من أمر توريد.</td>
<td>استخدم هذا الأسلوب لشراء الأصناف عندما تنشئ أمر مبيعات من مشروع.</td>
<td>يتم استهلاك الأصناف عند فوترة أمر التوريد إلى العميل.</td>
</tr>
<tr class="odd">
<td>إنشاء أمر شراء من أحد متطلبات الصنف.</td>
<td>استخدم هذا الأسلوب لشراء الأصناف عندما تنشئ أحد متطلبات الصنف من مشروع.</td>
<td>يتم استهلاك الأصناف عندما يتم تحديث إيصال تعبئة متطلبات الصنف.</td>
</tr>
</tbody>
</table>

> [!NOTE] 
> عند تحديث فاتورة المورد أو إيصال تعبئة، فإنه تتم مطالبتك بتحديث إيصال التعبئة الخاص بمتطلبات الصنف.

للحصول على مزيد من المعلومات، راجع [تلقي الأصناف على أمر شراء من طلبات الصنف‬](tasks/receive-items-purchase-order-item-requirement.md).
