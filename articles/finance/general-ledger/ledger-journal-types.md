---
title: أنواع دفاتر يومية دفتر الأستاذ
description: يصف هذا الموضوع أنواع دفاتر اليومية التي يمكنك تعيينها لدفاتر اليومية المالية.
author: ShylaThompson
manager: AnnBe
ms.date: 10/10/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 15631
ms.assetid: 81613b31-bc3c-43a0-8474-e01c9a482c40
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2b9ab4eeacc54d2d0ea8e7dc9eb3dd846ffc9e29
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176179"
---
# <a name="ledger-journal-types"></a>أنواع دفاتر يومية دفتر الأستاذ

[!include [banner](../includes/banner.md)]

يصف هذا الموضوع أنواع دفاتر اليومية التي يمكنك تعيينها لدفاتر اليومية المالية. استخدم صفحة **أسماء دفاتر اليومية** لإعداد دفاتر اليومية التي يمكنك استخدامها في Dynamics 365 Finance.

| نوع دفتر اليومية                      | الغرض                       | إدخال الحركات في هذه الصفحة                                |
|-----------------------------------|-------------------------------|----------------------------------------------------------------|
| التوزيع                        | إنشاء حركات التوزيع في دفتر يومية التوزيعات. قبل أن يمكنك إنشاء دفتر يومية توزيع، يجب عليك إنشاء قاعدة توزيع في صفحة **قاعدة توزيع دفتر الأستاذ**.      | طلب توزيع العملية             |
| اعتماد                          | ترحيل فواتير المورد التي تمت الموافقة عليها إلى حسابات دفتر الأستاذ المناسبة.  | دفتر يومية الموافقة على الفواتير                                       |
| عملية عكس الشيكات البنكية               | عكس شيك تم ترحيله. لاستخدام نوع دفتر اليومية هذا، حدد خيار **استخدام عملية المراجعة لعمليات إلغاء الدفع‬** في صفحة **‎محددات إدارة البنك والنقد**.   | عمليات عكس الشيك، إلغاء الدفع                   |
| إلغاء إيصال الإيداع البنكي    | إلغاء قسيمة إيداع. لاستخدام نوع دفتر اليومية هذا، حدد خيار **‏‫استخدام عملية المراجعة لعمليات إلغاء الدفع بإيصال الإيداع‬‬** في صفحة **‎محددات إدارة البنك والنقد**.   | عمليات إلغاء دفع إيصال الإيداع            |
| موازنة                            | معالجة مخصصات الموازنة. لاستخدام نوع دفتر اليومية هذا، حدد خيار **تمكين مخصصات الموازنة** في صفحة **معلمات دفتر الأستاذ العام**. تتضمن إدخالات دفتر يومية الموازنة المعلومات المستندة إلى حسابات دفتر الأستاذ التي تم تحديدها في صفحة **تعريفات الترحيل**.                                                        |                                                                |
| قبول العميل للكمبيالة  | إنشاء حركات وافق عليها العميل للكمبيالات.             | دفتر يومية سحب الكمبيالات‬، دفتر يومية إعادة سحب الكمبيالات‬ |
| حوالة العميل البنكية          | إنشاء ملف حوالة كمبيالة التي يمكن إرسالها إلى البنك الخاصة بمؤسستك. لاستخدام نوع دفتر اليومية هذا، قم بإلغاء تحديد خيار **التسوية التلقائية** في صفحة **معلمات** **الحسابات المدينة**.            | الحوالة                                                     |
| كمبيالة مسحوبة للعميل    | إنشاء حركات كمبيالة مسحوبة للعميل. لاستخدام نوع دفتر اليومية هذا، قم بإلغاء تحديد خيار **إنشاء وترحيل دفتر يومية سحب تلقائياً عند ترحيل الفواتير** في صفحة **طرق الدفع - العملاء**.   | دفتر يومية سحب الكمبيالات                                  |
| دفع العميل                  | إنشاء حركات الدفع الخاصة بالعميل.                             | دفتر يومية المدفوعات             |
| كمبيالة محتج عليها من قِبل العميل | إنشاء حركات كمبيالة محتج عليها من قبل العميل.                    | دفتر يومية الكمبيالات المحتج عليها                               |
| كمبيالة معاد سحبها من قِبل العميل  | إنشاء حركات كمبيالة تم إعادة سحبها للعميل.                     | دفتر يومية إعادة سحب الكمبيالات                                |
| كمبيالة تمت تسويتها من قِبل العميل  | إنشاء حركات تسوية كمبيالات للعميل.                       | دفتر يومية تسوية الكمبيالات                                |
| يوميًا                             | إنشاء الحركات اليومية في دفتر يومية عام.                          | دفتر اليومية العام                                                |
| استبعاد                       | إنشاء حركات استبعاد في دفتر يومية الاستبعاد. لاستخدام نوع دفتر اليومية هذا، حدد خياري **‏‫يُستخدم لعملية الاستبعاد المالي** و**استخدام لعملية توحيد مالي‬** في صفحة **الكيانات القانونية**. قبل أن يمكنك استخدام نوع دفتر اليومية هذا، يجب عليك إنشاء قاعدة استبعاد دفتر أستاذ في صفحة **قاعدة استبعاد دفتر الأستاذ‬**. | استبعاد                                                    |
| موازنة الأصل الثابت                | إنشاء إدخالات سجل موازنة الأصول الثابتة.                                                                                                                                                                                                                                                                                                                 | موازنة الأصل الثابت                                             |
| سجل الفواتير                  | تسجيل المعلومات الأساسية حول فواتير المورّد.                                                                                                                                                                                                                                                                                                           | سجل الفواتير                                               |
| صرف كشف الرواتب              | إصدار المدفوعات المستندة إلى بيانات دفع Payroll. لا يمكنك إدخال الحركات يدويًا في دفتر اليومية هذا. يجب إنشاء كشوف المرتبات وبعد ذلك تقديم تلك البيانات للدفع.                                                                                                                                                              |                                                                |
| دوري                          | إنشاء حركات دورية لدفتر اليومية الدوري.                                                                                                                                                                                                                                                                                                      | دفاتر اليومية الدورية                                              |
| ترحيل الأصول الثابتة                 | ترحيل حركات الأصول الثابتة.                                                                                                                                                                                                                                                                                                                              | الأصول الثابتة                                                   |
| المشروع - المصروفات                | إنشاء حركات مصروفات المشروع.                                                                                                                                                                                                                                                                                                                        | المصروفات                                                        |
| تسوية عملة التقارير     | إنشاء تسويات بعمله التقارير للأرصدة على حسابات دفتر الأستاذ.               | دفاتر يومية تسوية عملة التقارير                         |
| حركات إحصائية            | إنشاء حركات إحصائية.                                                                                                                                                                                                                                                                                                                            |                                                                |
| حوالة المورد البنكية            | إنشاء ملف حوالة سند إذني يمكن إرساله إلى البنك الخاصة بمؤسستك.                                                                                                                                                                                                                                                                      | دفتر يومية الحوالات                                             |
| نفقة المورد               | إنشاء حركات مصروفات المورد                                                                                                                                                                                                                                                                                                                    | دفتر يومية المدفوعات                                                |
| سند إذني لسحب المورد       | سحب السندات الإذنية للمورّد كوسيلة للدفع. لاستخدام نوع دفتر اليومية هذا، قم بإلغاء تحديد خيار **إنشاء وترحيل دفتر يومية سحب تلقائياً عند ترحيل الفواتير** في صفحة **طرق الدفع - الموردون**.                                                                                                                                          | دفتر يومية سحب السندات الإذنية                                   |
| وعاء فواتير المورّد باستثناء الترحيل | إنشاء حركات فواتير المورّد التي لم يتم ترحيلها إلى حساب وصول مؤقت.                                                                                                                                                                                                                                                             | وعاء فواتير الموردين باستثناء تفاصيل الترحيل                  |
| وعاء فواتير الموردين               | إنشاء حركات وعاء فواتير المورد.                                                                                                                                                                                                                                                                                                                    |                                                                |
| تسجيل فاتورة المورّد          | ترحيل فواتير المورد الموجودة في دفتر يومية.                                                                                                                                                                                                                                                                                                                 | دفتر يومية الفواتير                                                |
| سند إذني معاد سحبه للمورد     | إعادة سحب السند الإذني الذي تم سداده سابقًا بواسطة البنك لديك.                                                                                                                                                                                                                                                                      | دفتر يومية إعادة سحب السندات الإذنية                                 |
| السند الإذني الذي تمت تسويته من قبل المورد     | إنشاء حركات السند الإذني الذي تمت تسويته من قبل المورد.                                                                                                                                                                                                                                                                                                          | دفتر يومية تسوية السندات الإذنية                                 |




