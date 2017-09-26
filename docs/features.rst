主要重要特性包括以下:

* **插件管理使用 Vim-plug**! 你可以方便地安装或者卸载插件,它们被装在 ``.vim/plugged/`` 文件夹内. 更多信息点击 `here <https://github.com/junegunn/vim-plug>`_

* **智能补全**, 使用python的instrospection (补全模块名字,实例方法,属性) 或者基于文本 (从版本4.0开始, 它变得更加智能!). neocomplcache甚至可以自动补全打字错误.

* **模糊文件代码命令查询** (与Textmante或者Sublime Text 2相似):

	* ``,e`` = 打开文件 (就像是最初的 :e) ,可以进行地柜以及模糊匹配. 例如: 如果你输入 "mopy" ,它会找到子文件夹中的 "models.py". 你可以使用 ``Ctrl-t`` 在新标签中打开选中文件!
	* ``,g`` = fuzzy symbol finder (classes, methods, variables, functions, ...) on the current file. Example: if you type "usr" it will find the User class definition on the current file. ``,G`` does the same but on all opened files.
	* ``,c`` = fuzzy command finder (internal vim commands, or custom commands). Example: if you type "diff" it will find ``:GitDiff``, ``:diffthis``, and many other similar commands.
	* ``,f`` = 在所有打开文件中进行模糊文本查询。 例如: 如果你打 "ctm=6"，它会找到包含 "current_time = 16"的一行。
	* ``,m`` = 模糊查询最近打开的文件。
	* ``,we``, ``,wg``, ``,wc``, ``,wf`` and ``,wm`` = same as ``,e``, ``,g``, ``,c``, ``,f`` and ``,wm`` but initiate the search with the word under the cursor (also the upper case version of ``,G``, ``,wG``). Is useful to think about the ``,wg`` as a "fuzzy go to definition" (if the definition is in the same file, or ``,wG`` if the definition is on any of the opened files).
	* ``,pe`` = 和 ``,e`` 一样，但是使用光标下的路径启动搜索。


* **Ropevim for really neat python goodies!**:

	* **Go to definition** with ``,d``, or open the definition on a new tab with ``,D``.
	* **Find occurrences** with ``,o``.

* **Classes/module browser** that lists classes, functions, methods, and such of the current file, and navigates to them when ENTER is pressed. Toggle it with ``F4``.

* **待处理任务浏览** 按 ``F2``. 它会读取当前文件并查找诸如"TODO","FIXME" 等内容,在列表中显示它们,并允许类似于类浏览器的导航.

* **代码语法检查** 使用 Syntastic (它能检测未使用的变量、导入模块、语法错误等), 对于某些编程语言，高亮错误,并给出警告.你可以使用 ``\e`` 打开错误列表. python语法检查包括 **pep8** 和 **pylint**.

* **递归查询代码** 并浏览结果:

	* ``,r`` 使用ack命令 (一种优化过的用来进行代码查询的工具), 列出找到的匹配并允许你使用ENTER打开.
	* ``,wr`` 相同的效果, 但是搜索当前光标下的单词.

* Some settings for better **tabs and spaces handling**.

* **更好的文件浏览**,  ``F3`` 关闭, 使用 ``,t`` 选择文件并打开.

* **结果计数** 搜索文本的时候.

* **搜索、阅读python文档** 使用``:Pydoc``命令. 例如: ``:Pydoc collections`` (也可以在当前的单词上使用vim的默认帮助键绑定: ``Shift-K``).

* **注释代码** 使用 ``\ci``.

* **简答选项卡浏览**:

	* ``tt`` = 新选项卡，光标等待输入文件路径。 (输入空的话会打开一个空的选项卡)。
	* ``tn`` or ``Ctrl-Shift-Right`` = 下一个选项卡。
	* ``tp`` or ``Ctrl-Shift-Left`` = 上一个选项卡。
	* ``tm`` = 移动当前选项卡到一个具体位置。 (没有设置具体数值的话移动到最后)。
	* ``tl`` = 在侧栏显示当前选项卡及其内部窗口的列表。你可以浏览！
	* ``ts`` = 复制当前选项卡。

	以 ``t`` 开头的命令只在命令模式下有效，但是 ``Ctrl-Shift`` 在命令模式和插入模式都有效。

* **简易窗口浏览** 使用 ``Alt-arrows`` .

* 一些默认开启的vim插件:

	* **incremental search** (moves to the first result while you are typing).
	* **高亮搜索结果**.
	* **行号**.
	* 保持 **光标在浏览的时候距离屏幕边界3行**.
	* **shell-like autocompletion of commands and paths** (autocomplete the common part and show matching options).
	* 默认开启**语法高亮**.

* **vim中的python交互**, 或者别的控制台. 使用命令 ``:ConqueTerm`` ,他们以缓冲的方式打开. 例如: ``:ConqueTerm python``, ``:ConqueTerm bash``.

* **以sudo保存当前文件** 使用 ``:w!!``.

* **Navigate html/xml tags** the same way that you navigate (), {} and []: using ``%``.

* **Beautiful status line allways visible**, with colors, breadcrumbs and useful information about file type, encoding and position. When working with python files, it also displays the current python function or class where the cursor is.

* **自动删除尾随空格** 保存 python 文件的时候.

* **智能闭合 (, [, and {**

* **Beautiful color schemes for on vim with 256 colors (fisa colorscheme) and gvim (wombat colorscheme)**.

* **使用 256 色** 可能的话。

* **2 spaces indentation for html and javascript** (can disable it removing two lines from the ``.vimrc``).

* **各种编程语言的代码片段** 使用 SnipMate. 例如, 在python中你可以输入 ``cl`` ,之后按下 ``tab`` (在插入模式中), 它就会插入python类通用格式 (之后使用 ``tab`` 来浏览代码片段).

* **Zen coding** html使用: 生成大量html的简易代码表达.
	例如:

	1. 写 ``#books>ul>li.book*5>a``
	2. 按下 ``Ctrl-y ,``
	3. 它会生成e:

		 ::

			<div id="books">
					<ul>
							<li class="book">
									<a href=""></a>
							</li>
							<li class="book">
									<a href=""></a>
							</li>
							<li class="book">
									<a href=""></a>
							</li>
							<li class="book">
									<a href=""></a>
							</li>
							<li class="book">
									<a href=""></a>
							</li>
					</ul>
			</div>

	插件网站上查看更多 `site <https://github.com/mattn/zencoding-vim/>`_.

* **Git and other vcs integration**, with commands such as: ``:GitStatus``, ``:GitDiff``, ``:GitBlame``, ``:GitLog``, ``:GitCommit``, or simply ``:Git`` with your own command. Key mappings and syntax highlighting for git displays. Displays icons on the side of each line based on the result of a diff of the current file (example: if you added a line and still didn't commit the file, that line will have a green ``+`` on its side). And finally, when on a changed file you can **jump through changes** using ``\sn`` and ``\sp``.

* **更好的python缩进**.

* Really neat **surround actions** using the surround.vim plugin. Learn how to use it `here <https://github.com/tpope/vim-surround>`_.

* **Indentation defined text objects** for the editing language, named ``i``. For example, you can change an entire indented code block with ``cii``, or the indented block and its header line with ``cai`` (also yank, delete, ...).

* **基础代码块移动**使用 ``[-`` 移动至当前python代码块的开头,  ``]-`` 移至末尾, 更多信息 (简短参考 `here <https://github.com/jeetsukumaran/vim-indentwise>`_).

* **Python class and method/function text objects** for the editing language, named ``C`` and ``M``. For example, you can change an entire function content with ``ciM``, or delete a class including its header with ``daC``.

* **运行当前python文件** 使用 ``\r`` 显示输出。

* **插入、移除ipdb 断点** 使用 ``\b``。

* **Copy history navigation** using the YankRing plugin, which allows you to cicle the vim clipboard with ``Ctrl-p`` and ``Ctrl-n``, and many other features (described `here <http://www.vim.org/scripts/script.php?script_id=1234>`_).

* **自动给导入的模块排序** 使用 ``:Isort``.

* **Persistent undos** modify file, exit vim, reopen file, and you can undo changes done on the previous session.

* **更好地路径** 临时交换文件, 备份, 未完成文件 (它们都被存放在 ``~/.vim/dirs`` 下).

* **Drag visual blocks** (blocks selected on ``Ctrl-v`` and ``Shift-v`` visual modes) with ``Shift-Alt-arrows``, or even **duplicate** them with ``D``.

* **简单窗口选择**: 按 ``-`` ,你会看到每个窗口都有大的绿色字母,只需按下需要激活的窗口的字母.

* **Paint css color** values with the actual color.

* **格式化python代码** 使用 yapf (``:YapfFullFormat`` 格式化整个文件, 详情 `here <https://github.com/pignacio/vim-yapf-format>`_. **Works only if you have a vim compiled with python 2, not python 3**).

* **按文件夹自定义配置** 在工程的根目录添加一个 ``.vim.custom`` 文件.
	例如,如果你想要一个像下面这样的工程目录树，并且你不希望 ``folder_x`` 被检索, 在 ``.vim.custom`` 文件中写入 ``let g:ctrlp_custom_ignore["dir"] = g:ctrlp_custom_ignore["dir"] . '|\v[\/]folder_x$'`` .

	::

		project
		├── folder_1
		├── folder_2
		├── folder_x
		└── .vim.custom
