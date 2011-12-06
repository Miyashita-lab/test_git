=========================================
命令のまとめ
=========================================

作成時

最初にgithubでcreate new repositoryでレポジトリ登録
directoryを作成（test_gitなど）
構築
はじめに
::

$ git config --global user.name "name"
$ git config --global user.email "e-mail"

　directory(test_gitなど)中で
::

$ git init

何かファイルを作成。例えばREADME

足す・変更の場合
::

$ git add *

消す場合（これでファイルも消える）
::

$ git rm xxxx.fpp

$ git commit -m "20111129-miya-2300"

一番最初だけ(最初以外は飛ばす)
::

$ git remote add origin git@github.com:yukimya/test_git.git

$ git push origin master

githubからファイルを落とす。
::

$ git clone git@github.com:yukimya/test_git.git

push

編集後
::

$ git add *

$ git commit -m "20111129-miya-23:30"

$ git push

pull

cloneで作ったdirectoryで
::

$ git pull -u origin master2

など