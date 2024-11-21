目录介绍        
.venv：python的虚拟环境目录（打开任意python文件，底部状态栏显示当前使用的解释器，虚拟环境需要激活）
        • 命令-生成虚拟环境：python -m venv .venv
        • 查看是否激活虚拟环境：pip list，新的环境只有一个pip。
        • 激活虚拟环境：服务器运行命令，略。
            1.VsCode：按 Ctrl+Shift+P 打开命令面板
            2.输入并选择 Python: Select Interpreter
            3。选择python解释器为虚拟环境的解释器
    ├─Include：包含了 Python 的头文件，这些是编译扩展模块时需要的。如果你不打算自己编写 C 扩展，通常不需要关注这个目录
    ├─Lib：包含了 Python 标准库以及你用 pip 安装的所有第三方包
    │  └─site-packages：存放着所有通过 pip 安装的 Python 包
    └─Scripts：（在linux上是Bin）：包含了虚拟环境的可执行文件
requirements.txt：列出了虚拟环境中安装的所有软件包。然后，此文件可用于在其他地方重新创建相同的环境。
                    命令-生成软件包列表：pip freeze > requirements.txt
                    命令-安装依赖：pip install -r requirements.txt
benchmarks：基准测试相关文件的文件夹
deepface：项目源码
demo：个人测试用例
icon：README或其他文件使用的图片
scripts：启动/部署脚本
test：测试用例
.pylintrc：自定义Pylint的行为。Pylint 工具的配置文件。Pylint 是一个 Python 静态代码分析工具
CITATION.md：引用文献
README.md：项目介绍
entrypoint：启动脚本，gunicorn部署，端口5000


【使用方式】
1.通过gunicorn服务器来启动，可以进行web接口调用（先通过2/3的方式安装deepface库，再启动）。
windows：python .\deepface\api\src\api.py
linux：./scripts/service.sh

2.安装依赖库直接调用
$ pip install deepface

3.源码安装
$ git clone https://github.com/serengil/deepface.git
$ cd deepface
$ pip install -e .
# 安装库后导入使用
from deepface import DeepFace
