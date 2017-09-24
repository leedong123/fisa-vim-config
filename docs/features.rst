主要重要特性包括以下:

* **插件管理使用 Vim-plug**! You can easily install or remove plugins, and they are installed into ``.vim/plugged/``. More info `here <https://github.com/junegunn/vim-plug>`_

* **智能补全**, sometimes using python instrospection (completion of module names, instance methods and attributes) and sometimes text-based (used words) (从版本4.0开始, 它变得更加智能!). And with neocomplcache, it even can autocomplete with typos, thanks to the fuzzy completion settings.

* **Fuzzy file, code and command finder** (like Textmante or Sublime Text 2):

	* ``,e`` = open file (like the original :e) but with recursive and fuzzy file name matching. Example: if you type "mopy" it will find a file named "models.py" placed on a subdirectory. And allows you to open the selected file on a new tab with ``Ctrl-t``!
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

* **Pending tasks browser** pressing ``F2``. This reads the current file searching for comments that start with "TODO", "FIXME", and such, and shows them on a list that allows navigation similar to the class browser.

* **Error checking of code** using Syntastic (it will detect unused variables or imports, syntax errors, and such), for several languages, highlighting the errors and warnings in the code. You can open an errors list with ``\e``. In python, the error checking includes **pep8** validation, and **pylint**.

* **Grep code recursively** and navigate the results:

	* ``,r`` uses the ack command (a kind of grep optimized for code search), lists the found matches, and allows you to open them with ENTER.
	* ``,wr`` does the same, but searching the word under the cursor.

* Some settings for better **tabs and spaces handling**.

* **Better file browser**, toggle it with ``F3``, or open it with your current file selected using ``,t``.

* **Results count** while searching text.

* **搜索、阅读python文档** 使用``:Pydoc``命令. 例如: ``:Pydoc collections`` (也可以在当前的单词上使用vim的默认帮助键绑定: ``Shift-K``).

* **注释代码** 使用 ``\ci``.

* **简答选项卡浏览**:

	* ``tt`` = 新选项卡，光标等待输入文件路径。 (输入空的话会打开一个空的选项卡)。
	* ``tn`` or ``Ctrl-Shift-Right`` = 下一个选项卡。
	* ``tp`` or ``Ctrl-Shift-Left`` = 上一个选项卡。
	* ``tm`` = 移动当前选项卡到一个具体位置。 (没有设置具体数值的话移动到最后)。
	* ``tl`` = 在侧栏显示当前选项卡及其内部窗口的列表。你可以浏览！
	* ``ts`` = 复制当前选项卡。

	The mappings starting with the ``t`` letter work only on command mode, but the mappings with ``Ctrl-Shift`` work on both, command and insert mode.

* **简易窗口浏览** 使用 ``Alt-arrows`` .

* 一些默认开启的vim插件:

	* **incremental search** (moves to the first result while you are typing).
	* **高亮搜索结果**.
	* **行号**.
	* 保持 **光标在浏览的时候距离屏幕边界3行**.
	* **shell-like autocompletion of commands and paths** (autocomplete the common part and show matching options).
	* 默认开启**语法高亮**.

* **Python interpreter inside vim**, or any other console. They are opened as a buffer using the command ``:ConqueTerm``. Examples: ``:ConqueTerm python``, ``:ConqueTerm bash``.

* **以sudo保存当前文件** 使用 ``:w!!``.

* **Navigate html/xml tags** the same way that you navigate (), {} and []: using ``%``.

* **Beautiful status line allways visible**, with colors, breadcrumbs and useful information about file type, encoding and position. When working with python files, it also displays the current python function or class where the cursor is.

* **Automatically removes trailing spaces** when saving python files.

* **Smart autoclosing of (, [, and {**

* **Beautiful color schemes for on vim with 256 colors (fisa colorscheme) and gvim (wombat colorscheme)**.

* **使用 256 色** 可能的话。

* **2 spaces indentation for html and javascript** (can disable it removing two lines from the ``.vimrc``).

* **Thousands of code snippets for many languages** with SnipMate. Example, in python you can write ``cl`` and press ``tab`` (while in inser mode), and it will insert the boilerplate code of a common python class (then use ``tab`` to navigate the snippet fields).

* **Zen coding** for html: generate lots of html code writing simple and short expressions.
	Example:

	1. write ``#books>ul>li.book*5>a``
	2. press ``Ctrl-y ,``
	3. it will generate:

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

	Learn more on the plugin `site <https://github.com/mattn/zencoding-vim/>`_.

* **Git and other vcs integration**, with commands such as: ``:GitStatus``, ``:GitDiff``, ``:GitBlame``, ``:GitLog``, ``:GitCommit``, or simply ``:Git`` with your own command. Key mappings and syntax highlighting for git displays. Displays icons on the side of each line based on the result of a diff of the current file (example: if you added a line and still didn't commit the file, that line will have a green ``+`` on its side). And finally, when on a changed file you can **jump through changes** using ``\sn`` and ``\sp``.

* **更好的python缩进**.

* Really neat **surround actions** using the surround.vim plugin. Learn how to use it `here <https://github.com/tpope/vim-surround>`_.

* **Indentation defined text objects** for the editing language, named ``i``. For example, you can change an entire indented code block with ``cii``, or the indented block and its header line with ``cai`` (also yank, delete, ...).

* **Indentation based movements**, move to the header of your current python block with ``[-``, to the end of the block with ``]-``, and more (short reference `here <https://github.com/jeetsukumaran/vim-indentwise>`_).

* **Python class and method/function text objects** for the editing language, named ``C`` and ``M``. For example, you can change an entire function content with ``ciM``, or delete a class including its header with ``daC``.

* **运行当前python文件** 使用 ``\r`` 显示输出。

* **插入、移除ipdb 断点** 使用 ``\b``。

* **Copy history navigation** using the YankRing plugin, which allows you to cicle the vim clipboard with ``Ctrl-p`` and ``Ctrl-n``, and many other features (described `here <http://www.vim.org/scripts/script.php?script_id=1234>`_).

* **自动给导入的模块排序** 使用 ``:Isort``.

* **Persistent undos** modify file, exit vim, reopen file, and you can undo changes done on the previous session.

* **更好地路径** 临时交换文件, 备份, 未完成文件 (它们都被存放在 ``~/.vim/dirs`` 下).

* **Drag visual blocks** (blocks selected on ``Ctrl-v`` and ``Shift-v`` visual modes) with ``Shift-Alt-arrows``, or even **duplicate** them with ``D``.

* **Simple window chooser**: press ``-`` and you will see big green letters for each window. Just press the letter of the window you want to activate.

* **Paint css color** values with the actual color.

* **Format Python code** using yapf (``:YapfFullFormat`` formats the whole file, and has other commands as well, explained `here <https://github.com/pignacio/vim-yapf-format>`_. **Works only if you have a vim compiled with python 2, not python 3**).

* **Custom configs by folder** add a ``.vim.custom`` file in the project's root folder with whatever configs you want to customize for that project.
	For example, if you have a project tree like this example and you want to exclude ``folder_x`` from FuzzyFinder, put ``let g:ctrlp_custom_ignore["dir"] = g:ctrlp_custom_ignore["dir"] . '|\v[\/]folder_x$'`` in the ``.vim.custom`` file.

	::

		project
		├── folder_1
		├── folder_2
		├── folder_x
		└── .vim.custom
