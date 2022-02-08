# snippets使用小结

# #+draft: true
#+autoCollapseToc: false

** 常用指令
| hotkey    | M-x （function）         | note |
|-----------+------------------------+------|
| C-c & C-n | yas-new-snippet        |      |
| C-c & C-s | yas-insert-snippet     |      |
| C-c & C-v | yas-visit-snippet-file |      |
|           | yas-tryout-snippet     | test |

- 可以保存到两个地方：
  - ~/.emacs.d/private/snippets/modename-mode/
  - ~/.spacemacs.d/snippets/modename-mode/
    
** 模板说明

#+BEGIN_SRC C
  #name : #ifndef XXX; #define XXX; #endif
  # key: once
  # --
  #ifndef ${1:`(upcase (file-name-nondirectory (file-name-sans-extension (or (buffer-file-name) ""))))`_H}
  #define $1

  $0

  #endif /* $1 */
#+END_SRC

- $0
  代码片段中的 $0 表示代码片段填充之后光标最后停的地方，$1 $2 $3... 表示按 TAB 之后光标停的地方。

- =M-/= 触发
  spacemacs 的 TAB 按键被自动补全使用了，可以使用了 M-/ 来触发。

** auto-completion 整合

#+BEGIN_SRC emacs-lisp
(setq-default dotspacemacs-configuration-layers
              '((auto-completion :variables
                                 auto-completion-enable-snippets-in-popup t)))
#+END_SRC



