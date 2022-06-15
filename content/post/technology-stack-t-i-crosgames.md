---
timeToRead: 0
authors: []
title: Technology stack tại Crosgames
excerpt: Technology stack tại Crosgames
date: 2022-06-15T00:00:00+07:00
hero: "/images/15-06-2022-techstack.png"

---
Crosgames vốn bắt nguồn từ công ty chuyển sản xuất game bằng Unity3d engine, vì thế C# là ngôn ngữ chính của công ty. Trong quá trình mở rộng sang mảng web-server, javascript được phổ biến dần vào trong công ty.

## Mobile game team

Ở mảng game mobile, engine game được chọn là Unity3d đi cùng với networking solution là Photon.

Với Unity3d, đội phát triển đã thử nghiệm và tích hợp các package plugin khác nhau để chọn ra những gì cần thiết và hiệu quả nhất cho quá trình phát triển như textmesh pro, fmod studio...

Với Photon networking, để update và đảm bảo tính bảo mật cao, công ty đang nghiên cứu và áp dụng Photon Quantum vào trong quá trình sản xuất và đã thu được một số hiệu quả nhất định.

## Web team

Do đội web vốn được tách ra từ đội game, nên web framework được lựa chọn cũng hết sức tự nhiên là ASP.NET core. May mắn là thời điểm đội web được thành lập thì .Net core đang là phiên bản 3.1, chạy rất ổn định và đa nền tảng. Về sau với yêu cầu về tính năng thì Vue, Postgresql và Redis... được tích hợp vào.

Về hạ tầng, thì công ty sử dụng kết hợp server trong nước cho các dịch vụ nội bộ như kế toán, jira, một số web game nhỏ lẻ demo. Bên cạnh đó, là AWS cho môi trường production. Deploy một application áp dụng cả phương án build file truyền thống, docker-compose và kubernetes. Gần đây đang nghiên cứu thêm các dịch vụ static site hosting như cloudflare page, netlify.

Với luồng CI/CD thì công ty đang sử dụng gitlab CI/CD để build và ship app tới các môi trường cần thiết.