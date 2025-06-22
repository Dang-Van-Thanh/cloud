```
FastFoodStore/
│
├── FastFoodStore.Domain/                     # 📦 Tầng Domain: nghiệp vụ cốt lõi
│   ├── Entities/                             # 🧱 Các thực thể (Entity) - ánh xạ DB
│   │   ├── AppUser.cs                        # Người dùng (kế thừa IdentityUser)
│   │   ├── Food.cs                           # Món ăn
│   │   ├── Order.cs                          # Đơn hàng
│   │   ├── OrderItem.cs                      # Món trong đơn hàng
│   │   ├── CartItem.cs                       # Món trong giỏ hàng
│   │   └── Role.cs                           # Role (nếu dùng riêng)
│   │
│   ├── Interfaces/                           # 🔌 Interface cho Repository (không phụ thuộc công nghệ)
│   │   ├── IUserRepository.cs
│   │   ├── IFoodRepository.cs
│   │   └── IOrderRepository.cs
│   │
│   └── ValueObjects/                         # 🔒 Kiểu giá trị đặc biệt (nếu dùng)
│       └── Email.cs                          # Email dưới dạng kiểu riêng (tuỳ chọn)
│
├── FastFoodStore.Application/                # 💼 Tầng Application: xử lý logic nghiệp vụ
│   ├── Interfaces/                           # 🔌 Interface cho Services (kết nối tầng Domain)
│   │   ├── IUserService.cs
│   │   ├── IFoodService.cs
│   │   └── IOrderService.cs
│   │
│   ├── Services/                             # ⚙️ Lớp triển khai nghiệp vụ chính (dùng domain + repo)
│   │   ├── UserService.cs
│   │   ├── FoodService.cs
│   │   └── OrderService.cs
│   │
│   └── ViewModels/                           # 🪞 Dữ liệu truyền giữa Controller ↔ View
│       ├── LoginViewModel.cs
│       ├── RegisterViewModel.cs
│       ├── FoodViewModel.cs
│       ├── OrderViewModel.cs
│       ├── CartViewModel.cs
│       └── UserViewModel.cs
│
├── FastFoodStore.Infrastructure/            # 🏗️ Tầng hạ tầng: EF, DbContext, triển khai Repository
│   ├── Data/
│   │   ├── ApplicationDbContext.cs           # DbContext chính
│   │   └── Migrations/                       # EF Migrations
│   │       ├── ... .cs
│   │
│   ├── Repositories/                         # 💾 Repository pattern triển khai
│   │   ├── UserRepository.cs
│   │   ├── FoodRepository.cs
│   │   └── OrderRepository.cs
│   │
│   └── Identity/                             # 🔐 Cấu hình Identity, xác thực
│       └── IdentitySeeder.cs                 # Seed dữ liệu mặc định (Admin, Role)
│
├── FastFoodStore.WebUI/                      # 🌐 Tầng giao diện ASP.NET MVC (Presentation Layer)
│   ├── Areas/
│   │   └── Admin/
│   │       ├── Controllers/
│   │       │   ├── HomeController.cs
│   │       │   ├── AppUsersController.cs
│   │       │   ├── FoodsController.cs
│   │       │   └── OrdersController.cs
│   │       │
│   │       └── Views/
│   │           ├── Home/Index.cshtml
│   │           ├── AppUsers/
│   │           ├── Foods/
│   │           └── Orders/
│   │
│   ├── Controllers/
│   │   ├── HomeController.cs
│   │   ├── AccountController.cs
│   │   ├── FoodsController.cs
│   │   ├── OrdersController.cs
│   │   └── CartController.cs
│   │
│   ├── Views/
│   │   ├── Shared/                           # Layout chung
│   │   ├── Home/
│   │   ├── Account/
│   │   ├── Foods/
│   │   ├── Orders/
│   │   └── Cart/
│   │
│   ├── wwwroot/                              # 📁 Tệp tĩnh (CSS, JS, ảnh)
│   │   ├── css/
│   │   ├── js/
│   │   └── images/
│   │
│   ├── appsettings.json
│   ├── Program.cs
│   └── FastFoodStore.WebUI.csproj
│
├── FastFoodStore.sln                         # 🔧 Solution file liên kết tất cả project
└── README.md                                 # 📘 Hướng dẫn sử dụng dự án

```
```
FastFoodStore/
│
├── Areas/
│   └── Admin/
│       ├── Controllers/
│       │   ├── HomeController.cs            # Admin dashboard
│       │   ├── AppUsersController.cs        # Quản lý người dùng
│       │   ├── FoodsController.cs           # Quản lý món ăn
│       │   └── OrdersController.cs          # Quản lý đơn hàng
│       │
│       ├── Views/
│       │   ├── Home/
│       │   │   └── Index.cshtml             # Trang dashboard admin
│       │   ├── AppUsers/
│       │   │   ├── Index.cshtml             # Danh sách user admin
│       │   │   ├── Create.cshtml
│       │   │   ├── Edit.cshtml
│       │   │   └── Details.cshtml
│       │   ├── Foods/
│       │   │   ├── Index.cshtml             # Danh sách món ăn admin
│       │   │   ├── Create.cshtml
│       │   │   ├── Edit.cshtml
│       │   │   └── Details.cshtml
│       │   └── Orders/
│       │       ├── Index.cshtml             # Danh sách đơn hàng admin
│       │       └── Details.cshtml
│       │
│       └── AdminAreaRegistration.cs        # (chỉ với ASP.NET MVC, không cần .NET Core)
│
├── Controllers/
│   ├── HomeController.cs                    # Trang chủ user
│   ├── AccountController.cs                 # Đăng nhập, đăng ký, profile user
│   ├── FoodsController.cs                    # Danh sách món ăn, chi tiết món ăn user
│   ├── OrdersController.cs                   # Tạo đơn hàng, danh sách đơn user
│   └── CartController.cs                     # Quản lý giỏ hàng user
│
├── Models/
│   ├── AppUser.cs                           # Mở rộng IdentityUser
│   ├── Food.cs                             # Model món ăn
│   ├── Order.cs                            # Model đơn hàng
│   ├── OrderItem.cs                        # Chi tiết món trong đơn hàng
│   ├── LoginViewModel.cs                    # ViewModel đăng nhập
│   ├── RegisterViewModel.cs                 # ViewModel đăng ký
│   ├── Role.cs                            # (nếu có dùng riêng Role)
│   └── CartItem.cs                         # Model giỏ hàng (nếu lưu tạm thời)
│
├── Data/
│   ├── ApplicationDbContext.cs              # DbContext định nghĩa DbSet
│   └── Migrations/
│       ├── 20230618094512_InitialCreate.cs
│       ├── 20230618094512_InitialCreate.Designer.cs
│       └── ApplicationDbContextModelSnapshot.cs
│
├── Services/
│   ├── Interfaces/
│   │   ├── IUserService.cs
│   │   ├── IFoodService.cs
│   │   └── IOrderService.cs
│   ├── UserService.cs
│   ├── FoodService.cs
│   └── OrderService.cs
│
├── ViewModels/
│   ├── FoodViewModel.cs
│   ├── OrderViewModel.cs
│   ├── UserViewModel.cs
│   ├── AdminDashboardViewModel.cs
│   └── CartViewModel.cs
│
├── Views/
│   ├── Shared/
│   │   ├── _Layout.cshtml                  # Layout chung (header, footer, nav)
│   │   ├── _ValidationScriptsPartial.cshtml
│   │   └── Error.cshtml
│   │
│   ├── Home/
│   │   ├── Index.cshtml                    # Trang chủ user
│   │   ├── About.cshtml                    # Giới thiệu
│   │   └── Contact.cshtml                  # Liên hệ
│   │
│   ├── Account/
│   │   ├── Login.cshtml                    # Đăng nhập
│   │   ├── Register.cshtml                 # Đăng ký
│   │   ├── ForgotPassword.cshtml           # Quên mật khẩu
│   │   ├── ResetPassword.cshtml            # Đặt lại mật khẩu
│   │   └── Profile.cshtml                  # Quản lý tài khoản cá nhân
│   │
│   ├── Foods/
│   │   ├── Index.cshtml                    # Danh sách món ăn user
│   │   ├── Details.cshtml                  # Chi tiết món ăn
│   │   └── SearchResults.cshtml            # Kết quả tìm kiếm món ăn
│   │
│   ├── Orders/
│   │   ├── Index.cshtml                    # Danh sách đơn hàng user
│   │   ├── Details.cshtml                  # Chi tiết đơn hàng
│   │   ├── Create.cshtml                   # Tạo đơn hàng
│   │   ├── Checkout.cshtml                 # Thanh toán
│   │   └── OrderConfirmation.cshtml        # Xác nhận đơn hàng thành công
│   │
│   ├── Cart/
│   │   ├── Index.cshtml                    # Giỏ hàng
│   │   └── Update.cshtml                   # Cập nhật giỏ hàng
│   │
│   └── Error/
│       └── AccessDenied.cshtml             # Trang không có quyền truy cập
│
├── wwwroot/
│   ├── css/
│   │   ├── site.css
│   │   └── bootstrap.min.css
│   ├── js/
│   │   ├── site.js
│   │   └── bootstrap.bundle.min.js
│   ├── images/
│   │   └── logo.png
│   └── lib/
│       ├── jquery/
│       │   └── jquery.min.js
│       └── bootstrap/
│           ├── css/
│           │   └── bootstrap.min.css
│           └── js/
│               └── bootstrap.bundle.min.js
│
├── Properties/
│   └── launchSettings.json
│
├── appsettings.json
├── appsettings.Development.json
├── Program.cs
├── Startup.cs      # nếu dùng .NET 5 hoặc thấp hơn
├── FastFoodStore.csproj
└── README.md
```
