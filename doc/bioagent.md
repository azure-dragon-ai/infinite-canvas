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
项目首页，新建按钮不可用，删除游离会话，成员按钮不可用，起手下内容不可点
项目首页，删除div class="sp-sec"
项目首页，删除div class="sp-item sp-sess"
页面刷新后，之前选择的项目应该保持选中状态
页面刷新后，仍然提示尚未选择项目
普通会话和项目无关，普通会话页面删除项目相关内容
普通会话和项目会话，应包含会话的基本内容，聊天者头像，大模型响应前应提示思考中，同时会话使用了agent，应提示云电脑，会话支持任务，任务可以是基因分析，蛋白质分析，RNA分析等，任务完成后，应提示任务完成，同时提供任务结果，输入"/"应提示skills等技能，查看bioagent-os的代码，补全功能
由于是在浏览器中使用agent，所以需要告诉大模型agent可以从接口，本地浏览器获取需要的数据，比如当前项目可以从localStorage获取
普通会话和项目会话，聊天输入框上传文件不可用，同时应该提醒用户输入"/"可以使用使用skill，输入@可以添加资料，请补全功能
普通会话和项目会话，和所有大模型对话应用一样，请参考hermes等项目，应该可以删除会话，回滚会话，暂停会话，继续会话等操作
所有接口报错，http://localhost:5190/api/v1/projects
Request Method
GET
Status Code
502 Bad Gateway
普通会话可以使用公共数据集，项目会话可以使用项目数据集和公共数据集，输入@后应该弹出数据集和文件选择窗口，用户可以选择数据集或文件，点击确认后，应该将选中的数据集或文件添加到会话中
左侧导航增加技能菜单，点击技能菜单，应该显示所有技能，点击技能，应该显示技能的详细信息，skills已经通过data/skills挂载，为方便管理将技能写入到数据库，可以在页面上添加技能，管理技能，普通会话和项目会话输入"/"应该弹出技能列表，用户可以选择技能，点击确认后，应该将选中的技能添加到会话中
普通会话和项目会话，可以选择其中一个对话进行删除，重新定义鼠标右键菜单
普通会话和项目会话，我说的是聊天对话div class="chat"里面的对话内容，右键单击对话内容，应该显示删除等选项
为什么后端还没有起出来
普通会话和项目会话，聊天对话div class="chat"里面的对话内容，在鼠标悬停在聊天内容时，在下方应该显示复制，编辑，删除等选项，不再使用右键菜单，删除时先出现聊天内容选择，在左侧显示复选框，默认勾选当前聊天和对应的大模型回复
1.普通会话和项目会话，每次对话收到的是“未收到回复”
2.允许用户在多台设备登录
1.普通会话，会话列表经常多出几个会话
2.普通会话和项目会话，根据用户聊天信息自己给本次会话命名
普通会话和项目会话，当前输入的聊天，鼠标悬停时没有编辑和删除等选项
普通会话和项目会话，可以重命名会话，另外对于已经选中的会话，刷新页面后，应该保持选中状态
普通会话和项目会话，会话列表，在鼠标悬停在会话后，在每个会话右侧增加三个点，点击三个点，应该显示置顶，删除，重命名等选项，不再使用右键菜单
项目首页，项目列表，在鼠标悬停在项目后，在每个项目右侧增加三个点，点击三个点，应该显示置顶，删除，重命名等选项
项目首页，div class="sp-bd"中的项目列表没有任何变化，你改了哪里？div class="sp-bd"中的项目列表在鼠标悬停在项目后，在每个项目右侧增加三个点，点击三个点，应该显示置顶，删除，重命名等选项
长期记忆，就是保存一份md文档，类似agent.md，记录下所有的功能和操作，方便后续使用，新建长期记忆应该直接进入md编辑页面，根据md内容自动命名长期记忆，长期记忆列表，在鼠标悬停在长期记忆后，在每个长期记忆右侧增加三个点，点击三个点，应该显示置顶，删除，重命名等选项
顶部div class="ctx-switch"中，删除游离和未归项目，补全新建项目功能
普通会话和项目会话，输入框下方ask,agent,plan都表示什么，在鼠标悬停时给出说明
新增了长期记忆，在项目首页中没有显示长期记忆列表
普通会话和项目会话，初次和大模型对话时，需要带上长期记忆内容，提供查询当前会话使用的长期记忆内容，冗余存储，更新长期记忆时，历史会话还是之前使用长期记忆
数据管理，项目数据集没有关联到项目，project_id为空，修复bug
1. 普通会话输入"@"后，弹出的不是公共数据集列表，而是项目数据集列表
2. 项目会话输入"@"后，弹出的只有项目数据集列表，没有公共数据集列表，提供tab页选择公共数据集或项目数据集
公共数据集应该是本地样本库和参考库
数据管理，将公共数据集中参考库改名为本地参考库
后台管理没有长期记忆功能
数据管理，项目数据集列表，在鼠标悬停在数据集后，在每个数据集右侧增加三个点，点击三个点，应该显示置顶，删除，重命名等选项
接口请求全部失败改了什么
左侧导航将项目会话移到普通会话前面，更新icon
新会话hi，提示本会话尚未使用长期记忆（首次对话时自动携带当时的记忆内容），初次和大模型对话时，需要带上长期记忆内容，提供查询当前会话使用的长期记忆内容，冗余存储，更新长期记忆时，历史会话还是之前使用长期记忆
会话页面，仍然提示本会话尚未使用长期记忆（首次对话时自动携带当时的记忆内容），我看接口https://bioagent-new.7otech.com/api/v1/chat-persist/sessions/sess-1788646067826-id9ui7接口包含memory_snapshot字段
后台会话显示id数据错误，存在id为task-ev-verify的数据，id应保证唯一，不能重复，可以使用时间戳+随机数
会话中长期记忆只存了memory_snapshot，应该同时保存长期记忆id以方便溯源
技能，删除div class="subpanel"中添加按钮
画布编排，项目pipelines列表，在鼠标悬停在pipeline后，在每个pipeline右侧增加三个点，点击三个点，应该显示置顶，删除，重命名等选项
画布编排，节点以拖拉拽的方式添加到画布中
提供接口文档
1.项目会话，新建会话，聊天页面没有内容，同时后台显示会话id为undefined
2.普通会话，新建会话一样没有响应，同时后台显示没有新增会话
项目会话，新建会话，聊天页面仍然没有内容，同时后台显示会话id为undefined，请修复系统bug

1.项目会话，新建会话，聊天页面没有内容，同时后台显示会话id为undefined
2.普通会话，新建会话一样没有响应，同时后台显示没有新增会话
https://bioagent-new.7otech.com/api/v1/chat/stream 返回event: start data: undefined
curl --url 'https://bioagent-new.7otech.com/api/v1/chat/stream' \
  -H 'accept: */*' \
  -H 'accept-language: en-US,en;q=0.9,zh-CN;q=0.8,zh;q=0.7' \
  -H 'authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE3ODg3OTg1MjEsInN1YiI6ImE4ZjY5NjdmLTIwNmMtNGI4Ni05MzU2LTg5MmZiMWQ5YmRlMCJ9.X9KLiKuG6IvjxkZ7O_R1JMTfG1zj5LPJyG-8fvnWhHM' \
  -H 'cache-control: no-cache' \
  -H 'content-type: application/json' \
  -H 'origin: https://bioagent-new.7otech.com' \
  -H 'pragma: no-cache' \
  -H 'priority: u=1, i' \
  -H 'referer: https://bioagent-new.7otech.com/projects/0f1811eb-90d4-450f-9e92-917f40334732/chat' \
  -H 'sec-ch-ua: "Chromium";v="152", "Not?A_Brand";v="24", "Google Chrome";v="152"' \
  -H 'sec-ch-ua-mobile: ?0' \
  -H 'sec-ch-ua-platform: "Windows"' \
  -H 'sec-fetch-dest: empty' \
  -H 'sec-fetch-mode: cors' \
  -H 'sec-fetch-site: same-origin' \
  -H 'user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/152.0.0.0 Safari/537.36' \
  --data-raw $'{"message":"hi","session_id":"undefined","project_id":"0f1811eb-90d4-450f-9e92-917f40334732","mode":"ask","context_attachments":[{"type":"environment","id":"browser-agent-runtime","label":"Agent 运行环境（浏览器）","sublabel":"数据获取指引","metadata":{"说明":"你运行在浏览器 Agent 环境中。需要数据时按以下指引获取，不要臆造不存在的项目/数据集/实验 id。","后端接口":"统一前缀 /api/v1，鉴权由前端自动携带 Bearer token。常用：GET /projects 项目列表；GET /datasets 数据集；GET /skills 技能注册表（含参数 schema）；GET /pipelines 已存流水线；GET /experiments 实验；本地样本库 GET /datasets/library/browse（文件以 library:// URI 零拷贝引用）；GET /memory-notes?project_id=.. 项目的长期记忆（Markdown 笔记，记录功能与操作）","浏览器本地存储":"localStorage[\'bioagent_current_project\']=当前项目 id；localStorage[\'bioagent_token\']=登录 token","当前项目":"id=0f1811eb-90d4-450f-9e92-917f40334732，name=生物分析（localStorage[\'bioagent_current_project\']=0f1811eb-90d4-450f-9e92-917f40334732）"}}]}'

event: start
data: undefined

event: route
data: {"route_type": "conversational", "intent": "mode_ask", "confidence": 1.0}

data: Hello! It looks like you're using a bioinformatics platform in your browser. How can I assist you with your analysis today? If you need any help with accessing data, using the interface, or understanding the tools available, feel free to ask.

event: done
data: {"type": "done"}

data: [DONE]

普通会话和项目会话，新建会话，聊天页刚开始是空的，等接口返回才出现内容，应该先显示用户输入内容，然后提示大模型思考中，最后显示大模型回复

请求v1/chat/stream时，context_attachments没有长期记忆内容

由于是在浏览器中使用agent，所以需要告诉大模型agent可以从接口，本地浏览器获取需要的数据，比如当前项目可以从localStorage获取，接口文档 https://bioagent-new.7otech.com/docs，对于项目，画布，数据，技能，报告，运行记录等信息可以从接口获取
如果大模型在后端无法从接口获取数据，则在聊天时先从浏览器本地获取登录凭证authorization，从接口中将登录凭证传入大模型，再由大模型从接口获取数据
大模型从接口获取数据时报错了，Failed to list project files: object list can't be used in 'await' expression
普通会话和项目会话，增加深度思考选项，选择深度思考时，应该在聊天对话中体现出来思考过程，用户可以查看思考过程的所有内容
项目中含有数据集，但是大模型返回没有数据集，除了从接口获取数据，允许大模型提交shell或python脚本，在后端运行脚本，获取数据结果
运行记录，有一个任务一直在运行中，是否存在bug，请修复，查看bioagent-os的代码，补全功能
报告阅读，如果报告中包含结果文件，应该存入minio中，用户可以下载查看结果，查看bioagent-os的代码，补全功能
普通会话和项目会话，可以查看token消耗量
对于生物分析任务的运行环境，提供执行器管理，其中默认执行器不可删除，可以添加执行器，包括ip，端口，用户名，密码等信息，执行器类型（shell或python），可以使用ssh登录，登录后检查运行环境是否满足要求，对于不满足的情况可以自动安装依赖，可以使用celery等任务框架完成任务，数据从minio中获取，输出的结果需要放回minio以方便读取
默认执行器不是celery-worker吗？docker-compose.yml定义了celery-worker，默认执行器为什么是127.0.0.1，而且是shell类型，生物分析基本以python为主，该项目是生物分析智能体，告诉大模型该项目核心功能是生物分析智能体，127.0.0.1可以做为云端agent执行器
项目会话，输入"@"后可以选择数据集了，但是项目数据集无法选择文件
普通会话和项目会话，当大模型处在思考中时，如果用户选择会话列表中其它会话，应允许用户切换，并且之前的会话应该在后台继续运行，如果收到回复，应该在会话列表中提醒用户已经收到回复
普通会话和项目会话，当大模型处在思考中时，选择了其它会话，再切回之前的会话，应该提示思考中，但是页面显示大模型回复为空，且大模型已经停止思考
普通会话和项目会话，当大模型处在思考中时，选择了其它会话，再切回之前的会话，没有显示用户之前的输入和大模型思考中，而是等大模型回复时才一同显示
普通会话在系统上和项目没有关系，但是当用户和大模型交互时，比如创建项目或指定某个项目时，当前会话就和项目关联了，可以使用项目信息以及项目中的数据集，任务，报告等信息
关联项目按钮应该使用select下拉选择框，用户可以从下拉列表中选择项目
1.普通会话和项目会话，告诉大模型数据应包含上传数据和数据集
2.允许大模型在前端自行编写js代码，在后端编写shell或python脚本，但是需要提示让用户选择是否执行操作，可以允许本次，始终允许，不允许
普通会话和项目会话，大模型的回复内容，鼠标悬停时增加重新生成按钮
普通会话和项目会话，告诉大模型数据文件应包含上传数据文件和数据集中数据文件
1.普通会话和项目会话，询问数据时仍然告知没有数据，告诉大模型数据文件应包含聊天页面上传数据文件和数据集中数据文件，数据集包含项目数据集和公共数据集，可以从接口获取数据
2.对于大模型的答复，不需要完全使用文本输出，可以考虑使用markdown，html等方式输出，相关文件可以存入minio中，在聊天页右侧提供预览，如果包含数据文件，应该在聊天对话中体现出来，用户可以点击下载按钮下载数据文件，在右侧提供预览
1.普通会话和项目会话，聊天中上传的数据，应该保存到项目的默认数据集，在新建项目时应创建默认数据集
2.普通会话和项目会话，询问数据时大模型回复应该以表格形式展示，包含项目数据集，公共数据集，同时给出访问数据管理页面的链接
普通会话和项目会话，应该给出思考过程，同时保存思考过程到数据表，比如询问数据时，应显示正在从接口获取项目数据集并将完整的json返回结果存入思考过程，正在查看用户上传的数据文件，正在通过shell脚本查看服务器目录等操作
普通会话和项目会话，大模型回复包含[Referenced Entities]内容，不需要显示
普通会话和项目会话，思考过程应该和大模型的回复绑定在一起，后台提供查询
普通会话和项目会话，思考过程应该可以在大模型回复上方点击查看详情按钮，展开思考过程，用户可以查看思考过程的所有内容
普通会话和项目会话，应该有一个消息思考过程表，关联消息表，存储每个消息的思考过程，用户可以查看每个消息的思考过程，在后台看不到思考过程，应提供菜单可以查看思考过程
1.数据管理，项目数据集没有关联到项目，顶部切换项目，项目数据集没有变化
2.顶部切换项目时，左侧仍然停留在所选菜单
顶部切换项目时，不要回到/home，保持当前访问路径
后台没有找到在哪里可以查看思考过程，在大模型的回复上方也没有查看思考过程按钮
更新claude.md
1.数据管理隐藏公共数据集，在项目数据数据中，上传与导入中增加导入公共数据集按钮，用户可以点击公共数据集按钮，导入公共数据集
2.公共数据集的浏览，保留目录结构
3.项目会话，询问数据时，只需要读取项目数据集即可，但是需要项目数据集名称和数据集中文件信息
大模型优先使用tools获取数据，在思考过程中体现出来，list_project_files返回的files是空的，"project_id": "0f1811eb-90d4-450f-9e92-917f40334732"，项目下有数据集修复bug
大模型思考后，页面没有显示大模型的回复，刷新页面才能显示
大模型思考后，消息显示了但是思考过程按钮又没有了
数据管理，增加删除数据集中文件的功能，删除div class="subpanel"中的上传文件按钮
普通会话和项目会话，大模型应该使用交互式按钮等和用户进行交互，完整生物分析，聊天会话中，提供一个交互式界面，用户可以在界面上点击按钮，会话开始点击快速开始按钮，提供一个完整的示例，如何进行生物分析
普通会话和项目会话，大模型可以通过tool call等方式自行构建pipeline，完成生物分析任务
运行记录，列表点击没有反应
运行记录，详情什么也看不到，查看bioagent-os的代码，补全功能
运行记录，应能查看运行过程中的所有日志
bioagent-os为原项目, biomedical-agent-os为重构项目
普通会话和项目会话，刷新页面会话应该滚动到最底部
1.运行记录，点击左侧列表，应该直接进入任务详情页，而不是显示任务列表和弹窗
2.左侧新增查看所有任务按钮，点击后可以查看所有任务列表，每个任务提供查看详情按钮，保留取消和日志按钮，另外点击取消任务没有反应
3.新增任务详情页，展示任务详情，包括任务执行的脚本，使用了哪个执行器，任务使用的pipeline，任务使用的数据，任务所属会话，任务状态，任务日志，任务输出，每个pipeline节点运行情况等
1.运行记录，点击所有任务按钮没有反应，取消任务提示已取消请求，但是任务状态没有变化
2.默认显示任务tab，将实验tab放到任务tab后边
运行记录，点击左侧列表，可以查看任务详情页，但是点击另一个任务时，任务详情页没有更新
1.普通会话和项目会话，已经通过"/"和"@"选择了技能和数据，分析数据时自行关联技能和数据，数据根据前缀自行查找具体位置
2.大模型已经读取到项目关联的数据集，但是获取不到文件内容，请根据文件前缀自行获取文件内容，数据一般在BIOAGENT_LIBRARY_HOST_PATH和minio中
3.可以从公开的技能库中获取技能，用于任务分析，比如https://www.skillhub.cn/
普通会话和项目会话，确认删除按钮需要滚动到页面顶部，聊天框顶部需要固定显示
普通会话和项目会话，div class="cs"下第一个div和第二个div都应该固定在聊天框顶部，背景不透明
1.普通会话和项目会话，div class="cs-pin"背景应该是黑色，聊天区域应该在其下方，将所有div class="msg-item"放到div class="chat-content"中
2.调整div class="cs-pin"内的布局，按钮都挤到一起了
1.普通会话和项目会话，点击删除出现复选框时，应该定位到所选的聊天内容
2.div class="cs-pin"距离顶部有距离，滚动聊天记录时导致可以看到聊天记录
普通会话和项目会话，点击删除出现复选框时，确认删除按钮应该在div class="sess-tools"下方
数据管理，刷新页面会导致项目数据集列表显示错误，展示所有数据集，刷新页面是否读取到当前项目，如果读取了当前项目，数据集列表应该只展示当前项目的数据集
1.数据管理，数据集列表增加迁移按钮，迁移到另一个项目
2.选择项目后，在数据管理页面增加展示已选项目展示
3.数据管理，浏览增加检索功能
普通会话和项目会话，有bug输入框还在输入文字就提交了
很抱歉，我无法读取名为 "Artical.pdf" 的PDF文件。请确认文件名是否正确，或者尝试上传另一个PDF文件。如果您需要帮助，请告诉我。
数据集中存在文件，大模型却无法读取到文件内容，文件路径如下：library://Artical.pdf，在容器内部其真实路径为/data/library/Artical.pdf，请大模型根据文件路径开头协议，自动读取文件内容，references://对应真实路径为/data/references，其它文件路径存放在minio中
所有subpanel提供缩回功能
1.大模型应该根据内容自动找到合适的skills，pipeline等进行任务分析
2.用户输入请开始执行，没有回复，也没有执行
目前大模型使用的模型只显示kimi，应该显示是k3还是k2.7，kimi支持深度思考，没有看到kimi的思考过程，需要将所有思考过程保存，包括使用了哪些数据，哪些技能，哪些pipeline，在哪个执行器开始执行等
1.普通会话和项目会话，大模型选择select class="ci-mode model-select"，其中kimi是k3还是k2.7，是数据库配置的吗
2.设置里模型与会话，默认模型点击切换没有反应，检查设置里所有按钮，补全功能
普通会话和项目会话，将模型列表改为从接口获取，将模型信息保存到数据库，可以添加，更改，删除，查询，同时记录模型使用量，设置里存在降级，那当前会话到底使用哪个模型需要保存到会话表
大模型apikey在后台无法配置
llm_models，llm-settings统一到llm_models表中，apikey和baseurl要始终显示，使用时先从缓存获取数据，如果缓存没有再从表中获取数据
llm_models，llm-settings统一到llm_models表中，baseurl还是为空，将代码中的默认baseurl也存入数据表
增加请求大模型日志记录，记录大模型请求的地址，参数，返回结果，耗时等信息
如果大模型需要执行代码，请通过tools提交代码执行
将文献按钮隐藏
普通会话和项目会话，用户编辑自己发送的内容，应该是发送按钮，而不是保存按钮，点击发送后重新提交，删除对应的大模型回复并重新生成，另外只有最新的那条用户内容才有编辑按钮
后台管理不需要用户输入created_at和updated_at，应该由系统自动设置
技能列表加载太慢了，将系统内置技能也写入数据库，包括技能详细信息，技能所在路径
运行记录和报告都和项目相关，选择项目后应该只显示当前项目的运行记录和报告
技能列表增加类型过滤
普通会话和项目会话，使用"/"和"@"引用数据时，大模型结合用户需求自行分析技能和数据如何使用，技能所在目录/app/data/skills/
普通会话和项目会话，使用"@"引用文件时，大模型需要根据文件路径开头协议读取文件内容，文件路径如下：library://在容器内部其真实路径为/data/library，references://对应真实路径为/data/references，其它文件路径存放在minio中
1.普通会话和项目会话，增加将图片传给大模型功能
2.查看数据集和数据时，大模型返回的数据文件应支持在右侧面板预览功能
普通会话和项目会话，鼠标悬停菜单，留出固定高度，鼠标放上去时，不要变化高度，容易晕
普通会话和项目会话，新会话使用和已有会话同样的页面布局，目前新会话体验不一致
普通会话和项目会话，超链接也需要在右侧面板预览，同时左侧panel，聊天区域，右侧面板均可以调整区域大小
普通会话和项目会话，用户上传了图片，但是大模型思考中时，用户聊天记录里没有体现图片，大模型回复时才显示[附图]，期望显示图片内容，同时点击图片可以在右侧面板预览
显示图片加载中，图片地址错误，http://localhost:5190/api/v1/storage/download/projects/0f1811eb-90d4-450f-9e92-917f40334732/185461540d124c3f9378ef40755d1cc2_v2-3979fd7be53bcb333f0bd3c4ee01ca2d_r.jpg，图片404，docker-compose.yml开放minio端口，增加配置访问url
普通会话和项目会话，可以通过鼠标调整右侧面板大小，同时鼠标变为左右箭头，以提示用户可以调整面板大小
普通会话和项目会话，可以通过鼠标调整左侧panel大小，同时鼠标变为左右箭头，以提示用户可以调整panel大小
普通会话和项目会话，所有网站链接应该可以在右侧面板预览
这个会话sess-1789980425654-hi4q75，大模型回复已完成步骤，但是没有调用tools，skills，pipeline等进行生物分析，请修复
默认模型使用kimi k3，而不是GLM-4-Flash
会话sess-1789980425654-hi4q75确实执行了任务，但是运行记录显示任务失败了，大模型回复中应包含任务运行记录，任务执行情况，如果任务失败了，大模型应该根据失败日志，更正代码后重新执行任务，大模型需要有从互联网获取数据的能力，通过tools等方式从互联网获取数据
1.会话sess-1789980425654-hi4q75仍然没有显示任务运行记录，回复的是“I've completed the analysis steps. Here's what I found based on the tool results above.”，应该轮询任务信息，显示任务状态
2.div class="mu"，文字溢出了，没有换行
会话sess-1789980425654-hi4q75，大模型回复后显示了运行记录，但是刷新页面后大模型回复没有了，而用户提问有两个重复的记录，而且运行记录应该在右侧面板显示，用户主要通过聊天页面完成所有工作，通过聊天与大模型对话，所以可以在聊天页面查看所有内容，包括数据预览，网页预览，图片预览，文档预览，运行记录查看，技能查看，pipeline查看，报告查看等，均在右侧面板预览和查看
1.会话sess-1789980425654-hi4q75，问题仍然存在，大模型思考中显示了运行记录，大模型思考过程，但是刷新页面后大模型回复没有了，而用户提问有两个重复的记录
2.普通会话和项目会话，右侧面板增加项目信息，数据查看
会话sess-1789980425654-hi4q75，问题仍然存在，大模型思考中显示了运行记录，大模型思考过程，但是刷新页面后大模型回复没有了，而用户提问有两个重复的记录，大模型回复“I've completed the analysis steps. Here's what I found based on the tool results above.”，这个回复是什么情况？请修复，不要再回复这种内容，使用用户提问测试“确认使用 library://CRA013121_rnaseq_mini 示例数据，对比组为 WT_CKD vs WT_CTRL，按 fastqc→multiqc→star_align→featurecounts→deseq2→volcano_plot→heatmap→gsea→report 构建完整流水线并立即执行”
大模型循环跑满 5 轮工具调用上限是什么？删除次数限制
doc
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