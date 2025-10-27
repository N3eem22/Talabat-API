# 🍔 Talabat API

This project is a backend implementation for a **Talabat-style food delivery system**, built using **.NET Core Web API**.  
It provides APIs for products, brands, delivery options, and other e-commerce related functionalities.

---

## 📁 Project Structure

```
D:\Talabat\Talabat-API
│
├── Talabat.Repository
│   └── Data
│       └── DataSeed
│           ├── brands.json
│           ├── delivery.json
│           ├── products.json
│           └── types.json
│
└── TalabatAPIs
    ├── Properties
    │   └── launchSettings.json
    ├── appsettings.json
    └── appsettings.Development.json
```

---

## 📦 Data Seed Files

These files are used to populate initial data into the database during development or testing.

### 🏪 **brands.json**
Contains a list of product brands available in the system.

```json
[
  { "Name": "Starbucks" },
  { "Name": "Costa" },
  { "Name": "Cilantro" },
  { "Name": "TBS" },
  { "Name": "On The Run" },
  { "Name": "Caribou" },
  { "Name": "Krispy Kreme" }
]
```

---

### 🚚 **delivery.json**
Defines available delivery options.

```json
[
  {
    "ShortName": "UPS1",
    "Description": "Fastest delivery time",
    "DeliveryTime": "1-2 Days",
    "Cost": 10
  },
  {
    "ShortName": "UPS2",
    "Description": "Get it within 5 days",
    "DeliveryTime": "2-5 Days",
    "Cost": 5
  },
  {
    "ShortName": "UPS3",
    "Description": "Slower but cheap",
    "DeliveryTime": "5-10 Days",
    "Cost": 2
  },
  {
    "ShortName": "FREE",
    "Description": "Free! You get what you pay for",
    "DeliveryTime": "1-2 Weeks",
    "Cost": 0
  }
]
```

---

### ☕ **products.json**
Lists all products with descriptions, prices, and relationships to their brand and type.

Each product includes:
- `Name`
- `Description`
- `Price`
- `PictureUrl`
- `ProductTypeId`
- `ProductBrandId`

Example:
```json
{
  "Name": "Double Caramel Frappuccino",
  "Description": "Lorem ipsum dolor sit amet...",
  "Price": 200,
  "PictureUrl": "images/products/sb-ang1.png",
  "ProductTypeId": 1,
  "ProductBrandId": 1
}
```

---

### 🍩 **types.json**
Defines the categories or types of products.

```json
[
  { "Name": "Frappuccino" },
  { "Name": "Latte" },
  { "Name": "Mocha" },
  { "Name": "Macchiato" },
  { "Name": "Matcha" },
  { "Name": "Cake" },
  { "Name": "Donuts" },
  { "Name": "Salad" }
]
```

---

## ⚙️ Configuration

### **appsettings.json**
Main configuration file for:
- Logging
- Database connections
- JWT Authentication
- Stripe integration

```json
"ConnectionStrings": {
  "DefaultConnection": "Server = .; DataBase = TalabatDb; trusted_Connection = true; MultipleActiveResultSets= true",
  "IdentityConnection": "Server = .; DataBase = IdentityTalabatDb; trusted_Connection = true; MultipleActiveResultSets= true",
  "RedisConnection": "localhost"
},
"JWT": {
  "Key": "Fdh9u8rINxfivbrianbbVT1u232VQBZYKx1HGAGPt2I",
  "Issuer": "https://localhost:7095/",
  "Audience": "EncryptedKey",
  "DurationInDays": "2"
},
"StripeKeys": {
  "Publishablekey": "YOUR_STRIPE_PUBLISHABLE_KEY_HERE",
  "Secretkey": "YOUR_STRIPE_SECRET_KEY_HERE"
}
```

---

### **launchSettings.json**
Defines local development environment settings and URLs.

- **Application URLs:**
  - HTTPS: `https://localhost:7095`
  - HTTP: `http://localhost:5095`
- **Launch URL:** `/swagger` (opens Swagger UI by default)
- **Environment:** Development

---

### **appsettings.Development.json**
Overrides base settings during development (e.g., logging configuration).

---

## 🚀 How to Run

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/Talabat-API.git
   cd Talabat-API
   ```

2. **Restore dependencies:**
   ```bash
   dotnet restore
   ```

3. **Apply migrations and seed data:**
   ```bash
   dotnet ef database update
   ```

4. **Run the API:**
   ```bash
   dotnet run --project TalabatAPIs
   ```

5. **Open Swagger UI:**
   ```
   https://localhost:7095/swagger
   ```

---

## 🔐 Authentication

This API uses **JWT (JSON Web Token)** for secure authentication and authorization.  
Make sure the `JWT` key and `Issuer` are correctly configured in your `appsettings.json`.

---

## 💳 Payment Integration

The system supports **Stripe** for online payments.  
To enable it:
- Replace `YOUR_STRIPE_PUBLISHABLE_KEY_HERE` and `YOUR_STRIPE_SECRET_KEY_HERE` in `appsettings.json` with your actual Stripe API keys.

---

## 🧠 Technologies Used

- **.NET Core Web API**
- **Entity Framework Core**
- **SQL Server**
- **Redis Cache**
- **JWT Authentication**
- **Stripe API**
- **Swagger / OpenAPI**

---
