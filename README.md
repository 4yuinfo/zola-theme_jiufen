# jiufen
The 'jiufen' theme is a theme that references the [W3.CSS](https://www.w3schools.com/w3css/) 
Template and incorporates [ZOLA](https://www.getzola.org/)-related features. 

Jiufen is the name of an old street located on the island of Formosa (Taiwan). 
If you have the chance, you should definitely visit this island to experience life here.

[DEMO](https://4yuinfo.github.io/zola-theme_jiufen/)

![screenshot](https://4yuinfo.github.io/zola-theme_jiufen/images/screenshot.png)

## Installation
```mermaid
flowchart
    A[1.Installation Zola]
    B[2.Initialize Site]
    C[3.1.Git Initialize]
    D[3.2.Download Theme]
    E[4.Initialize Theme]
    F[4.1.Copy Sample]
    G[4.2.Edit Config]
    H[5.Other Options Setting]
    A --> B
    B -->| Use Git | C
    B -->| No Git | D
    C -->E
    D-->E
    E-->F
    E-->G
    F-->H
    G-->H
    click A "https://www.getzola.org/documentation/getting-started/installation/" "Install Zola" _blank
    click B "https://www.getzola.org/documentation/getting-started/overview/#initialize-site" "Initialize Site" _blank
```

### 1.Install Zola 
ZOLA DOCS [Installation](https://www.getzola.org/documentation/getting-started/installation/)

### 2.Initialize Site
ZOLA DOCS [Initialize Site](https://www.getzola.org/documentation/getting-started/overview/#initialize-site)

```shell
# rename [myblog]

zola init [myblog]

> What is the URL of your site? (https://example.com):
> Do you want to enable Sass compilation? [Y/n]: n
> Do you want to enable syntax highlighting? [y/N]: y
> Do you want to build a search index of the content? [y/N]: y

cd [myblog]
```

### 3.1.Git Initialize
```shell
git init;touch .gitignore
git submodule add https://github.com/4yuinfo/zola-theme_jiufen.git themes/jiufen
```

### 3.2.Download Theme
Download And Upzip to Theme

### 4.1 Copy Sample
```shell
mkdir -p content/posts
cp themes/jiufen/config.toml .
cp themes/jiufen/content/home.md content/
```

### 4.2.Edit Config
ZOLA DOCS [Configuration](https://www.getzola.org/documentation/getting-started/configuration/)

Adjust config.toml
```toml
#config.toml
theme="jiufen"
```

### 5.Other Options Setting

#### Header And Footer

> If Not Setting Hidden Header
> 
> Can Use Picture(html tag width set 100%)

```toml
# config.toml
[extra]
site_name = 'Zola Theme Jiufen'
site_desc = "Welcome to the Zola Theme Jiufen introduction website."
copyright = "Copyright © 2025 Saint Huang All rights reserved."
```

#### Navigation

> Navigation Display Control
> If Not Setting Show Home Button
> top and sidebar is option

```toml
# config.toml
[extra]
navigation_display_top = true
navigation_display_sidebar = true
navigation = [
    {name = '<i class="fa fa-home"></i>', url = "/",top=true, sidebar=false },
    {name = "Blog", url = "/blog/", top=false, sidebar=true },
    {name = "Camp", url = "/camp/", top=true, sidebar=false },
    {name = "Travel", url = "/travel/", top=true, sidebar=false },
    {name = "404", url = "/404/", top=true, sidebar=false },
]
```

#### Search

#### Google Analytics（GA4）

> Optional, Google Analytics
```toml
# config.toml
[extra]
# 啟用 GA4：填入你的 Measurement ID（格式類似 G-XXXXXXXXXX）
# google_analytics_id = "G-XXXXXXXXXX"
# 隱私選項：啟用 IP 匿名化（可選）
# google_analytics_anonymize_ip = true
```

#### Google Analytics User consent（Consent Mode v2）

> Optional, Google Analytics User consent
```toml
# config.toml
[extra]
# Enable GA4
# google_analytics_id = "G-XXXXXXXXXX"
# （Optional）IP Anonymization
# google_analytics_anonymize_ip = true
# Enable user consent banner
# google_analytics_consent = true
# （Optional）Customize banner text
# google_analytics_consent_message = "This website uses cookies for statistics and to improve your experience. Do you agree to our use of Google Analytics?"
# google_analytics_consent_accept_text = "agree"
# google_analytics_consent_decline_text = "disagree"
```

> Optional, if you want search

Only Support fuse_javascript
```toml
# config.toml
build_search_index = true

[slugify]
taxonomies = "safe"

[search]
include_title = true
include_content = true
include_description = true
include_date = false
include_path = false
index_format = "fuse_javascript"
```

#### Home.md

home.md
```toml
# home.md
+++
title = 'Home'
in_search_index = false
[extra]
image = "/images/jiufen.png"    # Option
+++
```

### Context 
context.md
```toml
+++
# context.md
title = "Blog01"
date = 2025-5-1
[taxonomies]
tags=["Blog", "Camp"]
[extra]
image = "/images/jiufen.png" # Option
+++
```

context/[folder]/_index.md
```toml
# context/[folder]/_index.md
+++
title = "List Theme Posts"
sort_by = "date"  # "date", "update_date", "title", "title_bytes", "weight", "slug"
paginate_by = 5
+++
```

### Shortcodes

youtube
```context
{{ youtube(id="NSZ6dhQIvXw") }}
```

imageh100
imageh200
imageh300
```context
{{ imageh100(path="/images/jiufen.png") }}
{{ imageh200(path="/images/jiufen.png") }}
{{ imageh300(path="/images/jiufen.png") }}
```

imagew
```context
{{ imagew(path="/images/jiufen.png") }}
```

code
 
```context
{% code(code="Rust",copy=true) %}
```Rust
fn main() {
    println!("Hello World!");
}
``
{% end %}
```
