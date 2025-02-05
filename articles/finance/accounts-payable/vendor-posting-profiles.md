---
title: ملفات تعريف ترحيل المورد
description: تتحكم ملفات تعريف ترحيل المورد‬ في ترحيل حركات المورِّدين إلى دفتر الأستاذ العام.
author: abruer
ms.date: 06/12/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 24691
ms.assetid: 18def866-7655-4f0b-b299-eec83098d23a
ms.search.form: VendPosting
ms.openlocfilehash: 922612e536164c7985f0be107f67ad8bbaef7898
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272967"
---
# <a name="vendor-posting-profiles"></a>ملفات تعريف ترحيل المورد

[!include [banner](../includes/banner.md)]

تتحكم ملفات تعريف ترحيل المورد‬ في ترحيل حركات المورِّدين إلى دفتر الأستاذ العام.

## <a name="vendor-posting-profiles"></a>ملفات تعريف ترحيل المورد

تمكنك ملفات تعريف ترحيل المورد من تعيين حسابات دفتر الأستاذ العام وإعدادات الوثيقة لكل الموردين أو مجموعة من الموردين أو مورد واحد. وسيتم استخدام هذه الإعدادات عندما تقوم بإنشاء أوامر شراء وفواتير الموردين والمدفوعات النقدية. ويمكنك في بعض الحركات تحديد ملف تعريف ترحيل يختلف عن إعداد ملفات تعريف الترحيل للحركات بهذه الصفحة وله الأسبقية عليه. ويتم تحديد ملف تعريف الترحيل الافتراضي في علامة التبويب السريعة **دفتر الأستاذ وضريبة المبيعات** في صفحة **معلمات الحسابات الدائنة**. يتم بعد ذلك تضمين ملف تعريف الترحيل الافتراضي تلقائيًا في رأس المستندات الجديدة، حيث يمكنك تغييره إلى ملف تعريف ترحيل مختلف، إذا لزم الأمر.

كما يمكنك إقران تعريفات الترحيل بأنواع ترحيل الحركة في صفحة **تعريفات ترحيل الحركة**. وتتحكم تعريفات الترحيل في ترحيل حركات المورد إلى إلى دفتر الأستاذ العام بدلاً من ملفات تعريف الترحيل.

## <a name="creating-a-posting-profile"></a>إنشاء ملف تعريف ترحيل
### <a name="setup"></a>**الإعداد**

تتيح تحديد حسابات دفتر الأستاذ المستخدمة في ترحيل الحركات التي تستخدم ملف تعريف الترحيل المحدد. حدد كود حساب ورقم حساب أو مجموعة، كلما أمكن، لملف تعريف الترحيل المحدد. في عملية الترحيل، يتم تحديد موقع ملف التعريف الأكثر ملاءمة لكل حركة من خلال البحث عن كود الحساب أو رقم الحساب أو مجموعة الحساب ومجموعة الأرقام الأكثر تحديدًا بالأولوية التالية.

| قيمة حقل **كود الحساب** | قيمة حقل **رقم الحساب/المجموعة**        | أولوية البحث |
|------------------------------|---------------------------------------------|-----------------|
| **الجدول**                    | حساب مورد معين                     | 1               |
| **مجموعة**                    | مجموعة الموردين التي يتم تعيينها للمورد | 2               |
| **الكل**                      | فارغ                                       | 3               |

إذا كنت ترغب في حصول حركات المورد على نفس ملف تعريف الترحيل، فقم بإعداد ملف تعريف ترحيل واحد فقط مع **الكل** في حقل **كود الحساب**. وحدد القيم التالية لإعداد ملف تعريف الترحيل الخاص بك.

<table>
<thead>
<tr class="header">
<th>الحقل</th>
<th>الوصف</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>ملف تعريف الترحيل</strong></td>
<td>أدخل كودًا لملف تعريف الترحيل. على سبيل المثال، يمكن إنشاء ملفي تعريف ترحيل للحصول على حساب واحد لأرصدة المورد بالعملة الوطنية وحساب آخر لأرصدة المورد بالعملة الأجنبية. ويمكن أن تطلق على أحدهما اسم "وطني" والآخر "أجنبي".</td>
</tr>
<tr class="even">
<td><strong>الوصف</strong></td>
<td>يتيح إدخال وصف لملف تعريف الترحيل.</td>
</tr>
<tr class="odd">
<td><strong>كود الحساب</strong></td>
<td>حدد ما إذا كان ملف التعريف الترحيل ينطبق على مورد محدد أم مجموعة موردين أو كافة الموردين أم لا:
<ul>
<li><strong>الجدول</strong> – ينطبق ملف تعريف الترحيل على مورد واحد. حدد حساب المورد في حقل <strong>رقم الحساب/المجموعة</strong>.</li>
<li><strong>المجموعة</strong> – ينطبق ملف تعريف الترحيل على مجموعة موردين. حدد مجموعة الموردين في حقل <strong>رقم الحساب/المجموعة</strong>.</li>
<li><strong>الكل</strong> – ينطبق ملف تعريف الترحيل على كافة الموردين. اترك حقل <strong>رقم الحساب/المجموعة</strong> فارغًا.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>رقم الحساب/المجموعة</strong></td>
<td>في حالة تحديد <strong>الجدول</strong> في حقل <strong>كود الحساب</strong>، حدد رقم حساب المورد المرتبط بملف تعريف الترحيل. وفي حالة تحديد <strong>مجموعة</strong>، حدد مجموعة موردين. وفي حالة تحديد <strong>الكل</strong>، اترك الحقل فارغًا.</td>
</tr>
<tr class="odd">
<td><strong>حساب ملخص</strong></td>
<td>حدد حساب دفتر الأستاذ الذي سيتم استخدامه كحساب الموردين الملخص الذي يرتبط به ملف تعريف الترحيل. سيتم وضع علامة على <strong>‏‫عدم السماح بالإدخال اليدوي</strong> لهذا الحساب الرئيسي. إذا قمت فيما بعد بإزالة هذا الحساب من ملف تعريف الترحيل، فلتحقق من صحة إعداد <strong>عدم السماح بالإدخال اليدوي</strong>في صفحة <strong>الحسابات الرئيسية </strong>. 
<p><strong>ملاحظة:</strong> إذا تم تحديد خيار <strong>استخدام تعريفات الترحيل</strong> في صفحة <strong>معلمات دفتر الأستاذ العام</strong>، فإنه يتم استخدام تعريف ترحيل الحركة لفواتير الموردين بدلاً من الحساب الملخص.</p>
</td>
</tr>
<tr class="even">
<td><strong>تسوية الحساب</strong></td>
<td>حدد حساب دفتر الأستاذ الخاص بالسيولة المستخدم لتنبؤات التدفقات النقدية. تتوفر هذه الحقول فقط عندما يتم تمكين التنبؤ بالتدفقات النقدية.</td>
</tr>
<tr class="odd">
<td><strong>الدفعات المقدمة لضريبة المبيعات</strong></td>
<td>حدد حساب لضريبة المبيعات للمدفوعات التي يتم استلامها مقدمًا.
<p><strong>ملاحظة:</strong> يتم تحديد ملف تعريف الترحيل المستخدم عند وضع علامة على الدفعة كدفعة مقدمة بملف تعريف <strong>الترحيل</strong> في حقل <strong>إيصال دفتر يومية الدفعة المقدمة</strong> في منطقة <strong>دفتر الأستاذ وضريبة المبيعات</strong> في صفحة <strong>معلمات الحسابات الدائنة</strong>.</p>
</td>
</tr>
<tr class="even">
<td><strong>الوصول</strong></td>
<td>حدد رقم حساب دفتر الأستاذ الذي يتم ترحيل معلومات حول فواتير المورد غير المعتمدة إليه. ويتم إدخال المعلومات في دفتر يومية سجل الفواتير. على سبيل المثال، يقوم مستخدم بإدخال معلومات أساسية للغاية حول فواتير المورد عند استلامها في سجل الفواتير. وعند ترحيل سجل الفواتير، يتم ترحيل الحركات إلى الحساب الذي يتم إدخاله هنا في حقل <strong>الحساب المقابل</strong>. وعند اعتماد الفواتير، يتم تحويل الدين من حساب الوصول إلى حساب ملخص المورد.</td>
</tr>
<tr class="odd">
<td><strong>الحساب المقابل</strong></td>
<td>حدد حساب دفتر الأستاذ المستخدم لمقابلة فواتير المورد غير المعتمدة التي يتم تحديثها من خلال استخدام سجل الفواتير. ويعمل الحساب المقابل كحساب مقابل للحركات التي تم ترحيلها إلى حسابات الوصول. ولذلك، يحتوي الحساب على مشتريات الموردين التي لم يتم اعتمادها بعد.</td>
</tr>
</tbody>
</table>


### <a name="table-restrictions"></a>**تقييدات الجداول**

في اللحركات التي تحتوي على ملف تعريف الترحيل المحدد، حدد ما إذا كان ستتم تسوية الحركات تلقائياً، وسيتم حساب الفائدة، وسيتم إصدار خطابات التحصيل. كما يمكنك تحديد الحساب الذي يُستخدم عند إغلاق الحركات المشتملة على ملف تعريف الترحيل المحدد.

حدد القيم التالية لإعداد ملف تعريف الترحيل الخاص بك.

| الحقل          | الوصف                                                                                                                                                                                                    |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **التسوية** | حدد هذا الخيار لتمكين التسوية التلقائية للحركات التي تتضمن ملف تعريف الترحيل هذا. في حالة إلغاء تحديد هذا الخيار، يجب تسوية الحركات يدوياً باستخدام صفحة **تسوية الحركات المفتوحة**. |
| **إلغاء**     | حدد هذا الخيار إذا أردت التمكن من إلغاء الحركات التي تتضمن ملف تعريف الترحيل هذا.                                                                                                               |
| **إغلاق**      | حدد ملف تعريف ترحيل للتغيير إليه عند إغلاق الحركات بملف تعريف الترحيل هذا. ويتم اعتبار الحركة مغلقة عند تسويتها بالكامل.                                       |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
