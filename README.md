# 刪除Ubuntu
wsl --unregister Ubuntu-22.04

# 在Ubuntu 安裝pyenv
sudo apt-get update
sudo apt install curl git bzip2 -y
curl https://pyenv.run | bash

echo 'export LC_ALL=C.UTF-8' >> ~/.bashrc
echo 'export LANG=C.UTF-8' >> ~/.bashrc
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
echo 'export PATH="$PYENV_ROOT/shims:$PATH"' >> ~/.bashrc
echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n eval "$(pyenv init -)"\nfi' >> ~/.bashrc
exec $SHELL

# 查看可安裝的Python Version
pyenv install -l

# 在pyenv安裝Python
pyenv install 3.8.10

# 設定Global 的 Python
pyenv global 3.8.10
# 設立當前目錄的 Python
pyenv local 3.8.10

# 安裝pipenv
pip install pipenv==2022.4.8

# 安裝Python，與設定當前目錄為什麼python環境
pipenv --python ~/.pyenv/versions/3.8.10/bin/python

# 讓當前目錄變成package
pipenv install flask==2.3.3