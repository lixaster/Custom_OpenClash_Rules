## openclash覆写设置

```yaml
rule-providers:
  My-Direct-Group:
    type: inline
    behavior: classical
    payload:
      - DOMAIN-SUFFIX,immersivetranslate.com
  My-NAS-Group:
    type: inline
    behavior: domain
    payload:
      - '+.synology.com'
      - '+.synology.cn'
      - '+.quickconnect.to'
      - '+.quickconnect.cn'
  My-PT-Group:
    type: inline
    behavior: classical
    payload:
      - DOMAIN-SUFFIX,hdkylin.com
      - DOMAIN-SUFFIX,hdkyl.top
      - DST-PORT,51222
      - DST-PORT,51666
  My-Proxy-Group:
    type: inline
    behavior: domain
    payload:
      - '+.anilist.co'
      - '+.synologyupdate.com'
      - '+.synocommunity.com'
      - '+.synologydownload.com'
      - '+.hacs.xyz'
      - '+.hacs.vip'
      - '+.home-assistant.io'
      - '+.playwright.azureedge.net'
      - '+.fanart.tv'
      - '+.ghcr.io'
      - '+.gallerycdn.vsassets.io'
      - '+.movie-pilot.org'
      - '+.lscr.io'
      - '+.gamebanana.com'
      - '+.blob.core.windows.net'
      - '+.xdaforums.com'
      - '+.androidfilehost.com'
      - '+.ftp.apnic.net'
      - '+.chariz.com'
      - '+.brew.sh'
      - '+.dl-cdn.alpinelinux.org'
      - '+.dl.delivery.mp.microsoft.com'
      # DNS泄露检测
      - '+.browserleaks.org'
      - '+.browserleaks.net'
      - '+.browserleaks.com'
  My-Game-Group:
    type: inline
    behavior: domain
    payload:
      - '+.cdpred.services'
      - '+.cdprojektred.com'
  My-Dockerhub-Group:
    type: inline
    behavior: domain
    payload:
      - '+.daocloud.io'
      - '+.daocloud.vip'
      - '+.dockerhub.azk8s.cn'
      - '+.docker.jianmuhub.com'
      - '+.beget.com'

rules:
# 支持的代理组:  🚀 手动选择,♻️ 自动选择
# 💬 即时通讯,🌐 社交媒体,🚀 GitHub,💻 开发者服务
# 🤖 AI服务,🎥 海外影音,📹 YouTube,🎥 Emby
# 📺 Bahamut,🌎 国外媒体,🛒 国外电商,📢 谷歌FCM
# 🇬 谷歌服务,🍎 苹果服务,Ⓜ️ 微软服务,🎮 游戏平台
# 🎮 Steam,⏬ PT站点,🚀 测速工具,🐟 漏网之鱼
  - RULE-SET,My-Direct-Group,DIRECT
  - GEOSITE,category-dev-cn,DIRECT
  - RULE-SET,My-NAS-Group,DIRECT
  - RULE-SET,My-PT-Group,⏬ PT站点
  - RULE-SET,My-Proxy-Group,🌎 国外媒体
  - RULE-SET,My-Dockerhub-Group,💻 开发者服务
  - RULE-SET,My-Game-Group,🎮 游戏平台
  - GEOSITE,category-ads-all,REJECT
  ```

## 小猫咪规则备份

```list
DOMAIN-SUFFIX,synology.com,DIRECT
DOMAIN-SUFFIX,synology.cn,DIRECT
DOMAIN-SUFFIX,quickconnect.to,DIRECT
DOMAIN-SUFFIX,quickconnect.cn,DIRECT
DOMAIN-SUFFIX,immersivetranslate.com,DIRECT
DOMAIN-SUFFIX,m-team.cc,DIRECT
DOMAIN-SUFFIX,m-team.io,DIRECT
DOMAIN-SUFFIX,hdsky.me,DIRECT
DOMAIN-SUFFIX,0ff.cc,DIRECT
DOMAIN-SUFFIX,btschool.club,DIRECT
DOMAIN-SUFFIX,ultrahd.net,DIRECT
DOMAIN-SUFFIX,pttime.org,DIRECT
DOMAIN-SUFFIX,pterclub.net,DIRECT
DOMAIN-SUFFIX,hdfans.org,DIRECT
DOMAIN-SUFFIX,hdkyl.in,DIRECT
DOMAIN-SUFFIX,hdkyl.top,DIRECT
DOMAIN-REGEX,^.*\.?amazon\.cn$,DIRECT
DST-PORT,51222,DIRECT
DST-PORT,51666,DIRECT
DOMAIN-SUFFIX,anilist.co,🇺🇳 国外网站
DOMAIN-SUFFIX,synologyupdate.com,🇺🇳 国外网站
DOMAIN-SUFFIX,synocommunity.com,🇺🇳 国外网站
DOMAIN-SUFFIX,synologydownload.com,🇺🇳 国外网站
DOMAIN-SUFFIX,pypi.org,🇺🇳 国外网站
DOMAIN-SUFFIX,pythonhosted.org,🇺🇳 国外网站
DOMAIN-SUFFIX,hacs.xyz,🇺🇳 国外网站
DOMAIN-SUFFIX,hacs.vip,🇺🇳 国外网站
DOMAIN-SUFFIX,home-assistant.io,🇺🇳 国外网站
DOMAIN-SUFFIX,playwright.azureedge.net,🇺🇳 国外网站
DOMAIN-SUFFIX,fanart.tv,🇺🇳 国外网站
DOMAIN-SUFFIX,ghcr.io,🇺🇳 国外网站
DOMAIN-SUFFIX,beget.com,🇺🇳 国外网站
DOMAIN-SUFFIX,gallerycdn.vsassets.io,🇺🇳 国外网站
DOMAIN-SUFFIX,movie-pilot.org,🇺🇳 国外网站
DOMAIN-SUFFIX,githubusercontent.com,🇺🇳 国外网站
DOMAIN-SUFFIX,lscr.io,🇺🇳 国外网站
DOMAIN-SUFFIX,gamebanana.com,🇺🇳 国外网站
DOMAIN-SUFFIX,npmjs.org,🇺🇳 国外网站
DOMAIN-SUFFIX,blob.core.windows.net,🇺🇳 国外网站
DOMAIN-SUFFIX,xdaforums.com,🇺🇳 国外网站
DOMAIN-SUFFIX,androidfilehost.com,🇺🇳 国外网站
DOMAIN-SUFFIX,ftp.apnic.net,🇺🇳 国外网站
DOMAIN-SUFFIX,chariz.com,🇺🇳 国外网站
DOMAIN-SUFFIX,brew.sh,🇺🇳 国外网站
DOMAIN-SUFFIX,dl-cdn.alpinelinux.org,🇺🇳 国外网站
DOMAIN-SUFFIX,dl.delivery.mp.microsoft.com,🇺🇳 国外网站
DOMAIN-SUFFIX,appcenter.ms,🧩 微软服务
DOMAIN-SUFFIX,clarity.ms,🧩 微软服务
DOMAIN-SUFFIX,anthropic.com,🤖 OpenAI
DOMAIN-SUFFIX,claude.ai,🤖 OpenAI
DOMAIN-SUFFIX,ubi.com,🎮 游戏平台
DOMAIN-SUFFIX,just-dance.com,🎮 游戏平台
DOMAIN-SUFFIX,ubisoft.com,🎮 游戏平台
DOMAIN-SUFFIX,cdpred.services,🎮 游戏平台
DOMAIN-SUFFIX,cdprojektred.com,🎮 游戏平台
DOMAIN-KEYWORD,amazon,🎬 Prime
```