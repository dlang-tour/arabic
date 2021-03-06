# D أهلاً بك إلى

.D أهلاً بك إلى الدورة التفاعلية للغة البرمجة

{{#dmanmobile}}

.الدورة تعطي نظرة حول هذه اللغة __القوية__ و __المعبرة__ التي تترجم لكود ألة __فعال__ و أصلي

{{/dmanmobile}}

### ؟D ما هي

:هي أوج _عقود من تجربة تنفيذ المترجمات_ للعديد من اللغات المتنوعة و لديها مجموعة من المزايا الفريدة D لغة 

{{#dmandesktop}}

- مشيدات __عالية المستوى__ لقوة نمذجة كبيرة
- لغة مترجمة عالية الأداء
- كتابة ثابتة
- واجهة مباشرة لواجهة نظام التشغيل البرمجة و قطع الحاسوب المادية
- وقت ترجمة سريع للغاية
- (SafeD) فرعية امنة للذاكرة
- _قابل للصيانة_ (للتحكم) و كود _سهل الإستيعاب_
- (و اللغات الأخرى Javaمشابه ل ,C منحنى تعليمي متدرج (تركيب مشابه للغة
- البرمجية C متوافق مع واجهة تطبيقات
- البرمجية C++ توافق محدود مع واجهة تطبيقات
- نماذج متعددة (أمرية, نموذجية, كائنية التوجه, عامة, برمجة نقية تابعية, و حتى التجميع أي تجميعية)
- كشف أخطاء مبني (العقود, الإختبارات الوحدية)

...و العديد من [المزايا](http://dlang.org/overview.html)

{{/dmandesktop}}

### حول الدورة

.D كل قسم يأتي مع مثال شيفرة مصدرية يمكن تعديله و استخدامه لتجربة مزايا لغة

.لترجمة الشيفرة المصدرية و تشغيلها (`Ctrl-enter` اضغط زر التشغيل (أو 

للتوجه خلال هذه الدورة, استخدم روابط رموز السهمين المتجه لليمين للتنقل للتالي و لليسار للوراء في أسفل الصفحة أو إذهب لأقسام محددة بإستخدام القوائم الموجودة في رأس الصفحة

### التطوع

.pull requests هذه الدورة [مفتوحة المصدر](https://github.com/dlang-tour) و نحن نرحب بجعلها أفضل عن طريق

## {SourceCode}

```d
import std.stdio;
import std.algorithm;
import std.range;

void main()
{
    // لنبدأ
    writeln("Hello World!");

    // هذا مثال للمبرمجين الذين لديهم خبرة
    // نأخذ 3 مصفوفات دون حاجة لوضعهم في الذاكرة و ترتيبهم في أمكنة المصفوفات
    int[] arr1 = [4, 9, 7];
    int[] arr2 = [5, 2, 1, 10];
    int[] arr3 = [6, 8, 3];
    sort(chain(arr1, arr2, arr3));
    writefln("%s\n%s\n%s\n", arr1, arr2, arr3);
    // أو ما يسمى بخوارزميات المدى "Range algorithms" لمعرفة المزيد من المعلومات حول هذا المثال, ألقي نظرة على صفحة 
    // "Gems" في قسم
}
```
