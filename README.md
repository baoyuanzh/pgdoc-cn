# PostgreSQL中文手册翻译计划
PostgreSQL官方手册对广大PostgreSQL用户来说是非常重要的学习和参考资料。
因此在2013年底PostgreSQL中国用户会成立了由志愿者组成的新的PG中文手册翻译小组，在社区第一代功勋laser所翻译的8.2.3中文手册的基础上开启了9.3.1版本的手册翻译工作。
目前已经完成9.3的所有sgml文件的翻译，正在进行校对工作。
但翻译中难免会有不准确的地方，尤其是尚未校对的部分，希望读者发现问题后及时帮忙纠正或者参与校对，不断完善PG的中文手册。

## 文档翻译QQ群
QQ:309292849

文档翻译QQ群用于文档翻译相关的交流。

## Github托管仓库
https://github.com/postgres-cn/pgdoc-cn

本Github仓库存放已翻译好的sgml文件，通过这些sgml文件可编译成html和pdf等各种格式的文档。
本Github仓库接受对已翻译好的文档的质量改善，欢迎读者的反馈和修正（通过Issues和Pull requests）。


## 文档的编译
### Windows上的编译
  1 . 安装Perl

http://www.activestate.com/activeperl/downloads

  2 . 下载本Github仓库
```shell
git clone https://github.com/postgres-cn/pgdoc-cn.git
```

  3 . 进入pgdoc-cn目录双击执行builddoc.bat
```shell
cd pgdoc-cn
builddoc.bat
```

  4 . 查看编译效果

打开以下html文件查看编译效果

pgdoc-cn/build/doc/src/sgml/html/index.html

### Linux/UNIX上的编译
  1 . 下载本Github仓库
```shell
git clone https://github.com/postgres-cn/pgdoc-cn.git
```

  2 . 下载对应版本的PostgreSQL源码并解压
```shell
wget https://ftp.postgresql.org/pub/source/v9.3.1/postgresql-9.3.1.tar.gz
tar xzf postgresql-9.3.1.tar.gz
```

  3 . 对Github仓库中的sgml文件进行转码（UTF8->GBK）
```shell
cd pgdoc-cn
perl tools/encoding_convert.pl
```

  4 . 用转码后的sgml文件覆盖PostgreSQL源码中的
```shell
cp -rf build/doc/src/sgml ../postgresql-9.3.1/doc/src/
```

  5 . 下载编译PG手册所必需的工具集

参考：http://www.postgresql.org/docs/9.3/static/docguide-toolsets.html

  6 .  编译PG手册
```shell
cd ../postgresql-9.3.1/
./configure
cd doc/src/sgml
gmake html
```
参考：http://www.postgresql.org/docs/9.3/static/docguide-build.html

  7 . 查看编译效果
打开以下html查看编译效果

postgresql-9.3.1/doc/src/sgml/html/index.html


## 在线中文手册
http://www.postgres.cn/docs/9.3

通过在线中文手册上每个页面右上角的“问题报告”和“纠错本页面”链接可直接跳转到Github仓库中的相应位置报告问题或在线修改。


## 离线中文手册
https://github.com/postgres-cn/pgdoc-cn/releases

从Release页面，可以下载html和pdf格式的离线手册


## 参与和协助翻译计划
### 1. 意见反馈
发现翻译文档中的问题后，进行反馈或对翻译工作提出建议

方式1. 在本Github仓库中[发行Issue](https://github.com/postgres-cn/pgdoc-cn/issues/new)，反映问题（请注明问题内容及所在的章节段落位置）或提出建议

方式2. 加入文档翻译QQ群（309292849），进行反馈

### 2. 错误纠正
发现翻译文档中的个别问题后，直接修正对应的sgml文件，并通过Pull Request向本Github仓库提交。
之后由系统管理员接受Pull Request。

关于html页面和sgml文件的对应关系，可通过点击“在线阅读”web页面右上角的“纠错本页面”链接跳转到Github仓库中的相应sgml文件的编辑页面。

### 3. 文档校对
文档校对工作通过Github + wiki的方式进行，详见[PostgreSQL 9.3.1 中文手册的翻译校对（志愿者募集中）](https://github.com/postgres-cn/pgdoc-cn/wiki/check9.3)。   
目前手册的大部分章节都没有经过校对，翻译上的小问题不少，欢迎有兴趣的同学参加校对工作。


## 其它
1. Github仓库中的sgml文件编码是UTF8。
2. Github仓库中的修正会由后台程序每隔十分钟自动反映到在线中文手册中。
3. 如果Github仓库中的修正迟迟未能反映到在线中文手册，可能发生了编译错误，可通过查看[编译日志](http://postgres.cn/docs/9.3/build.log)了解情况。
4. 目前PostgreSQL 9.4中文手册的翻译（通过“9.4”分支）也在同步进行，详见 [PostgreSQL9.4中文手册的翻译](https://github.com/postgres-cn/pgdoc-cn/wiki/pg9.4)，但我们希望新加入的小伙伴优先投入到9.3.1的校对工作中去。




