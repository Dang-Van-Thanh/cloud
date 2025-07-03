```
FastFoodStoreOnline/
│
├── Areas/
│   └── Admin/
│       ├── Controllers/
│       │   ├── DashboardController.cs
│       │   ├── FoodController.cs
│       │   ├── OrderController.cs
│       │   └── UserController.cs
│       ├── Views/
│       │   ├── Dashboard/
│       │   │   └── Index.cshtml
│       │   ├── Food/
│       │   │   ├── Index.cshtml
│       │   │   ├── Create.cshtml
│       │   │   ├── Edit.cshtml
│       │   │   └── Delete.cshtml
│       │   ├── Order/
│       │   │   ├── Index.cshtml
│       │   │   └── Details.cshtml
│       │   └── User/
│       │       ├── Index.cshtml
│       │       └── Edit.cshtml
│       └── ViewModels/
│           ├── FoodVM.cs
│           ├── OrderVM.cs
│           └── UserVM.cs
│
├── Controllers/
│   ├── HomeController.cs
│   ├── MenuController.cs
│   ├── CartController.cs
│   ├── CheckoutController.cs
│   └── AccountController.cs       <-- xử lý đăng nhập/đăng ký/thông tin cá nhân
│
├── Views/
│   ├── Home/
│   │   └── Index.cshtml
│   ├── Menu/
│   │   ├── Index.cshtml
│   │   └── Details.cshtml
│   ├── Cart/
│   │   └── Index.cshtml
│   ├── Checkout/
│   │   ├── Index.cshtml
│   │   └── Success.cshtml
│   └── Account/
│       ├── Login.cshtml           <-- giao diện đăng nhập
│       ├── Register.cshtml        <-- giao diện đăng ký
│       └── Profile.cshtml         <-- thông tin cá nhân (cập nhật tên, địa chỉ, email...)
│
├── Models/
│   ├── Food.cs
│   ├── Category.cs
│   ├── Order.cs
│   ├── OrderDetail.cs
│   ├── ShoppingCartItem.cs
│   └── ApplicationUser.cs
│
├── Services/
│   ├── IFoodService.cs
│   ├── FoodService.cs
│   ├── IOrderService.cs
│   ├── OrderService.cs
│   ├── IUserService.cs
│   └── UserService.cs
│
├── Data/
│   ├── ApplicationDbContext.cs
│   └── DbInitializer.cs
│
├── ViewModels/
│   ├── ShoppingCartVM.cs
│   ├── CheckoutVM.cs
│   ├── MenuItemVM.cs
│   ├── LoginViewModel.cs         <-- xử lý đăng nhập
│   ├── RegisterViewModel.cs      <-- xử lý đăng ký
│   └── ProfileViewModel.cs       <-- thông tin cá nhân
│
├── Utilities/
│   ├── Constants.cs
│   └── SD.cs
│
├── wwwroot/
│   ├── admin/
│   │   ├── css/
│   │   ├── js/
│   │   └── img/
│   ├── css/
│   ├── js/
│   └── images/
│       ├── foods/
│       └── banners/
│
├── Migrations/
│
├── appsettings.json
└── Program.cs
```
```
FastFoodStoreOnline/
│
├── Areas/
│   └── Admin/
│       ├── Controllers/
│       │   ├── DashboardController.cs
│       │   ├── FoodController.cs
│       │   ├── OrderController.cs
│       │   └── UserController.cs
│       ├── Views/
│       │   ├── Dashboard/
│       │   │   └── Index.cshtml
│       │   ├── Food/
│       │   │   ├── Index.cshtml
│       │   │   ├── Create.cshtml
│       │   │   ├── Edit.cshtml
│       │   │   └── Delete.cshtml
│       │   ├── Order/
│       │   │   ├── Index.cshtml
│       │   │   └── Details.cshtml
│       │   └── User/
│       │       ├── Index.cshtml
│       │       └── Edit.cshtml
│       └── ViewModels/
│           ├── FoodVM.cs
│           ├── OrderVM.cs
│           └── UserVM.cs
│
├── Controllers/
│   ├── HomeController.cs
│   ├── MenuController.cs
│   ├── CartController.cs
│   ├── CheckoutController.cs
│   └── AccountController.cs
│
├── Models/
│   ├── Food.cs
│   ├── Category.cs
│   ├── Order.cs
│   ├── OrderDetail.cs
│   ├── ShoppingCartItem.cs
│   └── ApplicationUser.cs
│
├── Services/
│   ├── IFoodService.cs
│   ├── FoodService.cs
│   ├── IOrderService.cs
│   ├── OrderService.cs
│   ├── IUserService.cs
│   └── UserService.cs
│
├── Data/
│   ├── ApplicationDbContext.cs
│   └── DbInitializer.cs
│
├── ViewModels/
│   ├── ShoppingCartVM.cs
│   ├── CheckoutVM.cs
│   └── MenuItemVM.cs
│
├── Utilities/
│   ├── Constants.cs
│   └── SD.cs  // Static Details
│
├── wwwroot/
│   ├── admin/
│   │   ├── css/
│   │   ├── js/
│   │   └── img/
│   ├── css/
│   ├── js/
│   └── images/
│       ├── foods/
│       └── banners/
│
├── Migrations/
│
├── appsettings.json
└── Program.cs
```
```
FastFoodStoreOnline/
│
├── Areas/
│   └── Admin/
│       ├── Controllers/
│       │   ├── HomeController.cs
│       │   ├── AppUsersController.cs
│       │   ├── FoodsController.cs
│       │   ├── OrdersController.cs
│       │   ├── CategoriesController.cs
│       │   ├── StatisticsController.cs
│       │   ├── PromotionsController.cs
│       │   ├── InventoryController.cs
│       │   └── CombosController.cs
│       │
│       ├── Views/
│       │   ├── Shared/
│       │   │   ├── _Layout.cshtml
│       │   │   └── _AdminSidebar.cshtml
│       │   ├── Home/
│       │   │   └── Index.cshtml
│       │   ├── Promotions/
│       │   │   ├── Index.cshtml
│       │   │   ├── Create.cshtml
│       │   │   ├── Edit.cshtml
│       │   │   └── Details.cshtml
│       │   ├── Inventory/
│       │   │   ├── Index.cshtml
│       │   │   └── StockReport.cshtml
│       │   └── Combos/
│       │       ├── Index.cshtml
│       │       ├── Create.cshtml
│       │       ├── Edit.cshtml
│       │       └── Details.cshtml
│       │
│       ├── Services/
│       │   ├── AdminFoodService.cs
│       │   ├── AdminOrderService.cs
│       │   ├── AdminPromotionService.cs
│       │   └── AdminComboService.cs
│       │
│       └── ViewModels/
│           ├── AdminFoodVM.cs
│           ├── AdminOrderVM.cs
│           ├── DashboardVM.cs
│           ├── PromotionVM.cs
│           ├── InventoryReportVM.cs
│           └── ComboVM.cs
│
├── Controllers/
│   ├── HomeController.cs
│   ├── AccountController.cs
│   ├── FoodsController.cs
│   ├── OrdersController.cs
│   ├── CartController.cs
│   ├── CategoriesController.cs
│   ├── CheckoutController.cs
│   ├── ReviewsController.cs
│   └── PromotionsController.cs
│
├── Models/
│   ├── Identity/
│   │   ├── ApplicationUser.cs
│   │   └── ApplicationRole.cs
│   ├── Food.cs
│   ├── Category.cs
│   ├── Order.cs
│   ├── OrderItem.cs
│   ├── CartItem.cs
│   ├── Address.cs
│   ├── PaymentInfo.cs
│   ├── Review.cs
│   ├── Promotion.cs
│   ├── Inventory.cs
│   ├── Combo.cs
│   ├── ComboItem.cs
│   │
│   ├── ViewModels/
│   │   ├── Account/
│   │   │   ├── LoginViewModel.cs
│   │   │   ├── RegisterViewModel.cs
│   │   │   └── ProfileViewModel.cs
│   │   ├── Shopping/
│   │   │   ├── CartViewModel.cs
│   │   │   ├── CheckoutViewModel.cs
│   │   │   └── OrderConfirmationViewModel.cs
│   │   ├── ReviewViewModel.cs
│   │   ├── ApplyCouponViewModel.cs
│   │   └── ComboViewModel.cs
│   │
│   └── Enums/
│       ├── OrderStatus.cs
│       ├── PaymentMethod.cs
│       ├── FoodSize.cs
│       ├── PromotionType.cs
│       └── InventoryStatus.cs
│
├── Services/
│   ├── Interfaces/
│   │   ├── IUserService.cs
│   │   ├── IFoodService.cs
│   │   ├── IOrderService.cs
│   │   ├── ICartService.cs
│   │   ├── ICategoryService.cs
│   │   ├── IPaymentService.cs
│   │   ├── IEmailService.cs
│   │   ├── IReviewService.cs
│   │   ├── IPromotionService.cs
│   │   ├── IInventoryService.cs
│   │   └── IComboService.cs
│   │
│   ├── Implementations/
│   │   ├── UserService.cs
│   │   ├── FoodService.cs
│   │   ├── OrderService.cs
│   │   ├── CartService.cs
│   │   ├── CategoryService.cs
│   │   ├── PaymentService.cs
│   │   ├── EmailService.cs
│   │   ├── ReviewService.cs
│   │   ├── PromotionService.cs
│   │   ├── InventoryService.cs
│   │   └── ComboService.cs
│   │
│   ├── Repositories/
│   │   ├── Base/
│   │   │   └── IRepository.cs
│   │   ├── FoodRepository.cs
│   │   ├── OrderRepository.cs
│   │   ├── UserRepository.cs
│   │   ├── ReviewRepository.cs
│   │   ├── PromotionRepository.cs
│   │   └── InventoryRepository.cs
│   │
│   └── Helpers/
│       ├── ImageUploader.cs
│       ├── PaymentGatewayHelper.cs
│       ├── ClaimsPrincipalExtensions.cs
│       └── PromotionCalculator.cs
│
├── Data/
│   ├── ApplicationDbContext.cs
│   ├── DbInitializer.cs
│   ├── Migrations/
│   └── SeedData/
│       ├── AdminUserSeeder.cs
│       ├── CategorySeeder.cs
│       ├── FoodSeeder.cs
│       ├── PromotionSeeder.cs
│       └── ComboSeeder.cs
│
├── Views/
│   ├── Shared/
│   │   ├── _Layout.cshtml
│   │   ├── _Navbar.cshtml
│   │   ├── _Footer.cshtml
│   │   ├── _LoginPartial.cshtml
│   │   ├── _ValidationScriptsPartial.cshtml
│   │   ├── Error.cshtml
│   │   ├── NotFound.cshtml
│   │   └── ServerError.cshtml
│   │
│   ├── Home/
│   │   ├── Index.cshtml
│   │   ├── About.cshtml
│   │   └── Contact.cshtml
│   │
│   ├── Account/
│   │   ├── Login.cshtml
│   │   ├── Register.cshtml
│   │   ├── ForgotPassword.cshtml
│   │   ├── ResetPassword.cshtml
│   │   ├── Profile.cshtml
│   │   └── ChangePassword.cshtml
│   │
│   ├── Foods/
│   │   ├── Index.cshtml
│   │   ├── Details.cshtml
│   │   ├── SearchResults.cshtml
│   │   ├── ByCategory.cshtml
│   │   ├── _ReviewsPartial.cshtml
│   │   └── AddReviewModal.cshtml
│   │
│   ├── Orders/
│   │   ├── Index.cshtml
│   │   ├── Details.cshtml
│   │   ├── Create.cshtml
│   │   ├── Checkout.cshtml
│   │   ├── OrderConfirmation.cshtml
│   │   └── Tracking.cshtml
│   │
│   ├── Cart/
│   │   ├── Index.cshtml
│   │   ├── AddToCart.cshtml
│   │   └── MiniCart.cshtml
│   │
│   ├── Categories/
│   │   └── Index.cshtml
│   │
│   ├── Promotions/
│   │   ├── Index.cshtml
│   │   └── ApplyCoupon.cshtml
│   │
│   ├── Combos/
│   │   ├── Index.cshtml
│   │   └── Details.cshtml
│   │
│   └── Error/
│       └── AccessDenied.cshtml
│
├── wwwroot/
│   ├── css/
│   │   ├── site.css
│   │   ├── admin.css
│   │   ├── shopping.css
│   │   └── responsive.css
│   ├── js/
│   │   ├── site.js
│   │   ├── cart.js
│   │   ├── checkout.js
│   │   ├── food-filter.js
│   │   ├── review.js
│   │   └── coupon.js
│   ├── images/
│   │   ├── logo.png
│   │   ├── foods/
│   │   ├── banners/
│   │   └── payments/
│   ├── lib/
│   │   ├── jquery/
│   │   ├── bootstrap/
│   │   ├── font-awesome/
│   │   └── toastr/
│   └── uploads/
│       ├── foods/
│       ├── combos/
│       └── users/
│
├── Properties/
│   └── launchSettings.json
│
├── Configurations/
│   ├── AppSettings.cs
│   ├── EmailSettings.cs
│   ├── PaymentSettings.cs
│   └── PromotionSettings.cs
│
├── Utilities/
│   ├── Exceptions/
│   │   ├── AppException.cs
│   │   └── NotFoundException.cs
│   ├── Extensions/
│   │   ├── ClaimsPrincipalExtensions.cs
│   │   └── StringExtensions.cs
│   └── Formatters/
│       └── CurrencyFormatter.cs
│
├── appsettings.json
├── appsettings.Development.json
├── Program.cs
├── FastFoodStoreOnline.csproj
├── GlobalUsings.cs
├── README.md
└── .gitignore
```
```
FastFoodShop/
│
├── Areas/
│   └── Admin/
│       ├── Controllers/
│       │   ├── HomeController.cs            # Dashboard Admin
│       │   ├── AppUsersController.cs        # Quản lý người dùng
│       │   ├── FoodsController.cs           # Quản lý món ăn
│       │   └── OrdersController.cs          # Quản lý đơn hàng
│       │
│       ├── Views/
│       │   ├── Shared/
│       │   │   └── _Layout.cshtml           # Layout riêng cho Admin
│       │   ├── Home/
│       │   │   └── Index.cshtml             # Trang Dashboard
│       │   ├── AppUsers/
│       │   │   ├── Index.cshtml
│       │   │   ├── Create.cshtml
│       │   │   ├── Edit.cshtml
│       │   │   └── Details.cshtml
│       │   ├── Foods/
│       │   │   ├── Index.cshtml
│       │   │   ├── Create.cshtml
│       │   │   ├── Edit.cshtml
│       │   │   └── Details.cshtml
│       │   └── Orders/
│       │       ├── Index.cshtml
│       │       └── Details.cshtml
│
├── Controllers/
│   ├── HomeController.cs                    # Trang chủ người dùng
│   ├── AccountController.cs                 # Đăng nhập, đăng ký, hồ sơ cá nhân
│   ├── FoodsController.cs                   # Xem danh sách và chi tiết món ăn
│   ├── OrdersController.cs                  # Tạo và xem đơn hàng người dùng
│   └── CartController.cs                    # Giỏ hàng
│
├── Models/
│   ├── AppUser.cs                           # Mở rộng từ IdentityUser
│   ├── Food.cs
│   ├── Order.cs
│   ├── OrderItem.cs
│   ├── CartItem.cs
│   ├── LoginViewModel.cs
│   ├── RegisterViewModel.cs
│   └── Role.cs                              # Nếu quản lý role riêng
│
├── ViewModels/
│   ├── FoodViewModel.cs
│   ├── OrderViewModel.cs
│   ├── CartViewModel.cs
│   ├── UserViewModel.cs
│   └── AdminDashboardViewModel.cs
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
├── Data/
│   ├── ApplicationDbContext.cs              # DbContext chính
│   └── Migrations/
│       ├── 20230618094512_InitialCreate.cs
│       ├── 20230618094512_InitialCreate.Designer.cs
│       └── ApplicationDbContextModelSnapshot.cs
│
├── Views/
│   ├── Shared/
│   │   ├── _Layout.cshtml                  # Layout chính cho user
│   │   ├── _LoginPartial.cshtml            # Hiển thị khi đã đăng nhập
│   │   ├── _ValidationScriptsPartial.cshtml
│   │   ├── Error.cshtml
│   │   ├── NotFound.cshtml                 # Lỗi 404
│   │   └── ServerError.cshtml              # Lỗi 500
│   │
│   ├── Home/
│   │   ├── Index.cshtml
│   │   ├── About.cshtml
│   │   └── Contact.cshtml
│   │
│   ├── Account/
│   │   ├── Login.cshtml
│   │   ├── Register.cshtml
│   │   ├── ForgotPassword.cshtml
│   │   ├── ResetPassword.cshtml
│   │   └── Profile.cshtml
│   │
│   ├── Foods/
│   │   ├── Index.cshtml
│   │   ├── Details.cshtml
│   │   └── SearchResults.cshtml
│   │
│   ├── Orders/
│   │   ├── Index.cshtml
│   │   ├── Details.cshtml
│   │   ├── Create.cshtml
│   │   ├── Checkout.cshtml
│   │   └── OrderConfirmation.cshtml
│   │
│   ├── Cart/
│   │   ├── Index.cshtml
│   │   └── Update.cshtml
│   │
│   └── Error/
│       └── AccessDenied.cshtml
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
├── FastFoodShop.csproj
├── Startup.cs                     # (nếu dùng .NET 5 hoặc thấp hơn)
└── README.md

```
```
# 📁 Tạo thư mục gốc
mkdir FastFoodStore
cd FastFoodStore

# 🧱 Tạo solution file (.sln)
dotnet new sln -n FastFoodStore

# 📦 Tạo các dự án con
dotnet new classlib -n FastFoodStore.Domain
dotnet new classlib -n FastFoodStore.Application
dotnet new classlib -n FastFoodStore.Infrastructure
dotnet new mvc      -n FastFoodStore.WebUI

# Thêm dự án vào solution
dotnet sln add FastFoodStore.Domain/FastFoodStore.Domain.csproj
dotnet sln add FastFoodStore.Application/FastFoodStore.Application.csproj
dotnet sln add FastFoodStore.Infrastructure/FastFoodStore.Infrastructure.csproj
dotnet sln add FastFoodStore.WebUI/FastFoodStore.WebUI.csproj

# Thêm tham chiếu giữa các dự án (project reference)
# Application cần dùng Domain
dotnet add FastFoodStore.Application/FastFoodStore.Application.csproj reference FastFoodStore.Domain/FastFoodStore.Domain.csproj

# Infrastructure cần dùng Domain
dotnet add FastFoodStore.Infrastructure/FastFoodStore.Infrastructure.csproj reference FastFoodStore.Domain/FastFoodStore.Domain.csproj

# WebUI cần dùng cả 3 lớp còn lại
dotnet add FastFoodStore.WebUI/FastFoodStore.WebUI.csproj reference FastFoodStore.Application/FastFoodStore.Application.csproj
dotnet add FastFoodStore.WebUI/FastFoodStore.WebUI.csproj reference FastFoodStore.Domain/FastFoodStore.Domain.csproj
dotnet add FastFoodStore.WebUI/FastFoodStore.WebUI.csproj reference FastFoodStore.Infrastructure/FastFoodStore.Infrastructure.csproj

# Chạy thử ứng dụng
cd FastFoodStore.WebUI
dotnet run

# Cài gói EF (thực hiện một lần):
dotnet add FastFoodStore.Infrastructure package Microsoft.EntityFrameworkCore.SqlServer
dotnet add FastFoodStore.Infrastructure package Microsoft.EntityFrameworkCore.Design

# Tạo migration & cập nhật DB:
# Từ thư mục Infrastructure
dotnet ef migrations add InitialCreate --project FastFoodStore.Infrastructure \
                                       --startup-project ../FastFoodStore.WebUI
dotnet ef database update --project FastFoodStore.Infrastructure \
                           --startup-project ../FastFoodStore.WebUI
# Cập nhật DB(nếu cần)
dotnet ef database update
```
```
FastFoodStore/
│
├── FastFoodStore.Domain/                     # 📦 Tầng Domain: nghiệp vụ cốt lõi
│   ├── Entities/                             # 🧱 Các thực thể (Entity) - ánh xạ DB
│   │   ├── AppUser.cs                        # Người dùng (kế thừa IdentityUser)
│   │   ├── Food.cs                           # Món ăn
│   │   ├── Order.cs                          # Đơn hàng
│   │   ├── OrderItem.cs                      # Chi tiết món trong đơn
│   │   ├── CartItem.cs                       # Món trong giỏ hàng tạm thời
│   │   └── Role.cs                           # Role người dùng (nếu quản lý riêng)
│   ├── Interfaces/                           # 🔌 Các interface Repository tương ứng Entity
│   │   ├── IUserRepository.cs                # Interface cho thao tác người dùng
│   │   ├── IFoodRepository.cs                # Interface cho thao tác món ăn
│   │   └── IOrderRepository.cs               # Interface cho thao tác đơn hàng
│   └── ValueObjects/                         # 🔒 Các kiểu giá trị bất biến, validate riêng
│       └── Email.cs                          # Kiểu Email hợp lệ (tuỳ chọn mở rộng)
│
├── FastFoodStore.Application/                # 💼 Tầng Application: xử lý logic nghiệp vụ
│   ├── Interfaces/                           # 🔌 Các interface service gọi từ controller
│   │   ├── IUserService.cs                   # Định nghĩa chức năng người dùng
│   │   ├── IFoodService.cs                   # Định nghĩa chức năng món ăn
│   │   └── IOrderService.cs                  # Định nghĩa chức năng đơn hàng
│   ├── Services/                             # ⚙️ Các lớp hiện thực interface service
│   │   ├── UserService.cs                    # Xử lý người dùng, đăng ký, đăng nhập
│   │   ├── FoodService.cs                    # Xử lý CRUD món ăn
│   │   └── OrderService.cs                   # Xử lý tạo và quản lý đơn hàng
│   └── ViewModels/                           # 🪞 Lớp mô hình hiển thị dữ liệu cho View
│       ├── LoginViewModel.cs                 # Thông tin đăng nhập
│       ├── RegisterViewModel.cs              # Thông tin đăng ký
│       ├── FoodViewModel.cs                  # Hiển thị thông tin món ăn
│       ├── OrderViewModel.cs                 # Hiển thị đơn hàng và chi tiết
│       ├── CartViewModel.cs                  # Hiển thị giỏ hàng người dùng
│       └── UserViewModel.cs                  # Thông tin người dùng hiển thị admin/user
│
├── FastFoodStore.Infrastructure/            # 🏗️ Tầng hạ tầng: triển khai kỹ thuật cụ thể
│   ├── Data/
│   │   ├── ApplicationDbContext.cs           # DbContext chứa DbSet<Entity>
│   │   └── Migrations/                       # 📜 EF Core migration
│   │       ├── 20230618094512_InitialCreate.cs
│   │       ├── 20230618094512_InitialCreate.Designer.cs
│   │       └── ApplicationDbContextModelSnapshot.cs
│   ├── Repositories/                         # 💾 Triển khai interface Repository
│   │   ├── UserRepository.cs
│   │   ├── FoodRepository.cs
│   │   └── OrderRepository.cs
│   └── Identity/
│       └── IdentitySeeder.cs                 # Seed tài khoản Admin, phân quyền
│
├── FastFoodStore.WebUI/                      # 🌐 Tầng trình bày (ASP.NET Core MVC)
│   ├── Areas/
│   │   └── Admin/                            # Khu vực quản trị
│   │       ├── Controllers/
│   │       │   ├── HomeController.cs         # Trang dashboard admin
│   │       │   ├── AppUsersController.cs     # Quản lý người dùng
│   │       │   ├── FoodsController.cs        # Quản lý món ăn
│   │       │   └── OrdersController.cs       # Quản lý đơn hàng
│   │       └── Views/
│   │           ├── Home/
│   │           │   └── Index.cshtml          # Trang tổng quan admin
│   │           ├── AppUsers/
│   │           │   ├── Index.cshtml          # Danh sách người dùng
│   │           │   ├── Create.cshtml         # Thêm người dùng
│   │           │   ├── Edit.cshtml           # Chỉnh sửa người dùng
│   │           │   └── Details.cshtml        # Thông tin chi tiết
│   │           ├── Foods/
│   │           │   ├── Index.cshtml          # Danh sách món ăn
│   │           │   ├── Create.cshtml         # Thêm món ăn
│   │           │   ├── Edit.cshtml           # Chỉnh sửa món ăn
│   │           │   └── Details.cshtml        # Xem chi tiết món ăn
│   │           └── Orders/
│   │               ├── Index.cshtml          # Danh sách đơn hàng
│   │               └── Details.cshtml        # Chi tiết đơn hàng
│   ├── Controllers/
│   │   ├── HomeController.cs                 # Trang chủ user
│   │   ├── AccountController.cs              # Đăng nhập, đăng ký, tài khoản user
│   │   ├── FoodsController.cs                # Hiển thị danh sách món ăn cho user
│   │   ├── OrdersController.cs               # Đặt và xem đơn hàng
│   │   └── CartController.cs                 # Giỏ hàng
│   ├── Views/
│   │   ├── Shared/                           # Layout và các phần dùng chung
│   │   │   ├── _Layout.cshtml                # Giao diện tổng thể (menu, header, footer)
│   │   │   ├── _ValidationScriptsPartial.cshtml # Hỗ trợ validate client
│   │   │   └── Error.cshtml                  # Trang lỗi chung
│   │   ├── Home/
│   │   │   ├── Index.cshtml                  # Trang chủ
│   │   │   ├── About.cshtml                  # Giới thiệu cửa hàng
│   │   │   └── Contact.cshtml                # Thông tin liên hệ
│   │   ├── Account/
│   │   │   ├── Login.cshtml                  # Đăng nhập
│   │   │   ├── Register.cshtml               # Đăng ký tài khoản
│   │   │   ├── ForgotPassword.cshtml         # Quên mật khẩu
│   │   │   ├── ResetPassword.cshtml          # Đặt lại mật khẩu
│   │   │   └── Profile.cshtml                # Cập nhật thông tin cá nhân
│   │   ├── Foods/
│   │   │   ├── Index.cshtml                  # Danh sách món ăn
│   │   │   ├── Details.cshtml                # Chi tiết món ăn
│   │   │   └── SearchResults.cshtml          # Kết quả tìm kiếm
│   │   ├── Orders/
│   │   │   ├── Index.cshtml                  # Danh sách đơn hàng người dùng
│   │   │   ├── Details.cshtml                # Chi tiết đơn
│   │   │   ├── Create.cshtml                 # Trang đặt đơn hàng
│   │   │   ├── Checkout.cshtml               # Thanh toán
│   │   │   └── OrderConfirmation.cshtml      # Xác nhận đơn thành công
│   │   └── Cart/
│   │       ├── Index.cshtml                  # Xem giỏ hàng
│   │       └── Update.cshtml                 # Cập nhật số lượng hoặc xóa
│   ├── wwwroot/                              # 📁 File tĩnh (JS, CSS, ảnh)
│   │   ├── css/
│   │   │   ├── site.css
│   │   │   └── bootstrap.min.css
│   │   ├── js/
│   │   │   ├── site.js
│   │   │   └── bootstrap.bundle.min.js
│   │   └── images/
│   │       └── logo.png
│   ├── appsettings.json                      # Cấu hình kết nối DB, JWT, v.v.
│   ├── Program.cs                            # Điểm khởi đầu app
│   └── FastFoodStore.WebUI.csproj            # File project MVC
├── FastFoodStore.sln                         # 🔧 Tập tin solution .NET
└── README.md                                 # 📘 Tài liệu hướng dẫn dự án

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
