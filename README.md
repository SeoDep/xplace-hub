<!DOCTYPE html>
<html lang="he" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>XPLACE | Dev Hub - מרכז הפרילנסרים למקצועות התוכנה</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Assistant:wght@300;400;600;700&display=swap" rel="stylesheet">
    <script src="https://unpkg.com/lucide@latest"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        body {
            font-family: 'Assistant', sans-serif;
            background-color: #f8f9fa;
        }
        :root {
            --brand-blue: #0052FF;
            --brand-dark: #0d1c3d;
            --brand-secondary: #00bfff;
        }
        .bg-brand-blue { background-color: var(--brand-blue); }
        .text-brand-blue { color: var(--brand-blue); }
        .bg-brand-dark { background-color: var(--brand-dark); }
        .text-brand-dark { color: var(--brand-dark); }
        .border-brand-blue { border-color: var(--brand-blue); }
        .hover-bg-brand-secondary:hover { background-color: var(--brand-secondary); }
        .section-title {
            font-size: 2.25rem;
            font-weight: 700;
            margin-bottom: 1.5rem;
            color: var(--brand-dark);
            text-align: center;
        }
        .card {
            background-color: white;
            border-radius: 0.75rem;
            box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1), 0 2px 4px -2px rgb(0 0 0 / 0.1);
            transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
            border: 1px solid #e5e7eb;
            display: flex;
            flex-direction: column;
        }
        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 15px -3px rgb(0 0 0 / 0.1), 0 4px 6px -2px rgb(0 0 0 / 0.05);
        }
        .card-title {
            font-size: 1.25rem;
            font-weight: 600;
            color: var(--brand-dark);
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }
        .card-content {
            flex-grow: 1;
        }
        .card-link {
            display: block;
            padding: 0.5rem 1rem;
            border-radius: 0.5rem;
            transition: background-color 0.2s;
            color: #374151;
        }
        .card-link:hover {
            background-color: #f3f4f6;
            color: var(--brand-blue);
        }
        .project-link {
            font-weight: 600;
            color: var(--brand-blue);
            background-color: #eef2ff;
        }
        .project-link:hover {
            background-color: #e0e7ff;
        }
        .cta-button {
            background-color: var(--brand-blue);
            color: white;
            padding: 0.75rem 2rem;
            border-radius: 0.5rem;
            font-weight: 600;
            transition: background-color 0.2s, transform 0.2s;
            display: inline-block;
        }
        .cta-button:hover {
            background-color: #0045d9;
            transform: scale(1.05);
        }
        .testimonial-card {
            background-color: #eef2ff;
            border-left: 4px solid var(--brand-blue);
        }
        .employer-button {
            display: block;
            width: 100%;
            text-align: center;
            background-color: #f3f4f6;
            color: var(--brand-dark);
            font-weight: 600;
            padding: 0.6rem 1rem;
            border-radius: 0.5rem;
            font-size: 0.875rem;
            transition: background-color 0.2s;
        }
        .employer-button:hover {
            background-color: #e5e7eb;
        }
    </style>
</head>
<body class="bg-gray-50">

    <!-- Header -->
    <header class="bg-white shadow-sm sticky top-0 z-50">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center py-4">
                <div>
                    <a href="#" class="text-3xl font-bold text-brand-blue">
                        XPLACE
                    </a>
                </div>
                <nav class="hidden md:flex items-center space-x-8" id="main-nav">
                    <a href="#categories" class="text-gray-600 hover:text-brand-blue transition">תחומים</a>
                    <a href="#salary" class="text-gray-600 hover:text-brand-blue transition">תעריפים</a>
                    <a href="#brand" class="text-gray-600 hover:text-brand-blue transition">מותג אישי</a>
                    <a href="#tips" class="text-gray-600 hover:text-brand-blue transition">טיפים</a>
                    <a href="#follow" class="text-gray-600 hover:text-brand-blue transition">כדאי לעקוב</a>
                    <a href="#tools" class="text-gray-600 hover:text-brand-blue transition">כלים</a>
                </nav>
                <a href="https://www.xplace.com/dev/jobs" target="_blank" class="cta-button hidden md:inline-block">מצא את הפרויקט הבא שלך</a>
                <button id="mobile-menu-button" class="md:hidden text-gray-700">
                    <i data-lucide="menu"></i>
                </button>
            </div>
             <!-- Mobile Menu -->
            <div id="mobile-menu" class="hidden md:hidden py-4">
                <a href="#categories" class="block py-2 px-4 text-gray-600 hover:bg-gray-100 rounded">תחומים</a>
                <a href="#salary" class="block py-2 px-4 text-gray-600 hover:bg-gray-100 rounded">תעריפים</a>
                <a href="#brand" class="block py-2 px-4 text-gray-600 hover:bg-gray-100 rounded">מותג אישי</a>
                <a href="#tips" class="block py-2 px-4 text-gray-600 hover:bg-gray-100 rounded">טיפים למפתחים</a>
                <a href="#follow" class="block py-2 px-4 text-gray-600 hover:bg-gray-100 rounded">כדאי לעקוב</a>
                <a href="#tools" class="block py-2 px-4 text-gray-600 hover:bg-gray-100 rounded">כלים ומשאבים</a>
            </div>
        </div>
    </header>

    <!-- Hero Section -->
    <main class="container mx-auto px-4 sm:px-6 lg:px-8 py-12 md:py-20">
        <section class="text-center">
            <h1 class="text-4xl md:text-6xl font-extrabold text-brand-dark mb-4 leading-tight">
                Dev Hub: מרכז הפרילנסרים למקצועות התוכנה
            </h1>
            <p class="text-lg md:text-xl text-gray-600 max-w-3xl mx-auto mb-8">
                כל מה שמפתחים, אנשי DevOps, דאטה ו-QA צריכים במקום אחד. מפרויקטים ועד כלים, קהילה ונטוורקינג.
            </p>
            <a href="https://www.xplace.com/dev/register" target="_blank" class="cta-button text-lg">
                הצטרפו לקהילת המומחים שלנו
            </a>
        </section>

        <!-- Main Categories -->
        <section id="categories" class="py-16 md:py-24">
            <h2 class="section-title">מצא פרויקטים או מומחים לפי תחום</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <div class="card p-6">
                    <div class="card-content">
                        <h3 class="card-title"><i data-lucide="code-2" class="text-brand-blue"></i>פיתוח ווב</h3>
                        <div class="mt-4 space-y-2">
                            <a href="#" class="card-link project-link">פרויקטים ב-Frontend</a>
                            <a href="#" class="card-link project-link">פרויקטים ב-Backend</a>
                            <a href="#" class="card-link project-link">פרויקטים ב-Full Stack</a>
                            <a href="#" class="card-link">מאמרים על טרנדים ב-Web</a>
                        </div>
                    </div>
                    <div class="border-t mt-4 pt-4">
                        <a href="#" class="employer-button">אני מעסיק/ה, צפה/י במומחים &rarr;</a>
                    </div>
                </div>
                <div class="card p-6">
                    <div class="card-content">
                        <h3 class="card-title"><i data-lucide="smartphone" class="text-brand-blue"></i>פיתוח מובייל</h3>
                        <div class="mt-4 space-y-2">
                            <a href="#" class="card-link project-link">פרויקטים ב-iOS (Swift)</a>
                            <a href="#" class="card-link project-link">פרויקטים באנדרואיד (Kotlin)</a>
                            <a href="#" class="card-link project-link">פרויקטים ב-React Native/Flutter</a>
                            <a href="#" class="card-link">כלים חדשים למפתחי מובייל</a>
                        </div>
                    </div>
                    <div class="border-t mt-4 pt-4">
                        <a href="#" class="employer-button">אני מעסיק/ה, צפה/י במומחים &rarr;</a>
                    </div>
                </div>
                <div class="card p-6">
                    <div class="card-content">
                        <h3 class="card-title"><i data-lucide="cloud-cog" class="text-brand-blue"></i>DevOps & Cloud</h3>
                        <div class="mt-4 space-y-2">
                            <a href="#" class="card-link project-link">פרויקטים ב-DevOps</a>
                            <a href="#" class="card-link project-link">פרויקטים ב-AWS / Azure / GCP</a>
                            <a href="#" class="card-link">מדריכים על CI/CD ו-Docker</a>
                            <a href="#" class="card-link">קורסי הסמכה בענן</a>
                        </div>
                    </div>
                    <div class="border-t mt-4 pt-4">
                        <a href="#" class="employer-button">אני מעסיק/ה, צפה/י במומחים &rarr;</a>
                    </div>
                </div>
                <div class="card p-6">
                    <div class="card-content">
                        <h3 class="card-title"><i data-lucide="brain-circuit" class="text-brand-blue"></i>Data Science & AI</h3>
                        <div class="mt-4 space-y-2">
                            <a href="#" class="card-link project-link">פרויקטים ב-Data Science</a>
                            <a href="#" class="card-link project-link">פרויקטים ב-Machine Learning</a>
                            <a href="#" class="card-link">מאמרים על Generative AI</a>
                            <a href="#" class="card-link">ספריות Python פופולריות</a>
                        </div>
                    </div>
                    <div class="border-t mt-4 pt-4">
                        <a href="#" class="employer-button">אני מעסיק/ה, צפה/י במומחים &rarr;</a>
                    </div>
                </div>
                <div class="card p-6">
                    <div class="card-content">
                        <h3 class="card-title"><i data-lucide="clipboard-check" class="text-brand-blue"></i>QA ואוטומציה</h3>
                        <div class="mt-4 space-y-2">
                            <a href="#" class="card-link project-link">פרויקטים ב-QA ואוטומציה</a>
                            <a href="#" class="card-link project-link">פרויקטים ב-Selenium / Cypress</a>
                            <a href="#" class="card-link">מדריכים לכתיבת טסטים</a>
                            <a href="#" class="card-link">כלים לבדיקות עומסים</a>
                        </div>
                    </div>
                    <div class="border-t mt-4 pt-4">
                        <a href="#" class="employer-button">אני מעסיק/ה, צפה/י במומחים &rarr;</a>
                    </div>
                </div>
                <div class="card p-6">
                    <div class="card-content">
                        <h3 class="card-title"><i data-lucide="shield-check" class="text-brand-blue"></i>Cybersecurity & AppSec</h3>
                        <div class="mt-4 space-y-2">
                            <a href="#" class="card-link project-link">פרויקטים ב-Penetration Testing</a>
                            <a href="#" class="card-link project-link">פרויקטים ב-Application Security</a>
                            <a href="#" class="card-link">מדריכים על Secure Coding</a>
                            <a href="#" class="card-link">כלים וקורסים בסייבר</a>
                        </div>
                    </div>
                    <div class="border-t mt-4 pt-4">
                        <a href="#" class="employer-button">אני מעסיק/ה, צפה/י במומחים &rarr;</a>
                    </div>
                </div>
            </div>
        </section>
        
        <!-- Salary Section -->
        <section id="salary" class="py-16 md:py-24 bg-white rounded-xl shadow-md -mx-4 px-4 md:-mx-8 md:px-8">
            <h2 class="section-title">תעריפים ושכר בתעשיית ההייטק</h2>
            <p class="text-center text-gray-600 mb-12 max-w-3xl mx-auto">תעריפים שעתיים מומלצים (בש"ח) לפרילנסרים לפי תחום, ניסיון ומיקום. הנתונים הם להמחשה בלבד ומבוססים על סקרי שוק.</p>
            <div class="grid grid-cols-1 md:grid-cols-3 gap-8 text-center">
                <div class="card p-6">
                    <h3 class="font-bold text-lg mb-4 text-brand-dark">תעריף לפי תחום</h3>
                    <canvas id="salaryByFieldChart"></canvas>
                </div>
                <div class="card p-6">
                     <h3 class="font-bold text-lg mb-4 text-brand-dark">תעריף לפי ניסיון</h3>
                    <canvas id="salaryByExperienceChart"></canvas>
                </div>
                <div class="card p-6">
                     <h3 class="font-bold text-lg mb-4 text-brand-dark">תעריף לפי מיקום</h3>
                    <canvas id="salaryByLocationChart"></canvas>
                </div>
            </div>
        </section>

        <!-- Personal Brand Section -->
        <section id="brand" class="py-16 md:py-24">
            <h2 class="section-title">בניית מותג אישי למפתחים</h2>
            <p class="text-center text-gray-600 mb-12 max-w-3xl mx-auto">איך לבלוט בשוק תחרותי, למשוך לקוחות איכותיים ולהעלות תעריפים? המפתח הוא מותג אישי חזק.</p>
            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8">
                <div class="card p-6 text-center">
                    <i data-lucide="briefcase" class="mx-auto text-brand-blue h-10 w-10 mb-3"></i>
                    <h3 class="font-bold text-lg mb-2 text-brand-dark">פורטפוליו מנצח</h3>
                    <p class="text-gray-600 text-sm">הצג את הפרויקטים הכי טובים שלך, תאר את האתגרים הטכנולוגיים והדגש את התוצאות.</p>
                </div>
                <div class="card p-6 text-center">
                    <i data-lucide="github" class="mx-auto text-brand-blue h-10 w-10 mb-3"></i>
                    <h3 class="font-bold text-lg mb-2 text-brand-dark">פרופיל GitHub פעיל</h3>
                    <p class="text-gray-600 text-sm">תרום לקוד פתוח, הצג פרויקטים אישיים והשתמש בפרופיל כקורות חיים דינמיים.</p>
                </div>
                <div class="card p-6 text-center">
                    <i data-lucide="linkedin" class="mx-auto text-brand-blue h-10 w-10 mb-3"></i>
                    <h3 class="font-bold text-lg mb-2 text-brand-dark">נוכחות בלינקדאין</h3>
                    <p class="text-gray-600 text-sm">שתף תובנות מקצועיות, צור קשרים עם לקוחות פוטנציאליים ובנה אוטוריטה בתחומך.</p>
                </div>
                <div class="card p-6 text-center">
                    <i data-lucide="file-text" class="mx-auto text-brand-blue h-10 w-10 mb-3"></i>
                    <h3 class="font-bold text-lg mb-2 text-brand-dark">כתיבת בלוג טכני</h3>
                    <p class="text-gray-600 text-sm">שתף מהידע שלך, פתור בעיות נפוצות והפוך למקור ידע שאחרים רוצים לעבוד איתו.</p>
                </div>
            </div>
        </section>

        <!-- Tips for new freelancers -->
        <section id="tips" class="py-16 md:py-24">
            <h2 class="section-title">טיפים והכוונה למפתחים פרילנסרים</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                 <div class="card p-6">
                    <h3 class="card-title"><i data-lucide="rocket" class="text-brand-blue"></i>מתחילים את הדרך?</h3>
                    <p class="mt-2 text-gray-600">כל מה שמפתח/ת צריך/ה לדעת כדי להתחיל. מבניית פורטפוליו ב-GitHub, פתיחת עוסק ועד מציאת פרויקט הפרילנס הראשון.</p>
                    <a href="#" class="text-brand-blue font-semibold mt-4 inline-block">המדריך המלא למפתח המתחיל &rarr;</a>
                </div>
                <div class="card p-6">
                    <h3 class="card-title"><i data-lucide="dollar-sign" class="text-brand-blue"></i>תמחור ומשא ומתן</h3>
                    <p class="mt-2 text-gray-600">איך לתמחר פרויקט פיתוח? מודלים שונים (שעתי, ריטיינר, פרויקטלי), איך לנהל מו"מ טכני בביטחון ואיך להעלות תעריפים.</p>
                    <a href="#" class="text-brand-blue font-semibold mt-4 inline-block">למדו איך לתמחר פרויקטים &rarr;</a>
                </div>
            </div>
        </section>

        <!-- Worth Following Section -->
        <section id="follow" class="py-16 md:py-24 bg-white rounded-xl shadow-md -mx-4 px-4 md:-mx-8 md:px-8">
            <h2 class="section-title">כדאי לעקוב אחרי</h2>
            <p class="text-center text-gray-600 mb-12 max-w-3xl mx-auto">הישארו מעודכנים עם הפודקאסטים, הקהילות ומובילי הדעה החשובים בתעשייה.</p>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-10">
                <div>
                    <h3 class="text-xl font-bold text-brand-dark mb-4 flex items-center gap-2"><i data-lucide="podcast"></i>פודקאסטים מומלצים</h3>
                    <ul class="space-y-3">
                        <li class="flex items-start gap-3"><i data-lucide="radio-tower" class="text-brand-blue mt-1 shrink-0"></i><div><a href="#" class="font-semibold hover:underline">מפתחים חסרי תרבות</a><p class="text-sm text-gray-500">שיחות על פיתוח, טכנולוגיה והחיים בהייטק.</p></div></li>
                        <li class="flex items-start gap-3"><i data-lucide="radio-tower" class="text-brand-blue mt-1 shrink-0"></i><div><a href="#" class="font-semibold hover:underline">רברס עם פלטפורמה</a><p class="text-sm text-gray-500">ראיונות עומק עם דמויות מפתח בתעשייה.</p></div></li>
                        <li class="flex items-start gap-3"><i data-lucide="radio-tower" class="text-brand-blue mt-1 shrink-0"></i><div><a href="#" class="font-semibold hover:underline">Software Engineering Daily</a><p class="text-sm text-gray-500">פודקאסט יומי (באנגלית) על כל היבטי הנדסת התוכנה.</p></div></li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-xl font-bold text-brand-dark mb-4 flex items-center gap-2"><i data-lucide="users"></i>מובילי דעה וקהילות</h3>
                    <ul class="space-y-3">
                        <li class="flex items-start gap-3"><i data-lucide="instagram" class="text-brand-blue mt-1 shrink-0"></i><div><a href="#" class="font-semibold hover:underline">גיקוניום (אינסטגרם)</a><p class="text-sm text-gray-500">חדשות, ממים ותכנים מעולם ההייטק והגיימינג.</p></div></li>
                        <li class="flex items-start gap-3"><i data-lucide="linkedin" class="text-brand-blue mt-1 shrink-0"></i><div><a href="#" class="font-semibold hover:underline">עוקבים אחרי בכירים בלינקדאין</a><p class="text-sm text-gray-500">מצאו והתחברו למנהלים ו-CTOs בחברות מובילות.</p></div></li>
                        <li class="flex items-start gap-3"><i data-lucide="facebook" class="text-brand-blue mt-1 shrink-0"></i><div><a href="#" class="font-semibold hover:underline">קהילת פיתוח בפייסבוק</a><p class="text-sm text-gray-500">התייעצו, שתפו ולמדו ממאות אלפי מפתחים אחרים.</p></div></li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- Tools & Resources -->
        <section id="tools" class="py-16 md:py-24">
            <h2 class="section-title">כלים ומשאבים חיוניים למפתח הפרילנסר</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
                <div>
                    <h4 class="font-bold text-lg mb-3 text-brand-dark flex items-center gap-2"><i data-lucide="folder-kanban"></i>ניהול פרויקטים</h4>
                    <ul class="space-y-2">
                        <li><a href="https://trello.com/" target="_blank" class="text-gray-600 hover:text-brand-blue">Trello</a></li>
                        <li><a href="https://www.atlassian.com/software/jira" target="_blank" class="text-gray-600 hover:text-brand-blue">Jira</a></li>
                        <li><a href="https://asana.com/" target="_blank" class="text-gray-600 hover:text-brand-blue">Asana</a></li>
                        <li><a href="https://monday.com/" target="_blank" class="text-gray-600 hover:text-brand-blue">Monday.com</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="font-bold text-lg mb-3 text-brand-dark flex items-center gap-2"><i data-lucide="clock"></i>ניהול זמן</h4>
                    <ul class="space-y-2">
                        <li><a href="https://toggl.com/track/" target="_blank" class="text-gray-600 hover:text-brand-blue">Toggl Track</a></li>
                        <li><a href="https://clockify.me/" target="_blank" class="text-gray-600 hover:text-brand-blue">Clockify</a></li>
                        <li><a href="https://www.harvest.com/" target="_blank" class="text-gray-600 hover:text-brand-blue">Harvest</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="font-bold text-lg mb-3 text-brand-dark flex items-center gap-2"><i data-lucide="receipt"></i>חשבוניות והנה"ח</h4>
                     <ul class="space-y-2">
                        <li><a href="https://www.invoiceninja.com/" target="_blank" class="text-gray-600 hover:text-brand-blue">Invoice Ninja</a></li>
                        <li><a href="https://www.ezcount.co.il/" target="_blank" class="text-gray-600 hover:text-brand-blue">iCount (חשבונית ירוקה)</a></li>
                        <li><a href="https://www.invoice-master.co.il/" target="_blank" class="text-gray-600 hover:text-brand-blue">Invoice Master</a></li>
                    </ul>
                </div>
                <div>
                    <h4 class="font-bold text-lg mb-3 text-brand-dark flex items-center gap-2"><i data-lucide="book-open"></i>למידה והתפתחות</h4>
                    <ul class="space-y-2">
                        <li><a href="https://www.udemy.com/" target="_blank" class="text-gray-600 hover:text-brand-blue">Udemy</a></li>
                        <li><a href="https://www.coursera.org/" target="_blank" class="text-gray-600 hover:text-brand-blue">Coursera</a></li>
                        <li><a href="https://frontendmasters.com/" target="_blank" class="text-gray-600 hover:text-brand-blue">Frontend Masters</a></li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- Why XPLACE Section -->
        <section class="bg-brand-dark text-white rounded-xl py-16 px-8 text-center">
            <h2 class="text-3xl md:text-4xl font-bold mb-4">למה מפתחים עובדים עם XPLACE?</h2>
            <p class="max-w-3xl mx-auto mb-8 text-gray-300">אנחנו לא עוד לוח פרויקטים. אנחנו ה-Partner הטכנולוגי שלכם. אנו מחברים אתכם לפרויקטי פיתוח, דאטה ו-DevOps מאתגרים בסטארטאפים וחברות הייטק מובילות, מבטיחים תשלום בזמן ומספקים מעטפת מקצועית מלאה.</p>
            <a href="https://www.xplace.com/dev/about" target="_blank" class="cta-button">גלו את כל היתרונות</a>
        </section>

        <!-- Testimonials -->
        <section id="testimonials" class="py-16 md:py-24">
            <h2 class="section-title">מפתחים ומומחים ממליצים</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8 max-w-4xl mx-auto">
                <div class="testimonial-card p-6 rounded-lg">
                    <p class="text-gray-700 italic">"XPLACE חיברו אותי לפרויקט Backend ב-Node.js ו-Microservices ששדרג לי את הפורטפוליו. התהליך היה מקצועי והתשלום הגיע תמיד בזמן, בלי כאבי ראש."</p>
                    <div class="mt-4 font-semibold text-brand-dark">- גיא כהן, מפתח Backend</div>
                </div>
                <div class="testimonial-card p-6 rounded-lg">
                    <p class="text-gray-700 italic">"כמהנדסת DevOps, הפלטפורמה אפשרה לי להגיע לפרויקטים מורכבים בענן שלא מפורסמים בלוחות הרגילים. הצוות של XPLACE מבין טכנולוגיה וזה יתרון ענק."</p>
                    <div class="mt-4 font-semibold text-brand-dark">- מאיה לוי, מהנדסת DevOps</div>
                </div>
            </div>
        </section>
        
        <!-- More Hubs Section -->
        <section id="more-hubs" class="py-16 md:py-24 border-t">
            <h2 class="section-title">גלו מרכזים נוספים לפרילנסרים</h2>
            <div class="grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-5 gap-4 md:gap-6 max-w-6xl mx-auto">
                <a href="#" class="card p-4 text-center">
                    <i data-lucide="megaphone" class="mx-auto text-brand-blue h-10 w-10 mb-3"></i>
                    <h3 class="font-semibold text-md text-brand-dark">שיווק דיגיטלי</h3>
                </a>
                <a href="#" class="card p-4 text-center">
                    <i data-lucide="video" class="mx-auto text-brand-blue h-10 w-10 mb-3"></i>
                    <h3 class="font-semibold text-md text-brand-dark">וידיאו ומולטימדיה</h3>
                </a>
                <a href="#" class="card p-4 text-center">
                    <i data-lucide="briefcase" class="mx-auto text-brand-blue h-10 w-10 mb-3"></i>
                    <h3 class="font-semibold text-md text-brand-dark">ייעוץ עסקי</h3>
                </a>
                <a href="#" class="card p-4 text-center">
                    <i data-lucide="file-pen-line" class="mx-auto text-brand-blue h-10 w-10 mb-3"></i>
                    <h3 class="font-semibold text-md text-brand-dark">כתיבה ותוכן</h3>
                </a>
                <a href="#" class="card p-4 text-center">
                    <i data-lucide="palette" class="mx-auto text-brand-blue h-10 w-10 mb-3"></i>
                    <h3 class="font-semibold text-md text-brand-dark">עיצוב ו-UI/UX</h3>
                </a>
            </div>
        </section>

    </main>

    <!-- Footer -->
    <footer class="bg-white border-t">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8 py-6 text-center text-gray-500">
            <p>&copy; 2025 XPLACE. כל הזכויות שמורות.</p>
        </div>
    </footer>

    <script>
        // Initialize Lucide Icons
        lucide.createIcons();

        // Mobile Menu Toggle
        const mobileMenuButton = document.getElementById('mobile-menu-button');
        const mobileMenu = document.getElementById('mobile-menu');
        mobileMenuButton.addEventListener('click', () => {
            mobileMenu.classList.toggle('hidden');
        });

        // Chart.js Configuration
        const chartOptions = {
            responsive: true,
            maintainAspectRatio: true,
            plugins: {
                legend: {
                    position: 'bottom',
                    labels: {
                        font: {
                           family: "'Assistant', sans-serif",
                           size: 14
                        },
                         boxWidth: 20,
                         padding: 20
                    }
                },
                tooltip: {
                    callbacks: {
                        label: function(context) {
                            let label = context.label || '';
                            if (label) {
                                label += ': ';
                            }
                            if (context.parsed !== null) {
                                label += 'כ-' + context.parsed + ' ₪ לשעה';
                            }
                            return label;
                        }
                    },
                    bodyFont: {
                        family: "'Assistant', sans-serif"
                    },
                    titleFont: {
                         family: "'Assistant', sans-serif"
                    }
                }
            }
        };

        const chartColors = ['#0052FF', '#0d1c3d', '#00bfff', '#5e82ff', '#ff6384', '#36a2eb'];

        // Chart 1: Salary by Field
        const salaryByFieldCtx = document.getElementById('salaryByFieldChart').getContext('2d');
        new Chart(salaryByFieldCtx, {
            type: 'pie',
            data: {
                labels: ['Backend', 'Frontend', 'DevOps', 'Data Science', 'Cybersecurity', 'QA'],
                datasets: [{
                    label: 'תעריף שעתי ממוצע',
                    data: [350, 320, 400, 380, 420, 280],
                    backgroundColor: chartColors,
                    borderColor: '#ffffff',
                    borderWidth: 2
                }]
            },
            options: chartOptions
        });

        // Chart 2: Salary by Experience
        const salaryByExperienceCtx = document.getElementById('salaryByExperienceChart').getContext('2d');
        new Chart(salaryByExperienceCtx, {
            type: 'pie',
            data: {
                labels: ['ג׳וניור (0-2)', 'מיד (3-5)', 'סניור (6+)'],
                datasets: [{
                    label: 'תעריף שעתי ממוצע',
                    data: [220, 330, 450],
                    backgroundColor: ['#00bfff', '#0052FF', '#0d1c3d'],
                    borderColor: '#ffffff',
                    borderWidth: 2
                }]
            },
            options: chartOptions
        });

        // Chart 3: Salary by Location
        const salaryByLocationCtx = document.getElementById('salaryByLocationChart').getContext('2d');
        new Chart(salaryByLocationCtx, {
            type: 'pie',
            data: {
                labels: ['תל אביב והמרכז', 'חיפה והצפון', 'ירושלים', 'באר שבע והדרום', 'עבודה מרחוק'],
                datasets: [{
                    label: 'תעריף שעתי ממוצע',
                    data: [380, 320, 310, 300, 350],
                    backgroundColor: chartColors.slice(0, 5),
                    borderColor: '#ffffff',
                    borderWidth: 2
                }]
            },
            options: chartOptions
        });
    </script>
</body>
</html>
