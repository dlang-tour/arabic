# الحلقات التكرارية

.أربع أنواع للحلقات التكرارية D توفر

### 1) `while`

:تنفذ الكود المعطى داخل الحلقة طالما يتم تحقق شرط `while` حلقات

    while (condition)
    {
        foo();
    }

### 2) `do ... while`

.تنفذ الكود المعطى داخل الحلقة طالما يتم تحقق شرط لكن الفرق عن السابقة أنها تنفذ الكود لمرة واحدة قبل التحقق من الشرط `do ... while` حلقة

    do
    {
        foo();
    } while (condition);

### 3) الكلاسيكية `for` حلقة

:مع _بداية_ و _شرط_ و _تعليمة_ التكرار Java و C/C++ و هي الحلقة المتعارف عليها من

    for (int i = 0; i < arr.length; i++)
    {
        ...

### 4) `foreach`

:سيشرح عنها بتفصيل أكبر في القسم القادم [`foreach` حلقة](basics/foreach) 

    foreach (el; arr)
    {
        ...
    }

#### الكلمات الخاصة و العناوين

.مباشرةً سوف توقف حلقة التكرار الحالية `break` الكلمة الخاصة

:في حلقة تكرار متداخلة يمكن استخدام _عنوان_ للخروج عن أي حلقة تكرارية خارجية

    outer: for (int i = 0; i < 10; ++i)
    {
        for (int j = 0; j < 5; ++j)
        {
            ...
            break outer;

.تبدأ بالتكرار التالي للحلقة `continue` الكلمة المفتاحية

### للتعمق

- `for` loop in [_Programming in D_](http://ddili.org/ders/d.en/for.html), [specification](https://dlang.org/spec/statement.html#ForStatement)
- `while` loop in [_Programming in D_](http://ddili.org/ders/d.en/while.html), [specification](https://dlang.org/spec/statement.html#WhileStatement)
- `do-while` loop in [_Programming in D_](http://ddili.org/ders/d.en/do_while.html), [specification](https://dlang.org/spec/statement.html#do-statement)

## {SourceCode}

```d
import std.stdio : writeln;

/*
.يحسب المتوسط الحسابي للعناصر ضمن مصفوفة
*/
double average(int[] array)
{
    immutable initialLength = array.length;
    double accumulator = 0.0;
    while (array.length)
    {
        // .front هذا يمكن أن يتم بواسطة
        // import std.array : front; بواسطة
        accumulator += array[0];
        array = array[1 .. $];
    }

    return accumulator / initialLength;
}

void main()
{
    auto testers = [ [5, 15], // 20
          [2, 3, 2, 3], // 10
          [3, 6, 2, 9] ]; // 20

    for (auto i = 0; i < testers.length; ++i)
    {
      writeln("The average of ", testers[i],
        " = ", average(testers[i]));
    }
}
```
