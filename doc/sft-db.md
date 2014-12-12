## 交易流水表sft_log

字段 | 格式 | 描述 |  
:---| :----| :--------
id  | 自动生成的id | asdfasdf

acc_id | | 接入渠道代码
ssn | | 渠道流水号
tdate|| 渠道交易日期
ttime | | 渠道交易时间
idx | | 批量中流水顺序号     0

sft_ssn| | 平台流水号
sft_tdate| 平台交易日期
sft_ttime| | 平台交易时间

acc_key || 接入渠道请求key, 组成规则为: acc_id + ssn + tdate + ttime + index(如为单笔作为-1)
sft_key || 平台key, 组成规则为: sft_ssn + sft_tdate + sft_ttime

tcode || 交易代码
tamt  || 交易金额       | 身份验证交易时可为空

acct_cat || 账户种类
acct_no || 账号
acct_name || 账户名称
id_type| | 证件类型
id_no |  | 证件号码
phone | | 手机号

bank_no    || 联行号
bank_code  || 银行编号

btype      || 业务代码


checkcode | | 短信验证码

resp_code | | 应答码

chnl_code || 路由渠道
status | | 流水状态: 0-插入, 1-已调度, 2-成功, 3-失败

## 路由组配置表 route_group
id          ||
name        || 路由组名称    工行-代收-保险    icbc-gather-insurance
bank_code   || 银行编号
tcode       ||
btype       || 业务类型

## 路由组信息 route_group_map
id        ||
rg_name   || 路由组名称
chnl_code || 渠道编号

## 银行渠道信息chnl_info
id         ||
chnl_code  || 渠道编码
chnl_name  || 渠道名称
chnl_tps   || 渠道处理能力, 每秒最多多少笔

## 渠道成本配置chnl_cost_cfg
rgm_id      || reference route_group_map
floor       || 保底      int(分)
ceiling     || 封顶      int(分)
ratio       || 比例      int
fix         || 固定      int(分)

## 交易成本表日志sft_cost_dtl
sft_key    || 平台key
cost       || 交易成本, 单位(分)

## 业务类型btype_cfg
