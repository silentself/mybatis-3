# mybatis-3

mybatis-3.5.1源码学习+注释
学习mybatis源码将mybatis源码从GitHub上clone下来之后,
首先需要先将pom文件中所有的
<optional>true</optional>改为<optional>false</optional>

MyBatis SQL Mapper Framework for Java
=====================================

[![Build Status](https://travis-ci.org/mybatis/mybatis-3.svg?branch=master)](https://travis-ci.org/mybatis/mybatis-3)
[![Coverage Status](https://coveralls.io/repos/mybatis/mybatis-3/badge.svg?branch=master&service=github)](https://coveralls.io/github/mybatis/mybatis-3?branch=master)
[![Maven central](https://maven-badges.herokuapp.com/maven-central/org.mybatis/mybatis/badge.svg)](https://maven-badges.herokuapp.com/maven-central/org.mybatis/mybatis)
[![Sonatype Nexus (Snapshots)](https://img.shields.io/nexus/s/https/oss.sonatype.org/org.mybatis/mybatis.svg)](https://oss.sonatype.org/content/repositories/snapshots/org/mybatis/mybatis/)
[![License](http://img.shields.io/:license-apache-brightgreen.svg)](http://www.apache.org/licenses/LICENSE-2.0.html)
[![Stack Overflow](http://img.shields.io/:stack%20overflow-mybatis-brightgreen.svg)](http://stackoverflow.com/questions/tagged/mybatis)
[![Project Stats](https://www.openhub.net/p/mybatis/widgets/project_thin_badge.gif)](https://www.openhub.net/p/mybatis)

![mybatis](http://mybatis.github.io/images/mybatis-logo.png)

The MyBatis SQL mapper framework makes it easier to use a relational database with object-oriented applications.
MyBatis couples objects with stored procedures or SQL statements using a XML descriptor or annotations.
Simplicity is the biggest advantage of the MyBatis data mapper over object relational mapping tools.

Essentials
----------

* [See the docs](http://mybatis.github.io/mybatis-3)
* [Download Latest](https://github.com/mybatis/mybatis-3/releases)
* [Download Snapshot](https://oss.sonatype.org/content/repositories/snapshots/org/mybatis/mybatis/)

### 问题：
-- 使用git提交时出现错误：
```$xslt
fatal: refusing to merge unrelated histories
```
### 背景：

在GitHub上创建的新仓库增加了README.md文件，在将mybatis源码通过如下命令
```$xslt
git init 
git add .
git commit -m "first commit"
git remote add origin https://github.com/silentself/mybatis-3.git
git pull origin master
```
最后执行**git pull origin master**命令的时候出现了错误

### 解决：
通过查询资料说是：
```$xslt
The default behavior has changed since Git 2.9:
"git merge" used to allow merging two branches that have no common base by default, 
which led to a brand new history of an existing project created and then get pulled by an unsuspecting maintainer, 
which allowed an unnecessary parallel history merged into the existing project. 
The command has been taught not to allow this by default, with an escape hatch --allow-unrelated-histories option to be used in a rare event that merges histories of two projects that started their lives independently.
```
翻译：
```$xslt
“ git merge”用于合并缺省情况下没有共同基础的两个分支，
这导致创建一个全新的已有项目历史，
然后被毫不知情的维护人员拉走，
这允许一个不必要的并行历史合并到现有项目中。 
该命令已被教导不允许这种默认情况下，
与逃生舱口——允许无关的历史选项，
用于一个罕见的事件，合并两个项目的历史，开始他们的生活独立。
```
所以需要在**git pull origin master**命令后加上--allow-unrelated-histories
即：
```$xslt
git pull origin master --allow-unrelated-histories
```