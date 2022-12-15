# Hướng dẫn tạo CSR bằng OPENSSL và ACS PORTAL

## 1. Tạo file CSR server bằng OpenSSL

- Chạy lệnh sau để tạo file CSR và key để cài đặt CITRIX hoặc Webserver:

```bash
openssl req -new -newkey rsa:2048 -nodes -out visa_server.csr -keyout visa_server.key
```

- Sau khi tạo xong file cần lưu lại key để cài đặt với chứng chỉ Ký với tổ chức thẻ.

![This is an image](https://user-images.githubusercontent.com/61931560/207807883-a065d156-9e53-4b58-8b9c-14be844ba11e.png)
.png)

## 2. Tạo Clients CSR và Signing CSR bằng Portal

- Tạo file Clients CSR:

![Tạo file Clients](https://user-images.githubusercontent.com/61931560/207808008-33c959c1-0532-421e-a54e-8b66f313eea0.png)


- Tạo file Signing CSR:

![Tạo file Clients](https://user-images.githubusercontent.com/61931560/207808051-484a4ee3-cab1-45b9-bcd8-4078810f19aa.png)

