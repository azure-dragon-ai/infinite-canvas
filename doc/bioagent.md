```shell
bioagent
claude
更新claude.md
统一异常处理
bioagent-os为原项目, biomedical-agent-os为重构项目，使用docker compose启动重构项目报错
重构项目biomedical-agent-os，前端根据原型biomedical-agent-os/docs/research/web_next_prototype.html重构，其余参考已有项目重构，重构目录为biomedical-agent-
  os1，统一异常处理，日志记录，编写api接口文档，提供后端管理页面，维护数据表的增删改查，使用vue+vite+element
使用docker-compose部署启

项目可以重命名，新建项目会话应该进入项目会话页面而不是普通会话页面，项目会话页面可以查看项目下的所有会话，每个会话可以进行管理，包括删除，暂停，继续等操作，项目会话页面多了长期记忆功能
在左侧导航菜单中增加项目会话菜单，项目会话不要和普通会话在一个页面
项目会话，删除div class="pc-sidebar"，长期记忆移到div class="subpanel"，并且应该有新长期记忆按钮，页面布局应该类似普通会话页面，右侧是产物，所有会话页面都应该可以和大模型对话
无法和大模型对话
http://localhost:5190/api/v1/chat
Request Method
POST
Status Code
307 Temporary Redirect
http://localhost/api/v1/chat/
Referrer Policy
strict-origin-when-cross-origin
查看bioagent-os的代码，补全docker-compose.yml文件配置，要求大模型可用
查看bioagent-os的.env文件，补全环境变量配置，补全agent分析等功能
普通会话，项目会话，新会话输入框也应该包含模型选择等内容
数据不支持上传，同时也看不到BIOAGENT_LIBRARY_HOST_PATH中数据
bioagent-os为原项目, biomedical-agent-os为重构项目，数据不支持上传，同时也看不到BIOAGENT_LIBRARY_HOST_PATH中数据
普通会话和项目会话应该是独立的
数据需要支持上传到minio中，BIOAGENT_REFERENCE_HOST_PATH数据也看不到，普通会话和项目无关，项目会话和项目相关，会话需要支持生物分析，包括基因分析，蛋白质分析，RNA分析等，给出示例
使用docker compose部署
apt使用阿里云镜像
docker compose build, celery-worker慢，apt使用http://deb.debian.org而不是阿里云
docker compose build太慢了，变更部署方式，将容器和代码分离，如在主机执行npm run build，在docker-compose.yml中配置代码挂载
上传与导入为什么只显示本地样本库，数据中div class="subpanel"应该提供新建数据集按钮，上传文件按钮，将div class="dt-list"的内容迁移到subpanel，删除div class="dt-list"，同时已有数据集应该显示在subpanel中，包括本地样本库，参考库，项目数据集
数据删除<span class="act">上传</span>
点击数据集进入数据集的详情页面，右侧tab中应该增加数据集浏览tab，浏览所选的数据集，上传与导入应该提供上传与导入功能而不是浏览本地样本库，点击左右本地样本库和参考库应该进入浏览本地样本库页面和参考库页面，本地样本库和参考库是公共数据集
点击本地样本库后，无法点击项目数据集，点击没有反应
画布编排很多功能不可用，查看bioagent-os的代码，补全功能
画布编排选中节点应该高亮
报告阅读很多功能不可用，查看bioagent-os的代码，补全功能
```

```shell
生成下载命令，如wget url -o 1.mp4
生成下载命令，如wget -O 1.mp4 url

改造完成并全部验证通过。

新部署模型：容器与代码分离

┌──────────────────┬─────────────────────────────────────────┬───────────────────────────────────────────────────┐
│       服务       │                  之前                   │                       现在                        │
├──────────────────┼─────────────────────────────────────────┼───────────────────────────────────────────────────┤
│ frontend / admin │ 镜像内 npm ci + build（每次构建几分钟） │ 纯 nginx:alpine，主机 dist/ 只读挂载              │
├──────────────────┼─────────────────────────────────────────┼───────────────────────────────────────────────────┤
│ backend / celery │ 代码 COPY 进镜像（改一行代码也要重建）  │ 镜像只装依赖，./backend:/app 挂载，改代码重启即可 │
└──────────────────┴─────────────────────────────────────────┴───────────────────────────────────────────────────┘

验证结果：前端/后台容器已是 nginx:alpine 且 healthy；后端 /app 确认为 virtiofs 挂载；门户 5190 / 后台 5191 / 后端 8010 / 经门户的 API 代理全部 200。加了两处细节：PYTHONDONTWRITEBYTECODE=1（防止容器内 root 写 __pycache__ 污染主机目录属主）；docker-compose.yml 通过 config --quiet 校验。

日常使用

# 一键部署/更新（等价于：构建前端产物 + docker compose up -d）
bash scripts/deploy.sh

# 只改了后端代码
docker compose restart backend celery-worker

# 只改了前端代码
cd frontend && npm run build        # 管理后台同理 cd admin

# 只有 requirements.txt / Dockerfile 变了才需要重建镜像（阿里云镜像源，首次之后全部走缓存）
docker compose --profile full build backend celery-worker && docker compose --profile full up -d

docker compose build 现在只涉及 backend/celery（且共享同一组层），前端和 admin 彻底退出镜像构建——日常迭代从十几分钟降到秒级。

scripts/deploy.sh 里前端构建用的是 npm ci（仅当 node_modules 缺失时）+ npm run build，并会带上 --profile full 保证 minio/chroma 不被落下。原 frontend/Dockerfile、admin/Dockerfile 保留未删，如需回到纯镜像部署随时可用。
```