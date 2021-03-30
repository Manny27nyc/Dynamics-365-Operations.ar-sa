---
title: تكوين وجهات ER المعتمدة علي الاجراء
description: يوضح هذا الموضوع معلومات كيفية تكوين وجهات بريد إلكتروني لكل مكون "ملف" أو "مجلد" لتنسيق إعداد التقارير الإلكترونية (ER) التي يتم تكوينها لإنشاء مستندات صادرة.
author: NickSelin
manager: AnnBe
ms.date: 02/09/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: f3055a27-717a-4c94-a912-f269a1288be6
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: ea7543fddef085cfd1e92edf0b1dabf6d0aac38a
ms.sourcegitcommit: 5264aaec3723c40a219e4d2867afe1ba9cc5f2a2
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/10/2021
ms.locfileid: "5153629"
---
# <a name="configure-action-dependent-er-destinations"></a>تكوين وجهات ER المعتمدة علي الاجراء

[!include [banner](../includes/banner.md)]

يمكنك تكوين [وجهات](electronic-reporting-destinations.md) لكل مكون إخراج (مجلد أو ملف) [لتكوين ](general-electronic-reporting.md) [تنسيق](general-electronic-reporting.md#FormatComponentOutbound) [إعداد التقارير الإلكترونية (ER)](general-electronic-reporting.md#Configuration) المستخدم لإنشاء مستند صادر. يستطيع المستخدمون الذين يقومون بتشغيل أحد تنسيقات ER من هذا النوع، ومن لهم حقوق الوصول المناسبة، تغيير إعدادات الوجهة المكونة في وقت التشغيل.

في Microsoft Dynamics 365 Finance **10.0.17 الإصدار والإصدارات الأحدث**، يمكن تشغيل التنسيق الخاص ب ER عن طريق [توفير](er-apis-app10-0-17.md) رمز اجراء يقوم به المستخدم بواسطة تشغيل تنسيق ER. علي سبيل المثال، في الوحدة النمطية **الحسابات المدينة**، في إعدادات أداره الطباعة، يمكنك تحديد تنسيق ER الذي يقوم بإنشاء مستند عمل معين، مثل فاتورة النص الحر. يمكنك عندئذ تحديد **عرض** لمعاينه الفاتورة أو **الطباعة** لإرسالها إلى الطابعة. إذا تم تمرير اجراء المستخدم للتنسيق الجاري تشغيله لـ ER في وقت التشغيل، يمكنك تكوين وجهات ER مختلفه لإجراءات المستخدم المختلفة. يوضح هذا الموضوع كيفيه تكوين وجات ER لهذا النوع من تنسيق ER.

## <a name="make-action-dependent-er-destinations-available"></a>إتاحة وجهات ER المعتمدة علي الاجراء

لتكوين وجهه تابعه للإجراءات في مثيل التمويل الحالي و [تمكين](er-apis-app10-0-17.md) واجهه برمجه تطبيقات ER الجديدة، [افتح](../../fin-ops/get-started/feature-management/feature-management-overview.md#the-feature-management-workspace)مساحة عمل أداره الميزات، وقم بتشغيل **مصادر تكوين المواقع التابعة المحددة لاستخدامها مع ميزه الإجراءات المساء المختلفة**. لاستخدام وجهات ER المكونة لتقارير [محدده](#reports-list-wave1) في وقت التشغيل، قم بتمكين الميزة، ثم **توجيه إخراج تقارير PM استنادا إلى وجهات ER التي تكون خاصه باجراء المستخدم (wave 1)**.

## <a name="configure-action-dependent-er-destinations"></a>تكوين وجهات ER المعتمدة علي الاجراء

عند تشغيل ميزة **تكوين المواقع التابعة المحددة لاستخدامها لميزات الإجراءات PM المختلفة**، يمكنك تكوين وجهات تابعه تعتمد علي الاجراء علي علامة التبويب السريعة **وجهة الملف** الخاص بالصفحة **الوجهة للتقارير الكترونيه**. بالنسبة لكل مكون، يمكنك أضافه سجل وتمكين وجهات ER محدده. بالنسبة لكل سجل، يجب تحديد نوع المستند الذي يجب تطبيق وجات ER المكونة عليه. في حقل **عملة المستند**، حدد إحدى القيم التالية:

- حدد **الكتروني** لتطبيق الوجهات التي تم تكوينها في حاله عدم تقديم كود اجراء المستخدم في وقت التشغيل.
- حدد **إدارة الطباعة** لتطبيق الوجهات التي تم تكوينها في حاله تقديم كود اجراء المستخدم في وقت التشغيل.
- حدد **أي** لتطبيق الوجهات التي تم تكوينها بغض النظر عن اجراء المستخدم المقدم في وقت التشغيل.

إذا قمت بتحديد نوع مستند **أداره الطباعة**، فيجب عليك تحديد إجراءات المستخدم التي يجب تطبيق وجات ER المكونة عليها. في حقل **إجراء إدارة الطباعة**، حدد إحدى القيم التالية:

- حدد **عرض** لتطبيق الوجهات التي تم تكوينها في حاله عدم تقديم اجراء المستخدم **عرض** في وقت التشغيل.
- حدد **طباعة** لتطبيق الوجهات التي تم تكوينها في حاله عدم تقديم اجراء المستخدم **طباعة** في وقت التشغيل.
- حدد **إرسال** لتطبيق الوجهات التي تم تكوينها في حاله عدم تقديم اجراء المستخدم **إرسال** في وقت التشغيل.

> [!NOTE]
> يمكن تحديد إجراءات متعددة لسجل وجهه واحد.

إذا قمت بتحديد نوع المستند **اي**، يتم تحديد **الكشف التلقائي** تلقائيا في حقل **اجراء أداره الطباعة** باعتباره أحد إجراءات المستخدم، ويحدث السلوك التالي:

- في حاله عدم تقديم كود اجراء المستخدم في وقت التشغيل، يتم تطبيق جميع وجهات ER التي تم تكوينها.
- في حاله توفير كود اجراء المستخدم في وقت التشغيل، يتم تطبيق وجهه ER التي تم تعريفها مسبقا لاجراء محدد، **بغض النظر عما إذا كان قد تم تمكينها ام لا**:

    - عندما يتم توفير اجراء **العرض** في وقت التشغيل، يتم تطبيق وجهه ER **الشاشة**.
    - عندما يتم توفير اجراء **إرسال** في وقت التشغيل، يتم تطبيق وجهه ER **البريد الإلكتروني**.
    - عندما يتم توفير اجراء **الطباعة** في وقت التشغيل، يتم تطبيق وجهه ER **الطباعة**.

علي سبيل المثال، يمكنك استخدام **التنسيق الخاص بالفاتورة ذات النص الحر (Excel)** لطباعه [فاتورة نص حر](https://docs.microsoft.com/dynamics365/finance/accounts-receivable/create-free-text-invoice-new) عند قيامك بترحيلها. لتوجيه مستند تم إنشاؤه، يجب تكوين وجهات ER لتنسيق ER هذا. علي سبيل المثال، قد تحتاج إلى تكوين وجهات ER هذه لتنفيذ ما يلي علي مستند تم إنشاؤه:

- أرشفه المستند إذا كان التنسيق الخاص بـ ER قيد التشغيل ولكن لم يتم توفير اي رمز اجراء (علي سبيل المثال، عندما يتم إرسال المستند الكترونيا).
- معاينه المستند في مستعرض ويب عندما يقوم المستخدم بتنفيذ اجراء **العرض**.
- أرشفه المستند وطباعته عند قيام المستخدم باجراء **الطباعة**.
- أرشفه المستند وإرساله بالبريد الكتروني كمرفق رسالة بريد الكتروني صادر عند قيام المستخدم باجراء **الإرسال**.

يبين الرسم التوضيحي التالي كيفيه القيام بتكوين وجهات ER هذه كمجموعه من سجلات الوجهة الفردية عند تكوين كل سجل لاجراء مستخدم فردي:

![صفحه وجهه التقارير الكترونيه التي تحتوي علي إعدادات وجهه تعتمد علي الإجراءات لتنسيق ER عند تكوين كل سجل وجهه لاجراء مستخدم واحد](./media/er-destination-action-dependent-01.png)

يبين الرسم التوضيحي التالي كيفيه القيام بتكوين وجهات ER هذه كمجموعه من سجلات الوجهة الفردية عند تكوين كل سجل لوجهة فردية:

![صفحه وجهه التقارير الكترونيه التي تحتوي علي إعدادات وجهه تعتمد علي الإجراءات لتنسيق ER عند تكوين كل سجل وجهه واحدة](./media/er-destination-action-dependent-01a.png)

> [!NOTE]
> إذا تم توفير رمز اجراء للتنسيق الجاري تشغيله، ولكن لم يتم تكوين إيه وجهات لرمز الاجراء هذا، يتم تطبيق سلوك الوجهة [الافتراضي](electronic-reporting-destinations.md#default-behavior).

## <a name="change-action-dependent-er-destinations-at-runtime"></a>تغيير وجهات ER المعتمدة علي الاجراء في وقت التشغيل

عند تشغيل تنسيق ER، إذا تم توفير إجراءات المستخدم من قبل المستخدمين الذين لديهم [أذونات](electronic-reporting-destinations.md#security-considerations) مناسبه لتغيير إعدادات الوجهة المكونة في وقت التشغيل، يظهر مربع حوار يعطي خيار تغيير إعدادات الوجهة المكونة. يعد مربع الحوار هذا اختياريا، ويعتمد مظهره علي كيفيه تنفيذ الاستدعاء الذي يقوم به اطار عمل ER بتشغيل تنسيق ER. في حاله ظهور مربع الحوار هذا، يتم تمكين الوجهات الخاصة بـ ER فيها وفقا لاجراء المستخدم الذي تم توفيره.

يبين الرسم التوضيحي التالي مثالا لمربع الحوار **وجهات تنسيق التقارير الإلكترونيه** التي تظهر عند [ترحيل](https://docs.microsoft.com/dynamics365/finance/accounts-receivable/create-free-text-invoice-new) فاتورة ويتم تشغيل تنسيق ER **فاتورة النص الحر (Excel)** لإنشاء هذا المستند، إذا تم توفير اجراء **الطابعة** وتم تكوين وجهات ER لهذا التنسيق كما هو موضح سابقا في هذا الموضوع.

![مربع الحوار الذي يعطي خيار تغيير وجات مبدئيًا التي تم تكوينها لتنسيق ER الجاري](./media/er-destination-action-dependent-02.gif)

> [!NOTE]
> إذا كنت قد قمت بتكوين وجهات ER لمكونات متعددة من التنسيق المشغل لـ ER، سيتم عرض أحد الخيارات بشكل منفصل لكل مكون مكون لتنسيق ER.

## <a name="verify-the-provided-user-action"></a>التحقق من الاجراء المقدم للمستخدم

يمكنك التحقق من اجراء المستخدم، ان وجد، الذي يتم توفيره لتنسيق ER الجاري عند تنفيذ اجراء مستخدم معين. يعد هذا التحقق مهما عندما يجب تكوين وجهات تابعه تعتمد علي الاجراء، ولكنك لم تكن متاكدا من رمز اجراء المستخدم، ان وجد، يتم توفيره. علي سبيل المثال، عند البدء في ترحيل فاتورة نص حر وتعيين خيار **طباعه الفاتورة** إلى **نعم** في مربع الحوار **فاتورة نص حر للترحيل**، يمكنك تعيين الخيار **استخدام وجهه أداره الطباعة** إلى **نعم** أو **لا**.

اتبع الخطوات التالية للتحقق من كود اجراء المستخدم الذي تم توفيره.

1. انتقل إلى **إدارة المؤسسة** \> **التقارير الإلكترونية** \> **التكوينات**.
2. في صفحة **التكوينات**، في جزء الإجراءات، في علامة التبويب **التكوينات**، في مجموعة **الإعدادات المتقدمة**، حدد **معلمات المستخدمين**.
3. في مربع الحوار **معلمات المستخدم**، قم [بتعيين خيار](er-trace-reports-compare-baseline.md#configure-er-parameters-to-use-the-baseline-feature) **تشغيل في وضع التصحيح** إلى **نعم**.
4. تنفيذ اجراء من مستخدم عن طريق تشغيل تنسيق ER. لاحظ أن معلمات مستخدم ER خاصة بالمستخدم والشركة.
5. انتقل إلى **إدارة المؤسسة** \> **التقارير الإلكترونية** \> **سجلات تصحيح التكوينات**.
6. في الصفحة **سجلات تصحيح التكوين**، قم بتصفية سجلات تشغيل ER للعثور علي سجل الخاص بالتنسيق الخاص بالتنسيق ER.
7. قم بمراجعه إدخالات السجل التي يجب ان تحتوي علي السجل الذي يقدم كود اجراء المستخدم الذي تم توفيره، إذا تم توفير اي اجراء لتشغيل التنسيق الخاص بـ ER.

    ![صفحه سجلات تشغيل التقارير الكترونيه التي تحتوي علي معلومات حول رمز اجراء المستخدم الذي تم توفيره للتشغيل المصفي لتنسيق ER](./media/er-destination-action-dependent-03.png)

## <a name=""></a><a name="reports-list-wave1">قائمه مستندات العمل (موجة 1)</a>

يتم التحكم في قائمه مستندات العمل التالية بواسطة الميزة، **إخراج التوجيه لتقارير PM استنادا إلى وجات ER التي تكون خاصه باجراء المستخدم (موجة 1)**:

- فاتورة العميل (فاتورة نص حر)
- فاتورة العميل (فاتورة المبيعات)
- أمر شراء
- استعلام الشراء لأمر الشراء
- تأكيد أمر المبيعات
- إشعار خطاب التحصيلات
- كشف حساب العميل
- إشعار الفائدة
- اخطار دفع المورد
- طلب عرض الأسعار

## <a name="additional-resources"></a>الموارد الإضافية

[نظرة عامة على إعداد التقارير الإلكترونية (ER)](general-electronic-reporting.md)

[وجهات إعداد التقارير الإلكترونية (ER)‬](electronic-reporting-destinations.md)

[التغييرات في واجهة برمجة التطبيقات (API) لإطار عمل التقارير الإلكترونية لـ Application update 10.0.17](er-apis-app10-0-17.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]