# SkyChat
### [简体中文](README.CN.md)
### [English](README.md)
## 简介
### SkyChat是一款基于中文GPT-3 API做的聊天机器人项目。更多细节可见[奇点智源官网文档](https://openapi.singularity-ai.com)

# Demo使用教程：
## 模型服务以及Python环境搭建
## Windows
1. 下载[Anaconda](https://www.anaconda.com/) 勾选添加到环境变量选项  
   <img src="./p/2c75f4cd-d1c1-4e9d-96b2-96c4c246c18b.jpeg" width = "500" height = "330" alt="图片名称" align=center />
2. 下载并解压[semantic_score_clean](http://open-dialogue.singularity-ai.com/open_dialogue/share_model/semantic_score_clean.zip)和[user_profile_clean](http://open-dialogue.singularity-ai.com/open_dialogue/share_model/user_profile_clean.zip)服务、模型以及示例训练数据
3. 打开Anaconda 输入  
   `conda create -n semantic` 创建新环境  
   `conda info --envs` 查看环境   
   `activate semantic` 启动环境   
   `cd C:\你的路径\semantic_score_clean\semantic_score_clean` cd到解压好的semantic_score_clean文件夹  
   `python -m pip uninstall numpy` 删掉初始自带的numpy  
   `python -m pip install -r requirements.txt` 或者 `pip install -r requirements.txt` 安装所需依赖包   
   `python semantic_score_api.py` 运行服务
4. [下载对应系统的Cuda并安装](https://developer.nvidia.com/cuda-downloads)
5. 打开一个新的Anaconda界面 输入  
   `conda create -n userprofile`创建新环境  
   `conda info --envs`查看环境   
   `activate userprofile`启动环境   
   `cd C:\你的路径\user_profile_clean\user_profile_clean`cd  到解压好的user_profile_clean文件夹  
   `python -m pip uninstall numpy`  删掉初始自带的numpy   
   `python -m pip install -r requirements.txt` 或者 `pip install -r requirements.txt`安装所需依赖包   
   `python -m pip install torch==1.11.0+cu115 -f https://download.pytorch.org/whl/torch_stable.html` 下载cuda版torch      
   `python server_v3.py`运行服务

***
## Unity版Demo
1.  Release中下载最新的包。
2.  [在openAPI网站](https://openapi.singularity-ai.com/index.html#/login) 或demo中点击注册 注册并认证 获得 api-key 和 api-secret
3.  点击设置 进入设置界面， 对应位置填入key和secret，以及双方姓名，完后点击保存并退出
4.  确认semantic_score_clean和user_profile_clean服务以部署到本地，如果远程部署请在设置中替换对应请求URL
5.  开聊
***
## Python版Demo
1. [在openAPI网站](https://openapi.singularity-ai.com/index.html#/login) 或demo中点击注册 注册并认证 获得 api-key 和 api-secret
2. 打开 `\你的路径\OpenAPIDemo\PythonDemo\main.py` 在对应位置填入api-key 和 api-secret 并修改需要修改的参数
   <img src="./p/ZmTZD3SgRo.jpg" width = "800" height = "330" alt="图片名称" align=center />
3. 打开Anaconda 输入  
   `conda create -n talk` 创建新环境  
   `conda info --envs` 查看环境   
   `activate talk` 启动环境   
   `cd C:\你的路径\OpenAPIDemo\PythonDemo` 导航到代码所在的文件夹  
   `python -m pip install requests` 下载依赖资源  
   `python main.py` 开始聊天（需确认2个服务以开启）
***
##### *最低配置要求Nvidia Gfx 1060