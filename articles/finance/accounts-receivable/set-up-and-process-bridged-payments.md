---
title: إعداد الدفعات الوسيطة ومعالجتها‬‏‫
description: يوضح هذا الموضوع كيفية إعداد دفعات العميل الوسيطة ومعالجتها‬‏‫. الدفعة الوسيطة هي دفعة يتم ترحيلها إلى دفتر الأستاذ العام في خطوتين.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPaymMode, VendPaymMode, LedgerJournalTable, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, LedgerJournalTransDaily
audience: Application User
ms.reviewer: roschlom
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5e1418e573f34fadcf0bebc7232d847ee7e9768b
ms.sourcegitcommit: 5bfd6511d710deb539b4030eb0e9c48d25513595
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 01/19/2022
ms.locfileid: "8014020"
---
# <a name="set-up-and-process-bridged-payments"></a>إعداد الدفعات الوسيطة ومعالجتها‬‏‫

[!include [banner](../includes/banner.md)]

الدفعة الوسيطة هي دفعة يتم ترحيلها إلى دفتر الأستاذ العام في خطوتين. عادةً ما يتم استخدام هذا الأسلوب عند تعيين طريقة الدفع إلى **البنك**، ولا يجب عليك ترحيل الحركات إلى الحساب البنكي إلا عندما ينتهي البنك من تسوية الحركة. ومع ذلك، يمكنك أيضًا استخدامه لحساب دفتر الأستاذ. في هذه الحالة، يقوم النظام بنقل المبلغ من حساب رئيسي إلى حساب رئيسي آخر عند معالجة الترحيل الوسيط.

يمكنك إنشاء دفعات وسيطة من كل من الحسابات الدائنة أو الحسابات المدينة. على الرغم من أن هذا الموضوع يشرح كيفية تكوين الترحيل الوسيط للحسابات المدينة، فإن خطوات حركات الحسابات الدائنة متشابهة.

## <a name="set-up-bridging-posting"></a>إعداد الترحيل الوسيط

لاستخدام الترحيل الوسيط، يجب عليك إعداد طريقة دفع واحدة أو أكثر كي تستخدم طريقة **الترحيل الوسيط**. ويجب بعد ذلك تحديد حساب وسيط.

1. انتقل إلى **الحسابات المدينة &gt; إعداد الدفع &gt; طرق الدفع**.
2. حدد طريقة دفع موجودة لتمكين الترحيل الوسيط. أو أنشئ طريقة دفع جديدة.
3. حدد خانة الاختيار **ترحيل وسيط**.
4. في الحقل **الحساب الوسيط**، حدد الحساب الرئيسي الذي يجب ترحيل الدفعات اليه قبل أن تتم تسويتها في الحساب البنكي.
5. قم بإغلاق الصفحة.

## <a name="process-and-transfer-bridging-posting"></a>معالجة الترحيل الوسيط ونقله

لإنشاء ترحيل وسيط ومعالجته، اتبع هذه الخطوات.

1. انتقل إلى **الحسابات المدينة &gt; المدفوعات &gt; دفتر يومية المدفوعات للعميل**.
2. حدد **جديد** لإنشاء دفتر يومية.
3. في حقل **الاسم**، حدد اسمًا.
4. أضف بنودًا إلى دفتر يومية مدفوعات العميل، وحدد طريقة الدفع التي تم تكوينها للترحيل الوسيط.
5. ترحيل دفتر اليومية. سيتم ترحيل الحركات إلى الحساب الرئيسي الذي قمت بتحديده في حقل **الحساب الوسيط** في الإجراء السابق.

عند تسوية الحركات في البنك، وإذا كنت ترغب في تحويل الدفع من الحساب الوسيط إلى حساب الدفع الذي تم تحديده لطريقه الدفع، اتبع الخطوات التالية.

1. انتقل إلى **دفتر الأستاذ العام &gt; إدخالات دفتر اليومية &gt; دفاتر اليومية العامة**‬.
2. حدد **جديد** لإنشاء دفتر يومية.
3. في حقل **الاسم**، حدد اسمًا.
4. حدد **البنود** لفتح تفاصيل دفتر اليومية.
5. حدد **الوظائف &gt; تحديد حركات وسيطة**.
6. قم بتمييز كل دفعة تمت تسويتها، ثم حدد **قبول**.
7. ترحيل دفتر اليومية.