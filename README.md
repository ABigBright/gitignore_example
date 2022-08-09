# gitignore example

测试的目录如下，
```sh
.
├── a
│   └── a1.txt
├── a.txt
├── b
│   ├── b1.txt
│   └── bd
├── c
│   ├── c1
│   │   └── ok.txt
│   └── c2
│       └── err.txt
└── README.md
```

按照如上方式创建相关的目录和文件，去检验当前的ignore规则


检验一个文件或者目录是否被ignore，通过命令check-ignore去调试, 具体用法请参照git check-igore相关文档

git check-ignore file or dir

```sh
$ git check-ignore **/*

a
a/a1.txt
b/bd
c/c1
c/c1/ok.txt

```

从上面可以看出，输出的目录和文件是被忽略的，出此之外，则是没有忽略的。


如果想看详细的ignore规则，可以继续如下命令显示结果：

```sh
$ git check-ignore -v **/*

.gitignore:1:/* a
.gitignore:1:/* a/a1.txt
.gitignore:3:!a.txt     a.txt
.gitignore:5:!/b        b
.gitignore:6:/b/bd      b/bd
.gitignore:8:!/c/       c
.gitignore:9:/c/c1/     c/c1
.gitignore:9:/c/c1/     c/c1/ok.txt

```

