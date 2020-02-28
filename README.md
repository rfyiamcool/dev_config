# dev_config

fast init config for mac and linux.

## Dep

```
python 2.7 (python-devel)
python 3.7
```

## Usage

"""step by step"""

install vim 8.2

```
cd ~
wget https://github.com/vim/vim/archive/v8.2.0326.tar.gz
tar zxvf v8.2.0326.tar.gz
cd v8.2.0326
# 注意python config位置
./configure --with-features=huge \
    --enable-cscope \
    --enable-fontset \
    --enable-perlinterp --enable-rubyinterp \
    --enable-pythoninterp=yes \
    --with-python-config-dir=/usr/lib/python2.7/config \
    --enable-python3interp=yes \
    --prefix=/usr/local

make -j 4 && make install

alias vim='/usr/local/bin/vim '
alias vi='/usr/local/bin/vim '
```

validate vim version

```
/usr/local/bin/vim --version| head -n 1
```

update vim plug

```
cd ~
mdir vimbak
mv .vimrc  vimbak/
mv .vim    vimbak/

\cp vim_config/.vimrc ~/.vimrc

curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim

vim +PlugInstall

cd ~/.vim/plugged/YouCompleteMe
python3 install.py --go-completer
```
