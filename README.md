PSR-0 PSR-4 示例

在做composer包时，调示方法为在vendor_name目录下进行composer install则会生成vendor目录然后可写单元进行composer配置和类方法测试。


附：
PSR-0规范
1、 一个完全合格的 namespace 和 class 必须符合这样的结构：“< Vendor Name>(< Namespace>)*< Class Name>”
2、每个 namespace 必须有一个顶层的 namespace（"Vendor Name" 提供者名字）
3、每个 namespace 可以有多个子 namespace
4、当从文件系统中加载时，每个 namespace 的分隔符(/)要转换成 DIRECTORY_SEPARATOR (操作系统路径分隔符)
5、在类名中，每个下划线(_)符号要转换成 DIRECTORY_SEPARATOR (操作系统路径分隔符)。在 namespace 中，下划线_符号是没有（特殊）意义的。
6、当从文件系统中载入时，合格的 namespace 和 class 一定是以 .php 结尾的
7、verdor name,namespaces,class 名可以由大小写字母组合而成（大小写敏感的）


PSR-4规范
PSR-4规范了如何指定文件路径从而自动加载类定义，同时规范了自动加载文件的位置。这个乍一看和 PSR-0 重复了，实际上，在功能上确实有所重复。区别在于 PSR-4 的规范比较干净，去除了兼容 PHP 5.3 以前版本的内容，有一点 PSR-0 升级版的感觉。当然，PSR-4 也不是要完全替代 PSR-0，而是在必要的时候补充 PSR-0 ——当然，如果你愿意，PSR-4 也可以替代 PSR-0。PSR-4 可以和包括 PSR-0 在内的其他自动加载机制共同使用。
  
PSR4标准与PSR0标准的区别：

1）在类名中使用下划线没有任何特殊含义。

2）命名空间与文件目录的映射方法有所调整。

PSR-0风格

    vendor/
    vendor_name/
        package_name/
            src/
                Vendor_Name/
                    Package_Name/
                        ClassName.php       # Vendor_Name\Package_Name\ClassName
            tests/
                Vendor_Name/
                    Package_Name/
                        ClassNameTest.php   # Vendor_Name\Package_Name\ClassName
  PSR-4风格

    vendor/
    vendor_name/
        package_name/
            src/
                ClassName.php       # Vendor_Name\Package_Name\ClassName
            tests/
                ClassNameTest.php   # Vendor_Name\Package_Name\ClassNameTest    vendor/
    vendor_name/
        package_name/
            src/
                ClassName.php       # Vendor_Name\Package_Name\ClassName
            tests/
                ClassNameTest.php   # Vendor_Name\Package_Name\ClassNameTest