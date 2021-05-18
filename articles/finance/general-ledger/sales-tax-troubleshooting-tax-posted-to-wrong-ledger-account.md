---
title: يتم ترحيل الضريبة إلى حساب دفتر الأستاذ الخطا في الإيصال
description: يوفر هذا الموضوع معلومات استكشاف الأخطاء وإصلاحها التي يمكن ان تساعد في حاله ترحيل الضريبة إلى حساب دفتر الأستاذ الخطا في الإيصال.
author: qire
manager: beya
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 0404d71f0492e188ed5da62387bb90a336e69c5a
ms.sourcegitcommit: 57668404d61359b33e0c0280f2f7c4eb829b1ed2
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/27/2021
ms.locfileid: "5947591"
---
# <a name="tax-is-posted-to-the-wrong-ledger-account-in-the-voucher"></a>يتم ترحيل الضريبة إلى حساب دفتر الأستاذ الخطا في الإيصال

[!include [banner](../includes/banner.md)]

أثناء الترحيل، قد يتم ترحيل الضريبة إلى حساب دفتر الأستاذ الخاطئ في الإيصال. لاستكشاف هذه المشكلة وإصلاحها، اتبع الخطوات الواردة في الأقسام التالية عند الضرورة. تستخدم الامثله الموجودة في هذا الموضوع أمر المبيعات كمستند اعمال.

## <a name="find-the-tax-code-of-the-incorrectly-posted-tax-transaction"></a>العثور علي كود الضريبة لحركه الضريبة المرحلة بشكل غير صحيح

1. في صفحة **حركات الإيصال**، حدد الحركة التي ترغب في العمل معها، ثم حدد **ضريبة المبيعات المرحلة**.

    [![زر ضريبة المبيعات المرحلة في صفحه حركات الإيصال](./media/tax-posted-to-wrong-ledger-account-Picture1.png)](./media/tax-posted-to-wrong-ledger-account-Picture1.png)

2. راجع القيمة في الحقل **كود ضريبة المبيعات**. في هذا المثال، تكون **VAT 19**.

    [![حقل كود ضريبة المبيعات في صفحه ضريبة المبيعات المرحلة](./media/tax-posted-to-wrong-ledger-account-Picture2.png)](./media/tax-posted-to-wrong-ledger-account-Picture2.png)

## <a name="check-the-ledger-posting-group-of-the-tax-code"></a>فحص مجموعه ترحيل دفتر الأستاذ الخاصة بكود الضريبة

1. انتقل إلى **الضريبة** \> **الضرائب غير المباشرة** \> **ضريبة المبيعات** \> **رموز ضرائب المبيعات**.
2. تتيح البحث عن كود الضريبة وتحديده، ثم مراجعه القيمة الموجودة في حقل **مجموعه ترحيل دفتر الأستاذ**. في هذا المثال، تكون **VAT**.

    [![حقل مجموعة ترحيل دفتر الأستاذ في صفحة أكواد ضريبة المبيعات](./media/tax-posted-to-wrong-ledger-account-Picture3.png)](./media/tax-posted-to-wrong-ledger-account-Picture3.png)

3. القيمة في حقل **مجموعة ترحيل دفتر الأستاذ** هي ارتباط. لعرض تفاصيل تكوين المجموعة، حدد الارتباط. بدلا من ذلك، حدد ثم اضغط (أو انقر بزر الماوس الأيمن) في الحقل، ثم حدد **عرض التفاصيل**.

    [![أمر عرض التفاصيل](./media/tax-posted-to-wrong-ledger-account-Picture4.png)](./media/tax-posted-to-wrong-ledger-account-Picture4.png)

4. في حقل **ضريبة المبيعات مستحقه الدفع**، تحقق من صحة رقم الحساب، وذلك وفقا لنوع الحركة. وإذا لم تكن كذلك، فحدد الحساب الصحيح الذي سيتم الترحيل اليه. في هذا المثال، يجب ترحيل ضريبة المبيعات الخاصة بامر التوريد إلى حساب ضريبة المبيعات المستحقة الدفع 222200.

    [![حقل ضريبة المبيعات المستحقة في صفحة مجموعات ترحيل دفتر الأستاذ](./media/tax-posted-to-wrong-ledger-account-Picture5.png)](./media/tax-posted-to-wrong-ledger-account-Picture5.png)

    يوفر الجدول التالي معلومات حول كل حقل في صفحة **مجموعات ترحيل دفتر الأستاذ**.

    | الحقل                  | الوصف |
    |------------------------|-------------|
    | ضريبة المبيعات مستحقة الدفع      | الحساب الرئيسي لضرائب المبيعات الصادرة المستحقة لهيئه الضرائب. |
    | ضريبة المبيعات مستحقة القبض   | الحساب الرئيسي للضرائب الواردة الواردة من مصلحة الضرائب. |
    | مصروفات ضريبة الانتفاع        | الحساب الرئيسي المستخدم لترحيل ضرائب الاستخدام القابلة للخصم التي لا يطالب بها البائعون أو يقدموا تقارير إلى مصلحة الضرائب كجزء من ضريبة السلع والخدمات (GST) / ضريبة المبيعات المنسقة (HST) في الاتحاد الأوروبي (EU). يجب تحديد **استخدام الضريبة** لرمز ضريبة المبيعات في مجموعة ضريبة المبيعات المستخدمة في الحركة. لا يتوفر هذا الحقل إذا كان **تطبيق قواعد فرض ضرائب على المبيعات** محددًا في صفحة **محددات دفتر الأستاذ العام**. |
    | ضريبة الانتفاع الدائنة        | الحساب الرئيسي المستخدم لترحيل ضرائب الاستخدام الوارد التي تمت الدفع لها إلى هيئات الضرائب. |
    | حساب التسوية     | الحساب الرئيسي المستخدم لترحيل صافي رصيد حسابات دفتر الأستاذ المحدد في حقلي **استخدام الضريبة مستحقة الدفع** و **ضريبة المبيعات المدينة**. |
    | الخصم النقدي للمورد   | الحساب الرئيسي المستخدم لترحيل خصم نقدي لأكواد ضريبة المبيعات المرتبطة بمجموعة ترحيل دفتر الأستاذ هذه. |
    | الخصم النقدي للعميل | الحساب الرئيسي المستخدم لترحيل خصم نقدي لأكواد ضريبة المبيعات المرتبطة بمجموعة ترحيل دفتر الأستاذ هذه. |

    لمزيد من المعلومات، راجع [إعداد مجموعات ترحيل دفتر الأستاذ لضريبة المبيعات](tasks/set-up-ledger-posting-groups-sales-tax.md)

## <a name="debug-in-code-to-check-ledger-dimensions"></a>تصحيح في التعليمات البرمجية للتحقق من ابعاد دفتر الأستاذ

في الكود، يتم تحديد حساب الترحيل حسب بعد دفتر الأستاذ. يقوم بعد دفتر الأستاذ بحفظ معرف السجل الخاص بأحد الحسابات في قاعده البيانات.

1. بالنسبة لأمر التوريد، أضف نقطه توقف في أسلوبي **Tax::saveAndPost()** و **Tax::post()**. انتبه إلى قيمة **\_ledgerDimension**.

    [![نموذج لكود أمر المبيعات الذي يحتوي علي نقطه توقف](./media/tax-posted-to-wrong-ledger-account-Picture6.png)](./media/tax-posted-to-wrong-ledger-account-Picture6.png)

    لأمر الشراء، أضف نقطة توقف عند أسلوبي **TaxPost::saveAndPost()** و **TaxPost::postToTaxTrans()**. انتبه إلى قيمة **\_ledgerDimension**.

    [![نموذج لكود أمر الشراء الذي يحتوي علي نقطه توقف](./media/tax-posted-to-wrong-ledger-account-Picture7.png)](./media/tax-posted-to-wrong-ledger-account-Picture7.png)

2. قم بتشغيل استعلام SQL التالي للعثور على قيمة عرض الحساب في قاعدة البيانات، بناءً على معرف السجل الذي تم حفظه بواسطة بُعد دفتر الأستاذ.

    ```sql
    select * from DIMENSIONATTRIBUTEVALUECOMBINATION where recid={the value of _ledgerDimension}
    ```

    [![عرض قيمة معرف السجل](./media/tax-posted-to-wrong-ledger-account-Picture8.png)](./media/tax-posted-to-wrong-ledger-account-Picture8.png)

3. افحص Callstack لتجد مكان تعيين قيمة **_ledgerDimension**. عادةً ما تكون القيمة من **TmpTaxWorkTrans**. في هذه الحالة، يجب إضافة نقطة توقف عند **TmpTaxWorkTrans::insert()** و **TmpTaxWorkTrans::update()** للعثور على مكان تعيين القيمة المحددة.

## <a name="determine-whether-customization-exists"></a>حدد ما إذا كان التخصيص موجودًا

إذا كنت قد أكملت الخطوات الواردة في الأقسام السابقة ولكنك لم تجد أي مشكلة، فحدد ما إذا كان التخصيص موجودًا أم لا. في حاله عدم وجود تخصيص، قم بإنشاء طلب خدمه Microsoft لمزيد من الدعم.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]