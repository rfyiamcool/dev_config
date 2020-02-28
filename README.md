# dev_config

fast init config for mac and linux.

<img src="static/vim.png" alt="vim-golang" width="230" />
<img src="static/golang.png" alt="golang" width="250" />

## Dep

```
python 2.7 (python-devel)
python 3.7
```

## Usage

**step by step**

install vim 8.2

```
cd ~
wget https://github.com/vim/vim/archive/v8.2.0326.tar.gz
tar zxvf v8.2.0326.tar.gz
cd v8.2.0326

# validate python-config path
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
```

reinstall ycm

```
cd ~/.vim/plugged/YouCompleteMe
python3 install.py --go-completer
```

## more doc

vim-go

```
https://github.com/fatih/vim-go
```
