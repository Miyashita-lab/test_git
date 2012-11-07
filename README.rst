=========================================
命令のまとめ
=========================================

作成時

最初にgithubでcreate new repositoryでレポジトリ登録
directoryを作成（test_gitなど）
構築

GitHub for macはgit commandのインストールに使う。あとはコマンドラインの方が小回りが利いて良い。


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
$ git mv xxx.fpp yyy.fpp
$ git mv yyy.fpp dir/.
$ git commit -m "20111129-miya-2300"

一番最初だけ(最初以外は飛ばす)
::

$ (old)
$ git remote add origin git@github.com:yukimya/test_git.git
$ (currenty)
$ git remote add origin https://github.com/yukimya/rein.git
$ git push -u origin master

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

ほかに
logなどは
::

$ git log
$ git status

１つ戻すとき
::

$ git reset


ブランチ
-------------------

Master, devel, project, versionを作成する。
develはMasterからの分岐にする。projectはdevelからの分岐。versionはMasterからの分岐とする。
::

ブランチを調べる。(必ず場所をチェックする。)
::

$ git branch -a

ブランチの作成（新規）
::

$ git branch -a
$ git checkout -b new_branch
$ git push origin new_branch

他のブランチからのpush
::

$ git push origin new_branch

ブランチの作成（取込み）
::

$ git branch -a
$ git checkout next_branch xxx/origin/next_branch

gitのアーカイブ化
::

$ git archive --format=tar HEAD --prefix=program/ | gzip > ../program_v.1.0.1.tar.gz

gitにタグを付ける
::

$ git tag new_tag
$ git push --tags

or

$ git push release_xxxx

タグを消す
::

$git tag origin :release_xxxx

masterにnext_branchをマージするとき（ブランチのマージ）。
::

$ git merge --no-ff next_branch  (master上で)

ブランチの作り直し（上だけで良いかも）
::

$ git rebase master (next_branch上で)

コミットの内容を取り消す。
::

$ git log --oneline
$ git revert --no-edit XXXX
$ git log --oneline

gitのブランチチェック
::

$ git log --oneline --graph