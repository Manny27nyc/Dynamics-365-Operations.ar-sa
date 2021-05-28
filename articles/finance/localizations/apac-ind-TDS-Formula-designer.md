---
title: مصمم المعادلة لحسابات TDS
description: يقدم هذا الموضوع مثالاً على كيفية حساب الضريبة المخصومة في المصدر (TDS) استنادًا إلى المعادلة المحددة لكل كود ضريبة TDS في مجموعة TDS المرفقة بالحركة.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: d0f644da640b56761a52baec9ff01c898e895d19
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022989"
---
# <a name="formula-designer-for-tds-calculations"></a>مصمم المعادلة لحسابات TDS

[!include [banner](../includes/banner.md)]

يقدم هذا الموضوع مثالاً على كيفية حساب الضريبة المخصومة في المصدر (TDS) استنادًا إلى المعادلة المحددة لكل كود ضريبة TDS. يتم تحديد أكواد ضريبة TDS في مجموعة TDS المرفقة بالحركة. قبل تصميم صيغ TDS، أكمل الإعداد الأساسي المطلوب لـ TDS كما هو موضح في الخطوات التالية. 

- قم بإعداد مجموعات مكون TDS باستخدام الصفحة **مجموعات مكون ضريبة الخصم**. 
- قم بإعداد مكونات TDS وقم بإرفاق مجموعة مكون TDS بمكون TDS باستخدام الصفحة **مكونات ضريبة الخصم**. 
- قم بإعداد أكواد ضريبة TDS وقم بإرفاق مكونات TDS بأكواد الضريبة باستخدام الصفحة **أكواد ضريبة الخصم**. 
- قم بإعداد مجموعات ضريبة TDS باستخدام الصفحة **مجموعات ضريبة الخصم**. ثم قم بإرفاق أكواد ضريبة TDS بمجموعة الضريبة، وحدد الصيغة باستخدام الصفحة **مصمم المعادلة**. 

**مثال المعادلة**

في هذا المثال، يتم إرفاق مجموعة TDS، الإيجار، بفاتورة شراء يتم إنشاؤها للمورد أ. مبلغ الفاتورة هو 100.000 دولارًا أمريكيًا. راجع الجدول التالي لعرض حساب TDS للفاتورة.

| مجموعة TDS                                                   | أكواد ضريبة TDS المرفقة بمجموعة TDS | قيمة              | أساس خاضع للضريبة (مصمم المعادلة) | تعبير الحساب (مصمم المعادلة) | مبلغ أساسي | مبلغ TDS المحسوب |
| ------------------------------------------------------------ | --------------------------------------- | ------------------ | --------------------------------- | :----------------------------------------: | ----------- | --------------------- |
| الإيجار                                                         | TDS (مكون TDS-TDS)                | 10%                | إجمالي المبلغ                      |                                            | 100,000      | 10,000                 |
| المصاريف الإضافية (مكون TDS-المصاريف الإضافية)                         | 10%                                     | استثناء المبلغ الإجمالي = 10.00 + 5.00 = 15.00 | +TDS                              |                   10000                    | 1,000        |                       |
| PE-Cess (مكون TDS- PE-Cess)                            | 2%                                      | استثناء المبلغ الإجمالي = 10.00 + 5.00 = 15.00 | +TDS+رسوم إضافية                    |                   11000                    | 220         |                       |
| SHE Cess (مكون TDS- SHE Cess)                          | 1%                                      | استثناء المبلغ الإجمالي = 10.00 + 5.00 = 15.00 | +TDS+رسوم إضافية                    |                   11000                    | 110         |                       |
| **إجمالي** **TDS**  **المحسوب** **لـ** **ل** **فاتورة** | **11,330**                               |                    |                                   |                                            |             |                       |

يتم إنشاء إدخالات الإيصال كما يلي.

| الحساب           | مدين  | دائن‬ |
| ----------------- | ------ | ------ |
| الإيجار              | 100,000 |        |
| المورد أ          |        | 100,000 |
| المورد أ          | 11,330  |        |
| TDS مستحق الدفع       |        | 10,000  |
| الرسوم الإضافية مستحقة للدفع |        | 1,000   |
| PE-Cess مستحق الدفع   |        | 220    |
| SHE Cess مستحق الدفع  |        | 110    |