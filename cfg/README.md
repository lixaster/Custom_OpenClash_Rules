
<<<<<<< HEAD
# 🧩 转换模板示例

下面将给出`ini`、`yaml`和`toml`格式的转换模板示例。

## example_external_config.ini

<details>  <summary>点击查看</summary>

```ini
[custom]
;This is an example external configuration file
;All possible customization settings are shown below

;Options for custom groups
;custom_proxy_group=Proxy`select`.*`[]AUTO`[]DIRECT`.*
;custom_proxy_group=AUTO`url-test`.*`https://www.gstatic.com/generate_204`300
;custom_proxy_group=google`select`.*
;custom_proxy_group=netflix`select`.*
;custom_proxy_group=动画疯`select`(深台|彰化|新北|台)
;custom_proxy_group=fox+`select`(HGC|HKBN|PCCW|HKT|深台|彰化|新北|台|新加坡|sg|hk|tw)
;custom_proxy_group=美区影视`select`(美|美国)
;custom_proxy_group=Global_media`select`.*
;custom_proxy_group=Domestic`select`[]DIRECT`[]Proxy
;custom_proxy_group=Apple`select`[]DIRECT`[]Proxy
;custom_proxy_group=Final`select`[]Proxy`[]DIRECT
;custom_proxy_group=屏蔽广告`select`[]REJECT`[]DIRECT
;custom_proxy_group=UnblockNeteaseMusic`select`云音乐解锁`[]DIRECT
;custom_proxy_group=Telegram`select`新加坡`[]Proxy
custom_proxy_group=!!import:snippets/groups_forcerule.txt

;Options for custom rulesets
enable_rule_generator=false
overwrite_original_rules=false
; Current project-owned resources used as safe examples:
;ruleset=Domestic,https://raw.githubusercontent.com/Aethersailor/Custom_OpenClash_Rules/main/rule/Custom_Direct.list
;ruleset=Proxy,https://raw.githubusercontent.com/Aethersailor/Custom_OpenClash_Rules/main/rule/Custom_Proxy.list
; SubConverter-Extended extension: append |no-resolve after interval for clash-ipcidr.
; Traditional subconverter preserves URL and interval but ignores this option.
; Do not write ...,28800,no-resolve.
;ruleset=🎯 全球直连,clash-ipcidr:https://example.com/cn-ip.yaml,28800|no-resolve

; SubConverter-Extended-only complete Clash rules. Repeated sources keep order.
; Traditional subconverter ignores these fields.
;ruleprepend=https://example.com/first.list
;ruleprepend=https://example.com/second.list
;ruleappend=https://example.com/last.yaml

;Options for custom base configuration file
clash_rule_base=base/forcerule.yml
;surge_rule_base=base/surge.conf
;surfboard_rule_base=base/surfboard.conf
;mellow_rule_base=base/mellow.conf
;quan_rule_base=base/quan.conf
;quanx_rule_base=base/quanx.conf
;loon_rule_base=base/loon.conf
;sssub_rule_base=base/shadowsocks_base.json
;singbox_rule_base=base/singbox.json
;stash_rule_base=base/stash.yaml

;Options for renaming nodes
;rename=Test-(.*?)-(.*?)-(.*?)\((.*?)\)@\1\4x测试线路_自\2到\3
;rename=\(?((x|X)?(\d+)(\.?\d+)?)((\s?倍率?)|(x|X))\)?@$1x

;Options for adding emojis
;add_emoji=true
;remove_old_emoji=true
;emoji=(流量|时间|应急),🏳️‍🌈
;emoji=阿根廷,🇦🇷

;Options for filtering nodes
;include_remarks=
;exclude_remarks=

;[template]
;;variables in the local scope
;clash.dns.port=5353
=======
# 🧩 OpenClash 订阅转换模板

**OpenClash `dev` 版内置的 8 个模板，以及 1 个兼容文件**

[使用方法](#-使用订阅转换模板) · [模板列表](#-模板列表) · [版本区别](#-版本区别) · [Stash 模板](#-stash-模板) · [其他配置方式](#-其他配置方式) · [备用链接](#-备用远程链接)

</div>

---

> [!IMPORTANT]
> 本目录直接存放 `.ini` 订阅转换模板。OpenClash `dev` 版当前已内置全部 8 个模板，包括标准版、轻量版、极简 GFW 版、重度分流版，以及文件名以 `_Fallback` 结尾的对应故障转移版。旧版如未显示对应条目，可手动填写远程模板地址。
>
> YAML 配置文件请查看 [`yaml/`](./yaml/)；通过远程覆写模块调用 YAML，请查看 [`../overwrite/yaml/`](../overwrite/yaml/)。

内置状态可在 OpenClash 上游 `dev` 分支的 [`sub_ini.list`](https://github.com/vernesong/OpenClash/blob/dev/luci-app-openclash/root/usr/share/openclash/res/sub_ini.list) 中核对。不同 OpenClash 分支或版本的内置列表可能不同。

## 🔄 使用订阅转换模板

1. 先按照项目 Wiki 的 [OpenClash 设置方案](https://github.com/Aethersailor/Custom_OpenClash_Rules/wiki/OpenClash-%E8%AE%BE%E7%BD%AE%E6%96%B9%E6%A1%88) 完成插件设置。
2. 进入 OpenClash 订阅管理，新增或编辑订阅。
3. 启用在线订阅转换。
4. 在模板列表中搜索并选择对应的「Aethersailor 规则」模板。如果当前 OpenClash 版本未显示对应条目，则手动填写本文提供的远程模板地址。
5. 保存并更新订阅。
6. 确认配置校验通过，内核、Provider、策略组和实际分流均正常。

OpenClash `dev` 分支的内置列表已收录本仓库全部 8 个模板的远程地址，模板内容仍由本项目维护。仓库更新后，后续订阅转换会获取对应分支上的当前模板。

> [!NOTE]
> `.ini` 文件是订阅转换模板，不能直接作为 OpenClash 运行配置上传。

### 关于转换后端

订阅转换会将订阅地址和转换参数发送给所选后端。公共后端的稳定性、兼容性和隐私不由本项目控制；重视可靠性或隐私时，可以使用自建兼容后端。

## 📁 模板列表

本目录包含 4 个普通版及对应的 4 个故障转移版，共 8 个模板：

| 版本 | 文件 | 定位 |
| --- | --- | --- |
| 标准版 | [`Custom_Clash.ini`](./Custom_Clash.ini) | 日常分流与复杂度均衡，建议多数用户优先选择 |
| 标准故障转移版 | [`Custom_Clash_Fallback.ini`](./Custom_Clash_Fallback.ini) | 标准版分流结构，主要业务组自动故障转移 |
| 轻量版 | [`Custom_Clash_Lite.ini`](./Custom_Clash_Lite.ini) | 策略组较少，结构简洁，维护成本较低 |
| 轻量故障转移版 | [`Custom_Clash_Lite_Fallback.ini`](./Custom_Clash_Lite_Fallback.ini) | 轻量结构与自动故障转移结合 |
| 极简 GFW 版 | [`Custom_Clash_GFW.ini`](./Custom_Clash_GFW.ini) | 主要处理 GFW 相关流量，其余流量默认直连 |
| 极简 GFW 故障转移版 | [`Custom_Clash_GFW_Fallback.ini`](./Custom_Clash_GFW_Fallback.ini) | 极简分流与自动故障转移结合 |
| 重度分流版 | [`Custom_Clash_Full.ini`](./Custom_Clash_Full.ini) | 业务、地区和节点用途分组更丰富 |
| 重度分流故障转移版 | [`Custom_Clash_Full_Fallback.ini`](./Custom_Clash_Full_Fallback.ini) | 重度分流结构与自动故障转移结合 |

[`Custom_Clash_Mainland.ini`](./Custom_Clash_Mainland.ini) 是由统一兼容配置生成流程从 `Custom_Clash.ini` 自动同步的文件，不是独立配置版本。不要直接修改该文件。

## 📊 版本区别

| 系列 | 特点 | 建议 |
| --- | --- | --- |
| **标准版** | 常用业务覆盖与复杂度均衡 | 不确定时优先选择 |
| **轻量版** | 策略组更少，结构更简洁 | 重视低维护成本 |
| **极简 GFW 版** | 主要代理 GFW 相关流量 | 只需要基础分流 |
| **重度分流版** | 业务、地区和节点用途分类最多 | 节点丰富并需要精细选路 |

<a id="普通版与-fallback-版"></a>

### 普通版与故障转移版

- **普通版：** 主要业务策略组使用 `select`，便于手动选择出口。
- **故障转移版：** 主要业务策略组使用 `fallback`，按候选顺序检测并自动切换。

> [!WARNING]
> `fallback` 只判断健康检查地址是否可达，不能判断节点是否具备流媒体、AI 服务或特定地区的解锁能力。

## 📲 Stash 模板

Stash 专用订阅转换模板仓库 [`Aethersailor/Custom_Stash_Rules`](https://github.com/Aethersailor/Custom_Stash_Rules) 已归档。本项目已停止生成和同步 Stash 模板，本目录仅维护 OpenClash 模板。历史 Stash 模板不再跟随本项目的规则和策略更新。

## 🧭 其他配置方式

除订阅转换外，本项目还提供两种使用同一套配置的方式：

| 方式 | 入口 |
| --- | --- |
| 远程 YAML 覆写模块 | [`../overwrite/yaml/`](../overwrite/yaml/) |
| 下载并手动导入 YAML | [`yaml/`](./yaml/) |

> [!IMPORTANT]
> 本项目按同一套配置设计维护订阅转换、远程 YAML 覆写模块和手动导入 YAML。选择相同版本且未自行修改时，策略组定位、规则顺序和分流逻辑应保持一致；文件结构和加载方式不同，实际结果还会受到订阅转换后端及 OpenClash 版本影响。

通常应从三种方式中选择一种作为主路径，不建议同时反复替换同一份当前配置。

## 🔗 备用远程链接

OpenClash `dev` 版通常可直接从内置列表选择全部 8 个模板。以下地址供旧版 OpenClash、自建订阅转换后端和其他兼容工具使用，也可用于兼容性排查或内置模板列表异常时备用。

<details>
<summary><strong>展开查看全部 8 个模板的备用地址</strong></summary>

<br>

### 标准版

加速地址（`cdn.jsdelivr.net`）：

```text
https://cdn.jsdelivr.net/gh/Aethersailor/Custom_OpenClash_Rules@main/cfg/Custom_Clash.ini
```

GitHub Raw 地址：

```text
https://raw.githubusercontent.com/Aethersailor/Custom_OpenClash_Rules/refs/heads/main/cfg/Custom_Clash.ini
```

<a id="标准-fallback-版"></a>

### 标准故障转移版

加速地址（`cdn.jsdelivr.net`）：

```text
https://cdn.jsdelivr.net/gh/Aethersailor/Custom_OpenClash_Rules@main/cfg/Custom_Clash_Fallback.ini
```

GitHub Raw 地址：

```text
https://raw.githubusercontent.com/Aethersailor/Custom_OpenClash_Rules/refs/heads/main/cfg/Custom_Clash_Fallback.ini
```

### 轻量版

加速地址（`cdn.jsdelivr.net`）：

```text
https://cdn.jsdelivr.net/gh/Aethersailor/Custom_OpenClash_Rules@main/cfg/Custom_Clash_Lite.ini
```

GitHub Raw 地址：

```text
https://raw.githubusercontent.com/Aethersailor/Custom_OpenClash_Rules/refs/heads/main/cfg/Custom_Clash_Lite.ini
```

<a id="轻量-fallback-版"></a>

### 轻量故障转移版

加速地址（`cdn.jsdelivr.net`）：

```text
https://cdn.jsdelivr.net/gh/Aethersailor/Custom_OpenClash_Rules@main/cfg/Custom_Clash_Lite_Fallback.ini
```

GitHub Raw 地址：

```text
https://raw.githubusercontent.com/Aethersailor/Custom_OpenClash_Rules/refs/heads/main/cfg/Custom_Clash_Lite_Fallback.ini
```

### 极简 GFW 版

加速地址（`cdn.jsdelivr.net`）：

```text
https://cdn.jsdelivr.net/gh/Aethersailor/Custom_OpenClash_Rules@main/cfg/Custom_Clash_GFW.ini
```

GitHub Raw 地址：

```text
https://raw.githubusercontent.com/Aethersailor/Custom_OpenClash_Rules/refs/heads/main/cfg/Custom_Clash_GFW.ini
```

<a id="极简-gfw-fallback-版"></a>

### 极简 GFW 故障转移版

加速地址（`cdn.jsdelivr.net`）：

```text
https://cdn.jsdelivr.net/gh/Aethersailor/Custom_OpenClash_Rules@main/cfg/Custom_Clash_GFW_Fallback.ini
```

GitHub Raw 地址：

```text
https://raw.githubusercontent.com/Aethersailor/Custom_OpenClash_Rules/refs/heads/main/cfg/Custom_Clash_GFW_Fallback.ini
```

### 重度分流版

加速地址（`cdn.jsdelivr.net`）：

```text
https://cdn.jsdelivr.net/gh/Aethersailor/Custom_OpenClash_Rules@main/cfg/Custom_Clash_Full.ini
```

GitHub Raw 地址：

```text
https://raw.githubusercontent.com/Aethersailor/Custom_OpenClash_Rules/refs/heads/main/cfg/Custom_Clash_Full.ini
```

<a id="重度分流-fallback-版"></a>

### 重度分流故障转移版

加速地址（`cdn.jsdelivr.net`）：

```text
https://cdn.jsdelivr.net/gh/Aethersailor/Custom_OpenClash_Rules@main/cfg/Custom_Clash_Full_Fallback.ini
```

GitHub Raw 地址：

```text
https://raw.githubusercontent.com/Aethersailor/Custom_OpenClash_Rules/refs/heads/main/cfg/Custom_Clash_Full_Fallback.ini
>>>>>>> Aethersailor/main
```

</details>

## example_external_config.yaml

<details>  <summary>点击查看</summary>

```yaml
custom:
  enable_rule_generator: false
  overwrite_original_rules: false

  # SubConverter-Extended-only complete Clash rules; target=clash only.
  # Traditional subconverter ignores these fields.
  # ruleprepend:
  #   - https://example.com/first.list
  # ruleappend:
  #   - https://example.com/last.yaml

  proxy_groups:
  - {import: snippets/groups_forcerule.txt}

#  rulesets:
#  - {import: snippets/rulesets_remote.txt}
#  - {ruleset: "clash-ipcidr:https://example.com/cn-ip.yaml", group: "🎯 全球直连", interval: 28800, options: ["no-resolve"]}

  clash_rule_base: base/forcerule.yml
#  surge_rule_base: base/surge.conf
#  surfboard_rule_base: base/surfboard.conf
#  mellow_rule_base: base/mellow.conf
#  quan_rule_base: base/quan.conf
#  quanx_rule_base: base/quanx.conf
#  loon_rule_base: base/loon.conf
#  sssub_rule_base: base/shadowsocks_base.json
#  singbox_rule_base: base/singbox.json
#  stash_rule_base: base/stash.yaml

#  rename_node:
#  - {import: snippets/rename_node.txt}

#  add_emoji: true
#  remove_old_emoji: true
#  emojis:
#  - {import: snippets/emoji.txt}

#  include_remarks: []
#  exclude_remarks: []
#  template_args:
#  - {key: clash.dns.port, value: 5353}
```

</details>

## example_external_config.toml

<details>  <summary>点击查看</summary>

```toml
version = 1
[custom]
enable_rule_generator = false
overwrite_original_rules = false

# SubConverter-Extended-only complete Clash rules; target=clash only.
# Traditional subconverter ignores these fields.
#ruleprepend = ["https://example.com/first.list"]
#ruleappend = ["https://example.com/last.yaml"]

# Options for custom base configuration file
clash_rule_base = "base/forcerule.yml"
#surge_rule_base = "base/surge.conf"
#surfboard_rule_base = "base/surfboard.conf"
#mellow_rule_base = "base/mellow.conf"
#quan_rule_base = "base/quan.conf"
#quanx_rule_base = "base/quanx.conf"
#loon_rule_base = "base/loon.conf"
#sssub_rule_base = "base/shadowsocks_base.json"
#singbox_rule_base = "base/singbox.json"
#stash_rule_base = "base/stash.yaml"

# Options for adding emojis
#add_emoji = true
#remove_old_emoji = true

# Options for filtering nodes
#include_remarks = []
#exclude_remarks = []

[[custom_groups]]
import = "snippets/groups_forcerule.toml"

#[[rulesets]]
#import = ""

#[[rulesets]]
#group = "🎯 全球直连"
#type = "clash-ipcidr"
#ruleset = "https://example.com/cn-ip.yaml"
#interval = 28800
#options = ["no-resolve"]

[[template_args]]
key = "clash.dns.port"
value = "5353"
```