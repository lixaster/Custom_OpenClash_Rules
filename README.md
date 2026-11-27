<h1 align="center">🚀 Custom_OpenClash_Rules 自用</h1>

## 使用方法
目前只关注和修改`配置`[`cfg/`](cfg/)和`规则`[`rule/`](rule/)两个目录，其他跟随上游即可。

| 目录功能 | 目录名称 |
<h1 align="center">
  🚀 Custom_OpenClash_Rules
</h1>

<p align="center"><b>OpenClash 配置方案、订阅转换模板、YAML 配置、规则文件、实用脚本与覆写模块资源</b></p>

<p align="center">
  <a href="https://github.com/Aethersailor/Custom_OpenClash_Rules/wiki">📖 项目 Wiki</a>
  &nbsp;•&nbsp;
  <a href="cfg/">🧩 配置资源</a>
  &nbsp;•&nbsp;
  <a href="rule/">🗂️ 规则文件</a>
  &nbsp;•&nbsp;
  <a href="overwrite/">⚙️ 覆写模块</a>
  &nbsp;•&nbsp;
  <a href="shell/">🛠️ 实用脚本</a>
</p>

<p align="center">
  <img alt="GitHub Repo stars" src="https://img.shields.io/github/stars/Aethersailor/Custom_OpenClash_Rules?style=flat">
  <img alt="GitHub contributors" src="https://img.shields.io/github/contributors-anon/Aethersailor/Custom_OpenClash_Rules?style=flat">
  <img alt="GitHub commit activity" src="https://img.shields.io/github/commit-activity/t/Aethersailor/Custom_OpenClash_Rules?style=flat">
  <img alt="OpenClash" src="https://img.shields.io/badge/OpenClash-resources-brightgreen?style=flat">
  <img alt="Website" src="https://img.shields.io/website?url=https%3A%2F%2Fapi.asailor.org%2Fversion&up_message=online&down_message=offline&style=flat&label=backend">
</p>

---

> [!WARNING]
> 本项目提供中立的技术资料，仅供在中华人民共和国境外学习和研究 OpenWrt 与 OpenClash。
>
> **禁止任何组织或个人在中国大陆访问、下载或使用本项目的任何内容。身处中国大陆的访客请立即关闭本页面。**
>
> 任何组织或个人均不得利用本项目内容从事违反适用法律法规的活动。使用者须自行承担其使用行为产生的法律责任。

## 📖 关于本项目

**Custom_OpenClash_Rules** 是一个围绕 [OpenClash](https://github.com/vernesong/OpenClash) 维护的配置与扩展资源仓库。

本项目提供 OpenClash 设置文档、订阅转换模板、YAML 配置、规则文件、远程覆写模块及辅助脚本。各类资源可以独立使用；完整配置方案需要结合项目 Wiki 中的 OpenClash LuCI 设置。

> [!TIP]
> **仅需 OpenClash，无需「套娃」**
>
> 本项目的所有配置方案均只需 OpenClash 一个插件，无需叠加其他代理或 DNS 插件，也无需进行任何「套娃」设置。

> [!IMPORTANT]
> **关于 DNS 泄漏防护**
>
> 使用本项目的 OpenClash 设置方案，并选择三种订阅路径中的任意一种（订阅转换、远程 YAML 覆写或手动导入 YAML），在以下条件同时满足时，可以避免本地 DNS 泄漏：
>
> - Fake-IP、流量接管和 DNS 设置均已按 Wiki 生效；
> - 终端 DNS 请求及相关流量均经过 OpenClash。
>
> 实际结果必须通过检测验证，不能仅以配置完成作为结论。客户端启用私有 DNS 或 DoH、设备或部分流量未被接管、插件或固件行为与文档不一致，或自行覆写 DNS 配置时，均超出该方案的控制范围，需要单独处理并验证。

根目录的 `README.md` 作为项目首页和资源导航，仅介绍各类资源的定位与入口。具体文件、版本区别、参数和使用方法，请进入对应目录查看其自动展示的 `README.md`。

> [!NOTE]
> 项目 Wiki 目前仅提供中文版本。

---

## ⚠️ 特别声明

> [!IMPORTANT]
> **项目边界声明**
>
> 本项目不提供可供用户使用的代理服务器、代理节点或节点订阅，不运营「机场」等代理服务，也不提供网络接入服务。本项目及其维护者与上述服务提供者不存在合作、代理或担保关系。

> [!WARNING]
> 使用本项目前，请展开并完整阅读下方声明。

<details>
<summary><strong>展开查看完整使用须知与免责声明</strong></summary>

<br>

**使用须知：**

1. 本项目仅用于 OpenWrt 系统及其插件 OpenClash 的技术学习与研究，相关内容属于中立性的技术实现示例与实验性资料，不涉及任何具体使用场景或用途导向。
2. 本项目不面向中华人民共和国境内提供，严禁任何个人或组织在中华人民共和国境内以任何形式访问、下载、复制、保存、安装、运行、部署、修改、传播或以其他方式使用本项目的全部或部分内容；已经取得相关内容的，应立即停止使用并彻底删除全部副本。
3. 使用者在访问、使用、复制本项目内容前，应自行确认其所在地及相关司法辖区的法律法规允许，且在学习和研究后于 24 小时内删除相关内容。
4. 本项目内容不得用于任何违反适用法律法规的用途。使用者在使用本项目内容时，应自行遵守其所在地及相关司法辖区的法律法规，包括中华人民共和国的相关法律法规，不得在中华人民共和国境内利用本项目内容从事获取、传播依法被限制或阻断的境外违法信息等行为。
5. 本项目不提供、亦不涉及设备、软件、工具、线路或服务。项目维护者不制作、不销售、不提供相关设备、软件、工具或技术服务，亦不为任何个人或组织获取、传播依法被限制或阻断的信息、规避监管制度提供技术支持、协助或其他形式的帮助。
6. 任何个人或组织因直接或间接使用本项目内容所实施的行为，均由其自行负责并承担相应法律责任。项目维护者不参与使用者的具体行为，对使用者的用途、方式及其产生的后果不承担任何责任，亦不承担任何形式的连带责任。
7. 基于本项目内容所进行的修改、二次开发、整合、分发或其他衍生行为，均属于相关个人或组织的独立行为，与本项目及其维护者无关，由此产生的任何法律责任由行为主体自行承担。
8. 本项目不鼓励任何形式的转载、再发布或二次传播，且严禁转载、再发布或二次传播本项目内容至中国大陆境内任何平台之上。
9. 任何转载、再发布或二次传播均不得暗示本项目或维护者对转载内容背书。因转载、传播或使用本项目内容所产生的法律风险，由行为主体自行承担，与本项目及其维护者无关。
10. 本项目维护者保留在任何时间对本免责声明进行修订或补充的权利。任何使用、复制或访问本项目内容的个人或组织，均视为已知悉并接受本免责声明。

**补充说明：**

- 本项目编写于 2024 年 4 月，为非营利性质的技术研究与经验整理项目。
- 本项目内容仅为维护者个人经验的总结，用于技术交流，不具权威性，亦不构成 OpenClash 的唯一或推荐使用方式。
- 本项目未运营任何 YouTube 频道，亦未在 YouTube 或其他视频平台发布任何形式的教学或指导视频。
- 本项目文档由维护者根据实际使用经验独立整理；引用或使用的第三方项目、资料与资源在对应位置或下方「感谢」中标注。如因使用其他来源的教程、模板或配置文件产生问题，请勿在本项目的 Issues 或 Discussions 中反馈。
- 内容采用相对易于理解的表述，不代表对任何用户群体作出教学、指导或支持承诺。

</details>

---

## 🚀 快速开始

| 需求 | 建议入口 |
| --- | --- |
| 使用订阅转换模板、YAML 配置或远程 YAML 覆写模块 | [`cfg/`](cfg/) |
| 为现有配置补充或修正规则 | [`rule/`](rule/) |
| 使用独立游戏规则 | [`rule/game_rule/`](rule/game_rule/) |
| 使用单功能远程覆写模块 | [`overwrite/`](overwrite/) |
| 安装、更新或检测 OpenClash | [`shell/`](shell/) |

> 目前只修改了cfg目录，如需修改rule，记得修改配置文件的引用文件url。

-  更详细的配置相关文档模板参考[`README`](cfg/README.md)。

## 关于`rule-providers`的写法(openclash中的覆写等)

### classical

```yaml
payload:
    - DOMAIN-SUFFIX,google.com
    - DOMAIN-KEYWORD,google
    - DOMAIN,ad.com
    - SRC-IP-CIDR,192.168.1.201/32
    - IP-CIDR,127.0.0.0/8
    - GEOIP,CN
    - DST-PORT,80
    - SRC-PORT,7777
```

### domain

domain类规则集合内容通配应遵守 `clash通配符`。

```yaml
payload:
    - '.blogger.com'
    - '*.*.microsoft.com'
    - 'books.itunes.apple.com'
```
#### clash 通配符

- 通配符`*`一次只能匹配一级域名

    `*.baidu.com 只匹配 tieba.baidu.com 而不匹配 123.tieba.baidu.com 或者 baidu.com`
    > `*`只匹配 localhost 等没有.的主机名

- 通配符`+`类似 DOMAIN-SUFFIX, 可以一次性匹配多个级别。

    `+.baidu.com 匹配 tieba.baidu.com 和 123.tieba.baidu.com 或者 baidu.com`
    > `+`只能用于域名前缀匹配

- 通配符`.`可以一次性匹配多个级别

    `.baidu.com 匹配 tieba.baidu.com 和 123.tieba.baidu.com, 但不能匹配 baidu.com`

    > `.`只能用于域名前缀匹配

##### 使用示例

使用通配符时，应当使用引号 ' '或 " "将内容包裹起来

```yaml
fake-ip-filter:
    - ".lan"
    - "xbox.*.microsoft.com"
    - "+.xboxlive.com"
    - localhost.ptlogin2.qq.com
```

### ipcidr

```yaml
payload:
    - '192.168.1.0/24'
    - '10.0.0.0.1/32'
```