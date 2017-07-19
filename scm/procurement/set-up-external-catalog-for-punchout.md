---
title: "إعداد كتالوج خارجي للتدبير الإلكتروني للبطاقات المثقبة"
description: "يصف هذا الموضوع استخدام كتالوج خارجي أو كتالوج البطاقات المثقبة لجمع معلومات عروض الأسعار من مورّد وإضافتها إلى طلب."
author: BibiSp
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchVendorPortalRequests
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: 2d853cb963471f81d7a2a09a0f7913722de8a417
ms.contentlocale: ar-sa
ms.lasthandoff: 06/20/2017


---

# <a name="set-up-an-external-catalog-for-punchout-eprocurement"></a>إعداد كتالوج خارجي للتدبير الإلكتروني للبطاقات المثقبة

باستخدام كتالوج خارجي، يمكنك أن تتأكد من أن معلومات المنتجات والأسعار التي تقوم فيما بعد بمعالجتها في Dynamics 365 for Finance and Operations, Enterprise edition لشهر يوليو 2017 هي معلومات دقيقة ومحدثة. ويمكن عندئذٍ الموافقة على الطلب وتحويله إلى أمر شراء ويمكن تقدير أمر لدى المورّد.

عندما يتم إعداد الكتالوج الخارجي ويعمل أحد الموظفين على إعداد طلب، سيكون هناك خيار لإعادة التوجيه إلى موقع خارجي، الكتالوج الخارجي، وإعادة عربة التسوق التي تم إنشاؤها في الموقع الخارجي. يستند هذا الاتصال إلى بروتوكول cXML ويجب إعداده بين أنظمة مؤسسة البيع ومؤسسة الشراء.

لإعداد الاتصال، يجب على المورّد توفير معلومات لك لاستخدامها في تكوين الكتالوج الخارجي مثل الهوية، ومجال شركة الشراء، على سبيل المثال، "DUNS" و "رقم DUNS"، وبيانات الاعتماد وعنوان URL للوصول إلى كتالوج المورّدين.

## <a name="setting-up-an-external-catalog"></a>إعداد كتالوج خارجي

يتعين على الكتالوج الخارجي أن يسمح بإعادة توجيه الموظف الذي يدخل طلب الشراء إلى موقع خارجي لاختيار المنتجات. يتم إرجاع المنتجات التي يختارها الموظف من الكتالوج الخارجي إلى Dynamics 365 for Finance and Operations مع معلومات أسعار حديثة ومن هنا، يمكنك إضافتها إلى طلب الشراء. الغرض ليس تمكين الموظفين من تقديم طلب في الموقع الخارجي. عند إعداد الكتالوج الخارجي، تحتاج إلى التأكد من أن غرض الموقع الذي يمكن الوصول إليه من قبل الكتالوج الخارجي هو جمع معلومات عروض الأسعار وليس تقديم طلب حقيقي.

### <a name="to-set-up-an-external-vendor-catalog-complete-the-following-tasks"></a>لإعداد كتالوج مورّد خارجي، يجب عليك إكمال المهام التالية:

1. اعمل على إعداد التدرج الهرمي لفئات التدبير. لمزيد من المعلومات، راجع [إعداد سياسات للتدرج الهرمي لفئات التدبير](/https://ax.help.dynamics.com/en/wiki/set-up-policies-for-procurement-category-hierarchies/).
2. سجّل المورّد في Finance and Operations. قبل أن تتمكن من إعداد التكوينات للوصول إلى كتالوج مورّد خارجي، يجب عليك إعداد المورّد وجهة اتصال المورّد في Microsoft Dynamics 365. يجب أيضًا إضافة مورّد الكتالوج الخارجي إلى فئة التدبير الخاصة. للحصول على مزيد من المعلومات حول تسجيل المورّدين في Microsoft Dynamics 365، راجع [إدارة مستخدمي تعاون المورّد](/procurement/manage-vendor-collaboration-users.md). لمزيد من المعلومات حول كيفية تعيين المورّد إلى فئة تدبير، راجع [الموافقة على المورّدين لفئات تدبير معين](/https://ax.help.dynamics.com/en/wiki/approve-vendors-for-specific-procurement-categories/).
3. تأكد من إعداد وحدات القياس والعملة التي يستخدمها المورّد. لمزيد من المعلومات حول كيفية إنشاء وحدة قياس، راجع [إنشاء وحدات القياس](/https://ax.help.dynamics.com/en/wiki/manage-unit-of-measure/).
4. قم بتكوين كتالوج المورّد الخارجي باستخدام المتطلبات لموقع الكتالوج الخارجي الخاص بالمورّد. لمزيد من المعلومات حول هذه المهمة، راجع القسم التالي.
5. اختبر تكوينات الكتالوج الخارجي الخاص بالمورّد للتحقق من صحة الإعدادات ومن قدرتك على الوصول إلى الكتالوج الخارجي الخاص بالمورّد. استخدم إجراء **التحقق من صحة الإعدادات** للتحقق من صحة رسالة إعداد الطلب التي قمت بتحديدها. يجب أن تتسبب هذه الرسالة في فتح موقع الكتالوج الخارجي للمورّدين في نافذة مستعرض. أثناء التحقق من الصحة، لا يمكنك طلب الأصناف والخدمات من المورّد. لطلب الأصناف والخدمات، يجب الوصول إلى كتالوج المورّد من طلب شراء.
6. قم بتنشيط الكتالوج الخارجي باستخدام الزر **تنشيط الكتالوج** في صفحة **الكتالوجات الخارجية**. يجب تنشيط الكتالوج الخارجي قبل أن يتمكن العاملون من استخدامه. يمكنك إلغاء تنشيط الكتالوج الخارجي في أي وقت.


## <a name="4-configure-the-external-vendor-catalog"></a>(4) تكوين كتالوج المورّد الخارجي

يوفر هذا القسم المزيد من التفاصيل حول المهمة الرابعة في القسم السابق.

1. أدخل اسما ووصفًا لكتالوج المورّد الخارجي. سوف يظهر الاسم الذي تدخله في عربة التسوق التي تمثل الكتالوج الخارجي الذي يظهر للموظفين الذين يقومون بإنشاء طلب. باستطاعة الموظفين النقر على سلة التسوق لفتح الكتالوج في موقع الكتالوج الخارجي الخاص بالمورّد.
2. أضف صورة باستخدام الإجراء **صورة الكتالوج الخارجي**. سوف تظهر الصورة التي تدخلها في عربة التسوق التي تمثل الكتالوج الخارجي الذي يظهر للموظفين الذين يقومون بإنشاء طلب. لاحظ أن عرض الصورة يجب أن يكون مساويًا لارتفاعها. وإلا، فلن تظهر الصورة بشكل صحيح.
3. حدد ما إذا كان يجب على موقع ويب للكتالوج الخارجي الخاص بالمورّد أن يظهر في نافذة المستعرض نفسها حيث أنشأ الموظف بطلب، أو أن يفتح في نافذة جديدة.
4. حدد المورّد الخاص بالكتالوج. في قائمة **الكيانات القانونية**، يوجد صف لكل كيان قانوني حيث تم إعداد المورّد. للسماح للمستخدمين بطلب المنتجات مباشرة من كتالوج المورّد في بعض الكيانات القانونية ولكن ليس الأخرى، يمكنك استخدام الزر **منع الوصول** أو **السماح بالوصول** لكل كيان قانوني حيث تريد أن يكون الكتالوج متوفرًا أو غير متوفر.
5. في الحقل **فترة انتهاء الصلاحية الافتراضية (بالأيام)‬**، أدخل عدد الأيام التي يكون خلاله عرض أسعار تم تلقيه من الكتالوج الخارجي صالحًا ويمكن استخدامه للشراء من المورّد الخارجي. وعند إنشاء عرض أسعار واستعادته من موقع الكتالوج الخارجي للمورّد، يكون الكتالوج صالحًا منذ تاريخ النظام الحالي، ويظل صالحًا لعدد الأيام التي تدخلها في هذا الحقل.
6. انقر فوق الزر **إضافة** لبدء تعيين فئات التدبير للكتالوج الخارجي. ثم في قائم اسم الفئة، حدد فئةً. إن قائمة الفئات هي مجموعة فرعية من فئات التدبير التي تم تعيين المورّد إليها في كافة الكيانات القانونية التي تم إعدادها للمورّد.
[!NOTE]
يتم استخدام سياسات التدبير للسماح بالوصول أو تقييده إلى فئات الكيان القانوني للشراء أو وحدة تشغيل الاستلام. تتطلب البطاقة المثقبة لكتالوج خارجي أن يتم السماح بالوصول لواحدة من فئات التدبير على الأقل التي تم تعيينها إلى الكتالوج.
7. قم بإعداد رسالة طلب إعداد cXML التي سيتم إرسالها إلى المورّد. تنسيق الرسالة التي يتم إنشاؤها تلقائيًا هو قالب الحد الأدنى المطلوب لبدء جلسة عمل. اعمل على تعبئة القيم للعلامات.

في أي وقت، يمكنك إعادة تحميل قالب الرسالة التي تم إنشاؤها بواسطة النظام عن طريق النقر فوق **استعادة تنسيق الرسالة**. لاحظ أنك إذا قمت باستعادة تنسيق الرسالة، فسيتم استبدال الرسالة الحالية بتنسيق الرسالة التي تم إنشاؤها تلقائيًا، والذي يحتوي على علامات فارغة.

### <a name="cxml-setup-message"></a>رسالة إعداد cXML
فيما يلي يمكنك العثور على وصف للعلامات التي تم تضمينها في القالب:

| الحقل | ‏‏الوصف | 
|---------|---------|
|< Header >< From >< Credential domain=”” >|المجال الخاص بشركة المشتري.|
|< Header >< From >< Credential>< Identity >< /Identity > | الهوية الخاصة بشركة المشتري.|
|< Header >< To >< Credential domain=”” > | المجال الخاص بشركة المورّد.|
|< Header >< To >< Credential>< Identity >< /Identity> | الهوية الخاصة بشركة المورّد.|
|< Header >< Sender >< Credential domain=”” > | المجال الخاص بشركة المشتري.|
|< Header >< Sender >< Credential >< Identity >< /Identity> | الهوية الخاصة بشركة المشتري.|
|< Header >< Sender >< Credential >< SharedSecret >< /SharedSecret >|السر المشترك للشركة الخاصة بالمشتري.|
|< Request deploymentMode=”” >|الاختبار أو نشر الإنتاج.|
|< Request >< PunchOutSetupRequest >< SupplierSetup >< URL >< /URL>|عنوان URL لنقطة نهاية البطاقة المثقبة الخاصة بالمورّد.|

### <a name="extrinsic-elements"></a>العناصر الخارجية

العنصر الخارجي عبارة عن معلومات إضافية، مثل اسم المستخدم الذي يستند إلى مستخدم يسجل الوقت. يتم تعيين العنصر الخارجي عند حدوث تسجيل الوقت، ويمكن إرساله في رسالة إعداد الطلب.
قد يكون للمورّد مطلب يتعلق بتلقي عنصر خارجي في طلب الإعداد. في هذه الحالة، يجب إضافة العنصر الخارجي إلى قائمة العناصر الخارجية في مقطع **تنسيق الرسالة** في صفحة **الكتالوج الخارجي**. حدد اسمًا للعنصر الخارجية الذي يستطيع المورّد التعرف عليه وتعيينه إلى قيمة. خيارات القيم هي: اسم المستخدم أو البريد الإلكتروني للمستخدم أو قيم عشوائية.
للحصول على مزيد من المعلومات حول بروتوكول cXML، راجع: http://cxml.org/

## <a name="post-back-message"></a>رسالة إعادة إرسال البيانات
رسالة إعادة إرسال البيانات هي الرسالة التي يتم استلامها من المورّد عندما يخرج المستخدم من الموقع الخارجي ويعود إلى Finance and Operations. يتعذر ترحيل تكوين رسائل إعادة نشر البيانات. تستند هذه الرسائل إلى تعريف بروتوكول cXML. فيما يلي المعلومات التي يمكن أن تكون جزءًا من رسالة إعادة إرسال البيانات التي يتم تلقيها في بند طلب:

| الرسالة المستلمة من المورّد | منسوخة إلى بند طلب في Finance and Operations|
|------------------------------|----------------------------------------------------------|
|< ItemIn quantity=”” > |الكمية|
|< ItemIn>< ItemID >< SupplierPartID >< /SupplierPartID >|معرف صنف خارجي|
|< ItemDetail>< UnitPrice >< Money currency=”” >| العملة|
|< ItemDetail >< UnitPrice >< Money >< /Money >| سعر الوحدة|
|< ItemDetail >< Description ShortName=”” >|اسم المنتج|
|< ItemDetail >< Description >< /Description >|مضمنة في وصف الصنف، اسم المنتج إذا لم يتم تحديد ShortName.|
|< ItemDetail >< UnitOfMeasure >< /UnitOfMeasure >|الوحدة|
|< ItemDetail >< Classification >< /Classification >|مضمنة في وصف الصنف|
|< ItemDetail >< Classification domain=”” >|مضمنة في وصف الصنف|

## <a name="delete-an-external-catalog"></a>حذف كتالوج خارجي
حذف كتالوج خارجي باستخدام إجراء الحذف في الصفحة.

إذا تم طلب منتج من كتالوج المورّد الخارجي، فسيتعذر حذف كتالوج المورّد الخارجي. بدلاً من ذلك، يتم تعيين حالة كتالوج المورّد الخارجي إلى غير نشط. إذا كنت ترغب في إزالة الوصول إلى موقع كتالوج المورّد الخارجي، وليس حذفه، فعليك تغيير حالة الكتالوج الخارجي إلى غير نشط.

