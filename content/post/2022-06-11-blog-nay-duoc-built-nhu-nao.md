---
title: Blog này được xây dựng như nào
date: 2022-06-11
hero: /images/2022_06_11_import_novela_to_forestry.jpg
excerpt: xử dụng hugo, github và cloudflare để xây dựng blog tech
timeToRead: 4
authors:
  - Anh Ngoc

---

# Overview
Tác giả là một người hâm mộ các công ty lớn có những blog tech rất hay ho như [Tiki](https://engineering.tiki.vn/),[Riot game](https://technology.riotgames.com/),[Netlify](https://www.netlify.com/blog/tags/engineering/)... nên cũng đề xuất lên lãnh đạo công ty và may mắn được duyêt :v.

Blog này mình chọn dùng hugo vì đã quen thuộc với markdown, ngoài ra tránh được các phiền phức như tạo database, bảo trì server và các vấn đề liên quan tới lỗ hổng bảo mật của wordpress.



# Setup
## Create project
Theme mình chọn là [Novela](https://themes.gohugo.io/themes/hugo-theme-novela/) vì trông sạch và đơn giản, phù hợp với nhu cầu viết tạp chí về tech của công ty.

Sau đó chúng ta ấn vào "Import to Forestry" để tạo github repository và import vào forestry
![alt import](/images/2022_06_11_import_novela_to_forestry.jpg)

![](/images/2022-06-11-create-github-repo.jpg)

![](/images/2022_06_11_import_done.jpg)

## Setup cloudflare page
Việc setup cloudflare account và domain nằm ngoài khuôn khổ của bài viết này. Mình sẽ tập trung vào setup cloudflare page thôi.

- Chúng ta sẽ tạo một page trên cloudflare bằng cách ấn vào "create a project"
    ![](/images/2022_06_11_cloudflare_create_project.jpg)
- Tiếp theo chúng ta sẽ connect vào github để select repository
    ![](/images/2022_06_11_connect_git.jpg)
- Sau đó chúng ta sẽ cấu hình lệnh build.
    - Command build: hugo --gc --minify -b $CF_PAGES_URL
    - Build output directory: /public
    - Add go version vào environment: GO_VERSION (1.12)
    - Add hugo version vào environment: HUGO_VERSION (0.65.3)
    - Ấn "save and deploy"

    ![](/images/2022_06_11_setup_config.jpg)

    ![](/images/2022-06-11-build_complete.jpg)

- Sau khi project build xong thì chúng ta sẽ config dns cho website
    ![](/images/2022_06_11_configure_dns.jpg)

    ![](/images/2022-06-11-done-dns.jpg)
- Sau khi dns setup xong thì website đã bắt đầu up.
    ![](/images/2022-06-11-website-up.jpg)

## Setup theme và viết bài
-  Để setup theme và viết bài thì chúng ta có thể chỉnh sửa trực tiếp trên forestry.io
    ![](/images/2022_06_11_forestry.jpg)
- Hoặc clone project từ github về máy, edit và commit lại lên git.


