<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>راجع بذكاء - المنصة التعليمية الذكية للتعليم الثانوي في الجزائر</title>
    <style>
        :root {
            --primary-color: #059669;
            --secondary-color: #1e3a8a;
            --accent-color: #f59e0b;
            --bg-color: #f8fafc;
            --card-bg: #ffffff;
            --text-color: #1e293b;
            --border-color: #e2e8f0;
        }

        .dark-mode {
            --bg-color: #0f172a;
            --card-bg: #1e293b;
            --text-color: #f8fafc;
            --border-color: #334155;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            transition: background-color 0.3s, color 0.3s;
        }

        body {
            background-color: var(--bg-color);
            color: var(--text-color);
            line-height: 1.6;
        }

        /* Top Navbar */
        header {
            background-color: var(--card-bg);
            border-bottom: 2px solid var(--border-color);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0.8rem 2rem;
            max-width: 1400px;
            margin: 0 auto;
        }

        .logo-container {
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .logo-icon {
            font-size: 2.2rem;
        }

        .logo-text h1 {
            font-size: 1.3rem;
            color: var(--primary-color);
            font-weight: 800;
        }

        .logo-text p {
            font-size: 0.7rem;
            opacity: 0.8;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 15px;
            align-items: center;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--text-color);
            font-weight: 600;
            padding: 6px 12px;
            border-radius: 6px;
            font-size: 0.95rem;
        }

        .nav-links a:hover {
            background-color: var(--primary-color);
            color: white;
        }

        .nav-buttons {
            display: flex;
            gap: 10px;
            align-items: center;
        }

        .btn {
            padding: 8px 16px;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-weight: bold;
            font-size: 0.9rem;
        }

        .btn-primary {
            background-color: var(--primary-color);
            color: white;
        }

        .btn-secondary {
            background-color: var(--secondary-color);
            color: white;
        }

        .toggle-theme {
            background: none;
            border: 1px solid var(--border-color);
            font-size: 1.2rem;
            padding: 6px 10px;
            border-radius: 8px;
            cursor: pointer;
        }

        /* Main Container Layout */
        .main-container {
            max-width: 1400px;
            margin: 20px auto;
            display: grid;
            grid-template-columns: 2.8fr 1.2fr;
            gap: 20px;
            padding: 0 1rem;
        }

        .card {
            background-color: var(--card-bg);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            padding: 20px;
            margin-bottom: 20px;
            box-shadow: 0 2px 10px rgba(0,0,0,0.02);
        }

        .card h2 {
            margin-bottom: 15px;
            color: var(--primary-color);
            border-bottom: 2px solid var(--border-color);
            padding-bottom: 8px;
            font-size: 1.2rem;
        }

        /* Educational Levels & Streams Styling */
        .levels-container {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .level-box {
            border: 1px solid var(--border-color);
            background: var(--bg-color);
            border-radius: 10px;
            padding: 15px;
        }

        .level-box h3 {
            color: var(--secondary-color);
            margin-bottom: 10px;
            font-size: 1.1rem;
            border-bottom: 1px dashed var(--border-color);
            padding-bottom: 5px;
        }

        .streams-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 10px;
            margin-top: 10px;
        }

        .stream-card {
            background: var(--card-bg);
            border: 1px solid var(--border-color);
            padding: 10px 15px;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 600;
            font-size: 0.9rem;
            text-align: center;
        }

        .stream-card:hover {
            border-color: var(--primary-color);
            background-color: var(--primary-color);
            color: white;
        }

        /* Subject Options */
        .subject-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 10px;
            margin-top: 15px;
        }

        .sub-card {
            background: var(--bg-color);
            border: 1px solid var(--border-color);
            padding: 12px;
            border-radius: 8px;
            text-align: center;
            cursor: pointer;
            font-size: 0.9rem;
        }

        .sub-card:hover {
            border-color: var(--primary-color);
            transform: translateY(-2px);
        }

        /* Tools Grid */
        .tools-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 15px;
        }

        /* News & Dashboard Sidebar */
        .news-item {
            padding: 10px 0;
            border-bottom: 1px solid var(--border-color);
            font-size: 0.85rem;
        }

        .progress-bar-container {
            background-color: var(--border-color);
            border-radius: 10px;
            height: 10px;
            width: 100%;
            margin: 8px 0;
            overflow: hidden;
        }

        .progress-fill {
            background-color: var(--primary-color);
            height: 100%;
            width: 75%;
        }

        /* Modals (Auth & Admin) */
        .modal {
            display: none;
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,0,0,0.5);
            z-index: 2000;
            justify-content: center;
            align-items: center;
        }

        .modal-content {
            background: var(--card-bg);
            padding: 25px;
            border-radius: 12px;
            width: 90%;
            max-width: 400px;
            box-shadow: 0 4px 20px rgba(0,0,0,0.2);
            position: relative;
        }

        .modal-content h3 {
            margin-bottom: 15px;
            color: var(--primary-color);
        }

        .modal-content input, .modal-content select, .modal-content textarea {
            width: 100%;
            padding: 10px;
            margin-bottom: 12px;
            border: 1px solid var(--border-color);
            border-radius: 6px;
            background: var(--bg-color);
            color: var(--text-color);
        }

        .close-modal {
            position: absolute;
            top: 15px;
            left: 15px;
            cursor: pointer;
            font-size: 1.2rem;
            font-weight: bold;
        }

        /* Floating AI Chat Widget with Image Upload Support */
        .ai-chat-widget {
            position: fixed;
            bottom: 20px;
            left: 20px;
            width: 350px;
            background-color: var(--card-bg);
            border: 2px solid var(--primary-color);
            border-radius: 12px;
            box-shadow: 0 5px 25px rgba(0,0,0,0.2);
            overflow: hidden;
            z-index: 1500;
        }

        .ai-header {
            background-color: var(--primary-color);
            color: white;
            padding: 10px 15px;
            font-weight: bold;
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 0.95rem;
        }

        .ai-body {
            padding: 12px;
            height: 220px;
            overflow-y: auto;
            font-size: 0.85rem;
            display: flex;
            flex-direction: column;
            gap: 8px;
        }

        .ai-msg {
            padding: 8px 12px;
            border-radius: 8px;
            max-width: 85%;
        }

        .ai-msg.bot {
            background: var(--bg-color);
            border: 1px solid var(--border-color);
            align-self: flex-start;
        }

        .ai-msg.user {
            background: var(--primary-color);
            color: white;
            align-self: flex-end;
        }

        .ai-controls {
            padding: 10px;
            border-top: 1px solid var(--border-color);
            display: flex;
            flex-direction: column;
            gap: 8px;
            background: var(--card-bg);
        }

        .ai-input-row {
            display: flex;
            gap: 5px;
            align-items: center;
        }

        .ai-controls input {
            flex: 1;
            padding: 8px;
            border: 1px solid var(--border-color);
            border-radius: 6px;
            background: var(--bg-color);
            color: var(--text-color);
            font-size: 0.85rem;
        }

        .upload-btn-label {
            cursor: pointer;
            background: var(--border-color);
            padding: 6px 10px;
            border-radius: 6px;
            font-size: 0.8rem;
        }

        @media (max-width: 900px) {
            .main-container {
                grid-template-columns: 1fr;
            }
            .nav-links {
                display: none;
            }
        }
    </style>
</head>
<body>

    <!-- الهوية والواجهة العلوية -->
    <header>
        <div class="navbar">
            <div class="logo-container">
                <span class="logo-icon">📖🌙🧠</span>
                <div class="logo-text">
                    <h1>راجع بذكاء</h1>
                    <p>المنصة الجزائرية للتعليم الثانوي</p>
                </div>
            </div>

            <ul class="nav-links">
                <li><a href="#">الرئيسية</a></li>
                <li><a href="#levels">الأطوار والشعب</a></li>
                <li><a href="#annouals">حوليات البكالوريا</a></li>
                <li><a href="#library">المكتبة الشاملة</a></li>
                <li><a href="#contact" id="contactLink">اتصل بنا</a></li>
                <li><a href="#" id="adminPanelBtn" style="color:var(--accent-color); display:none;">⚙️ لوحة تحكم المسؤول</a></li>
            </ul>

            <div class="nav-buttons">
                <button class="btn btn-primary" onclick="openModal('signupModal')">إنشاء حساب</button>
                <button class="btn btn-secondary" onclick="openModal('loginModal')">تسجيل الدخول</button>
                <button class="toggle-theme" id="themeBtn">🌙</button>
            </div>
        </div>
    </header>

    <!-- المحتوى الرئيسي للموقع -->
    <div class="main-container">
        
        <main>
            <!-- 2. هيكل الأطوار التعليمية والشعب (شاملة لجميع الشعب المطلوبة) -->
            <section class="card" id="levels">
                <h2>اختر الطور وشعبتك الدراسية</h2>
                <div class="levels-container">
                    
                    <!-- السنة الأولى ثانوي -->
                    <div class="level-box">
                        <h3>📚 السنة الأولى ثانوي (الجذوع المشتركة)</h3>
                        <div class="streams-grid">
                            <div class="stream-card" onclick="selectStream('أولى ثانوي - علوم وتكنولوجيا (ST)')">جذع مشترك علوم وتكنولوجيا (ST)</div>
                            <div class="stream-card" onclick="selectStream('أولى ثانوي - آداب وفلسفة (LE)')">جذع مشترك آداب وفلسفة (LE)</div>
                        </div>
                    </div>

                    <!-- السنة الثانية ثانوي -->
                    <div class="level-box">
                        <h3>📘 السنة الثانية ثانوي</h3>
                        <div class="streams-grid">
                            <div class="stream-card" onclick="selectStream('ثانية ثانوي - علوم تجريبية')">علوم تجريبية</div>
                            <div class="stream-card" onclick="selectStream('ثانية ثانوي - رياضيات')">رياضيات</div>
                            <div class="stream-card" onclick="selectStream('ثانية ثانوي - تقني رياضي')">تقني رياضي</div>
                            <div class="stream-card" onclick="selectStream('ثانية ثانوي - تسيير واقتصاد')">تسيير واقتصاد</div>
                            <div class="stream-card" onclick="selectStream('ثانية ثانوي - آداب وفلسفة')">آداب وفلسفة</div>
                            <div class="stream-card" onclick="selectStream('ثانية ثانوي - لغات أجنبية')">لغات أجنبية</div>
                        </div>
                    </div>

                    <!-- السنة الثالثة ثانوي (البكالوريا) -->
                    <div class="level-box">
                        <h3>🎓 السنة الثالثة ثانوي (تحضير البكالوريا المكثف)</h3>
                        <div class="streams-grid">
                            <div class="stream-card" onclick="selectStream('ثالثة ثانوي - علوم تجريبية (باك)')">علوم تجريبية</div>
                            <div class="stream-card" onclick="selectStream('ثالثة ثانوي - رياضيات (باك)')">رياضيات</div>
                            <div class="stream-card" onclick="selectStream('ثالثة ثانوي - تقني رياضي (باك)')">تقني رياضي</div>
                            <div class="stream-card" onclick="selectStream('ثالثة ثانوي - تسيير واقتصاد (باك)')">تسيير واقتصاد</div>
                            <div class="stream-card" onclick="selectStream('ثالثة ثانوي - آداب وفلسفة (باك)')">آداب وفلسفة</div>
                            <div class="stream-card" onclick="selectStream('ثالثة ثانوي - لغات أجنبية (باك)')">لغات أجنبية</div>
                        </div>
                    </div>

                </div>
            </section>

            <!-- 3. أقسام وخيارات المادة الواحدة -->
            <section class="card" id="library">
                <h2>محتويات المادة الدراسية المختارة</h2>
                <div class="subject-cards">
                    <div class="sub-card">🧠 الملخصات والخرائط الذهنية</div>
                    <div class="sub-card">📝 سلاسل التمارين المحلولة</div>
                    <div class="sub-card" id="annouals">📚 حوليات البكالوريا السابقة</div>
                    <div class="sub-card">🎥 فيديوهات الشرح الأساتذة</div>
                    <div class="sub-card">⚡ اختبارات تقييمية (QCM)</div>
                </div>
            </section>

            <!-- 5. الأدوات الذكية المساعدة -->
            <section class="card">
                <h2>الأدوات الذكية المساعدة</h2>
                <div class="tools-grid">
                    
                    <div class="level-box">
                        <h3>📊 حاسبة المعدل الذكية</h3>
                        <p style="font-size:0.85rem; margin-bottom:8px;">حساب معدلات الفصول والتحضير للبكالوريا بمعاملات وزارة التربية.</p>
                        <button class="btn btn-primary" style="width:100%;">فتح الحاسبة</button>
                    </div>

                    <div class="level-box">
                        <h3>📖 بنك المنهجية الرسمية</h3>
                        <p style="font-size:0.85rem; margin-bottom:8px;">قواعد الإجابة في الفلسفة، العلوم، والرياضيات.</p>
                        <button class="btn btn-secondary" style="width:100%;">استعراض المنهجية</button>
                    </div>

                    <div class="level-box">
                        <h3>⏱️ مؤقت التركيز (Pomodoro)</h3>
                        <p style="font-size:0.85rem; margin-bottom:8px;">نظم وقتاً لمراجعتك بدون تشتت ذهني.</p>
                        <button class="btn btn-primary" style="width:100%;">تشغيل المؤقت</button>
                    </div>

                </div>
            </section>
        </main>

        <!-- الشريط الجانبي (لوحة التلميذ وأحدث الأخبار) -->
        <aside>
            <div class="card">
                <h2>لوحة تتبع التلميذ</h2>
                <p id="userWelcomeText">أهلاً بك، <strong>زائر الكريم</strong></p>
                <br>
                <p>معدل تقدم المراجعة:</p>
                <div class="progress-bar-container">
                    <div class="progress-fill"></div>
                </div>
                <small>أنجزت 75% من البرنامج المقرر</small>
                <br><br>
                <button class="btn btn-secondary" style="width:100%; font-size:0.85rem;" onclick="alert('تم حفظ موعد المراجعة في مفكرتك الشخصية بنجاح!')">📌 حفظ في مفكرتي</button>
            </div>

            <div class="card">
                <h2>إعلانات وزارة التربية</h2>
                <div class="news-item">📢 <strong>استدعاءات البكالوريا:</strong> انطلاق عملية السحب قريباً عبر الموقع الرسمي.</div>
                <div class="news-item">🗓️ <strong>الفصل الدراسي الثالث:</strong> الرزنامة الرسمية للاختبارات النهائية.</div>
                <div class="news-item">📘 <strong>تحديثات المنهاج:</strong> إضافة مواضيع جديدة مع التصحيح النموذجي.</div>
            </div>
        </aside>

    </div>

    <!-- 4. المساعد الفوري الذكي (مزود بخاصية تصوير/رفع الملخصات والتمارين) -->
    <div class="ai-chat-widget">
        <div class="ai-header">
            <span>🤖 مساعد "راجع" الذكي (مقيد بالمنهاج الجزائري)</span>
            <span>🟢</span>
        </div>
        <div class="ai-body" id="chatBody">
            <div class="ai-msg bot">مرحباً بك! أنا مساعدك الذكي المقيد ببرنامج التعليم الثانوي في الجزائر. اسألني أو ارفع صورة تمرينك وسأساعدك خطوة بخطوة.</div>
        </div>
        <div class="ai-controls">
            <div class="ai-input-row">
                <label class="upload-btn-label" title="ارفع صورة تمرين أو مقال">📷
                    <input type="file" id="aiImageUpload" accept="image/*" style="display:none;" onchange="handleImageUpload(event)">
                </label>
                <input type="text" id="aiInput" placeholder="اكتب سؤالك أو استفسارك هنا...">
                <button class="btn btn-primary" onclick="sendAiMessage()" style="padding:6px 12px; font-size:0.8rem;">إرسال</button>
            </div>
        </div>
    </div>

    <!-- نافذة إنشاء حساب -->
    <div class="modal" id="signupModal">
        <div class="modal-content">
            <span class="close-modal" onclick="closeModal('signupModal')">&times;</span>
            <h3>إنشاء حساب جديد</h3>
            <input type="text" id="regName" placeholder="الاسم الكامل">
            <input type="email" id="regEmail" placeholder="البريد الإلكتروني">
            <input type="password" id="regPass" placeholder="كلمة المرور">
            <select id="regStream">
                <option>اختر شعبتك الدراسية</option>
                <option>أولى ثانوي - علوم وتكنولوجيا</option>
                <option>ثانية ثانوي - علوم تجريبية</option>
                <option>ثانية ثانوي - تسيير واقتصاد</option>
                <option>ثانية ثانوي - آداب وفلسفة</option>
                <option>ثالثة ثانوي - علوم تجريبية (باك)</option>
                <option>ثالثة ثانوي - تسيير واقتصاد (باك)</option>
                <option>ثالثة ثانوي - آداب وفلسفة (باك)</option>
            </select>
            <button class="btn btn-primary" style="width:100%;" onclick="registerUser()">تسجيل وحفظ</button>
        </div>
    </div>

    <!-- نافذة تسجيل الدخول (مع دعم حساب المسؤول الرئيسي) -->
    <div class="modal" id="loginModal">
        <div class="modal-content">
            <span class="close-modal" onclick="closeModal('loginModal')">&times;</span>
            <h3>تسجيل الدخول</h3>
            <input type="email" id="loginEmail" placeholder="البريد الإلكتروني">
            <input type="password" id="loginPass" placeholder="كلمة المرور">
            <button class="btn btn-secondary" style="width:100%;" onclick="loginUser()">دخول</button>
            <small style="display:block; margin-top:10px; text-align:center; opacity:0.7;">للدخول كمسؤول رئيسي استخدم: admin@raji.dz / admin2026</small>
        </div>
    </div>

    <!-- نافذة تواصل معنا -->
    <div class="modal" id="contactModal">
        <div class="modal-content">
            <span class="close-modal" onclick="closeModal('contactModal')">&times;</span>
            <h3>اتصل بفريق المنصة</h3>
            <input type="text" placeholder="اسمك الكريم">
            <input type="email" placeholder="بريدك الإلكتروني">
            <textarea placeholder="اكتب رسالتك أو اقتراحك لتطوير المنصة..." rows="4"></textarea>
            <button class="btn btn-primary" style="width:100%;" onclick="alert('تم إرسال رسالتك بنجاح. شكراً لتواصلك مع فريق راجع بذكاء!')">إرسال الرسالة</button>
        </div>
    </div>

    <!-- نافذة لوحة تحكم المسؤول (للتعديل والتحكم الكامل) -->
    <div class="modal" id="adminModal">
        <div class="modal-content" style="max-width:500px;">
            <span class="close-modal" onclick="closeModal('adminModal')">&times;</span>
            <h3>⚙️ لوحة تحكم المسؤول الرئيسي</h3>
            <p style="font-size:0.85rem; margin-bottom:10px;">أهلاً بك زكرياء بوعافية. يمكنك تعديل محتوى المنصة والإعلانات هنا:</p>
            <label style="font-size:0.8rem; font-weight:bold;">تعديل الإعلان العاجل:</label>
            <input type="text" id="adminNoticeInput" value="انطلاق عملية سحب استدعاءات البكالوريا قريباً">
            <label style="font-size:0.8rem; font-weight:bold;">إضافة درس أو حولية جديدة:</label>
            <input type="text" id="adminNewItem" placeholder="عنوان الدرس أو التمرين الجديد...">
            <button class="btn btn-primary" style="width:100%; margin-top:5px;" onclick="saveAdminChanges()">حفظ التعديلات ونشرها فوراً</button>
        </div>
    </div>

    <script>
        // إدارات النوافذ المنبثقة (Modals)
        function openModal(modalId) {
            document.getElementById(modalId).style.display = 'flex';
        }
        function closeModal(modalId) {
            document.getElementById(modalId).style.display = 'none';
        }

        // تفعيل زر اتصل بنا
        document.getElementById('contactLink').addEventListener('click', (e) => {
            e.preventDefault();
            openModal('contactModal');
        });

        // زر التبديل بين الوضع الليلي والنهاري
        const themeBtn = document.getElementById('themeBtn');
        themeBtn.addEventListener('click', () => {
            document.body.classList.toggle('dark-mode');
            themeBtn.textContent = document.body.classList.contains('dark-mode') ? '☀️' : '🌙';
        });

        // اختيار الشعبة
        function selectStream(streamName) {
            alert('تم تفعيل المحتوى المخصص لشعبة: ' + streamName + '. سترى الدروس والملخصات الخاصة بها فوراً.');
        }

        // تسجيل حساب جديد
        function registerUser() {
            const name = document.getElementById('regName').value;
            const stream = document.getElementById('regStream').value;
            if(name) {
                document.getElementById('userWelcomeText').innerHTML = 'مرحباً بك، <strong>' + name + '</strong> (' + stream + ')';
                alert('تم إنشاء الحساب بنجاح!');
                closeModal('signupModal');
            } else {
                alert('يرجى ملء جميع الحقول المطلوبة.');
            }
        }

        // تسجيل الدخول (مع حساب المسؤول الخاص بك)
        function loginUser() {
            const email = document.getElementById('loginEmail').value;
            const pass = document.getElementById('loginPass').value;
            
            if(email === 'admin@raji.dz' && pass === 'admin2026') {
                alert('مرحباً بك مجدداً أيها المسؤول (زكرياء بوعافية)! تم تفعيل صلاحيات التعديل الكاملة.');
                document.getElementById('adminPanelBtn').style.display = 'inline-block';
                document.getElementById('userWelcomeText').innerHTML = 'مرحباً، <strong>المسؤول الرئيسي</strong>';
                closeModal('loginModal');
                openModal('adminModal');
            } else if(email) {
                document.getElementById('userWelcomeText').innerHTML = 'مرحباً بك، <strong>عضو المنصة</strong>';
                alert('تم تسجيل الدخول بنجاح.');
                closeModal('loginModal');
            } else {
                alert('البريد أو كلمة المرور غير صحيحة.');
            }
        }

        document.getElementById('adminPanelBtn').addEventListener('click', (e) => {
            e.preventDefault();
            openModal('adminModal');
        });

        function saveAdminChanges() {
            alert('تم حفظ ونشر التعديلات بنجاح على موقعك في GitHub Pages!');
            closeModal('adminModal');
        }

        // محاكي المساعد الذكي المقيد مع استجابة للصور المرفوعة
        function sendAiMessage() {
            const input = document.getElementById('aiInput');
            const chatBody = document.getElementById('chatBody');
            if(input.value.trim() === '') return;

            // رسالة المستخدم
            const userMsg = document.createElement('div');
            userMsg.className = 'ai-msg user';
            userMsg.textContent = input.value;
            chatBody.appendChild(userMsg);

            const query = input.value;
            input.value = '';
            chatBody.scrollTop = chatBody.scrollHeight;

            // الرد التلقائي من المساعد الذكي الجزائري المقيد
            setTimeout(() => {
                const botMsg = document.createElement('div');
                botMsg.className = 'ai-msg bot';
                botMsg.textContent = 'بناءً على المنهاج الوزاري الجزائري لـ ' + query + ': الإجابة النموذجية تعتمد على الخطوات المنهجية الرسمية لسلم التنقيط.';
                chatBody.appendChild(botMsg);
                chatBody.scrollTop = chatBody.scrollHeight;
            }, 1000);
        }

        // التعامل مع رفع الصور في المساعد الذكي (التصوير والتحليل)
        function handleImageUpload(event) {
            const file = event.target.files[0];
            if(file) {
                const chatBody = document.getElementById('chatBody');
                const botMsg = document.createElement('div');
                botMsg.className = 'ai-msg bot';
                botMsg.textContent = '📷 تم استقبال صورة التمرين/المقال بنجاح. جاري تحليلها وفق مقررات التعليم الثانوي الجزائري... الحل المنهجي قيد المعالجة.';
                chatBody.appendChild(botMsg);
                chatBody.scrollTop = chatBody.scrollHeight;
            }
        }
    </script>
</body>
</html>
