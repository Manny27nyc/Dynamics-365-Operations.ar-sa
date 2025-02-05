---
title: إنشاء فواتير أمر المبيعات
description: توضح هذه المقالة كيفية إعداد فاتورة لأمر مبيعات، بما في ذلك دمج الفواتير ومعالجة الدُفعات.
author: ShivamPandey-msft
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesEditLines,  SysQueryForm, SysRecurrence
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ceda837cae563dab68969cb9f05de113079d4495
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/03/2022
ms.locfileid: "8910247"
---
# <a name="create-sales-order-invoices"></a>إنشاء فواتير أمر المبيعات

[!include [banner](../../includes/banner.md)]

توضح هذه المقالة كيفية إعداد فاتورة لأمر مبيعات، بما في ذلك دمج الفواتير ومعالجة الدُفعات. يستخدم هذا الإجراء شركة بيانات العرض التوضيحي USMF.


## <a name="create-an-invoice-from-a-sales-order"></a>إنشاء فاتورة من أمر مبيعات
1. انتقل إلى **جزء التنقل > الوحدات النمطية > الحسابات المدينة > الأوامر > أوامر المبيعات المشحونة وغير المفوترة‬**.
2. حدد أمر مبيعات من القائمة. 
3. في **جزء الإجراءات **، انقر فوق** فاتورة > عام > فاتورة**. لاحظ أن أمر المبيعات هذا لديه إيصالات تعبئة متعددة مقترنة به. وسوف يعرض كلمة *متعدد* فقط بدلاً من رقم إيصال التعبئة.  
4. قم بتوسيع قسم **المحددات**.
    - يجب تعيين الترحيل إلى "نعم" لترحيل الفاتورة. يمكنك أيضًا إيقاف ترحيل الفاتورة وطباعتها فقط. ومع ذلك، يمكنك تحقيق نفس النتيجة عن طريق إنشاء فاتورة مبدئية بدلاً من فاتورة.  
    - وهذا الخيار يُستخدم لوظائف الدُفعات. ويتم إجراء الاستعلام عند تشغيل وظيفة الدُفعة.
5. في الحقل **طباعة**، حدد "بعد".
6. حدد **نعم** في **طباعة الفاتورة**. بإمكان إدارة الطباعة‬ طباعة نسخ متعددة من الفاتورة وأيضًا إرسال الفاتورة عبر البريد الإلكتروني كملف PDF.  
7. في الحقل **طباعة التكاليف**، حدد "تلخيص‬".
8. في حقل **فحص الحد الائتماني‬**، حدد "الرصيد'.
9. وانقر فوق **إلغاء الأمر**.

## <a name="combine-orders-into-a-single-invoice"></a>دمج أوامر في فاتورة واحدة
1. انتقل إلى **جزء التنقل > الوحدات النمطية > الحسابات المدينة > الأوامر > كافة أوامر المبيعات**.
2. حدد موقع عميل لديه عدة فواتير مفتوحة.
3. حدد أوامر مبيعات مفتوحة متعددة من نفس العميل.
4. في **جزء الإجراءات **، انقر فوق** فاتورة > عام > فاتورة**.
5. قم بتوسيع قسم **المحددات**.
6. في حقل **الكمية** ، حدد "الكل". لاحظ أن مقطع النظرة العامة يتضمن فاتورتين مدرجتين فيه. لنعمل الآن على دمجهما في فاتورة واحدة.  
7. في الحقل **تحديث ملخص لـ‬**، حدد "حساب الفاتورة".
8. انقر فوق **ترتيب** لدمج أوامر المبيعات في فاتورة واحدة. تم الآن دمج أمري المبيعات في فاتورة واحدة.   
9. وانقر فوق **إلغاء الأمر**.
10. انقر فوق **نعم**.

## <a name="post-invoices-in-a-batch"></a>ترحيل الفواتير في دُفعة
1. انتقل إلى **جزء التنقل > الوحدات النمطية > الحسابات المدينة > الفواتير > فوترة الدُفعة‬ > فاتورة‬**.
2. انقر فوق **تحديد**.
3. انقر فوق **موافق**.
4. انقر فوق **دُفعة**.
5. في **معالجة الدُفعة**، حدد **نعم**.
6. انقر فوق **التكرار**.
7. حدد **الأيام‬**.
8. انقر فوق **موافق**.
9. انقر فوق **موافق**.
10. وانقر فوق **إلغاء الأمر**.
11. انقر فوق **نعم**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
