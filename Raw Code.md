<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>🇹🇭 THAIPOST MARKETPLACE (บริษัท ต๋อยฮาไม่ จำกัด)</title>
    <style>
        /* Theme: Primary Red & Bright Blue */
        :root {
            --primary-red: #FF0000;
            --bright-blue: #00BFFF;
            --header-title-color: #0000FF;
            --background-light: #F0F0F0; 
            --text-color: #222222;
            --border-color: #DDDDDD;
            --font-family: 'Arial', sans-serif;
        }

        body {
            font-family: var(--font-family);
            background-color: var(--background-light);
            color: var(--text-color);
            margin: 0;
            padding: 0;
            line-height: 1.6;
        }

        .container {
            width: 90%;
            max-width: 1200px;
            margin: 20px auto;
            padding: 20px;
            background-color: #FFFFFF;
            box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
            border-radius: 10px;
        }

        header {
            background-color: var(--primary-red);
            color: white;
            padding: 20px 0;
            text-align: center;
            margin-bottom: 25px;
            border-radius: 10px 10px 0 0;
            position: relative;
        }

        header h1 {
            margin: 0;
            font-size: 2.2em;
            letter-spacing: 1px;
        }
        
        header h1 .marketplace-title {
            color: var(--header-title-color); 
            background-color: white; 
            padding: 0 8px;
            border-radius: 4px;
        }
        
        .thai-post-logo {
            position: absolute;
            top: 10px;
            right: 15px;
            width: 70px; 
            height: auto;
            background-color: white;
            padding: 5px;
            border-radius: 50%;
            box-shadow: 0 0 5px rgba(0, 0, 0, 0.3);
        }

        nav {
            text-align: center;
            border-bottom: 2px solid var(--border-color);
            margin-bottom: 15px;
            /* เพิ่ม overflow เพื่อให้รองรับเมนูที่มากขึ้นในหน้าจอขนาดเล็ก */
            overflow-x: auto; 
            white-space: nowrap;
            padding-bottom: 5px; /* เพิ่มพื้นที่ด้านล่างเพื่อป้องกันขอบล่างชนปุ่ม */
        }

        /* แก้ไข Nav Button: กำหนด font-weight bold ตั้งแต่แรก และใช้สีอ่อนลงเพื่อแก้ปัญหาการขยับ */
        nav button {
            background: none;
            border: none;
            padding: 12px 20px; /* ลด padding แนวราบเล็กน้อย */
            margin: 0 2px; /* ลด margin ระหว่างปุ่ม */
            cursor: pointer;
            font-size: 1.0em; /* ลด font-size เล็กน้อย */
            color: #666666; /* สีตัวอักษรจางลงในสถานะปกติ */
            font-weight: bold; /* ให้เป็นตัวหนาตั้งแต่แรกเพื่อจองพื้นที่ */
            border-bottom: 3px solid transparent; /* จองพื้นที่ขอบล่าง */
            transition: border-bottom 0.3s, color 0.3s;
        }

        /* แก้ไข Nav Active/Hover: เปลี่ยนเฉพาะสีตัวอักษรและสีขอบล่างเท่านั้น */
        nav button.active, nav button:hover {
            border-bottom: 3px solid var(--bright-blue);
            color: var(--bright-blue);
        }

        .section {
            display: none;
            padding: 15px 0;
        }

        .section.active {
            display: block;
        }

        /* Forms and Inputs */
        input[type="text"], input[type="number"], textarea, select, input[type="password"], input[type="email"] {
            width: 100%;
            padding: 12px;
            margin-bottom: 15px;
            border: 1px solid var(--border-color);
            border-radius: 6px;
            box-sizing: border-box;
            font-family: var(--font-family);
        }

        button.primary {
            background-color: var(--primary-red);
            color: white;
            padding: 12px 20px;
            border: none;
            border-radius: 6px;
            cursor: pointer;
            font-size: 1em;
            transition: background-color 0.3s;
        }

        button.primary:hover {
            background-color: #CC0000; 
        }
        
        button.secondary {
            background-color: var(--bright-blue);
            color: white;
            padding: 8px 15px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 0.9em;
            transition: background-color 0.3s;
        }

        button.secondary:hover {
            background-color: #008CBA;
        }
        
        /* --- (NEW) Style for Featured Button --- */
        button.btn-feature {
            background-color: #FFC107; /* Yellow/Gold */
            color: #333;
            padding: 8px 15px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 0.9em;
            transition: background-color 0.3s;
        }
        button.btn-feature.featured {
            background-color: #28a745; /* Green */
            color: white;
        }
        /* --- End New Style --- */

        /* Product Cards/List */
        .product-list, .order-list {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 25px;
        }

        .product-card {
            background-color: #FFFFFF;
            padding: 20px;
            border-radius: 8px;
            border: 1px solid var(--border-color);
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.05);
        }
        
        /* Product Card Image Style */
        .product-card img {
            width: 100%; 
            height: 200px; 
            object-fit: cover; 
            border-radius: 6px;
            margin-bottom: 10px;
            border: 1px solid var(--border-color);
        }

        /* สำหรับหน้า Consignor จัดการสินค้า */
        .product-card img[style*="contain"] {
             height: 100px; 
             object-fit: contain;
        }
        
        .product-card h3 {
            margin-top: 0;
            color: var(--bright-blue);
            border-bottom: 2px solid var(--primary-red);
            padding-bottom: 5px;
        }

        .product-card .price {
            font-size: 1.4em;
            font-weight: bold;
            color: var(--primary-red);
            margin-top: 10px;
        }
        
        .seller-info {
            font-size: 0.9em;
            color: #666;
            margin-bottom: 10px;
        }
        
        .cart-summary h4 {
            border-top: 1px dashed #CCC;
            padding-top: 10px;
        }

        /* ------------------------------------------ */
        /* --- Styles for Login and Home Sections --- */
        /* ------------------------------------------ */
        .login-box {
            max-width: 400px;
            margin: 50px auto;
            padding: 30px;
            border: 1px solid var(--border-color);
            border-radius: 8px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
        }
        
        .login-box h2 {
            text-align: center;
            color: var(--primary-red);
            margin-bottom: 25px;
            border-bottom: 2px solid var(--bright-blue);
            padding-bottom: 10px;
        }

        .home-hero {
            text-align: center;
            background-color: #FFF8E1; /* สีครีมอ่อน */
            padding: 40px 20px;
            border-radius: 8px;
            margin-bottom: 30px;
            border: 1px dashed #FFD700;
        }

        .home-hero h2 {
            font-size: 2.5em;
            color: var(--primary-red);
            margin-bottom: 10px;
        }

        .home-hero p {
            font-size: 1.2em;
            color: #555;
        }
        
        .feature-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            text-align: center;
        }
        
        .feature-card {
            padding: 20px;
            border-radius: 8px;
            background-color: var(--background-light);
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.05);
            border-left: 5px solid var(--bright-blue);
        }
        
        .feature-card h3 {
            color: var(--bright-blue);
        }

        /* --- (NEW) Profile Page Styles --- */
        .profile-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
        }
        .profile-card {
            background-color: #FFFFFF;
            padding: 25px;
            border-radius: 8px;
            border: 1px solid var(--border-color);
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.05);
        }
        .profile-card h3 {
            margin-top: 0;
            color: var(--primary-red);
            border-bottom: 2px solid var(--border-color);
            padding-bottom: 10px;
        }
        .profile-card p {
            font-size: 1.1em;
            line-height: 1.7;
        }
        .profile-card p strong {
            color: #333;
        }

        /* --- (NEW) Admin User Table Styles --- */
        .user-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 20px;
        }
        .user-table th, .user-table td {
            border: 1px solid var(--border-color);
            padding: 12px;
            text-align: left;
        }
        .user-table th {
            background-color: var(--background-light);
            color: var(--primary-red);
        }
        .user-table tr:nth-child(even) {
            background-color: #f9f9f9;
        }
        .user-table .btn-suspend {
            background-color: #FFC107; /* Yellow */
            color: #333;
        }
        .user-table .btn-suspend.active {
            background-color: #6c757d; /* Gray */
            color: white;
        }
        .user-table .btn-deactivate {
            background-color: #dc3545; /* Red */
            color: white;
        }
        .user-table .btn-deactivate.active {
            background-color: #6c757d; /* Gray */
            color: white;
        }
        /* --- End Admin Table --- */

        /* For responsive nav buttons */
        @media (max-width: 768px) {
            nav button {
                font-size: 0.9em;
                padding: 10px 15px;
            }
            .product-list {
                grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            }
        }
    </style>
</head>
<body>

    <header>
        <img src="https://raw.githubusercontent.com/zxteaparty-dev/SJMeow/refs/heads/main/ThailandPost_Logo_(2021).svg" alt="Thai Post Logo" class="thai-post-logo">
        
        <h1><span class="marketplace-title">🇹🇭 THAIPOST MARKETPLACE</span></h1>
        <p>ดำเนินการโดย: บริษัท ต๋อยฮาไม่ จำกัด | จัดส่งทั่วไทย</p>
    </header>

    <div class="container">
        <nav>
            <button onclick="showSection('home-view')" class="active" id="nav-home">🏠 หน้าแรก</button>
            <button onclick="showSection('customer-view')" id="nav-customer">🛍️ ตลาดสินค้า (Market)</button>
            <button onclick="showSection('catalog-view')" id="nav-catalog">🔎 แคตตาล็อกสินค้า (Catalog)</button>
            <!-- ปุ่ม Admin/User จะถูกซ่อน/แสดงโดย JavaScript -->
            <button onclick="showSection('consignor-management')" id="nav-consignor">🏢 จัดการร้านค้า/สินค้า</button>
            <button onclick="showSection('shipping-tracking')" id="nav-shipping">📦 การจัดส่งและติดตาม</button>
            <button onclick="showSection('commission-report')" id="nav-commission">📊 รายงานค่าคอมมิชชั่น</button>
            <!-- (NEW) เพิ่มปุ่มจัดการผู้ใช้ -->
            <button onclick="showSection('admin-user-management-view')" id="nav-admin-users">👤 จัดการผู้ใช้</button>
            <button onclick="showSection('profile-view')" id="nav-profile">👤 ข้อมูลผู้ใช้</button>
            <button onclick="toggleLogin()" id="nav-login">🔒 เข้าสู่ระบบ</button>
        </nav>

        <div id="home-view" class="section active">
            <div class="home-hero">
                <h2>ยินดีต้อนรับสู่ THAIPOST MARKETPLACE 🇹🇭</h2>
                <p>ศูนย์รวมสินค้าคุณภาพจากผู้ประกอบการทั่วประเทศ จัดส่งง่ายๆ ผ่านเครือข่ายไปรษณีย์ไทย</p>
                <button class="primary" onclick="showSection('customer-view')" style="margin-top: 20px;">เริ่มช้อปปิ้งเลย! 🛒</button>
            </div>

            <h2>✨ จุดเด่นของเรา</h2>
            <div class="feature-grid">
                <div class="feature-card">
                    <h3>🚚 จัดส่งทั่วไทย</h3>
                    <p>รวดเร็ว ปลอดภัย ด้วยมาตรฐานการจัดส่งจากไปรษณีย์ไทย</p>
                </div>
                <div class="feature-card">
                    <h3>💡 สินค้าชุมชน</h3>
                    <p>สนับสนุนผู้ประกอบการท้องถิ่น คัดสรรสินค้าคุณภาพ</p>
                </div>
                <div class="feature-card">
                    <h3>💰 ค่าคอมมิชชั่น 10%</h3>
                    <p>โมเดลจำลองที่โปร่งใสสำหรับการจัดการร้านค้า</p>
                </div>
            </div>
            
            <h2 style="margin-top: 30px;">⭐ สินค้าแนะนำ</h2>
            <div id="home-featured-products" class="product-list">
            </div>
        </div>
        
        <!-- (MODIFIED) เพิ่มช่องสำหรับลงทะเบียน -->
        <div id="login-view" class="section">
            <div class="login-box">
                <h2 id="login-title">เข้าสู่ระบบ (จำลอง)</h2>
                <form id="login-form">
                    
                    <!-- (NEW) Signup Fields (ซ่อนไว้เริ่มต้น) -->
                    <div id="signup-fields" style="display: none;">
                        <input type="text" id="signup-firstname" placeholder="ชื่อ (Name)">
                        <input type="text" id="signup-lastname" placeholder="นามสกุล (Lastname)">
                        <input type="text" id="signup-phone" placeholder="เบอร์โทรศัพท์ (Phone)">
                        <textarea id="signup-address" placeholder="ที่อยู่ (Address)" style="height: 80px;"></textarea>
                        <hr style="margin-bottom: 15px;">
                    </div>
                    <!-- End Signup Fields -->

                    <input type="email" id="login-email" placeholder="อีเมล (admin@thaipost.com หรือ user@example.com)" required>
                    <input type="password" id="login-password" placeholder="รหัสผ่าน (123456)" required>
                    <button type="submit" class="primary" style="width: 100%; margin-bottom: 10px;" id="auth-submit-button">เข้าสู่ระบบ</button>
                    <p style="text-align: center; font-size: 0.9em; color: #777;">
                        <span id="toggle-form-text">ยังไม่มีบัญชี?</span> 
                        <a href="#" onclick="switchForm(event)">ลงทะเบียน</a>
                    </p>
                </form>
            </div>
        </div>

        <div id="customer-view" class="section">
            <h2>⭐ สินค้าเด่นประจำ Marketplace</h2>
            <div id="customer-product-list" class="product-list">
            </div>
            
            <hr>

            <h2>🛒 ตะกร้าสินค้า</h2>
            <div id="cart-items">
                <p>ไม่มีสินค้าในตะกร้า</p>
            </div>
            <p style="font-size: 1.2em;">รวมยอดสุทธิ: <strong id="cart-total" style="color: var(--primary-red);">0.00</strong> บาท</p>
            <button class="primary" onclick="checkout()">ดำเนินการสั่งซื้อและชำระเงิน</button>
        </div>

        <div id="catalog-view" class="section">
            <h2>🔎 ค้นหาสินค้าทั้งหมดใน Marketplace</h2>
            <div style="margin-bottom: 20px;">
                <input type="text" id="catalog-search-input" placeholder="ป้อนชื่อสินค้า หรือร้านค้าที่ต้องการค้นหา..." onkeyup="searchProducts(this.value)">
            </div>
            <div id="catalog-product-list" class="product-list">
            </div>
        </div>

        <div id="consignor-management" class="section">
            <h2>➕ เพิ่มสินค้าใหม่ (Marketplace Item)</h2>
            <!-- *** เพิ่ม ID สำหรับการแก้ไข *** -->
            <input type="hidden" id="editing-product-id" value="">
            
            <form id="add-product-form">
                <input type="text" id="product-name" placeholder="ชื่อสินค้า" required>
                <textarea id="product-description" placeholder="รายละเอียดสินค้า" required></textarea>
                <input type="number" id="product-price" placeholder="ราคา (บาท)" step="0.01" min="0" required>
                <input type="number" id="product-stock" placeholder="จำนวนสินค้าในสต็อก" min="0" required>
                <input type="text" id="product-image" placeholder="URL รูปภาพ (ตัวอย่าง: https://i.ibb.co/TqY90gV/drip-coffee.jpg)">
                <select id="consignor-name" required>
                    <option value="">เลือกชื่อร้านค้า (ผู้ฝากขาย)</option>
                    <option value="Store A">ร้านค้า A (ผลิตภัณฑ์ชุมชน)</option>
                    <option value="Store B">ร้านค้า B (สินค้าแฟชั่น)</option>
                    <option value="Store C">ร้านค้า C (อาหารแห้ง)</option>
                </select>
                <!-- *** ปุ่ม บันทึก/อัปเดต/ยกเลิก *** -->
                <button type="submit" class="primary" id="btn-save-product">บันทึกสินค้า</button>
                <button type="button" class="secondary" id="btn-update-product" style="display: none; background-color: var(--bright-blue);">อัปเดตสินค้า</button>
                <button type="button" class="secondary" id="btn-cancel-edit" style="display: none; background-color: #666;">ยกเลิกแก้ไข</button>
            </form>

            <hr>

            <h2>📋 รายการสินค้าทั้งหมดใน Marketplace</h2>
            <div id="consignor-product-list" class="product-list">
            </div>
        </div>

        <div id="shipping-tracking" class="section">
            <div style="padding: 12px; background-color: #FFEFD5; color: #8B4513; border: 1px solid #FFE4B5; border-left: 5px solid var(--primary-red); border-radius: 4px; margin-bottom: 15px;">
                ⚠️ **ระบบจัดส่งไปรษณีย์ไทย (จำลอง):** การจัดการหมายเลขพัสดุและสถานะการจัดส่ง
            </div>
            <h2>รายการสั่งซื้อที่ต้องดำเนินการจัดส่ง</h2>
            <div id="order-list" class="order-list">
            </div>

            <hr>

            <h2>🔍 ติดตามสถานะพัสดุ</h2>
            <input type="text" id="tracking-input" placeholder="ป้อนหมายเลขพัสดุ (เช่น TH001)">
            <button class="primary" onclick="trackShipment()">ค้นหาสถานะ</button>
            <div id="tracking-result" style="margin-top: 15px;">
            </div>
        </div>
        
        <div id="commission-report" class="section">
            <h2>📊 รายงานค่าคอมมิชชั่นและการจ่ายเงิน (จำลอง)</h2>
            <div style="margin-bottom: 20px; font-weight: bold;">
                <p>อัตราค่าคอมมิชชั่น: <span style="color: var(--primary-red);">10%</span> ของราคาสินค้าทุกรายการ</p>
                <p>จำนวนคำสั่งซื้อที่สำเร็จ (จำลอง): <span id="completed-orders-count">0</span> รายการ</p>
            </div>
            <div id="commission-summary">
                <p>ยังไม่มีข้อมูลการขายที่สำเร็จ</p>
            </div>
        </div>

        <!-- (NEW) 8. Admin User Management -->
        <div id="admin-user-management-view" class="section">
            <h2>👤 จัดการผู้ใช้งานทั้งหมด</h2>
            <p>ในหน้านี้ คุณสามารถระงับ หรือ ปิดใช้งานบัญชีผู้ใช้ทั่วไปได้</p>
            <div style="overflow-x: auto;"> <!-- For responsive table -->
                <table class="user-table">
                    <thead>
                        <tr>
                            <th>อีเมล</th>
                            <th>ชื่อ</th>
                            <th>Role</th>
                            <th>สถานะ</th>
                            <th>ดำเนินการ</th>
                        </tr>
                    </thead>
                    <tbody id="user-management-table-body">
                        <!-- JS will populate this -->
                    </tbody>
                </table>
            </div>
        </div>

        <!-- (NEW) 9. หน้าข้อมูลผู้ใช้ -->
        <div id="profile-view" class="section">
            <h2>👤 ข้อมูลผู้ใช้งาน</h2>
            <!-- (NEW) Add Edit/Save/Cancel buttons -->
            <button class="primary" id="btn-edit-profile" onclick="toggleProfileEdit(true)">✏️ แก้ไขข้อมูล</button>
            <button class="primary" id="btn-save-profile" onclick="saveProfileEdit()" style="display: none; background-color: #28a745;">💾 บันทึกข้อมูล</button>
            <button class="secondary" id="btn-cancel-profile" onclick="toggleProfileEdit(false)" style="display: none; background-color: #666;">ยกเลิก</button>

            <div class="profile-container" style="margin-top: 20px;">
                <div class="profile-card">
                    <h3>ข้อมูลบัญชี</h3>
                    <p><strong>อีเมล:</strong> <span class="profile-view" id="profile-email">...</span></p>
                    <p><strong>สถานะบัญชี:</strong> <span class="profile-view" id="profile-role">...</span></p>
                    
                    <!-- (MODIFIED) Add spans for view mode and inputs for edit mode -->
                    <p><strong>ชื่อ:</strong>
                        <span class="profile-view" id="profile-name">...</span>
                        <input type="text" class="profile-edit" id="profile-edit-firstname" style="display: none;">
                    </p>
                    <p><strong>นามสกุล:</strong>
                        <span class="profile-view" id="profile-lastname">...</span>
                        <input type="text" class="profile-edit" id="profile-edit-lastname" style="display: none;">
                    </p>
                    <p><strong>เบอร์โทรศัพท์:</strong>
                        <span class="profile-view" id="profile-phone">...</span>
                        <input type="text" class="profile-edit" id="profile-edit-phone" style="display: none;">
                    </p>
                    <p><strong>ที่อยู่:</strong>
                        <span class="profile-view" id="profile-address" style="white-space: pre-wrap;">...</span>
                        <textarea class="profile-edit" id="profile-edit-address" style="display: none; height: 100px;"></textarea>
                    </p>
                </div>
                <div class="profile-card">
                    <h3>สรุปคำสั่งซื้อ</h3>
                    <p><strong>จำนวนคำสั่งซื้อทั้งหมด:</strong> <span id="profile-total-orders">0</span> ชิ้น</p>
                    <p><strong>จัดส่งสำเร็จแล้ว:</strong> <span id="profile-completed-orders" style="color: green;">0</span> ชิ้น</p>
                    <p><strong>กำลังดำเนินการ/รอจัดส่ง:</strong> <span id="profile-pending-orders" style="color: var(--bright-blue);">0</span> ชิ้น</p>
                </div>
            </div>
        </div>


    </div>

    <script>
        // *** 1. Data Structure (In-Memory Simulation) ***
        const COMMISSION_RATE = 0.10; // 10% commission rate

        let products = [
            // *** (MODIFIED) เพิ่ม isFeatured property ***
            { id: 1, name: "กาแฟดริป (Store A)", description: "กาแฟอาราบิก้าจากเชียงราย", price: 150.00, stock: 10, consignor: 'Store A', imageURL: 'https://i.ibb.co/TqY90gV/drip-coffee.jpg', isFeatured: true }, // <-- ตั้งเป็นแนะนำ
            { id: 2, name: "ผ้าถุงลายไทยประยุกต์", description: "งานฝีมือคุณภาพเยี่ยม", price: 499.00, stock: 5, consignor: 'Store B', imageURL: 'https://i.ibb.co/6y4V5kQ/thai-sarong.jpg', isFeatured: false },
            { id: 3, name: "ข้าวกล้องอินทรีย์ 1kg", description: "จากเกษตรกรในเครือข่าย", price: 85.00, stock: 30, consignor: 'Store C', imageURL: 'https://i.ibb.co/hK5262c/organic-rice.jpg', isFeatured: false }
        ];

        let cart = [];
        let orders = []; 
        let nextProductId = products.length > 0 ? Math.max(...products.map(p => p.id)) + 1 : 1;
        let nextOrderId = orders.length + 1;
        
        // *** 1.1 สถานะการล็อกอิน (สำคัญ) ***
        let isLoggedIn = false; 
        let currentUserEmail = null; // ติดตามว่าเป็น Admin หรือไม่
        let currentUserRole = 'guest'; // (NEW) เพิ่ม Role

        // *** (NEW) 1.2 ฐานข้อมูลจำลองสำหรับผู้ใช้ ***
        let simulatedUsers = [
            { 
                email: 'admin@thaipost.com', 
                password: '123456', 
                role: 'admin', 
                name: 'Admin',
                status: 'active' // (NEW)
            },
            { 
                email: 'user@example.com', 
                password: '123456', 
                role: 'user', 
                name: 'User', 
                lastName: 'Example', 
                phone: '0812345678', 
                address: '123 Bangkok Thailand',
                status: 'active' // (NEW)
            }
        ];


        // *** 2. Core Functions & Navigation ***

        function showSection(sectionId) {
            
            // *** 2.1 ตรวจสอบสิทธิ์การเข้าถึง (สำคัญ) ***
            // (MODIFIED) เพิ่ม admin-user-management-view
            const adminOnlyPages = ['consignor-management', 'commission-report', 'admin-user-management-view']; 
            // (MODIFIED) เพิ่ม profile-view
            const needsLoginPages = ['shipping-tracking', 'profile-view']; 
            
            const isStrictAdminPage = adminOnlyPages.includes(sectionId);
            const isLoginPage = needsLoginPages.includes(sectionId);

            // ตรวจสอบหน้า Admin เท่านั้น
            if (isStrictAdminPage && (!isLoggedIn || currentUserRole !== 'admin')) {
                alert('⚠️ คุณไม่มีสิทธิ์เข้าถึงส่วนนี้ กรุณาเข้าสู่ระบบด้วยบัญชีผู้ดูแลระบบ');
                showSection('login-view'); // บังคับไปหน้าล็อกอิน
                return;
            }
            
            // ตรวจสอบหน้าที่ต้องล็อกอิน
            if (isLoginPage && !isLoggedIn) {
                 alert('⚠️ กรุณาเข้าสู่ระบบเพื่อดูหน้านี้');
                 showSection('login-view'); // บังคับไปหน้าล็อกอิน
                 return;
            }
            
            document.querySelectorAll('.section').forEach(section => {
                section.classList.remove('active');
            });
            document.getElementById(sectionId).classList.add('active');
            
            document.querySelectorAll('nav button').forEach(button => {
                button.classList.remove('active');
            });
            
            try {
                let navButtonId;
                if (sectionId === 'login-view') {
                    navButtonId = 'nav-login';
                } else if (sectionId === 'home-view') {
                    navButtonId = 'nav-home';
                } else {
                    const navId = sectionId.replace('-view', ''); 
                    navButtonId = `nav-${navId}`;
                }
                
                const targetButton = document.getElementById(navButtonId);
                if (targetButton) {
                    targetButton.classList.add('active');
                }
            } catch (error) {
                // Ignore
            }

            // Load data functions
            if (sectionId === 'home-view') renderHomeFeaturedProducts();
            if (sectionId === 'customer-view') renderCustomerProducts();
            if (sectionId === 'catalog-view') renderCatalogProducts();
            if (sectionId === 'consignor-management') renderConsignorProducts();
            if (sectionId === 'shipping-tracking') renderOrderList();
            if (sectionId === 'commission-report') renderCommissionReport();
            // (NEW) โหลดหน้าโปรไฟล์
            if (sectionId === 'profile-view') renderProfilePage();
            // (NEW) โหลดหน้าจัดการผู้ใช้
            if (sectionId === 'admin-user-management-view') renderUserManagement();
        }

        // *** 2.2 ฟังก์ชันซ่อน/แสดงแท็บ Admin ***
        function updateNavVisibility() {
            // *** (MODIFIED) ใช้ Role แทน Email ***
            const isAdmin = (isLoggedIn && currentUserRole === 'admin');
            
            // (MODIFIED) เพิ่ม nav-admin-users
            const adminOnlyTabs = ['nav-consignor', 'nav-commission', 'nav-admin-users'];
            // (MODIFIED) เพิ่ม nav-profile
            const loggedInTabs = ['nav-shipping', 'nav-profile']; 

            // แท็บ Admin เท่านั้น
            adminOnlyTabs.forEach(id => {
                document.getElementById(id).style.display = isAdmin ? 'inline-block' : 'none';
            });
            
            // แท็บที่ต้อง Login (User หรือ Admin)
            loggedInTabs.forEach(id => {
                document.getElementById(id).style.display = isLoggedIn ? 'inline-block' : 'none';
            });
        }


        // *** 2.3 Login/Logout/Switch Form Logic (ปรับปรุง) ***

        document.getElementById('login-form').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const email = document.getElementById('login-email').value;
            const password = document.getElementById('login-password').value;
            const title = document.getElementById('login-title').textContent;

            // --- (MODIFIED) ตรวจสอบว่าอยู่ในโหมด "เข้าสู่ระบบ" หรือ "ลงทะเบียน" ---
            
            if (title.includes('เข้าสู่ระบบ')) {
                // --- LOGIN LOGIC ---
                // ค้นหาผู้ใช้ในฐานข้อมูลจำลอง
                const user = simulatedUsers.find(u => u.email === email && u.password === password);
                
                if (user) {
                    // *** (NEW) Check Status ***
                    if (user.status === 'suspended') {
                        alert('❌ บัญชีของคุณถูกระงับชั่วคราว กรุณาติดต่อผู้ดูแลระบบ');
                        return;
                    }
                    if (user.status === 'deactivated') {
                        alert('❌ บัญชีของคุณถูกปิดใช้งาน กรุณาติดต่อผู้ดูแลระบบ');
                        return;
                    }
                    // *** End Status Check ***

                    isLoggedIn = true;
                    currentUserEmail = user.email;
                    currentUserRole = user.role; // (NEW) Set role
                    
                    alert(`✅ เข้าสู่ระบบสำเร็จ! ยินดีต้อนรับ ${user.name || user.email}`);
                    document.getElementById('nav-login').innerHTML = '🚪 ออกจากระบบ';
                    updateNavVisibility(); // อัปเดต Nav
                    
                    if (user.role === 'admin') {
                        showSection('consignor-management'); 
                    } else {
                        showSection('customer-view'); 
                    }
                } else {
                    alert('❌ เข้าสู่ระบบไม่สำเร็จ! โปรดตรวจสอบอีเมล/รหัสผ่าน');
                }
                
            } else {
                // --- SIGN UP LOGIC (NEW) ---
                const firstName = document.getElementById('signup-firstname').value;
                const lastName = document.getElementById('signup-lastname').value;
                const phone = document.getElementById('signup-phone').value;
                const address = document.getElementById('signup-address').value;

                // ตรวจสอบ Input
                if (!firstName || !lastName || !phone || !address || !email || !password) {
                    alert("❌ กรุณากรอกข้อมูลลงทะเบียนให้ครบทุกช่อง");
                    return;
                }

                // ตรวจสอบว่ามีอีเมลนี้ในระบบหรือยัง
                if (simulatedUsers.find(u => u.email === email)) {
                    alert('❌ อีเมลนี้ถูกใช้งานแล้ว กรุณาใช้อีเมลอื่น หรือเข้าสู่ระบบ');
                    return;
                }
                
                // เพิ่มผู้ใช้ใหม่เข้า Array จำลอง
                const newUser = {
                    email: email,
                    password: password,
                    role: 'user', // บัญชีใหม่เป็น 'user' เสมอ
                    name: firstName,
                    lastName: lastName,
                    phone: phone,
                    address: address,
                    status: 'active' // (NEW) สถานะเริ่มต้น
                };
                simulatedUsers.push(newUser);
                
                console.log("New user registered:", newUser);
                console.log("Current user list:", simulatedUsers);
                
                alert(`✅ ลงทะเบียนสำเร็จ! ยินดีต้อนรับ ${firstName} (บัญชี ${email})\nคุณสามารถเข้าสู่ระบบได้เลย`);
                
                // สลับกลับไปหน้าล็อกอิน และล้างฟอร์ม
                switchForm(e, true); // (true = บังคับกลับไปหน้า Login)
                document.getElementById('login-form').reset(); 
            }
        });

        function toggleLogin() {
            if (isLoggedIn) {
                // Logout Logic
                isLoggedIn = false;
                currentUserEmail = null; // ล้างค่าผู้ใช้
                currentUserRole = 'guest'; // (NEW) รีเซ็ต Role
                document.getElementById('nav-login').innerHTML = '🔒 เข้าสู่ระบบ';
                alert('ออกจากระบบเรียบร้อยแล้ว');
                updateNavVisibility(); // อัปเดต Nav
                showSection('home-view');
            } else {
                // Go to Login Page
                showSection('login-view');
            }
        }

        // (MODIFIED) อัปเดตฟังก์ชันสลับฟอร์ม
        function switchForm(e, forceToLogin = false) {
            if(e) e.preventDefault(); 
            
            const title = document.getElementById('login-title');
            const toggleText = document.getElementById('toggle-form-text');
            const submitButton = document.getElementById('auth-submit-button');
            const signupFields = document.getElementById('signup-fields'); // (NEW)
            
            const signupFirstname = document.getElementById('signup-firstname');
            const signupLastname = document.getElementById('signup-lastname');
            const signupPhone = document.getElementById('signup-phone');
            const signupAddress = document.getElementById('signup-address');

            if (title.textContent.includes('เข้าสู่ระบบ') && !forceToLogin) {
                // --- Switch to Signup ---
                title.textContent = 'ลงทะเบียน (จำลอง)';
                toggleText.textContent = 'มีบัญชีอยู่แล้ว?';
                submitButton.textContent = 'ลงทะเบียน';
                signupFields.style.display = 'block'; // (NEW) Show fields
                
                // (NEW) ทำให้ช่องลงทะเบียนจำเป็น
                signupFirstname.required = true;
                signupLastname.required = true;
                signupPhone.required = true;
                signupAddress.required = true;
            } else {
                // --- Switch back to Login ---
                title.textContent = 'เข้าสู่ระบบ (จำลอง)';
                toggleText.textContent = 'ยังไม่มีบัญชี?';
                submitButton.textContent = 'เข้าสู่ระบบ';
                signupFields.style.display = 'none'; // (NEW) Hide fields
                
                // (NEW) ทำให้ช่องลงทะเบียนไม่จำเป็น (สำหรับการ Login)
                signupFirstname.required = false;
                signupLastname.required = false;
                signupPhone.required = false;
                signupAddress.required = false;
            }
        }

        // *** (NEW) 3. Profile Page Logic ***
        function renderProfilePage() {
            if (!isLoggedIn || !currentUserEmail) {
                showSection('login-view');
                return;
            }
            
            // (MODIFIED) ออกจากโหมดแก้ไขทุกครั้งที่โหลดหน้า
            toggleProfileEdit(false);

            // 1. Find User Data
            const user = simulatedUsers.find(u => u.email === currentUserEmail);
            if (!user) {
                console.error("Could not find logged in user data.");
                return;
            }

            // 2. Find Order Data
            const userOrders = orders.filter(o => o.customerName === currentUserEmail);
            
            // 3. Calculate Stats
            const totalOrders = userOrders.length;
            const completedOrders = userOrders.filter(o => o.isCompleted).length;
            const pendingOrders = totalOrders - completedOrders;

            // 4. Map Role to Thai Text
            let roleText = "ไม่ทราบสถานะ";
            if (user.role === 'admin') {
                roleText = "ผู้ดูแลระบบ (Admin)";
            } else if (user.role === 'user') {
                roleText = "ผู้ใช้ทั่วไป (User)";
            }

            // 5. Populate Profile Card (View mode)
            document.getElementById('profile-email').textContent = user.email || "ไม่มีข้อมูล";
            document.getElementById('profile-role').textContent = roleText;
            document.getElementById('profile-name').textContent = `${user.name || ''} ${user.lastName || ''}`.trim() || "ไม่มีข้อมูล";
            document.getElementById('profile-phone').textContent = user.phone || "ไม่มีข้อมูล";
            document.getElementById('profile-address').textContent = user.address || "ไม่มีข้อมูล";

            // 6. Populate Stats Card
            document.getElementById('profile-total-orders').textContent = totalOrders;
            document.getElementById('profile-completed-orders').textContent = completedOrders;
            document.getElementById('profile-pending-orders').textContent = pendingOrders;
        }

        // *** (NEW) 3.1 Profile Page Edit Functions ***
        function toggleProfileEdit(isEditing) {
            // Toggle visibility of view spans vs edit inputs
            document.querySelectorAll('.profile-view').forEach(el => el.style.display = isEditing ? 'none' : 'block');
            document.querySelectorAll('.profile-edit').forEach(el => el.style.display = isEditing ? 'block' : 'none');
            
            // Toggle visibility of buttons
            document.getElementById('btn-edit-profile').style.display = isEditing ? 'none' : 'inline-block';
            document.getElementById('btn-save-profile').style.display = isEditing ? 'inline-block' : 'none';
            document.getElementById('btn-cancel-profile').style.display = isEditing ? 'inline-block' : 'none';

            if (isEditing) {
                // Load current data into edit fields
                const user = simulatedUsers.find(u => u.email === currentUserEmail);
                if (!user) return;
                
                document.getElementById('profile-edit-firstname').value = user.name || '';
                document.getElementById('profile-edit-lastname').value = user.lastName || '';
                document.getElementById('profile-edit-phone').value = user.phone || '';
                document.getElementById('profile-edit-address').value = user.address || '';
            }
        }

        function saveProfileEdit() {
            const userIndex = simulatedUsers.findIndex(u => u.email === currentUserEmail);
            if (userIndex === -1) return;

            // Save new data back to the array
            simulatedUsers[userIndex].name = document.getElementById('profile-edit-firstname').value;
            simulatedUsers[userIndex].lastName = document.getElementById('profile-edit-lastname').value;
            simulatedUsers[userIndex].phone = document.getElementById('profile-edit-phone').value;
            simulatedUsers[userIndex].address = document.getElementById('profile-edit-address').value;

            alert('✅ บันทึกข้อมูลส่วนตัวเรียบร้อยแล้ว');
            
            // Exit edit mode and refresh profile page
            toggleProfileEdit(false);
            renderProfilePage();
        }


        // *** (NEW) 3.2 Admin User Management Functions ***
        function renderUserManagement() {
            const tableBody = document.getElementById('user-management-table-body');
            tableBody.innerHTML = ''; // Clear existing table

            simulatedUsers.forEach(user => {
                // Admin shouldn't be able to edit themselves
                if (user.role === 'admin') return; 

                const tr = document.createElement('tr');
                
                let statusText, suspendClass, suspendText, deactivateClass, deactivateText;
                
                // Determine status and button text
                switch (user.status) {
                    case 'active':
                        statusText = '<span style="color: green; font-weight: bold;">ใช้งานปกติ</span>';
                        suspendClass = 'btn-suspend';
                        suspendText = 'ระงับบัญชี';
                        deactivateClass = 'btn-deactivate';
                        deactivateText = 'ปิดใช้งาน';
                        break;
                    case 'suspended':
                        statusText = '<span style="color: #FFC107; font-weight: bold;">ถูกระงับ</span>';
                        suspendClass = 'btn-suspend active';
                        suspendText = 'ยกเลิกระงับ';
                        deactivateClass = 'btn-deactivate';
                        deactivateText = 'ปิดใช้งาน';
                        break;
                    case 'deactivated':
                        statusText = '<span style="color: #dc3545; font-weight: bold;">ปิดใช้งาน</span>';
                        suspendClass = 'btn-suspend active'; // Cannot unsuspend a deactivated account
                        suspendText = 'ระงับ';
                        deactivateClass = 'btn-deactivate active';
                        deactivateText = 'เปิดใช้งาน';
                        break;
                }

                tr.innerHTML = `
                    <td>${user.email}</td>
                    <td>${user.name || ''} ${user.lastName || ''}</td>
                    <td>${user.role}</td>
                    <td>${statusText}</td>
                    <td>
                        <button class="secondary ${suspendClass}" style="margin-right: 5px; margin-bottom: 5px;" onclick="adminToggleUserStatus('${user.email}', 'suspend')">${suspendText}</button>
                        <button class="secondary ${deactivateClass}" style="margin-bottom: 5px;" onclick="adminToggleUserStatus('${user.email}', 'deactivate')">${deactivateText}</button>
                    </td>
                `;
                tableBody.appendChild(tr);
            });
        }

        function adminToggleUserStatus(email, action) {
            const userIndex = simulatedUsers.findIndex(u => u.email === email);
            if (userIndex === -1) return;
            
            const user = simulatedUsers[userIndex];

            if (action === 'suspend') {
                if (user.status === 'suspended') {
                    user.status = 'active';
                    alert(`ปลดระงับบัญชี ${email} เรียบร้อยแล้ว`);
                } else if (user.status === 'active') {
                    user.status = 'suspended';
                    alert(`ระงับบัญชี ${email} เรียบร้อยแล้ว`);
                } else {
                    alert(`ไม่สามารถระงับบัญชีที่ถูกปิดใช้งาน`);
                }
            }
            
            if (action === 'deactivate') {
                if (user.status === 'deactivated') {
                    user.status = 'active';
                    alert(`เปิดใช้งานบัญชี ${email} เรียบร้อยแล้ว`);
                } else {
                    user.status = 'deactivated';
                    alert(`ปิดใช้งานบัญชี ${email} เรียบร้อยแล้ว`);
                }
            }

            renderUserManagement(); // Refresh the table
        }

        // *** 4. Home View Logic (MODIFIED) ***
        function renderHomeFeaturedProducts() {
            const listElement = document.getElementById('home-featured-products');
            listElement.innerHTML = '';
            
            // *** กรองเฉพาะสินค้าที่ isFeatured = true ***
            const featuredProducts = products.filter(p => p.isFeatured === true); 
            
            if (featuredProducts.length === 0) {
                listElement.innerHTML = '<p style="color: #666;">ยังไม่มีสินค้าแนะนำในขณะนี้</p>';
                return;
            }
            
            featuredProducts.forEach(product => {
                const stockStatus = product.stock <= 5 && product.stock > 0 ? `<span style="color: var(--primary-red); font-weight: bold;">เหลือ ${product.stock} ชิ้น (ใกล้หมด!)</span>` : `คงเหลือ: ${product.stock} ชิ้น`;
                
                const card = document.createElement('div');
                card.className = 'product-card';
                card.innerHTML = `
                    <img src="${product.imageURL}" alt="${product.name}" onerror="this.onerror=null; this.src='https://i.ibb.co/L84kQcQ/placeholder.jpg';" loading="lazy">
                    <h3>${product.name}</h3>
                    <p class="seller-info">ขายโดย: ${product.consignor}</p>
                    <p class="price">${product.price.toFixed(2)} บาท</p>
                    <button class="primary" ${product.stock === 0 ? 'disabled' : ''} onclick="addToCart(${product.id}); showSection('customer-view')">
                        ${product.stock === 0 ? 'สินค้าหมด' : 'เพิ่มลงตะกร้า'}
                    </button>
                `;
                listElement.appendChild(card);
            });
        }


        // *** 5. Customer View Logic (Marketplace) ***

        function renderCustomerProducts() {
            const listElement = document.getElementById('customer-product-list');
            listElement.innerHTML = '';
            
            if (products.length === 0) {
                listElement.innerHTML = '<p>ยังไม่มีสินค้าใน Marketplace</p>';
                return;
            }

            products.forEach(product => {
                const stockStatus = product.stock <= 5 && product.stock > 0 ? `<span style="color: var(--primary-red); font-weight: bold;">เหลือ ${product.stock} ชิ้น (ใกล้หมด!)</span>` : `คงเหลือ: ${product.stock} ชิ้น`;
                
                const card = document.createElement('div');
                card.className = 'product-card';
                // *** ผู้ใช้ทั่วไป (Customer) จะไม่เห็นปุ่มแก้ไข/ลบ ***
                card.innerHTML = `
                    <img src="${product.imageURL}" alt="${product.name}" onerror="this.onerror=null; this.src='https://i.ibb.co/L84kQcQ/placeholder.jpg';" loading="lazy">
                    <h3>${product.name}</h3>
                    <p class="seller-info">ขายโดย: ${product.consignor}</p>
                    <p>${product.description}</p>
                    <p>${stockStatus}</p>
                    <p class="price">${product.price.toFixed(2)} บาท</p>
                    <button class="primary" ${product.stock === 0 ? 'disabled' : ''} onclick="addToCart(${product.id})">
                        ${product.stock === 0 ? 'สินค้าหมด' : 'เพิ่มลงตะกร้า'}
                    </button>
                `;
                listElement.appendChild(card);
            });
            renderCart();
        }

        function addToCart(productId) {
            const product = products.find(p => p.id === productId);
            if (!product || product.stock <= 0) return;

            const cartItem = cart.find(item => item.id === productId);

            if (cartItem) {
                if (cartItem.quantity < product.stock) {
                    cartItem.quantity++;
                } else {
                    alert(`สินค้า ${product.name} มีในสต็อกเหลือเพียง ${product.stock} ชิ้น`);
                    return;
                }
            } else {
                cart.push({ id: productId, name: product.name, price: product.price, quantity: 1, consignor: product.consignor });
            }
            renderCart();
        }

        function renderCart() {
            const cartItemsElement = document.getElementById('cart-items');
            const cartTotalElement = document.getElementById('cart-total');
            let total = 0;

            cartItemsElement.innerHTML = '';

            if (cart.length === 0) {
                cartItemsElement.innerHTML = '<p style="color: #666;">ไม่มีสินค้าในตะกร้า</p>';
            } else {
                const groupedCart = cart.reduce((acc, item) => {
                    const seller = item.consignor;
                    if (!acc[seller]) acc[seller] = [];
                    acc[seller].push(item);
                    return acc;
                }, {});

                for (const seller in groupedCart) {
                    const sellerTotal = groupedCart[seller].reduce((sum, item) => sum + item.price * item.quantity, 0);
                    total += sellerTotal;

                    const sellerSection = document.createElement('div');
                    sellerSection.className = 'cart-summary';
                    sellerSection.innerHTML = `<h4 style="color: var(--bright-blue); margin: 10px 0 5px 0;">จากร้าน: ${seller} (รวม: ${sellerTotal.toFixed(2)} บาท)</h4>`;
                    groupedCart[seller].forEach(item => {
                        const itemTotal = item.price * item.quantity;
                        const p = document.createElement('p');
                        p.innerHTML = `${item.name} (${item.price.toFixed(2)} x ${item.quantity}) = <strong>${itemTotal.toFixed(2)} บาท</strong>`;
                        sellerSection.appendChild(p);
                    });
                    cartItemsElement.appendChild(sellerSection);
                }
            }

            cartTotalElement.textContent = total.toFixed(2);
        }

        function checkout() {
            if (cart.length === 0) {
                alert("กรุณาเพิ่มสินค้าลงในตะกร้าก่อนดำเนินการชำระเงิน");
                return;
            }
            
            // (NEW) ตรวจสอบว่าล็อกอินหรือยัง
            if (!isLoggedIn) {
                alert("กรุณาเข้าสู่ระบบก่อนดำเนินการสั่งซื้อ");
                showSection('login-view');
                return;
            }

            const newOrderId = `TH${String(nextOrderId++).padStart(3, '0')}`;
            const orderTotal = cart.reduce((sum, item) => sum + item.price * item.quantity, 0);
            
            const customerName = currentUserEmail; // ใช้ Email ของคนที่ล็อกอินอยู่

            orders.push({
                id: newOrderId,
                items: JSON.parse(JSON.stringify(cart)), 
                total: orderTotal,
                customerName: customerName,
                status: "รอการจัดส่ง",
                isCompleted: false,
                date: new Date().toLocaleDateString('th-TH'),
                consignors: [...new Set(cart.map(c => products.find(p => p.id === c.id)?.consignor).filter(Boolean))] 
            });

            // Deduct stock
            cart.forEach(cartItem => {
                const product = products.find(p => p.id === cartItem.id);
                if (product) {
                    product.stock -= cartItem.quantity;
                }
            });

            alert(`✅ สั่งซื้อสำเร็จ! เลขที่พัสดุจำลอง: ${newOrderId}\nยอดรวม: ${orderTotal.toFixed(2)} บาท\nรายการนี้จะถูกจัดส่งจาก Marketplace ผ่านไปรษณีย์ไทย`);
            cart = [];
            renderCustomerProducts();
            renderHomeFeaturedProducts(); // อัปเดตสต็อกสินค้าที่แสดงในหน้าแรกด้วย
        }

        // *** 6. Catalog and Search Logic ***
        function renderCatalogProducts(productList = products) {
            const listElement = document.getElementById('catalog-product-list');
            listElement.innerHTML = '';

            if (productList.length === 0) {
                listElement.innerHTML = '<p>ไม่พบสินค้าตามเงื่อนไขที่ค้นหา</p>';
                return;
            }

            products.forEach(product => {
                const stockStatus = product.stock <= 5 && product.stock > 0 ? `<span style="color: var(--primary-red); font-weight: bold;">เหลือ ${product.stock} ชิ้น (ใกล้หมด!)</span>` : `คงเหลือ: ${product.stock} ชิ้น`;
                
                const card = document.createElement('div');
                card.className = 'product-card';
                // *** ผู้ใช้ทั่วไป (Catalog) จะไม่เห็นปุ่มแก้ไข/ลบ ***
                card.innerHTML = `
                    <img src="${product.imageURL}" alt="${product.name}" onerror="this.onerror=null; this.src='https://i.ibb.co/L84kQcQ/placeholder.jpg';" loading="lazy">
                    <h3>${product.name}</h3>
                    <p class="seller-info">ขายโดย: ${product.consignor}</p>
                    <p>${product.description}</p>
                    <p>${stockStatus}</p>
                    <p class="price">${product.price.toFixed(2)} บาท</p>
                    <button class="primary" ${product.stock === 0 ? 'disabled' : ''} onclick="addToCart(${product.id}); showSection('customer-view')">
                        ${product.stock === 0 ? 'สินค้าหมด' : 'เพิ่มลงตะกร้า'}
                    </button>
                `;
                listElement.appendChild(card);
            });
        }

        function searchProducts(searchTerm) {
            const lowerCaseSearch = searchTerm.toLowerCase().trim();
            if (lowerCaseSearch === '') {
                renderCatalogProducts(products);
                return;
            }

            const filteredProducts = products.filter(product => {
                const nameMatch = product.name.toLowerCase().includes(lowerCaseSearch);
                const descMatch = product.description.toLowerCase().includes(lowerCaseSearch);
                const consignorMatch = product.consignor.toLowerCase().includes(lowerCaseSearch);
                
                return nameMatch || descMatch || consignorMatch;
            });

            renderCatalogProducts(filteredProducts);
        }


        // *** 7. Commission Report Logic ***

        function calculateCommissionData() {
            const completedOrders = orders.filter(o => o.isCompleted);
            const summary = {};
            let totalCommission = 0;
            let totalPayout = 0;

            completedOrders.forEach(order => {
                order.items.forEach(item => {
                    const seller = item.consignor;
                    const revenue = item.price * item.quantity;
                    const commission = revenue * COMMISSION_RATE;
                    const payout = revenue - commission;

                    if (!summary[seller]) {
                        summary[seller] = {
                            sales: 0,
                            commission: 0,
                            payout: 0,
                            orders: 0
                        };
                    }

                    summary[seller].sales += revenue;
                    summary[seller].commission += commission;
                    summary[seller].payout += payout;
                    summary[seller].orders++; 
                    
                    totalCommission += commission;
                    totalPayout += payout;
                });
            });
            
            return { summary, completedOrdersCount: completedOrders.length, totalCommission, totalPayout };
        }

        function renderCommissionReport() {
            const data = calculateCommissionData();
            const summaryElement = document.getElementById('commission-summary');
            const countElement = document.getElementById('completed-orders-count');
            
            countElement.textContent = data.completedOrdersCount;
            summaryElement.innerHTML = '';

            if (data.completedOrdersCount === 0) {
                summaryElement.innerHTML = '<p>ยังไม่มีคำสั่งซื้อที่ส่งมอบสำเร็จเพื่อคำนวณค่าคอมมิชชั่น</p>';
                return;
            }

            let html = `
                <table style="width: 100%; border-collapse: collapse; text-align: left;">
                    <thead>
                        <tr style="background-color: var(--bright-blue); color: white;">
                            <th style="padding: 10px; border: 1px solid #FFF;">ร้านค้า</th>
                            <th style="padding: 10px; border: 1px solid #FFF;">ยอดขายรวม</th>
                            <th style="padding: 10px; border: 1px solid #FFF;">ค่าคอมมิชชั่น (10%)</th>
                            <th style="padding: 10px; border: 1px solid #FFF;">เงินที่ร้านค้าได้รับ</th>
                        </tr>
                    </thead>
                    <tbody>
            `;
            
            for (const seller in data.summary) {
                const s = data.summary[seller];
                html += `
                    <tr style="border-bottom: 1px solid #EEE;">
                        <td style="padding: 10px;"><strong>${seller}</strong> (${s.orders} คำสั่งซื้อ)</td>
                        <td style="padding: 10px;">${s.sales.toFixed(2)} บาท</td>
                        <td style="padding: 10px; color: var(--primary-red);">${s.commission.toFixed(2)} บาท</td>
                        <td style="padding: 10px; color: green; font-weight: bold;">${s.payout.toFixed(2)} บาท</td>
                    </tr>
                `;
            }

            html += `
                    </tbody>
                </table>
                <h3 style="margin-top: 20px;">สรุปรายได้รวม (บริษัท ต๋อยฮาไม่ จำกัด)</h3>
                <p>ค่าคอมมิชชั่นรวมที่ได้รับ: <strong style="color: var(--primary-red);">${data.totalCommission.toFixed(2)} บาท</strong></p>
                <p>รวมเงินที่ต้องจ่ายคืนร้านค้า: <strong style="color: green;">${data.totalPayout.toFixed(2)} บาท</strong></p>
            `;
            
            summaryElement.innerHTML = html;
        }


        // *** 8. Consignor Management Logic (ปรับปรุงสำหรับ Admin) ***

        document.getElementById('add-product-form').addEventListener('submit', function(e) {
            e.preventDefault();
            // นี่คือฟังก์ชันสำหรับ 'บันทึกสินค้าใหม่'
            
            const name = document.getElementById('product-name').value;
            const description = document.getElementById('product-description').value;
            const price = parseFloat(document.getElementById('product-price').value);
            const stock = parseInt(document.getElementById('product-stock').value);
            const consignor = document.getElementById('consignor-name').value;
            let imageURL = document.getElementById('product-image').value;

            if (isNaN(price) || isNaN(stock) || stock < 0 || price < 0 || !consignor) {
                alert("กรุณาตรวจสอบข้อมูลราคา/สต็อก และเลือกร้านค้าให้ถูกต้อง");
                return;
            }
            
            if (!imageURL) { // ถ้า URL ว่าง ให้ใช้ Placeholder
                imageURL = 'https://i.ibb.co/L84kQcQ/placeholder.jpg';
            }
            
            products.push({
                id: nextProductId++,
                name,
                description,
                price,
                stock,
                consignor,
                imageURL: imageURL,
                isFeatured: false // *** (NEW) เพิ่ม isFeatured เริ่มต้น ***
            });

            alert(`สินค้า "${name}" (ร้าน ${consignor}) ถูกเพิ่มเข้าสู่ Marketplace แล้ว`);
            this.reset();
            renderConsignorProducts();
            renderAllProductViews(); // อัปเดตทุกหน้า
        });
        
        // *** 8.1 ฟังก์ชันอัปเดต/ยกเลิก (สำหรับปุ่มใหม่) ***
        document.getElementById('btn-update-product').addEventListener('click', function() {
            const editingId = parseInt(document.getElementById('editing-product-id').value);
            if (!editingId) return;

            const productIndex = products.findIndex(p => p.id === editingId);
            if (productIndex === -1) return;

            // อัปเดตข้อมูลใน Array
            products[productIndex].name = document.getElementById('product-name').value;
            products[productIndex].description = document.getElementById('product-description').value;
            products[productIndex].price = parseFloat(document.getElementById('product-price').value);
            products[productIndex].stock = parseInt(document.getElementById('product-stock').value);
            products[productIndex].consignor = document.getElementById('consignor-name').value;
            products[productIndex].imageURL = document.getElementById('product-image').value || 'https://i.ibb.co/L84kQcQ/placeholder.jpg';
            // (isFeatured ไม่ถูกแก้ไขในฟอร์มนี้ จะถูกแก้โดยปุ่ม toggleFeatured เท่านั้น)

            alert("อัปเดตสินค้าเรียบร้อยแล้ว");
            cancelEditMode();
            renderConsignorProducts();
            renderAllProductViews(); // อัปเดตทุกหน้า
        });

        document.getElementById('btn-cancel-edit').addEventListener('click', function() {
            cancelEditMode();
        });

        function cancelEditMode() {
            document.getElementById('add-product-form').reset();
            document.getElementById('editing-product-id').value = '';
            
            // สลับปุ่มกลับเป็นโหมด "บันทึก"
            document.getElementById('btn-save-product').style.display = 'block';
            document.getElementById('btn-update-product').style.display = 'none';
            document.getElementById('btn-cancel-edit').style.display = 'none';
        }
        
        // *** 8.2 อัปเดต RenderConsignorProducts (แสดงปุ่ม Admin) ***
        function renderConsignorProducts() {
            const listElement = document.getElementById('consignor-product-list');
            listElement.innerHTML = '';
            
            if (products.length === 0) {
                listElement.innerHTML = '<p>ยังไม่มีสินค้าใน Marketplace</p>';
                return;
            }

            products.forEach(product => {
                const card = document.createElement('div');
                card.className = 'product-card';
                
                // *** (NEW) สร้างปุ่ม Featured ***
                const featureButtonText = product.isFeatured ? '✓ ยกเลิกติดดาว' : '⭐ ติดดาวสินค้า';
                const featureButtonClass = product.isFeatured ? 'btn-feature featured' : 'btn-feature';

                // *** (MODIFIED) เพิ่มปุ่ม Featured และจัดเรียงปุ่ม ***
                card.innerHTML = `
                    <img src="${product.imageURL}" alt="${product.name}" style="height: 100px; object-fit: contain;">
                    <h3>[ID: ${product.id}] ${product.name}</h3>
                    <p><strong>ร้านค้า:</strong> <span style="color: var(--bright-blue);">${product.consignor}</span></p>
                    <p><strong>ราคา:</strong> <span style="color: var(--primary-red);">${product.price.toFixed(2)} บาท</span></p>
                    <p><strong>คงเหลือ:</strong> ${product.stock} ชิ้น</p>
                    <button class="secondary" onclick="editProduct(${product.id})" style="margin-right: 5px; margin-bottom: 5px;">แก้ไขสินค้า</button>
                    <button class="secondary" onclick="deleteProduct(${product.id})" style="background-color: #666; border-color: #666; margin-right: 5px; margin-bottom: 5px;">ลบ</button>
                    <button class="${featureButtonClass}" onclick="toggleFeatured(${product.id})" style="margin-bottom: 5px;">${featureButtonText}</button>
                `;
                listElement.appendChild(card);
            });
        }
        
        // *** (NEW) 8.3 ฟังก์ชันสลับสถานะสินค้าแนะนำ (Admin only) ***
        function toggleFeatured(productId) {
            const product = products.find(p => p.id === productId);
            if (!product) return;

            // สลับสถานะ
            product.isFeatured = !product.isFeatured;

            if (product.isFeatured) {
                alert(`"${product.name}" ถูกกำหนดเป็นสินค้าแนะนำแล้ว`);
            } else {
                alert(`"${product.name}" ถูกยกเลิกจากการเป็นสินค้าแนะนำแล้ว`);
            }

            // Render หน้าร้าน (Home) และหน้า Admin ใหม่
            renderConsignorProducts();
            renderHomeFeaturedProducts();
        }

        // *** 8.4 อัปเดตฟังก์ชัน editProduct (ให้กรอกข้อมูลในฟอร์ม) ***
        function editProduct(productId) {
            const product = products.find(p => p.id === productId);
            if (!product) return;
            
            // 1. กรอกข้อมูลสินค้าลงในฟอร์ม
            document.getElementById('editing-product-id').value = product.id;
            document.getElementById('product-name').value = product.name;
            document.getElementById('product-description').value = product.description;
            document.getElementById('product-price').value = product.price;
            document.getElementById('product-stock').value = product.stock;
            document.getElementById('consignor-name').value = product.consignor;
            document.getElementById('product-image').value = product.imageURL;

            // 2. สลับปุ่ม
            document.getElementById('btn-save-product').style.display = 'none';
            document.getElementById('btn-update-product').style.display = 'block';
            document.getElementById('btn-cancel-edit').style.display = 'inline-block';
            
            // 3. เลื่อนจอขึ้นไปที่ฟอร์ม
            window.scrollTo(0, document.getElementById('add-product-form').offsetTop);
        }

        // *** 8.5 อัปเดตฟังก์ชัน deleteProduct (นำ confirm ออก) ***
        function deleteProduct(productId) {
            // นำกล่องยืนยัน (confirm) ออก เนื่องจากอาจไม่ทำงานใน Google Sites iFrame
            // การลบจะเกิดขึ้นทันที
            
            products = products.filter(p => p.id !== productId);
            alert("ลบสินค้าเรียบร้อยแล้ว");
            renderConsignorProducts();
            renderAllProductViews(); // อัปเดตทุกหน้า
        }
        
        // *** 8.6 ฟังก์ชัน helper ให้อัปเดตทุกหน้า ***
        function renderAllProductViews() {
            // อัปเดตหน้าอื่น ๆ ที่แสดงผลสินค้าด้วย
            renderHomeFeaturedProducts();
            renderCustomerProducts();
            renderCatalogProducts();
        }

        
        // *** 9. Shipping & Tracking Logic (Thai Post) ***

        function renderOrderList() {
            const orderListElement = document.getElementById('order-list');
            orderListElement.innerHTML = '';
            
            // *** (MODIFIED) ใช้ Role แทน Email ***
            const isAdmin = (isLoggedIn && currentUserRole === 'admin');
            
            // กรองออเดอร์: Admin เห็นทั้งหมด, User เห็นเฉพาะของตัวเอง
            const userOrders = isAdmin ? orders : orders.filter(o => o.customerName === currentUserEmail);

            if (userOrders.length === 0) {
                orderListElement.innerHTML = '<p style="color: #666;">ยังไม่มีรายการสั่งซื้อรอการจัดส่ง</p>';
                return;
            }

            userOrders.forEach(order => {
                const totalItems = order.items.reduce((sum, item) => sum + item.quantity, 0);
                const orderDetail = order.items.map(item => `${item.name} (x${item.quantity})`).join(', ');

                // สร้างปุ่ม Admin (ถ้าเป็น Admin)
                let adminButtons = '';
                if (isAdmin) {
                     adminButtons = !order.isCompleted ? `
                        <button onclick="updateShippingStatus('${order.id}', 'สินค้าถูกรับเข้าระบบ (ฝากส่ง Thai Post)', false)" class="primary" style="background-color: #FF8C00; margin-right: 5px;">📦 รับเข้าระบบ</button>
                        <button onclick="updateShippingStatus('${order.id}', 'อยู่ระหว่างการนำจ่าย (นำส่งโดยบุรุษไปรษณีย์)', false)" class="primary" style="background-color: var(--bright-blue); margin-right: 5px;">🚚 นำจ่าย</button>
                        <button onclick="updateShippingStatus('${order.id}', 'ส่งมอบสำเร็จ', true)" class="secondary" style="background-color: #28A745;">✅ ส่งมอบสำเร็จ (Final)</button>
                    ` : `<p style="color: green; font-weight: bold;">คำสั่งซื้อนี้เสร็จสมบูรณ์แล้ว</p>`;
                } else {
                    // ถ้าเป็น User ธรรมดา และออเดอร์เสร็จแล้ว
                    adminButtons = order.isCompleted ? `<p style="color: green; font-weight: bold;">คำสั่งซื้อนี้เสร็จสมบูรณ์แล้ว</p>` : '';
                }

                const item = document.createElement('div');
                item.className = 'product-card';
                item.style.backgroundColor = '#F7F7F7';
                item.innerHTML = `
                    <p style="color: var(--primary-red); font-weight: bold;">หมายเลขพัสดุ (จำลอง): ${order.id}</p>
                    <p><strong>สถานะ:</strong> <span style="color: ${order.isCompleted ? 'green' : 'var(--bright-blue)'}; font-weight: bold;">${order.status}</span></p>
                    <p><strong>ร้านค้าที่เกี่ยวข้อง:</strong> ${order.consignors.join(', ')}</p>
                    <p>ยอดรวม: ${order.total.toFixed(2)} บาท (${totalItems} รายการ)</p>
                    <p style="font-size: 0.9em;">**รายละเอียด:** ${orderDetail}</p>
                    ${adminButtons}
                `;
                orderListElement.appendChild(item);
            });
        }

        function updateShippingStatus(orderId, newStatus, isCompleted) {
            const order = orders.find(o => o.id === orderId);
            if (order) {
                order.status = newStatus;
                if (isCompleted !== undefined) {
                    order.isCompleted = isCompleted;
                }
                alert(`อัปเดตสถานะคำสั่งซื้อ ${orderId} เป็น: ${newStatus}`);
                renderOrderList();
                renderCommissionReport(); // Update report when status changes to completed
            }
        }

        function trackShipment() {
            const trackingId = document.getElementById('tracking-input').value.trim();
            const resultElement = document.getElementById('tracking-result');
            resultElement.innerHTML = '';

            if (trackingId === '') {
                resultElement.innerHTML = '<p style="color: var(--primary-red);">กรุณาป้อนหมายเลขพัสดุ</p>';
                return;
            }

            const order = orders.find(o => o.id === trackingId);

            if (order) {
                // *** (MODIFIED) ใช้ Role แทน Email ***
                const isAdmin = (isLoggedIn && currentUserRole === 'admin');
                
                // ถ้าไม่ใช่ Admin และ ไม่ใช่เจ้าของออเดอร์
                if (!isAdmin && order.customerName !== currentUserEmail) {
                     resultElement.innerHTML = `<p style="color: var(--primary-red);">ไม่พบหมายเลขพัสดุ <strong>${trackingId}</strong> ในระบบของคุณ</p>`;
                     return;
                }
                
                // ถ้าเป็น Admin หรือ เจ้าของ
                resultElement.innerHTML = `
                    <p style="font-size: 1.1em; color: var(--primary-red);">**หมายเลขพัสดุ:** ${order.id} (จำลอง)</p>
                    <p><strong>สถานะล่าสุด:</strong> <strong style="color: ${order.isCompleted ? 'green' : 'var(--bright-blue)'};">${order.status}</strong></p>
                    <p>สินค้าจากร้าน: ${order.consignors.join(', ')}</p>
                    <p style="font-size: 0.9em;">ดำเนินการจัดส่งโดย <span style="font-weight: bold;">ไปรษณีย์ไทย</span> ผ่าน THAIPOST MARKETPLACE</p>
                `;
            } else {
                resultElement.innerHTML = `<p style="color: var(--primary-red);">ไม่พบหมายเลขพัสดุ <strong>${trackingId}</strong> ในระบบ</p>`;
            }
        }

        // *** 10. Initialization ***
        document.addEventListener('DOMContentLoaded', () => {
            updateNavVisibility(); // ซ่อนแท็บ Admin/User ในตอนเริ่มต้น
            showSection('home-view'); // ตั้งให้หน้าแรกเป็นหน้าเริ่มต้น
        });
    </script>
</body>
</html>
