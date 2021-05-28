---
title: إعداد مجموعة TDS وPAN ومعلومات TAN للموردين والعملاء
description: يوضح هذا الموضوع كيفية إعداد المعلومات المتعلقة بمجموعة الضريبة المخصومة في مجموعة المصدر (TDS)، ورقم الحساب الدائم (PAN)، ورقم حساب الضريبة (TAN) للموردين والعملاء.
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
ms.openlocfilehash: fd33b1775afefed798f1e9bb7601f4112222c430
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022999"
---
# <a name="tds-group-pan-and-tan-information-setup-for-vendors-and-customers"></a>إعداد مجموعة TDS وPAN ومعلومات TAN للموردين والعملاء

[!include [banner](../includes/banner.md)]

يوضح هذا الموضوع كيفية إعداد المعلومات المتعلقة بمجموعة الضريبة المخصومة في مجموعة المصدر (TDS)، ورقم الحساب الدائم (PAN)، ورقم حساب الضريبة (TAN) للموردين والعملاء.

1. انتقل إلى **الحسابات المدينة \> الموردين \> كافة الموردين** أو **الحسابات المدينة \> العملاء \> جميع العملاء**.

    [![صفحة كافة الموردين](./media/apac-ind-TDS-55.png)](./media/apac-ind-TDS-55.png)

2. في جزء الإجراء، حدد **جديد** لإنشاء مورد أو عميل، وأدخل التفاصيل المطلوبة. أو بدلاً من ذلك، حدد موردًا أو عميلاً موجودًا.
3. في علامة التبويب السريعة **الفاتورة والتسليم**، في القسم **ضريبة الخصم**، قم بتعيين الخيار **حساب ضريبة الخصم** إلى **نعم** لحساب ضريبة الخصم أو TDS أو الضريبة التي تم جمعها في المصدر (TCS) للمورد أو العميل.
4. يتم حساب TDS لفاتورة الشراء استنادًا إلى مجموعة TDS الافتراضية التي يتم تحديدها للمورد أو العميل. في حقل **مجموعة TDS**، حدد مجموعة TDS الافتراضية.

    > [!NOTE]
    > عندما تقوم بتحديد مجموعة TDS في الحقل **مجموعة TDS**، فقد يصبح الحقلين **مجموعة ضريبة الخصم** و **مجموعة TCS** غير متاحين.

5. في علامة التبويب السريعة **معلومات الضريبة**، في القسم **معلومات PAN**، في الحقل **الحالة**، حدد حالة رقم الحساب الدائم للمورد أو العميل:

    - **غير متاح** – لا يحتوي المورد أو العميل على PAN.
    - **مستلم**– يكون للمورد أو العميل PAN.
    - **مطبق** – تم تطبيق المورد أو العميل لـ PAN.
    - **غير صالح** – يمتلك المورد أو العميل PAN، ولكنه غير صالح.

6. إذا قمت بتحديد **مستلم** في الحقل **الحالة** للإشارة إلى أن المورد أو العميل له رقم PAN، أدخل PAN في الحقل **الرقم**. يجب أن تتكون القيمة PAN من خمسة أحرف أبجدية، ثم أربعة أحرف رقمية، ثم حرفًا أبجديًا واحدًا. وفيما يلي مثال على ذلك: **ABCDE1260A**.
7. إذا قمت بتحديد **مطبق** في الحقل **الحالة** للإشارة إلى أن المورد أو العميل قد قام بتطبيق رقم PAN، أدخل الرقم المرجعي في الحقل **الرقم المرجعي**.
8. في الحقل **طبيعة المقيم**، حدد فئة طبيعة المقيم التي ينتمي إليها المورد أو العميل:

    - الشركة
    - HUF
    - تأكيد
    - فردي
    - AOP
    - BOI
    - السلطة المحلية
    - غير ذلك

    [![علامة التبويب السريعة معلومات الضريبة](./media/apac-ind-TDS-56.png)](./media/apac-ind-TDS-56.png)

9. في جزء الإجراءات، ضمن علامة التبويب **المورد**، في مجموعة **التسجيل**، حدد **معرفات التسجيل** لفتح الصفحة **إدارة العناوين**.
10. في الصفحة **إدارة العناوين**، في علامة التبويب السريعة **معلومات الضريبة**، حدد **إضافة** أو **تحرير** لفتح الصفحة **إدارة معلومات الضريبة**، حيث يمكنك الاحتفاظ بإدخال تسجيل الضريبة.
11. في الصفحة **إدارة معلومات الضريبة**، على علامة التبويب السريعة **ضريبة الخصم**، في الحقل **رقم حساب الضريبة (TAN)**، أدخل الرقم TAN. يجب أن تتكون القيمة TAN من أربعة أحرف أبجدية، ثم خمسة أحرف رقمية، ثم حرفًا أبجديًا واحدًا. وفيما يلي مثال على ذلك: **AFGH54821T**.
12. قم بإغلاق الصفحة.