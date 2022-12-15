# Hướng dẫn tạo CSR bằng OPENSSL và ACS PORTAL

## 1. Tạo file CSR server bằng OpenSSL

- Chạy lệnh sau để tạo file CSR và key để cài đặt CITRIX hoặc Webserver:

```bash
openssl req -new -newkey rsa:2048 -nodes -out visa_server.csr -keyout visa_server.key
```

- Sau khi tạo xong file cần lưu lại key để cài đặt với chứng chỉ Ký với tổ chức thẻ.

![This is an image](http://cdn.hevivu.cyou/root/1234.png)

## 2. Tạo Clients CSR và Signing CSR bằng Portal

- Tạo file Clients CSR:

![Tạo file Clients](http://cdn.hevivu.cyou/root/Screenshot_1.png)

- Tạo file Signing CSR:

![Tạo file Clients](http://cdn.hevivu.cyou/root/Screenshot_2.png)
