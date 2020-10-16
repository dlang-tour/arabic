# Mir

:هذه الحزمة تتضمن

 - [mir-algorithm package](dub/mir-algorithm). ndslice - داخلية للرياضيات, الصرافة و مكان لحزمة المصفوفات متعددة الأبعاد D مكتبة.
 - [mir-random package](dub/mir-random). إنشاء أرقام عشوائية متقدم
 - Sparse tensors
 - Hoffman

## الروابط

 - [Mir الواجهة البرمجية لخوارزمية](http://mir-algorithm.libmir.org)
 - [Mir الواجهة البرمجية لعشوائية](http://mir-random.libmir.org)
 - [Mirالواجهة البرمجية ل](http://mir.libmir.org)
 - [GitHub](https://github.com/libmir/mir)
 - [Lubeck](https://github.com/kaleidicassociates/lubeck) - NDSliceمكتبة جبر خطية مبنية على الواجهة البرمجية ل.

## {SourceCode}

```d
/+dub.sdl:
dependency "mir" version="~>3.2"
+/
import mir.sparse;
import std.stdio: writeln;

void main()
{
    // DOK صيغة
    auto sl = sparse!double(5, 8);
    sl[] =
        [[0, 2, 0, 0, 0, 0, 0, 1],
         [0, 0, 0, 0, 0, 0, 0, 4],
         [0, 0, 0, 0, 0, 0, 0, 0],
         [6, 0, 0, 0, 0, 0, 0, 9],
         [0, 0, 0, 0, 0, 0, 0, 5]];

    // CRS/CSR صيغة
    auto crs = sl.compress;
    writeln(crs);
}
```
