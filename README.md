<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>الحقني | المساعدة العاجلة على الطريق</title>
    <!-- Fonts & Icons -->
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Cairo', sans-serif;
            background: radial-gradient(ellipse at 30% 40%, #0a0f1e, #03050b);
            color: #eef5ff;
            scroll-behavior: smooth;
            overflow-x: hidden;
            position: relative;
        }

        /* Stars background dynamic */
        .stars {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 0;
        }

        .star {
            position: absolute;
            background-color: #fff;
            border-radius: 50%;
            opacity: 0.7;
            animation: twinkle 3s infinite alternate;
            box-shadow: 0 0 8px rgba(255,255,200,0.8);
        }

        @keyframes twinkle {
            0% { opacity: 0.2; transform: scale(1);}
            100% { opacity: 1; transform: scale(1.2);}
        }

        /* Main content layer */
        .container {
            position: relative;
            z-index: 2;
            max-width: 1300px;
            margin: 0 auto;
            padding: 1rem 2rem;
        }

        /* Glowing text & borders */
        .glow-text {
            text-shadow: 0 0 6px #b0f0ff, 0 0 12px #4effdc, 0 0 20px #00a6c4;
            transition: all 0.3s ease;
        }

        h1, h2, h3, .logo {
            font-weight: 700;
        }

        h2 {
            font-size: 2.2rem;
            margin-bottom: 1rem;
            border-right: 4px solid #0ff;
            padding-right: 1rem;
            display: inline-block;
            text-shadow: 0 0 5px cyan;
        }

        /* Navigation */
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            background: rgba(0,0,0,0.65);
            backdrop-filter: blur(12px);
            border-radius: 60px;
            padding: 0.8rem 2rem;
            margin-bottom: 2rem;
            border: 1px solid rgba(0,255,255,0.2);
            box-shadow: 0 0 20px rgba(0,180,220,0.2);
        }

        .logo i {
            font-size: 2rem;
            color: #0ff;
            margin-left: 0.5rem;
        }

        .nav-links {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
        }

        .nav-links a {
            color: #eef5ff;
            text-decoration: none;
            font-weight: 500;
            padding: 0.5rem 1rem;
            border-radius: 40px;
            transition: 0.2s;
            letter-spacing: 0.5px;
            position: relative;
        }

        .nav-links a:hover, .nav-links a.active {
            background: rgba(0, 255, 255, 0.2);
            text-shadow: 0 0 6px cyan;
            box-shadow: 0 0 10px rgba(0,255,255,0.4);
        }

        /* Page sections */
        .page {
            display: none;
            animation: fadeSlide 0.5s ease-out;
            background: rgba(8, 12, 25, 0.55);
            backdrop-filter: blur(2px);
            border-radius: 2rem;
            padding: 2rem;
            margin-top: 1rem;
            border: 1px solid rgba(0, 255, 255, 0.25);
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
        }

        .active-page {
            display: block;
        }

        @keyframes fadeSlide {
            from { opacity: 0; transform: translateY(15px);}
            to { opacity: 1; transform: translateY(0);}
        }

        /* Cards grid */
        .services-grid, .features-grid, .faq-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 1.8rem;
            margin-top: 2rem;
        }

        .card {
            background: rgba(0, 0, 0, 0.65);
            backdrop-filter: blur(5px);
            border-radius: 1.5rem;
            padding: 1.5rem;
            transition: 0.25s;
            border: 1px solid rgba(0, 255, 255, 0.3);
            box-shadow: 0 8px 20px rgba(0,0,0,0.5);
        }

        .card i {
            font-size: 2.5rem;
            color: #0ff;
            margin-bottom: 1rem;
        }

        .card h3 {
            margin-bottom: 0.8rem;
            font-size: 1.5rem;
        }

        .card p {
            color: #ccddf8;
            line-height: 1.5;
        }

        .card:hover {
            transform: translateY(-8px);
            border-color: #0ff;
            box-shadow: 0 0 25px rgba(0,255,255,0.4);
        }

        /* Buttons */
        .btn {
            background: linear-gradient(95deg, #00b8b0, #0088aa);
            border: none;
            padding: 0.7rem 1.4rem;
            border-radius: 2rem;
            font-family: 'Cairo', sans-serif;
            font-weight: bold;
            color: white;
            cursor: pointer;
            transition: 0.2s;
            box-shadow: 0 0 8px cyan;
            font-size: 1rem;
        }

        .btn-outline {
            background: transparent;
            border: 1px solid #0ff;
            color: #0ff;
        }

        .btn:hover {
            transform: scale(1.02);
            background: #00d4ff;
            color: #010101;
            box-shadow: 0 0 15px cyan;
        }

        /* Form */
        .request-form input, .request-form select, .request-form textarea {
            width: 100%;
            padding: 0.8rem;
            margin: 0.8rem 0;
            background: rgba(0,0,0,0.6);
            border: 1px solid #0ff;
            border-radius: 1rem;
            color: white;
            font-family: 'Cairo', sans-serif;
        }

        /* footer */
        footer {
            text-align: center;
            margin-top: 3rem;
            padding: 1.5rem;
            border-top: 1px solid rgba(0,255,255,0.3);
            font-size: 0.8rem;
        }

        .order-list {
            background: rgba(0,0,0,0.5);
            border-radius: 1rem;
            padding: 1rem;
        }

        .order-item {
            border-bottom: 1px solid cyan;
            padding: 1rem;
            margin-bottom: 0.5rem;
        }

        /* Responsive */
        @media (max-width: 780px) {
            .container { padding: 1rem; }
            nav { flex-direction: column; gap: 1rem; }
            h2 { font-size: 1.8rem; }
        }

        .status-badge {
            display: inline-block;
            padding: 0.2rem 1rem;
            border-radius: 30px;
            font-size: 0.75rem;
            font-weight: bold;
        }
        .status-pending { background: #f0b400; color: #1e1a00; }
        .status-progress { background: #0a6eff; color: white; }
        .status-completed { background: #00cc88; color: #002b1a; }
        .status-cancelled { background: #aa2e4e; color: white; }
    </style>
</head>
<body>
<div class="stars" id="starsContainer"></div>
<div class="container">
    <nav>
        <div class="logo glow-text"><i class="fas fa-car-crash"></i> الحقني</div>
        <div class="nav-links" id="navLinks">
            <a href="#" data-page="home" class="active">🏠 الرئيسية</a>
            <a href="#" data-page="services">🛠️ الخدمات</a>
            <a href="#" data-page="request">📢 طلب مساعدة</a>
            <a href="#" data-page="myorders">📋 طلباتي</a>
            <a href="#" data-page="features">✨ الميزات</a>
            <a href="#" data-page="faq">❓ الأسئلة</a>
            <a href="#" data-page="contact">📞 تواصل</a>
        </div>
    </nav>

    <!-- PAGE: Home -->
    <div id="home" class="page active-page">
        <h2 class="glow-text">⭐ مرحباً بك في الحقني</h2>
        <p style="font-size:1.2rem; margin-top:1rem;">تطبيق المساعدة العاجلة للسيارات والشاحنات في الجزائر — 24 ساعة، سرعة فائقة، خدمات متكاملة.</p>
        <div class="services-grid" style="margin-top:2rem;">
            <div class="card"><i class="fas fa-wrench"></i><h3>ميكانيكي متنقل</h3><p>إصلاح عاجل في موقع العطل.</p></div>
            <div class="card"><i class="fas fa-gas-pump"></i><h3>توصيل وقود</h3><p>نفذ البنزين؟ نوصل لك الوقود أينما كنت.</p></div>
            <div class="card"><i class="fas fa-oil-can"></i><h3>زيوت وقطع غيار</h3><p>توصيل الزيوت المناسبة وقطع الغيار.</p></div>
            <div class="card"><i class="fas fa-truck"></i><h3>ديبناج (سحب)</h3><p>شاحنة رفع لنقل سيارتك إلى أقرب ورشة.</p></div>
        </div>
        <div style="margin-top:2rem;text-align:center;">
            <button class="btn" id="quickRequestBtn">📱 اطلب المساعدة الآن</button>
        </div>
    </div>

    <!-- PAGE: Services -->
    <div id="services" class="page">
        <h2 class="glow-text">🚛 جميع الخدمات</h2>
        <div class="services-grid">
            <div class="card"><i class="fas fa-tools"></i><h3>إصلاح ميكانيكي</h3><p>ميكانيكي محترف يصل إلى موقعك خلال دقائق.</p></div>
            <div class="card"><i class="fas fa-tint"></i><h3>توصيل الزيوت</h3><p>زيت محرك, ناقل حركة, فرامل حسب الطلب.</p></div>
            <div class="card"><i class="fas fa-charging-station"></i><h3>توصيل الوقود</h3><p>بنزين، ديزل، غاز — نصل لأي مكان.</p></div>
            <div class="card"><i class="fas fa-car-battery"></i><h3>بطارية وقطع غيار</h3><p>توصيل بطاريات، إطارات، قطع غيار أصلية.</p></div>
            <div class="card"><i class="fas fa-map-marked-alt"></i><h3>توجيه إلى ورشات</h3><p>أقرب ورشة تصليح معتمدة.</p></div>
            <div class="card"><i class="fas fa-truck-moving"></i><h3>خدمة السحب</h3><p>سيارة ديبناج مجهزة لسحب جميع أنواع المركبات.</p></div>
        </div>
    </div>

    <!-- PAGE: Request Help -->
    <div id="request" class="page">
        <h2 class="glow-text">📢 طلب مساعدة فورية</h2>
        <div class="card" style="max-width:700px; margin:1rem auto;">
            <form id="helpRequestForm">
                <label>نوع الخدمة *</label>
                <select id="serviceType" required>
                    <option value="ميكانيكي متنقل">🔧 ميكانيكي متنقل</option>
                    <option value="توصيل وقود">⛽ توصيل وقود</option>
                    <option value="توصيل زيوت">🛢️ توصيل زيوت</option>
                    <option value="قطع غيار">⚙️ قطع غيار</option>
                    <option value="ديبناج (سحب)">🚚 ديبناج / سحب</option>
                    <option value="توجيه إلى ورشة">🗺️ توجيه إلى ورشة</option>
                </select>
                <label>وصف المشكلة (اختياري)</label>
                <textarea rows="2" id="problemDesc" placeholder="مثال: السيارة لا تدور، صوت غريب..."></textarea>
                <label>رقم هاتفك *</label>
                <input type="tel" id="phoneReq" placeholder="05xxxxxxxx" required>
                <label>الموقع الجغرافي</label>
                <div style="display:flex; gap:0.5rem; flex-wrap:wrap;">
                    <button type="button" id="getLocationBtn" class="btn btn-outline" style="flex:1"><i class="fas fa-location-dot"></i> 📍 تحديد موقعي تلقائي</button>
                    <input type="text" id="locationLink" placeholder="رابط الخريطة أو العنوان" style="flex:2">
                </div>
                <p id="locationMsg" style="font-size:0.8rem; color:#aaf"></p>
                <button type="submit" class="btn" style="width:100%; margin-top:1rem;">✨ إرسال الطلب ✨</button>
            </form>
        </div>
        <p class="glow-text" style="text-align:center;">⚡ هز هاتفك للإبلاغ السريع (تمتع بالميزة)</p>
    </div>

    <!-- PAGE: My Orders (طلباتي) -->
    <div id="myorders" class="page">
        <h2 class="glow-text">📋 طلباتي السابقة والحالية</h2>
        <div id="ordersContainer" class="order-list">
            <p style="text-align:center;">✨ سيتم عرض طلباتك هنا بعد تقديم طلب ✨</p>
        </div>
        <button id="refreshOrdersBtn" class="btn btn-outline" style="margin-top:1rem;">🔄 تحديث الطلبات</button>
    </div>

    <!-- PAGE: Features -->
    <div id="features" class="page">
        <h2 class="glow-text">💎 مميزات التطبيق الفريدة</h2>
        <div class="features-grid">
            <div class="card"><i class="fas fa-bolt"></i><h3>هز الهاتف للتبليغ</h3><p>هز جهازك لفتح طلب مساعدة بسرعة البرق.</p></div>
            <div class="card"><i class="fas fa-moon"></i><h3>وضع ليلي / نهاري</h3><p>واجهة مريحة مع نجوم متلألئة.</p></div>
            <div class="card"><i class="fas fa-chart-line"></i><h3>متابعة الطلبات</h3><p>حالة الطلب: انتظار، تنفيذ، مكتمل، ملغي.</p></div>
            <div class="card"><i class="fas fa-map-pin"></i><h3>GPS دقيق</h3><p>نسخ رابط موقع Google Maps بدقة عالية.</p></div>
            <div class="card"><i class="fas fa-shield-alt"></i><h3>أمان وخصوصية</h3><p>بياناتك مشفرة عبر Supabase (نظام متقدم).</p></div>
            <div class="card"><i class="fas fa-headset"></i><h3>دعم مباشر 24/7</h3><p>قنوات اتصال سريعة عبر البريد والإبلاغ عن مشكلة.</p></div>
        </div>
    </div>

    <!-- PAGE: FAQ -->
    <div id="faq" class="page">
        <h2 class="glow-text">❓ الأسئلة الشائعة</h2>
        <div class="faq-grid">
            <div class="card"><h3>❓ كيف أطلب المساعدة؟</h3><p>اختر الخدمة من صفحة الطلب، حدد موقعك، ثم أرسل الطلب.</p></div>
            <div class="card"><h3>⏱️ كم سرعة الاستجابة؟</h3><p>فريقنا المنتشر يستجيب خلال 15-30 دقيقة حسب الموقع.</p></div>
            <div class="card"><h3>💰 هل التطبيق مجاني؟</h3><p>نعم، جميع الخدمات الأساسية مجانية، رسوم الخدمات تحددها الجهة المقدمة.</p></div>
            <div class="card"><h3>🔧 ماذا لو احتجت ميكانيكي متخصص؟</h3><p>نوفر ميكانيكيين مدربين مع قطع الغيار إن أمكن.</p></div>
            <div class="card"><h3>🚗 هل تغطيون جميع مناطق الجزائر؟</h3><p>نعمل حالياً في كبرى المدن والطرق السريعة، والتوسع مستمر.</p></div>
            <div class="card"><h3>📱 كيف أتابع طلبي؟</h3><p>من صفحة "طلباتي" تجد كل التفاصيل والحالة المحدثة.</p></div>
            <div class="card"><h3>🔄 هل يمكن إلغاء الطلب؟</h3><p>نعم، قبل وصول المساعدة يمكنك إلغاء الطلب عبر التواصل مع الدعم.</p></div>
            <div class="card"><h3>📧 كيف أتواصل مع الدعم؟</h3><p>يمكنك استخدام صفحة "تواصل" أو إرسال بريد إلكتروني.</p></div>
        </div>
    </div>

    <!-- PAGE: Contact & Support -->
    <div id="contact" class="page">
        <h2 class="glow-text">📧 تواصل مع فريق الحقني</h2>
        <div class="card" style="max-width:600px; margin:1rem auto;">
            <p><i class="fas fa-envelope"></i> البريد الإلكتروني: support@alhaqni.com</p>
            <p><i class="fas fa-phone-alt"></i> الخط الساخن: 1555 (رقم وهمي للتجربة)</p>
            <p><i class="fab fa-whatsapp"></i> واتساب: +213 123 456 789</p>
            <hr style="margin:1rem 0; border-color:cyan;">
            <h3>الإبلاغ عن مشكلة أو اقتراح</h3>
            <form id="reportIssue">
                <input type="text" placeholder="اسمك" id="reportName">
                <textarea rows="3" placeholder="تفاصيل المشكلة..." id="reportMsg"></textarea>
                <button type="submit" class="btn">إرسال التبليغ 🌟</button>
            </form>
            <p style="font-size:0.8rem; margin-top:1rem;">سوف يتم التواصل معك قريباً.</p>
        </div>
    </div>

    <footer>
        <p class="glow-text">© 2025 الحقني — مساعدة الطريق بلا حدود | تصميم فضائي احترافي</p>
    </footer>
</div>

<script>
    // ------------------ STAR GENERATION ------------------
    function generateStars() {
        const starsDiv = document.getElementById('starsContainer');
        starsDiv.innerHTML = '';
        const starCount = 300;
        for(let i=0; i<starCount; i++) {
            let star = document.createElement('div');
            star.classList.add('star');
            let size = Math.random() * 3 + 1;
            star.style.width = size + 'px';
            star.style.height = size + 'px';
            star.style.left = Math.random() * 100 + '%';
            star.style.top = Math.random() * 100 + '%';
            star.style.animationDelay = Math.random() * 5 + 's';
            star.style.animationDuration = 1.5 + Math.random() * 3 + 's';
            starsDiv.appendChild(star);
        }
    }
    generateStars();

    // ------------------ PAGE NAVIGATION (7 صفحات) ------------------
    const pages = ['home','services','request','myorders','features','faq','contact'];
    function showPage(pageId) {
        pages.forEach(p => {
            const el = document.getElementById(p);
            if(el) el.classList.remove('active-page');
        });
        document.getElementById(pageId).classList.add('active-page');
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.classList.remove('active');
            if(link.getAttribute('data-page') === pageId) link.classList.add('active');
        });
        // حفظ الصفحة الحالية
        localStorage.setItem('currentPage', pageId);
    }
    document.querySelectorAll('.nav-links a').forEach(link => {
        link.addEventListener('click', (e) => {
            e.preventDefault();
            const page = link.getAttribute('data-page');
            if(page && pages.includes(page)) showPage(page);
        });
    });
    const currentSaved = localStorage.getItem('currentPage');
    if(currentSaved && pages.includes(currentSaved)) showPage(currentSaved);

    // زر طلب سريع من الرئيسية
    document.getElementById('quickRequestBtn')?.addEventListener('click', () => showPage('request'));

    // ------------------ LOCAL STORAGE ORDERS (محاكاة قواعد بيانات supabase محلياً لجاهزية العرض) ------------------
    let orders = JSON.parse(localStorage.getItem('haqni_orders')) || [];
    function saveOrders() {
        localStorage.setItem('haqni_orders', JSON.stringify(orders));
    }
    function renderOrders() {
        const container = document.getElementById('ordersContainer');
        if(!container) return;
        if(orders.length === 0) {
            container.innerHTML = '<p style="text-align:center;">✨ لا توجد طلبات بعد. قم بتقديم طلب جديد ✨</p>';
            return;
        }
        container.innerHTML = '';
        orders.slice().reverse().forEach(order => {
            const div = document.createElement('div');
            div.className = 'order-item';
            let statusClass = '';
            if(order.status === 'pending') statusClass = 'status-pending';
            else if(order.status === 'in_progress') statusClass = 'status-progress';
            else if(order.status === 'completed') statusClass = 'status-completed';
            else if(order.status === 'cancelled') statusClass = 'status-cancelled';
            let statusText = {pending:'قيد الانتظار', in_progress:'قيد التنفيذ', completed:'مكتمل', cancelled:'ملغي'}[order.status] || 'قيد الانتظار';
            div.innerHTML = `
                <strong><i class="fas fa-concierge-bell"></i> ${order.service}</strong><br>
                📞 ${order.phone} &nbsp;| 📍 ${order.location || 'موقع غير محدد'}<br>
                📝 ${order.description || 'لا يوجد وصف'}<br>
                <span class="status-badge ${statusClass}">${statusText}</span>
                <small style="float:left;">${new Date(order.timestamp).toLocaleString('ar-DZ')}</small>
                <div style="clear:both"></div>
                <button class="btn-outline" style="margin-top:6px; font-size:0.7rem;" onclick="cancelOrder('${order.id}')">إلغاء الطلب</button>
            `;
            container.appendChild(div);
        });
    }
    window.cancelOrder = function(id) {
        const idx = orders.findIndex(o => o.id === id);
        if(idx !== -1 && orders[idx].status !== 'completed' && orders[idx].status !== 'cancelled') {
            orders[idx].status = 'cancelled';
            saveOrders();
            renderOrders();
            alert("تم إلغاء الطلب بنجاح");
        } else {
            alert("لا يمكن إلغاء طلب مكتمل أو ملغي مسبقاً");
        }
    };
    function addOrder(service, phone, location, description) {
        const newOrder = {
            id: Date.now().toString() + Math.floor(Math.random()*1000),
            service: service,
            phone: phone,
            location: location || 'تم تحديد الموقع تلقائياً',
            description: description,
            status: 'pending',
            timestamp: new Date().toISOString()
        };
        orders.unshift(newOrder);
        saveOrders();
        renderOrders();
        showPage('myorders');
        return newOrder;
    }
    // تحديث الطلبات يدويا
    document.getElementById('refreshOrdersBtn')?.addEventListener('click', () => {
        renderOrders();
        alert("تم تحديث قائمة الطلبات");
    });
    // معالج التقديم
    const formReq = document.getElementById('helpRequestForm');
    if(formReq) {
        formReq.addEventListener('submit', (e) => {
            e.preventDefault();
            const serviceType = document.getElementById('serviceType').value;
            const problemDesc = document.getElementById('problemDesc').value;
            const phoneReq = document.getElementById('phoneReq').value;
            let locationLink = document.getElementById('locationLink').value;
            if(!phoneReq) { alert("الرجاء إدخال رقم الهاتف"); return; }
            if(!locationLink) locationLink = "لم يتم تحديد الموقع، يرجى مشاركة الموقع يدوياً";
            addOrder(serviceType, phoneReq, locationLink, problemDesc);
            formReq.reset();
            alert("✅ تم إرسال الطلب بنجاح! سيتم توجيه المساعدة قريباً.");
        });
    }
    // Geolocation
    const getLocBtn = document.getElementById('getLocationBtn');
    if(getLocBtn) {
        getLocBtn.addEventListener('click', () => {
            if(navigator.geolocation) {
                navigator.geolocation.getCurrentPosition(pos => {
                    const lat = pos.coords.latitude;
                    const lng = pos.coords.longitude;
                    const mapsLink = `https://www.google.com/maps?q=${lat},${lng}`;
                    document.getElementById('locationLink').value = mapsLink;
                    document.getElementById('locationMsg').innerHTML = '✅ تم تحديد موقعك بدقة، رابط الخريطة جاهز.';
                }, () => {
                    document.getElementById('locationMsg').innerHTML = '⚠️ تعذر تحديد الموقع، تأكد من الإذن.';
                });
            } else { alert("المتصفح لا يدعم تحديد الموقع");}
        });
    }
    // ميزة هز الهاتف
    let lastShake = 0;
    if(window.DeviceMotionEvent) {
        window.addEventListener('devicemotion', (e) => {
            let acc = e.accelerationIncludingGravity;
            if(acc && (Math.abs(acc.x) > 15 || Math.abs(acc.y) > 15 || Math.abs(acc.z) > 15)) {
                const now = Date.now();
                if(now - lastShake > 1500) {
                    lastShake = now;
                    if(confirm('🚨 هزاز الهاتف تم تفعيله! هل تريد طلب مساعدة عاجلة؟')) {
                        showPage('request');
                        // سكرول إلى الفورم
                        document.getElementById('helpRequestForm')?.scrollIntoView({behavior:'smooth'});
                    }
                }
            }
        });
    } else {
        console.log("جهاز بدون دعم motion");
    }
    // الإبلاغ عن مشكلة
    const reportForm = document.getElementById('reportIssue');
    if(reportForm) {
        reportForm.addEventListener('submit', (e) => {
            e.preventDefault();
            const name = document.getElementById('reportName').value || 'مستخدم';
            const msg = document.getElementById('reportMsg').value;
            if(msg) alert(`شكراً ${name}، تم استلام بلاغك وسنقوم بمراجعته بأسرع وقت.`);
            else alert('الرجاء كتابة تفاصيل المشكلة');
            reportForm.reset();
        });
    }

    // إضافة تأثير الكتابة اللامعة تلقائياً لجميع العناوين
    document.querySelectorAll('h2, .logo, .glow-text').forEach(el => el.classList.add('glow-text'));
    renderOrders();
</script>
</body>
</html>
