# git 常用命令

## 克隆

```bash
git clone https://git.oschina.net/chenjianlong/hello-world.git

# 自定义目录名
git clone https://git.oschina.net/chenjianlong/hello-world.git my-hello-world
```

## 分支

```bash
# 查看本地分支
git branch

# 查看所有分支（本地加远程）
git branch -a

# 创建分支
git branch <branch-name> # 例： git branch develop

# 切换（检出）分支
git checkout <branch-name> # 例： git checkout develop

# 创建并切换到新建分支
git checkout -b <branch-name> # 例：git checkout -b develop 
```

## 提交

```bash
# 跟踪新文件或者已有文件的改动
git add <file-name> # 添加一个文件 例：git add ./index.html

# 监控工作区的状态树，把工作时的所有变化提交到暂存区，包括文件内容修改(modified)以及新文件(new)，但不包括被删除的文件
git add .

# 监控已经被add的文件（即tracked file），他会将被修改的文件提交到暂存区。add -u 不会提交新文件（untracked file）。（git add --update的缩写）
git add -u

# 监控所有文件，新的未跟踪的，已删除的，已修改的（git add --all的缩写）
git add -A

# 提交代码
git commit -m <comment> # 例：git commit -m "修复了issue-1：错别字"
```

## 拉取

```bash
# 从远端拉取
git pull
```

## 推送

```bash
# 推送到远端
git push
```

## 合并

```bash
# 切换到master主干并将develop分支的代码合并过来
git checkout master
git merge <branch-name> # 例：git merge develop
```