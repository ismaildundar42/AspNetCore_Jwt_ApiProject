# 🔐 ASP.NET Core JWT Auth API

Bu repo, **ASP.NET Core 8.0 + MSSQL** ile geliştirilmiş modern bir **JWT kimlik doğrulama API’si** içerir.  
Kullanıcılar **kayıt olabilir, giriş yapabilir, token alıp Postman ile test edebilir.** 🚀

---

## ✨ Özellikler
- 📝 **Register / Login**  
- 🔑 **JWT Access & Refresh Token**  
- 👤 **Korumalı kullanıcı bilgileri (/me)**  
- 🛡️ **Rol tabanlı yetkilendirme**  
- 🗄️ **EF Core + MSSQL**  
- 📑 **Swagger/OpenAPI** (dev)  
- 🧪 **Postman Collection** desteği  

---

## ⚡ Kurulum
```bash
git clone https://github.com/<user>/<repo>.git
cd <repo>
dotnet restore
dotnet ef database update
dotnet run

API: https://localhost:5001
Swagger: /swagger
DB: MSSQL (LocalDB veya SQL Server)

🚦 Endpoint’ler
POST /api/auth/register → yeni kullanıcı
POST /api/auth/login → access + refresh token
POST /api/auth/refresh → token yenile
POST /api/auth/logout → çıkış
GET /api/users/me → korumalı profil

🧪 Postman Test
Postman’e import et → Swagger veya Postman Collection
Register → kullanıcı oluştur
Login → Access Token al
Header’a ekle:Authorization: Bearer <ACCESS_TOKEN>
/me çağır → korumalı içerik ✔️

📌 Notlar
appsettings.json içindeki JWT SigningKey en az 32 karakter olmalı.
Prod ortamında User Secrets veya ENV değişkenleri ile saklayın.
