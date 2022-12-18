# Hướng dẫn tạo CSR bằng OPENSSL và ACS PORTAL, Cập nhật chứng chỉ Lên Portal và Server

## I. Tạo CSR bằng OPENSSL

## 1. Tạo file CSR server bằng OpenSSL

> a. Chạy lệnh sau để tạo file CSR và key để cài đặt CITRIX hoặc Webserver:

```bash
openssl req -new -newkey rsa:2048 -nodes -out visa_server.csr -keyout visa_server.key
```

```notes
// Visa,JCB,AMEX
Country Name (2 letter code) [AU]:VN
State or Province Name (full name) [Some-State]:Hanoi
Locality Name (eg, city) []:Hanoi
Organization Name (eg, company) [Internet Widgits Pty Ltd]:Joint Stock Commercial Bank for Foreign Trade of Vietnam
Organizational Unit Name (eg, section) []:IT Center
Common Name (e.g. server FQDN or YOUR name) []:test3ds2.vietcombank.com.vn

// Master Card
Country Name (2 letter code) [AU]:VN
State or Province Name (full name) [Some-State]:Hanoi
Locality Name (eg, city) []:Hanoi
Organization Name (eg, company) [Internet Widgits Pty Ltd]:Joint Stock Commercial Bank for Foreign Trade of Vietnam
Organizational Unit Name (eg, section) []:ACSS-MTF-V210-JOINT-STOCK-C0002-48588-SERVER
Common Name (e.g. server FQDN or YOUR name) []:test3ds2.vietcombank.com.vn
```

> Sau khi tạo xong file cần lưu lại key để cài đặt với chứng chỉ Ký với tổ chức thẻ.

![This is an image](https://user-images.githubusercontent.com/61931560/207807883-a065d156-9e53-4b58-8b9c-14be844ba11e.png)

## 2. Tạo Clients CSR và Signing CSR bằng Portal

> a. Tạo file Clients CSR:

![Tạo file Clients](https://user-images.githubusercontent.com/61931560/207808008-33c959c1-0532-421e-a54e-8b66f313eea0.png)
![CSR Info](https://user-images.githubusercontent.com/61931560/207811484-12299df8-9896-4464-8ee5-a4517c61c0df.png)

```notes
// Visa,JCB,AMEX
Country Name (2 letter code) [AU]:VN
State or Province Name (full name) [Some-State]:Hanoi
Locality Name (eg, city) []:Hanoi
Organization Name (eg, company) [Internet Widgits Pty Ltd]:Joint Stock Commercial Bank for Foreign Trade of Vietnam
Organizational Unit Name (eg, section) []:IT Center
Common Name (e.g. server FQDN or YOUR name) []:test3ds2.vietcombank.com.vn

// Master Card
Country Name (2 letter code) [AU]:VN
State or Province Name (full name) [Some-State]:Hanoi
Locality Name (eg, city) []:Hanoi
Organization Name (eg, company) [Internet Widgits Pty Ltd]:Joint Stock Commercial Bank for Foreign Trade of Vietnam
Organizational Unit Name (eg, section) []:ACSC-MTF-V210-JOINT-STOCK-C0002-48588-CLIENT
Common Name (e.g. server FQDN or YOUR name) []:test3ds2.vietcombank.com.vn
```

> b. Tạo file Signing CSR:

![Tạo file Clients](https://user-images.githubusercontent.com/61931560/207808051-484a4ee3-cab1-45b9-bcd8-4078810f19aa.png)
![CSR Info](https://user-images.githubusercontent.com/61931560/207811484-12299df8-9896-4464-8ee5-a4517c61c0df.png)

```notes
// Visa,JCB,AMEX
Country Name (2 letter code) [AU]:VN
State or Province Name (full name) [Some-State]:Hanoi
Locality Name (eg, city) []:Hanoi
Organization Name (eg, company) [Internet Widgits Pty Ltd]:Joint Stock Commercial Bank for Foreign Trade of Vietnam
Organizational Unit Name (eg, section) []:IT Center
Common Name (e.g. server FQDN or YOUR name) []:test3ds2.vietcombank.com.vn

// Master Card
Country Name (2 letter code) [AU]:VN
State or Province Name (full name) [Some-State]:Hanoi
Locality Name (eg, city) []:Hanoi
Organization Name (eg, company) [Internet Widgits Pty Ltd]:Joint Stock Commercial Bank for Foreign Trade of Vietnam
Organizational Unit Name (eg, section) []:ACSMS-MTF-V210-JOINT-STOCK-C0002-48588-SIGNING
Common Name (e.g. server FQDN or YOUR name) []:test3ds2.vietcombank.com.vn
```

## 3. Cài đặt chứng chỉ

> Chứng chỉ nhận được gồm 3 phần SSL, CA, Root. Copy SSL và CA Chia thành 2 file SSl.pem và CA.pem:

![Screenshot_7](https://user-images.githubusercontent.com/61931560/207817841-c73bc2d7-d850-492a-ae99-fe999813dc95.png)

> Tải chứng vừa chia thành 2 phần lên Portal:

> CA Certificate
![Screenshot_8](https://user-images.githubusercontent.com/61931560/207818750-8a566eec-24e8-4291-bf46-3dfa9040f758.png)
> ![Screenshot_10](https://user-images.githubusercontent.com/61931560/207819099-0f76e54b-44bb-4df8-9c5a-c273ae2c0fc5.png)

> SSL Certificate
> ![SSL Certificate](https://user-images.githubusercontent.com/61931560/207818533-d3a6f56d-094a-40c5-854e-dc56b083c987.png)
