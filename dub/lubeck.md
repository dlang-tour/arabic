# Lubeck

.Mir و خوارزمية ,LAPACK ,CBLAS مكتبة جبر خطية عالية المستوى مبنية على

## التبعيات

.`dub.sdl` ربما عليك تثبيتهم و من ثم تحديث ,LAPACK و الواجهة البرمجية ل CBLASل Lubeck تتبع

.MacOS مثبتون مسبقاً على LAPACK و CBLAS

.Windows و Linuxموصى بهم ل [Intel MKL](https://software.intel.com/en-us/mkl) أو [OpenBLAS](http://www.openblas.net) طرفيات

## الروابط

 - [GitHub](https://github.com/kaleidicassociates/lubeck)
 - [Mir الواحهة البرمجية لخوارزمية](http://mir-algorithm.libmir.org)
 - [Mir الواجهة البرمجة للعشوائيات في](http://mir-random.libmir.org)
 - [البرمجية Mir واجهة](http://mir.libmir.org)

## {SourceCode:incomplete}

```d
/+dub.sdl:
dependency "lubeck" version="~>1.1"
+/
import kaleidic.lubeck: mtimes;
import mir.algorithm.iteration: each;
import mir.ndslice: magic, repeat, as,
    slice, byDim;
import std.stdio: writeln;

void main()
{
    auto n = 5;
    // المربع السحري
    auto matrix = n.magic.as!double.slice;
    // [1 1 1 1 1]
    auto vec = 1.repeat(n).as!double.slice;
    // لعملية الضرب CBLAS استخدم
    matrix.mtimes(vec).writeln;
    "-----".writeln;
    matrix.mtimes(matrix).byDim!0.each!writeln;
}
```
