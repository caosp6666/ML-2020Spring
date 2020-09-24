# ML-2020Spring

## 环境准备

### WSL or mac OS or Linux

- 安装unzip
- 安装zsh

### python 虚拟环境——[pyenv](https://github.com/pyenv/pyenv)

- 安装

  ```shell
  git clone https://github.com/pyenv/pyenv.git ~/.pyenv
  echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bash_profile
  echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bash_profile
  echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n
  eval "$(pyenv init -)"\nfi ' >> ~/.bash_profile
  exec "$SHELL"
  # 其中.bash_profile 因环境而异：bash 为.bashrc，zsh 为.zshrc
  ```

- 安装python make依赖

  `sudo apt-get update; sudo apt-get install --no-install-recommends make build-essential libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev xz-utils tk-dev libxml2-dev libxmlsec1-dev libffi-dev liblzma-dev`

- 安装python 3.6.8

  `pyenv install 3.6.8`

- 查看现有的环境

  `pyenv versions`

- 设定当前想要的环境

  `pyenv global 3.6.8`

### 安装python包

- `pip install numpy` 此时就安装在了pyenv global指定的版本上
- `pip install pandas`
- `pip install jupyter`
- 在WSL中启动，即可在外部使用浏览器访问WSL中的jupyter notebook

### kaggle注册与[kaggle-API](https://github.com/Kaggle/kaggle-api)使用

- caosp6666@163.com / csp819426311 / username: albertcsp
- `pip install kaggle`
- 在my account页面create kaggle API token，生成的json文件放到~/.kaggle/kaggle.json
- 修改权限`chmod 600 ~/.kaggle/kaggle.json`
- cd到目标文件夹 `kaggle competitions download -c ml2020spring-hw1`即可下载一个zip文件
- `unzip ml2020spring-hw1.zip` 即可在当前文件夹下获取对应的数据，放到./hw1/data中

### 建立git仓库

- 记得将所有data文件加入到data文件夹中，并将data文件夹加入到gitignore