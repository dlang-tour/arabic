# Pegged

.(PEG) مولد قواعد لمفسر تعبيرات 

.الفكرة هي إعطاء المولد قواعد مفسر تعبيرات
.و من القواعد المحددة مجموعة من التفسيرات المتعلقة سيتم إنشائها, لتستخدم في وقت التشغيل أو وقت الترجمة

## اقرأ أيضاً

- [GitHub على Pegged](https://github.com/PhilippeSigaud/Pegged)
- [Pegged مقالة مرجعية لتركيب](http://bford.info/pub/lang/peg)

## {SourceCode:fullWidth:incomplete}

```d
/+dub.sdl:
dependency "pegged" version="~>0.4"
+/
import pegged.grammar;
import std.stdio;

mixin(grammar(`
Arithmetic:
    Term     < Factor (Add / Sub)*
    Add      < "+" Factor
    Sub      < "-" Factor
    Factor   < Primary (Mul / Div)*
    Mul      < "*" Primary
    Div      < "/" Primary
    Primary  < Parens / Neg / Pos / Number / Variable
    Parens   < "(" Term ")"
    Neg      < "-" Primary
    Pos      < "+" Primary
    Number   < ~([0-9]+)

    Variable <- identifier
`));

void main()
{
    // التفسير في وقت الترجمة
    enum parseTree1 = Arithmetic("1 + 2 - (3*x-5)*6");

    pragma(msg, parseTree1.matches);
    assert(parseTree1.matches == ["1", "+", "2", "-",
       "(", "3", "*", "x", "-", "5", ")", "*", "6"]);
    writeln(parseTree1);

    // و في وقت التشغيل أيضاً
    auto parseTree2 = Arithmetic(" 0 + 123 - 456 ");
    assert(parseTree2.matches == ["0", "+", "123", "-", "456"]);
}
```
