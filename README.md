
## 📖 快速开始

### 环境要求
- Python 3.8+

### 安装与环境配置

推荐使用虚拟环境以保持系统纯净。

**方案一：使用 `uv` (推荐)**
```shell
# 安装 uv
pip install uv

# 安装依赖
uv sync             # 仅核心功能
uv sync --group dev # 含 Web 管理后台
```

可通过 `uv run 脚本.py` 执行项目，无需手动激活环境；
如需手动进入虚拟环境，先运行：

```shell
.\.venv\Scripts\activate  # Windows
source .venv/bin/activate # Linux/macOS
```

**方案二：使用原生 `venv`**
```shell
python -m venv venv

# 激活环境
.\venv\Scripts\activate  # Windows
source venv/bin/activate # Linux/macOS
# 安装依赖
pip install -r requirements.txt      # 仅核心功能
pip install -r requirements-dev.txt  # Web 管理后台
```

### 运行方式

#### 1. Web 可视化模式
```shell
# 启动 Flask 后台 (默认监听 9090 端口)
python run_flask_app.py start -p 9090
```
访问 `http://127.0.0.1:9090/admin/` 即可进入管理后台。

#### 2. 命令行模式
默认使用 `api.json` 中的接口进行测试。
```shell
# 启动 64 线程，对目标手机号进行 1 轮测试
python smsboom.py run -t 64 -p 188xxxxxxxx
# 启动 64 线程，循环测试 60 次，间隔 30 秒
python smsboom.py run -t 64 -p 188xxxxxxxx -f 60 -i 30
# 使用指定的接口 json 文件
python smsboom.py run -p 188xxxxxxxx -a custom_api.json
```

## ⚖️ 免责声明

1. 本程序仅供开发者进行系统性能压力测试、接口安全性验证及学习研究使用。
2. 严禁用于任何形式的非法骚扰、恶意攻击或盈利活动。
3. 使用者因滥用本项目产生的一切法律后果由其自行承担，作者不承担任何连带责任。
4. 请在遵守当地法律法规的前提下使用。
