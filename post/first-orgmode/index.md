# First-orgmode


* 简述

采用 =emacs org-mde= 在 =Hugo + Github= 部署的静态网站上记录个人博客。

* Hugo

- Hugo 是由 Go 语言实现的静态网站生成器。
- 简单、易用、高效、易扩展、快速部署。

* Github

github pages

- 完全免费
- 可以绑定域名
- 使用免费的 HTTPS
- 自己 DIY 网站的主题
- 使用他人开发好的插件

* Org-mode

** Read More

生成的文章要支持 Read More ，在需要分割的地方添加 ~#more~ (中间有空格)即可。

# more

** meta
#+begin_src org
#+title: First-orgmode
#+Author: daoyi
#+date: 2022-02-03T10:41:17+08:00
#+tags[]: org, hugo, emacs
#+categories[]: emacs
#+end_src

** titile

#+begin_src org
  * 一级标题
  ** 二级标题
#+end_src

** code

*** cmd
#+begin_src org
M-x
org-insert-structure-template
#+end_src

*** hotkey
在 spacemacs 中，使用快捷键 , i b 会弹出一个 minor 窗口，键入 s 即会在光标位置插入代码块，根据实际补充语言名称，最后会生成对应的高亮效果。

- 原始内容
#+begin_src org
  #+begin_src python
  def hello():
    return "hello world"

  return hello()
#+end_src

- 渲染效果
#+begin_src python
  def hello():
    return "hello world"

  return hello()
#+end_src

** image
#+begin_src org
[[/images/emacs/insert-source-code-block.png]]
#+end_src

** table
- 原始内容
#+begin_src org
  | A | B | C |
  |---+---+---+
  | a | b | c |
#+end_src

- 渲染效果
| A | B | C |
|---+---+---|
| a | b | c |

** footnote

spacemacs 添加脚注的快捷键是 =, i f= 。

*** sytax
#+begin_src org
  [1]
  　　纯数字脚注。和 footnote.el 兼容但是不建议，因为代码段里常常出现[1]
  [fn:名字]
  　　命名的脚注参考，名字是唯一的标签，或者可以自动地创建成数字。
  [fn::内联定义]
  　　LaTeX-like 的匿名脚注，定义直接在引用点（reference point）给出。
  [fn:名字:定义]
  　　一个内联的 fotnote，也指定名字作为提示。
      因为 Org 允许多个引用指向同一个名字，你可以用[fn:name]来创建额外的引用。
#+end_src

*** example

#+begin_src org
在这行添加第一个脚注[fn:1]。

在这行添加第二个脚注[fn:2]。
#+end_src

** Footnotes

[fn:1] 这是第一个脚注

[fn:2] 这是第二个脚注

** org-mode 转义

\vert 这样的符号在 org 里是需要转义，可以在 spacemacs 中键入 =SPC SPC= ，输入 =org-entities-help= 找到对应的转义码。

#+begin_center
[[https://kangxiaoning.github.io/images/emacs/org-entities-help.png]]
#+end_center

