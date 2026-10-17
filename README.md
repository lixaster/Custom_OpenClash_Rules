<h1 align="center">🚀 Custom_OpenClash_Rules 自用</h1>

## 使用方法
目前只关注和修改`配置`[`cfg/`](cfg/)和`规则`[`rule/`](rule/)两个目录，其他跟随上游即可。

| 目录功能 | 目录名称 |
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