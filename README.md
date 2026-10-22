<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>شمسك - متجر الطاقة الشمسية</title>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, Tahoma, sans-serif;
        }

        body {
            background: #f5f6f8;
            color: #222;
        }

        /* ================= NAVBAR ================= */

        .navbar {
            height: 65px;
            background: #111;
            color: white;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0 8%;
        }

        .logo {
            font-size: 24px;
            font-weight: bold;
        }

        .logo span {
            color: #907;
        }

        .nav-links {
            display: flex;
            gap: 30px;
            align-items: center;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            font-size: 15px;
            transition: .3s;
        }

        .nav-links a:hover {
            color: #ffc400;
        }

        .nav-icons {
            display: flex;
            gap: 22px;
            font-size: 20px;
        }

        .nav-icons span {
            cursor: pointer;
        }

        /* ================= HERO ================= */

        .hero {
            width: 82%;
            min-height: 315px;
            margin: 25px auto 40px;
            border-radius: 20px;
            overflow: hidden;

            background:
                linear-gradient(
                    90deg,
                    rgba(20, 20, 10, .95),
                    rgba(15, 27, 48, .95)
                );

            display: flex;
            align-items: center;
            justify-content: flex-start;
            padding: 45px;
            position: relative;
        }

        .hero::before {
            content: "⚡";
            position: absolute;
            left: 35px;
            bottom: 35px;
            font-size: 60px;
            color: #777;
            opacity: .35;
        }

        .hero-content {
            width: 55%;
            margin-right: auto;
        }

        .hero h1 {
            color: white;
            font-size: 46px;
            line-height: 1.2;
            margin-bottom: 20px;
        }

        .hero h1 span {
            color: #fff;
        }

        .hero p {
            color: #ddd;
            font-size: 17px;
            line-height: 1.8;
            margin-bottom: 25px;
        }

        .buttons {
            display: flex;
            gap: 12px;
            flex-wrap: wrap;
        }

        .btn {
            border: none;
            padding: 14px 25px;
            border-radius: 10px;
            font-size: 15px;
            cursor: pointer;
            font-weight: bold;
        }

        .btn-yellow {
            background: #ffc400;
            color: #111;
        }

        .btn-dark {
            background: #344258;
            color: white;
        }

        .btn-white {
            background: white;
            color: #222;
        }

        .btn:hover {
            transform: translateY(-2px);
        }

        /* ================= PRODUCTS ================= */

        .products-section {
            width: 82%;
            margin: auto;
        }

        .section-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }

        .section-header h2 {
            font-size: 28px;
        }

        .section-header h2 span {
            color: #ffc400;
        }

        .show-all {
            color: #333;
            text-decoration: none;
            font-size: 15px;
        }

        .products {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 25px;
        }

        .product-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 4px 15px rgba(0,0,0,.08);
            position: relative;
            transition: .3s;
        }

        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(0,0,0,.13);
        }

        .badge {
            position: absolute;
            top: 12px;
            right: 12px;
            background: #e53935;
            color: white;
            padding: 6px 12px;
            border-radius: 15px;
            font-size: 12px;
        }

        .product-image {
            height: 190px;
            background: #eef0f4;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 75px;
            color: #8991a4;
        }

        .product-info {
            padding: 18px;
        }

        .rating {
            color: #ffc400;
            font-size: 14px;
            margin-bottom: 8px;
        }

        .category {
            color: #888;
            font-size: 13px;
        }

        .product-title {
            font-size: 19px;
            font-weight: bold;
            margin: 10px 0;
        }

        .description {
            color: #777;
            font-size: 13px;
            line-height: 1.6;
        }

        .price {
            color: #111;
            font-size: 20px;
            font-weight: bold;
            margin-top: 15px;
        }

        .add-cart {
            width: 100%;
            border: none;
            background: #ffc400;
            padding: 12px;
            border-radius: 8px;
            margin-top: 12px;
            cursor: pointer;
            font-weight: bold;
        }

        .add-cart:hover {
            background: #eeb700;
        }

        /* ================= WHATSAPP ================= */

        .whatsapp {
            position: fixed;
            bottom: 25px;
            right: 25px;
            width: 52px;
            height: 52px;
            border-radius: 50%;
            background: #25d366;
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 27px;
            box-shadow: 0 4px 15px rgba(0,0,0,.25);
            cursor: pointer;
        }

        /* ================= RESPONSIVE ================= */

        @media (max-width: 900px) {

            .navbar {
                padding: 0 4%;
            }

            .nav-links {
                gap: 12px;
            }

            .hero,
            .products-section {
                width: 94%;
            }

            .hero-content {
                width: 80%;
            }

            .hero h1 {
                font-size: 35px;
            }

            .products {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (max-width: 600px) {

            .navbar {
                height: auto;
                padding: 15px;
                flex-wrap: wrap;
                gap: 15px;
            }

            .nav-links {
                order: 3;
                width: 100%;
                justify-content: center;
            }

            .hero {
                padding: 30px 20px;
                min-height: 400px;
            }

            .hero-content {
                width: 100%;
            }

            .hero h1 {
                font-size: 32px;
            }

            .products {
                grid-template-columns: 1fr;
            }

            .section-header h2 {
                font-size: 22px;
            }
        }
    </style>
</head>

<body>

    <!-- ================= NAVBAR ================= -->

    <nav class="navbar">

        <div class="logo">
            شمسك <span>☀</span>
        </div>

        <div class="nav-links">
            <a href="#">الرئيسية</a>
            <a href="#products">المنتجات</a>
            <a href="#">عن المتجر</a>
            <a href="#">اتصل بنا</a>
        </div>

        <div class="nav-icons">
            <span title="حساب المستخدم">👤</span>
            <span title="السلة" onclick="showCart()">🛒</span>
        </div>

    </nav>


    <!-- ================= HERO ================= -->

    <section class="hero">

        <div class="hero-content">

            <h1>
                مستقبل الطاقة<br>
                يبدأ هنا ☀️
            </h1>

            <p>
                أحدث تقنيات الطاقة الشمسية بأسعار تنافسية،
                وفر فاتورتك واستثمر في المستقبل.
            </p>

            <div class="buttons">

                <button class="btn btn-yellow"
                        onclick="shopNow()">
                    🛒 تسوق الآن
                </button>

                <button class="btn btn-dark"
                        onclick="watchVideo()">
                    ▶ شاهد الفيديو
                </button>

                <button class="btn btn-white"
                        onclick="solarInfo()">
                    ☀ استثمر طاقتك الشمسية
                </button>

            </div>

        </div>

    </section>


    <!-- ================= PRODUCTS ================= -->

    <section class="products-section" id="products">

        <div class="section-header">

            <h2>
                منتجات مميزة ⭐
            </h2>

            <a class="show-all" href="#">
                عرض الكل ←
            </a>

        </div>


        <div class="products">

            <!-- PRODUCT 1 -->

            <div class="product-card">

                <span class="badge">
                    الأكثر مبيعاً
                </span>

                <div class="product-image">
                    ☀️
                </div>

                <div class="product-info">

                    <div class="rating">
                        ★★★★★
                        <span class="category">
                            (12 تقييم)
                        </span>
                    </div>

                    <div class="product-title">
                        لوح شمسي 550 واط أحادي البلورة
                    </div>

                    <div class="description">
                        لوح شمسي عالي الكفاءة مناسب
                        للمنازل والمشاريع.
                    </div>

                    <div class="price">
                        350,000 ج.س
                    </div>

                    <button class="add-cart"
                            onclick="addToCart('لوح شمسي 550 واط')">
                        إضافة إلى السلة 🛒
                    </button>

                </div>

            </div>


            <!-- PRODUCT 2 -->

            <div class="product-card">

                <span class="badge">
                    الأكثر مبيعاً
                </span>

                <div class="product-image">
                    ☀️
                </div>

                <div class="product-info">

                    <div class="rating">
                        ★★★★★
                        <span class="category">
                            (8 تقييم)
                        </span>
                    </div>

                    <div class="product-title">
                        انفرتر 5 كيلو واط هجين
                    </div>

                    <div class="description">
                        انفرتر ذكي لإدارة الطاقة
                        الشمسية والبطاريات.
                    </div>

                    <div class="price">
                        850,000 ج.س
                    </div>

                    <button class="add-cart"
                            onclick="addToCart('انفرتر 5 كيلو واط')">
                        إضافة إلى السلة 🛒
                    </button>

                </div>

            </div>


            <!-- PRODUCT 3 -->

            <div class="product-card">

                <span class="badge">
                    جديد
                </span>

                <div class="product-image">
                    🔋
                </div>

                <div class="product-info">

                    <div class="rating">
                        ★★★★☆
                        <span class="category">
                            (6 تقييم)
                        </span>
                    </div>

                    <div class="product-title">
                        بطارية ليثيوم 5 كيلو واط
                    </div>

                    <div class="description">
                        بطارية تخزين عالية الجودة
                        للاستخدام المنزلي.
                    </div>

                    <div class="price">
                        1,200,000 ج.س
                    </div>

                    <button class="add-cart"
                            onclick="addToCart('بطارية ليثيوم 5 كيلو واط')">
                        إضافة إلى السلة 🛒
                    </button>

                </div>

            </div>

        </div>

    </section>


    <!-- ================= WHATSAPP ================= -->

    <div class="whatsapp"
     onclick="openWhatsApp()">
        ☎
    </div>


    <!-- ================= JAVASCRIPT ================= -->

    <script>

        let cart = [];

        function addToCart(product) {

            cart.push(product);

            alert(
                "تمت إضافة " +
                product +
                " إلى السلة ✅"
            );
        }


        function showCart() {

            if (cart.length === 0) {

                alert("السلة فارغة 🛒");

            } else {

                alert(
                    "المنتجات في السلة:\n\n" +
                    cart.join("\n")
                );
            }
        }


        function shopNow() {

            document
                .getElementById("products")
                .scrollIntoView({
                    behavior: "smooth"
                });
        }


        function watchVideo() {

            alert(
                "سيتم إضافة فيديو تعريفي بالطاقة الشمسية هنا 🎥"
            );
        }


        function solarInfo() {

            alert(
                "نساعدك على اختيار معدات الطاقة الشمسية المناسبة لمنزلك ومشروعك ☀️"
            );
        }


        function openWhatsApp() {

            window.open(
                "https://wa.me/249000000000",
                "_blank"
            );
        }

    </script>

</body>
</html>
