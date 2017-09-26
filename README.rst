fisa-vim-config-Zh
===============

fisa-vim-config的中文翻译版本
这是一个给pythoner的vim配置

安装::

	sudo apt-get install curl vim exuberant-ctags git ack-grep
	sudo pip install pep8 flake8 pyflakes isort yapf
	wget -O vimrcc https://raw.githubusercontent.com/strange-jiong/fisa-vim-config/master/.vimrc
	mv ~/.vimrc ~/.vimrcbak
	mv vimrcc ~/.vimrc

如果打开vim没有自动安装插件的话,输入一下命令::

	:PlugClean
	:PlugInstall
	:PlugUpdate


