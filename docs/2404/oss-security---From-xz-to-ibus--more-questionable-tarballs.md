<!--yml

分类：未分类

日期：2024-05-27 12:50:52

-->

# oss-security - 从 **xz** 到 **ibus**：更多可疑的 **tarballs**

> 来源：[https://www.openwall.com/lists/oss-security/2024/04/01/1](https://www.openwall.com/lists/oss-security/2024/04/01/1)

[[<prev]](../../../2024/03/31/13) [[next>]](2 **[[""]]( "")**  [[thread-next>]](3 [[day]](.) [[month]](..) [[year]](../..) [[list]](../../..)

```
Date: Mon, 1 Apr 2024 14:58:30 +0200 (CEST)
From: Jan Engelhardt <jengelh@...i.de>
To: oss-security@...ts.openwall.com
cc: takao.fujiwara1@...il.com
Subject: From xz to ibus: more questionable tarballs

In the ibus repository at https://github.com/ibus/ibus ,
commit 0ad8e77bd36545974ad8acd0a5283cf72bc7c8ad
was tagged as refs/tags/1.5.29-rc2 (+signed) on 2023-11-09,
and a disted tarball was made available (but unsigned), and Linux distros have
imported it (file checksums all line up).

https://github.com/ibus/ibus/releases/download/1.5.29/ibus-1.5.29-rc2.tar.gz

Comparing this disttar to the git repository and favorably
*discounting* autotools-related files and (what appears to be)
vala-to-c transpiling, I'm left with benign, but unexplicable
changes. It seems the git is "older", as e.g. one still finds "beta3"
in the diff, but also the disttar's ibuscodegen.h has an older
copyright line and an incomplete cherry-pick from
8f00d67b809036b0b76ae257cfe7e102bc8f1dec.

*runs away screaming*

In light of the xz revelations, I thought it's worth pointing out 
this class of problems.

$ tar -xf ibus-1.5.29-rc2.tar.gz
$ git clone -b 1.5.29-rc2 https://github.com/ibus/ibus ibus-git
$ diff -dprux .git ibus-git ibus-1.5.29-rc2
diff -dpru ibus-git/engine/simple.xml.in ibus-1.5.29-rc2/engine/simple.xml.in
--- ibus-git/engine/simple.xml.in       2024-04-01 14:08:16.541903956 +0200
+++ ibus-1.5.29-rc2/engine/simple.xml.in        2023-11-09 07:10:15.000000000 +0100
@@ -3,781 +3,596 @@
     <name>org.freedesktop.IBus.Simple</name>
     <description>A table based simple engine</description>
     <exec>@libexecdir@...us-engine-simple</exec>
-    <version>1.5.29-beta3.20230822</version>
+    <version>1.5.29-rc2.20231109</version>
     <author>Peng Huang &lt;shawn.p.huang@...il.com&gt;</author>
     <license>GPL</license>
...
--- ibus-git/po/de.po   2024-04-01 14:08:16.555237247 +0200
+++ ibus-1.5.29-rc2/po/de.po    2023-11-09 07:10:08.000000000 +0100
@@ -22,7 +22,7 @@ msgid ""
 msgstr ""
 "Project-Id-Version: IBus\n"
 "Report-Msgid-Bugs-To: https://github.com/ibus/ibus/issues\n"
-"POT-Creation-Date: 2023-08-02 00:14+0900\n"
+"POT-Creation-Date: 2023-11-09 15:10+0900\n"
 "PO-Revision-Date: 2023-08-04 17:21+0000\n"
 "Last-Translator: Mike FABIAN <mfabian@...hat.com>\n"
 "Language-Team: German <https://translate.fedoraproject.org/projects/ibus/"
diff -dpru ibus-git/src/ibusunicodegen.h ibus-1.5.29-rc2/src/ibusunicodegen.h
--- ibus-git/src/ibusunicodegen.h       2024-04-01 14:08:16.568570535 +0200
+++ ibus-1.5.29-rc2/src/ibusunicodegen.h        2023-11-09 07:09:53.000000000 +0100
@@ -1,8 +1,8 @@
 /* -*- mode: C; c-basic-offset: 4; indent-tabs-mode: nil; -*- */
 /* vim:set et sts=4: */
 /* ibus - The Input Bus
- * Copyright (C) 2018-2023 Takao Fujiwara <takao.fujiwara1@...il.com>
- * Copyright (C) 2018-2023 Red Hat, Inc.
+ * Copyright (C) 2018-2021 Takao Fujiwara <takao.fujiwara1@...il.com>
+ * Copyright (C) 2018-2021 Red Hat, Inc.
  *
  * This library is free software; you can redistribute it and/or
  * modify it under the terms of the GNU Lesser General Public
@@ -1310,6 +1310,10 @@ const static char *unicode_blocks[] = {
     /* TRANSLATORS: You might refer the translations from gucharmap with
                     the following command:
        msgmerge -C gucharmap.po ibus.po ibus.pot */
+    N_("CJK Unified Ideographs Extension I"),
+    /* TRANSLATORS: You might refer the translations from gucharmap with
+                    the following command:
+       msgmerge -C gucharmap.po ibus.po ibus.pot */
     N_("CJK Compatibility Ideographs Supplement"),
     /* TRANSLATORS: You might refer the translations from gucharmap with
                     the following command:

```

[由 blists 提供支持](http://www.openwall.com/blists/) - [更多邮件列表](http://lists.openwall.net)

请查看 [开源软件安全维基](https://oss-security.openwall.org/wiki/)，这是与此 [邮件列表](https://oss-security.openwall.org/wiki/mailing-lists/oss-security) 相对应的网站。

对 [邮件列表](/lists/) 及其使用感到困惑吗？ [在维基百科上阅读关于邮件列表的介绍](https://zh.wikipedia.org/wiki/电子邮件列表)，并查看这些 [关于消息正确格式化的指南](https://www.complang.tuwien.ac.at/anton/mail-news-errors.html)。
