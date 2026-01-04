<!doctype html>
<html lang="fa" dir="rtl" class="h-full">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>دایرکتوری جامع هوش مصنوعی</title>
  <script src="/_sdk/element_sdk.js"></script>
  <style>
        @import url('https://fonts.googleapis.com/css2?family=Vazirmatn:wght@300;400;500;600;700;800&display=swap');
        
        body {
            box-sizing: border-box;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        html, body {
            height: 100%;
            font-family: 'Vazirmatn', sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #1e3c72 0%, #2a5298 50%, #7e22ce 100%);
            color: #1a202c;
        }
        
        .main-container {
            width: 100%;
            height: 100%;
            overflow-y: auto;
            background: linear-gradient(135deg, #1e3c72 0%, #2a5298 50%, #7e22ce 100%);
        }
        
        .content-wrapper {
            max-width: 1600px;
            margin: 0 auto;
            padding: 30px 20px;
        }
        
        .header {
            text-align: center;
            margin-bottom: 40px;
            animation: fadeInDown 0.8s ease-out;
        }
        
        .header h1 {
            font-size: 3.8rem;
            font-weight: 800;
            background: linear-gradient(135deg, #ffffff 0%, #fbbf24 50%, #f472b6 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-shadow: 0 0 30px rgba(255,255,255,0.3);
            margin-bottom: 12px;
            letter-spacing: -1px;
        }
        
        .header p {
            font-size: 1.4rem;
            color: #e0e7ff;
            font-weight: 500;
        }
        
        .category-nav {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            justify-content: center;
            margin-bottom: 35px;
            animation: fadeIn 1s ease-out;
        }
        
        .category-btn {
            padding: 14px 30px;
            background: rgba(255, 255, 255, 0.15);
            border: 2px solid rgba(255, 255, 255, 0.25);
            border-radius: 50px;
            color: #ffffff;
            font-size: 1.05rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
            position: relative;
            overflow: hidden;
        }
        
        .category-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            transition: left 0.5s;
        }
        
        .category-btn:hover::before {
            left: 100%;
        }
        
        .category-btn:hover {
            background: rgba(255, 255, 255, 0.25);
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.3);
        }
        
        .category-btn.active {
            background: linear-gradient(135deg, #fbbf24, #f59e0b);
            color: #1a202c;
            box-shadow: 0 10px 30px rgba(251, 191, 36, 0.4);
            border-color: #fbbf24;
        }
        
        .category-content {
            display: none;
        }
        
        .category-content.active {
            display: block;
            animation: fadeInUp 0.6s ease-out;
        }
        
        .tools-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
            gap: 25px;
            margin-bottom: 30px;
        }
        
        .tool-card {
            background: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            padding: 28px;
            box-shadow: 0 15px 40px rgba(0,0,0,0.2);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            border: 2px solid rgba(255, 255, 255, 0.3);
            position: relative;
            overflow: hidden;
        }
        
        .tool-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 4px;
            background: linear-gradient(90deg, #fbbf24, #f59e0b, #ec4899);
            transform: scaleX(0);
            transition: transform 0.4s ease;
        }
        
        .tool-card:hover {
            transform: translateY(-8px) scale(1.02);
            box-shadow: 0 25px 60px rgba(0,0,0,0.3);
            border-color: #fbbf24;
        }
        
        .tool-card:hover::before {
            transform: scaleX(1);
        }
        
        .tool-header {
            display: flex;
            align-items: center;
            gap: 15px;
            margin-bottom: 18px;
            padding-bottom: 15px;
            border-bottom: 2px solid #f0f0f0;
        }
        
        .tool-icon {
            font-size: 2.8rem;
            filter: drop-shadow(0 4px 8px rgba(0,0,0,0.15));
        }
        
        .tool-title h3 {
            font-size: 1.5rem;
            color: #1e3c72;
            font-weight: 700;
            margin-bottom: 3px;
        }
        
        .tool-company {
            font-size: 0.95rem;
            color: #6b7280;
            font-weight: 500;
        }
        
        .tool-description {
            font-size: 1.05rem;
            color: #4b5563;
            line-height: 1.7;
            margin-bottom: 15px;
        }
        
        .tool-features {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-bottom: 18px;
        }
        
        .feature-tag {
            padding: 6px 14px;
            background: linear-gradient(135deg, #e0e7ff, #ddd6fe);
            color: #5b21b6;
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: 600;
        }
        
        .tool-link {
            display: inline-block;
            padding: 12px 28px;
            background: linear-gradient(135deg, #1e3c72, #2a5298);
            color: #ffffff;
            text-decoration: none;
            border-radius: 50px;
            font-size: 1rem;
            font-weight: 600;
            transition: all 0.3s ease;
            box-shadow: 0 6px 20px rgba(30, 60, 114, 0.3);
        }
        
        .tool-link:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 30px rgba(30, 60, 114, 0.5);
            background: linear-gradient(135deg, #2a5298, #1e3c72);
        }
        
        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }
        
        @media (max-width: 768px) {
            .header h1 {
                font-size: 2.5rem;
            }
            
            .header p {
                font-size: 1.1rem;
            }
            
            .category-btn {
                padding: 10px 20px;
                font-size: 0.95rem;
            }
            
            .tools-grid {
                grid-template-columns: 1fr;
            }
            
            .tool-card {
                padding: 20px;
            }
        }
    </style>
  <style>@view-transition { navigation: auto; }</style>
  <script src="/_sdk/data_sdk.js" type="text/javascript"></script>
  <script src="https://cdn.tailwindcss.com" type="text/javascript"></script>
 </head>
 <body class="h-full">
  <div class="main-container">
   <div class="content-wrapper">
    <header class="header">
     <h1 id="site-title">دایرکتوری جامع هوش مصنوعی</h1>
     <p id="site-subtitle">۱۰۰ ابزار هوش مصنوعی برتر دنیا در ۱۰ دسته‌بندی</p>
    </header>
    <nav class="category-nav"><button class="category-btn active" data-category="chat">💬 چت و متن</button> <button class="category-btn" data-category="image">🎨 تصویرسازی</button> <button class="category-btn" data-category="video">🎬 ویدیو</button> <button class="category-btn" data-category="audio">🎙️ صدا و موسیقی</button> <button class="category-btn" data-category="code">👨‍💻 برنامه‌نویسی</button> <button class="category-btn" data-category="business">💼 کسب و کار</button> <button class="category-btn" data-category="design">✨ طراحی</button> <button class="category-btn" data-category="research">🔬 تحقیق</button> <button class="category-btn" data-category="productivity">⚡ بهره‌وری</button> <button class="category-btn" data-category="creative">🌟 خلاقیت</button>
    </nav>
    <main><!-- Category 1: Chat & Text -->
     <div class="category-content active" data-category="chat">
      <div class="tools-grid">
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🤖
         </div>
         <div class="tool-title">
          <h3>ChatGPT</h3>
          <p class="tool-company">OpenAI</p>
         </div>
        </div>
        <p class="tool-description">قدرتمندترین مدل زبانی برای گفتگو، نوشتن محتوا، برنامه‌نویسی و حل مسائل پیچیده</p>
        <div class="tool-features"><span class="feature-tag">GPT-4</span> <span class="feature-tag">چندزبانه</span> <span class="feature-tag">تولید کد</span>
        </div><a href="https://chat.openai.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          💬
         </div>
         <div class="tool-title">
          <h3>Claude</h3>
          <p class="tool-company">Anthropic</p>
         </div>
        </div>
        <p class="tool-description">دستیار هوش مصنوعی با تمرکز بر ایمنی و تحلیل متون طولانی تا 100 هزار کلمه</p>
        <div class="tool-features"><span class="feature-tag">ایمن</span> <span class="feature-tag">تحلیل عمیق</span> <span class="feature-tag">متن طولانی</span>
        </div><a href="https://claude.ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          ✨
         </div>
         <div class="tool-title">
          <h3>Gemini</h3>
          <p class="tool-company">Google</p>
         </div>
        </div>
        <p class="tool-description">مدل چندوجهی گوگل با یکپارچگی عمیق با سرویس‌های Google Workspace</p>
        <div class="tool-features"><span class="feature-tag">چندوجهی</span> <span class="feature-tag">یکپارچگی Google</span> <span class="feature-tag">به‌روز</span>
        </div><a href="https://gemini.google.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🔮
         </div>
         <div class="tool-title">
          <h3>Jasper AI</h3>
          <p class="tool-company">Jasper</p>
         </div>
        </div>
        <p class="tool-description">دستیار نوشتن محتوای بازاریابی، پست شبکه‌های اجتماعی و کپی‌رایتینگ</p>
        <div class="tool-features"><span class="feature-tag">بازاریابی</span> <span class="feature-tag">SEO</span> <span class="feature-tag">قالب‌های آماده</span>
        </div><a href="https://www.jasper.ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          📝
         </div>
         <div class="tool-title">
          <h3>Copy.ai</h3>
          <p class="tool-company">Copy.ai</p>
         </div>
        </div>
        <p class="tool-description">ابزار تولید محتوای بازاریابی، ایمیل و متن تبلیغاتی با سرعت بالا</p>
        <div class="tool-features"><span class="feature-tag">کپی‌رایتینگ</span> <span class="feature-tag">تبلیغات</span> <span class="feature-tag">سریع</span>
        </div><a href="https://www.copy.ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎯
         </div>
         <div class="tool-title">
          <h3>Writesonic</h3>
          <p class="tool-company">Writesonic</p>
         </div>
        </div>
        <p class="tool-description">پلتفرم نوشتن محتوا با تمرکز بر مقالات SEO و محتوای بلاگ</p>
        <div class="tool-features"><span class="feature-tag">مقاله‌نویسی</span> <span class="feature-tag">SEO</span> <span class="feature-tag">بهینه</span>
        </div><a href="https://writesonic.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          📚
         </div>
         <div class="tool-title">
          <h3>QuillBot</h3>
          <p class="tool-company">QuillBot</p>
         </div>
        </div>
        <p class="tool-description">ابزار بازنویسی و بهبود متن با دستور زبان و غلط‌یاب پیشرفته</p>
        <div class="tool-features"><span class="feature-tag">بازنویسی</span> <span class="feature-tag">گرامر</span> <span class="feature-tag">خلاصه‌سازی</span>
        </div><a href="https://quillbot.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🔍
         </div>
         <div class="tool-title">
          <h3>Perplexity AI</h3>
          <p class="tool-company">Perplexity</p>
         </div>
        </div>
        <p class="tool-description">موتور جستجوی هوشمند با پاسخ‌های مستند و دسترسی به اطلاعات به‌روز</p>
        <div class="tool-features"><span class="feature-tag">جستجو</span> <span class="feature-tag">تحقیق</span> <span class="feature-tag">منابع معتبر</span>
        </div><a href="https://www.perplexity.ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          💭
         </div>
         <div class="tool-title">
          <h3>Notion AI</h3>
          <p class="tool-company">Notion</p>
         </div>
        </div>
        <p class="tool-description">دستیار نوشتن یکپارچه در Notion برای خلاصه‌سازی و تولید محتوا</p>
        <div class="tool-features"><span class="feature-tag">یادداشت</span> <span class="feature-tag">یکپارچه</span> <span class="feature-tag">سازماندهی</span>
        </div><a href="https://www.notion.so/product/ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🌐
         </div>
         <div class="tool-title">
          <h3>DeepL Write</h3>
          <p class="tool-company">DeepL</p>
         </div>
        </div>
        <p class="tool-description">بهبود و ویرایش متن با تمرکز بر دستور زبان و سبک نوشتاری</p>
        <div class="tool-features"><span class="feature-tag">ویرایش</span> <span class="feature-tag">چندزبانه</span> <span class="feature-tag">دقیق</span>
        </div><a href="https://www.deepl.com/write" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
      </div>
     </div><!-- Category 2: Image -->
     <div class="category-content" data-category="image">
      <div class="tools-grid">
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎨
         </div>
         <div class="tool-title">
          <h3>Midjourney</h3>
          <p class="tool-company">Midjourney</p>
         </div>
        </div>
        <p class="tool-description">تولید تصاویر هنری باکیفیت فوق‌العاده با استایل‌های متنوع از متن</p>
        <div class="tool-features"><span class="feature-tag">هنری</span> <span class="feature-tag">کیفیت بالا</span> <span class="feature-tag">خلاقانه</span>
        </div><a href="https://www.midjourney.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🖼️
         </div>
         <div class="tool-title">
          <h3>DALL-E 3</h3>
          <p class="tool-company">OpenAI</p>
         </div>
        </div>
        <p class="tool-description">تولید تصویر دقیق از توضیحات متنی با درک عمیق از زمینه</p>
        <div class="tool-features"><span class="feature-tag">دقیق</span> <span class="feature-tag">ویرایش</span> <span class="feature-tag">واقع‌گرا</span>
        </div><a href="https://openai.com/dall-e-3" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🌈
         </div>
         <div class="tool-title">
          <h3>Stable Diffusion</h3>
          <p class="tool-company">Stability AI</p>
         </div>
        </div>
        <p class="tool-description">مدل متن‌باز تولید تصویر با امکان اجرا محلی و سفارشی‌سازی کامل</p>
        <div class="tool-features"><span class="feature-tag">متن‌باز</span> <span class="feature-tag">محلی</span> <span class="feature-tag">سفارشی</span>
        </div><a href="https://stability.ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎭
         </div>
         <div class="tool-title">
          <h3>Leonardo AI</h3>
          <p class="tool-company">Leonardo</p>
         </div>
        </div>
        <p class="tool-description">تولید تصویر با تمرکز بر گیم‌آرت، کاراکتر و دارایی‌های بازی</p>
        <div class="tool-features"><span class="feature-tag">گیم‌آرت</span> <span class="feature-tag">کاراکتر</span> <span class="feature-tag">سریع</span>
        </div><a href="https://leonardo.ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          ✏️
         </div>
         <div class="tool-title">
          <h3>Adobe Firefly</h3>
          <p class="tool-company">Adobe</p>
         </div>
        </div>
        <p class="tool-description">هوش مصنوعی ادوبی برای تولید و ویرایش تصویر در اکوسیستم Creative Cloud</p>
        <div class="tool-features"><span class="feature-tag">Adobe</span> <span class="feature-tag">حرفه‌ای</span> <span class="feature-tag">یکپارچه</span>
        </div><a href="https://www.adobe.com/products/firefly.html" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🖌️
         </div>
         <div class="tool-title">
          <h3>Canva AI</h3>
          <p class="tool-company">Canva</p>
         </div>
        </div>
        <p class="tool-description">تولید تصویر یکپارچه در Canva برای طراحی‌های گرافیکی سریع</p>
        <div class="tool-features"><span class="feature-tag">طراحی</span> <span class="feature-tag">آسان</span> <span class="feature-tag">قالب‌های آماده</span>
        </div><a href="https://www.canva.com/ai-image-generator" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🌟
         </div>
         <div class="tool-title">
          <h3>Ideogram</h3>
          <p class="tool-company">Ideogram</p>
         </div>
        </div>
        <p class="tool-description">تولید تصویر با تمرکز بر تایپوگرافی و متن دقیق در تصاویر</p>
        <div class="tool-features"><span class="feature-tag">تایپوگرافی</span> <span class="feature-tag">متن</span> <span class="feature-tag">دقیق</span>
        </div><a href="https://ideogram.ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎪
         </div>
         <div class="tool-title">
          <h3>Playground AI</h3>
          <p class="tool-company">Playground</p>
         </div>
        </div>
        <p class="tool-description">پلتفرم تولید تصویر با رابط کاربری ساده و امکانات ویرایش</p>
        <div class="tool-features"><span class="feature-tag">ساده</span> <span class="feature-tag">ویرایش</span> <span class="feature-tag">رایگان</span>
        </div><a href="https://playground.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🔮
         </div>
         <div class="tool-title">
          <h3>DreamStudio</h3>
          <p class="tool-company">Stability AI</p>
         </div>
        </div>
        <p class="tool-description">رابط وب برای Stable Diffusion با کنترل‌های پیشرفته</p>
        <div class="tool-features"><span class="feature-tag">پیشرفته</span> <span class="feature-tag">کنترل</span> <span class="feature-tag">قدرتمند</span>
        </div><a href="https://dreamstudio.ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎆
         </div>
         <div class="tool-title">
          <h3>Artbreeder</h3>
          <p class="tool-company">Artbreeder</p>
         </div>
        </div>
        <p class="tool-description">ترکیب و تکامل تصاویر برای ایجاد آثار هنری منحصر به فرد</p>
        <div class="tool-features"><span class="feature-tag">ترکیب</span> <span class="feature-tag">تکامل</span> <span class="feature-tag">خلاقانه</span>
        </div><a href="https://www.artbreeder.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
      </div>
     </div><!-- Category 3: Video -->
     <div class="category-content" data-category="video">
      <div class="tools-grid">
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎬
         </div>
         <div class="tool-title">
          <h3>Runway ML</h3>
          <p class="tool-company">Runway</p>
         </div>
        </div>
        <p class="tool-description">پلتفرم کامل تولید و ویرایش ویدیو با هوش مصنوعی برای فیلمسازان</p>
        <div class="tool-features"><span class="feature-tag">متن به ویدیو</span> <span class="feature-tag">ویرایش</span> <span class="feature-tag">حرفه‌ای</span>
        </div><a href="https://runwayml.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎥
         </div>
         <div class="tool-title">
          <h3>Synthesia</h3>
          <p class="tool-company">Synthesia</p>
         </div>
        </div>
        <p class="tool-description">تولید ویدیوی آواتار با گوینده مجازی بدون نیاز به فیلمبرداری</p>
        <div class="tool-features"><span class="feature-tag">آواتار</span> <span class="feature-tag">گوینده</span> <span class="feature-tag">چندزبانه</span>
        </div><a href="https://www.synthesia.io" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎞️
         </div>
         <div class="tool-title">
          <h3>Pika Labs</h3>
          <p class="tool-company">Pika</p>
         </div>
        </div>
        <p class="tool-description">تبدیل ایده‌های متنی به ویدیوهای کوتاه با کیفیت سینمایی</p>
        <div class="tool-features"><span class="feature-tag">متن به ویدیو</span> <span class="feature-tag">سینمایی</span> <span class="feature-tag">سریع</span>
        </div><a href="https://pika.art" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          📹
         </div>
         <div class="tool-title">
          <h3>Descript</h3>
          <p class="tool-company">Descript</p>
         </div>
        </div>
        <p class="tool-description">ویرایش ویدیو و پادکست با ویرایش متنی و حذف خودکار سکوت</p>
        <div class="tool-features"><span class="feature-tag">ویرایش متنی</span> <span class="feature-tag">پادکست</span> <span class="feature-tag">ساده</span>
        </div><a href="https://www.descript.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎭
         </div>
         <div class="tool-title">
          <h3>HeyGen</h3>
          <p class="tool-company">HeyGen</p>
         </div>
        </div>
        <p class="tool-description">ساخت ویدیوی تبلیغاتی با آواتارهای واقع‌گرا و همگام‌سازی لب</p>
        <div class="tool-features"><span class="feature-tag">تبلیغات</span> <span class="feature-tag">واقع‌گرا</span> <span class="feature-tag">لب‌خوانی</span>
        </div><a href="https://www.heygen.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🌊
         </div>
         <div class="tool-title">
          <h3>Wonder Studio</h3>
          <p class="tool-company">Wonder Dynamics</p>
         </div>
        </div>
        <p class="tool-description">انیمیشن کاراکترهای CG و ادغام خودکار در ویدیوهای لایو اکشن</p>
        <div class="tool-features"><span class="feature-tag">CG</span> <span class="feature-tag">انیمیشن</span> <span class="feature-tag">VFX</span>
        </div><a href="https://wonderdynamics.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎨
         </div>
         <div class="tool-title">
          <h3>Kaiber</h3>
          <p class="tool-company">Kaiber</p>
         </div>
        </div>
        <p class="tool-description">تبدیل تصاویر و ویدیوها به استایل‌های هنری منحصر به فرد</p>
        <div class="tool-features"><span class="feature-tag">هنری</span> <span class="feature-tag">استایل</span> <span class="feature-tag">موزیک ویدیو</span>
        </div><a href="https://kaiber.ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🔄
         </div>
         <div class="tool-title">
          <h3>Topaz Video AI</h3>
          <p class="tool-company">Topaz Labs</p>
         </div>
        </div>
        <p class="tool-description">افزایش وضوح و بهبود کیفیت ویدیوهای قدیمی با هوش مصنوعی</p>
        <div class="tool-features"><span class="feature-tag">ارتقا کیفیت</span> <span class="feature-tag">بهبود</span> <span class="feature-tag">نویززدایی</span>
        </div><a href="https://www.topazlabs.com/topaz-video-ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          ✂️
         </div>
         <div class="tool-title">
          <h3>Opus Clip</h3>
          <p class="tool-company">Opus</p>
         </div>
        </div>
        <p class="tool-description">تبدیل ویدیوهای بلند به کلیپ‌های کوتاه برای شبکه‌های اجتماعی</p>
        <div class="tool-features"><span class="feature-tag">کلیپ‌سازی</span> <span class="feature-tag">شبکه‌های اجتماعی</span> <span class="feature-tag">خودکار</span>
        </div><a href="https://www.opus.pro" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎯
         </div>
         <div class="tool-title">
          <h3>Pictory</h3>
          <p class="tool-company">Pictory</p>
         </div>
        </div>
        <p class="tool-description">تبدیل مقالات و اسکریپت‌ها به ویدیوهای تبلیغاتی جذاب</p>
        <div class="tool-features"><span class="feature-tag">اسکریپت به ویدیو</span> <span class="feature-tag">تبلیغات</span> <span class="feature-tag">سریع</span>
        </div><a href="https://pictory.ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
      </div>
     </div><!-- Category 4: Audio & Music -->
     <div class="category-content" data-category="audio">
      <div class="tools-grid">
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎙️
         </div>
         <div class="tool-title">
          <h3>ElevenLabs</h3>
          <p class="tool-company">ElevenLabs</p>
         </div>
        </div>
        <p class="tool-description">تبدیل متن به گفتار با کیفیت استودیویی و شبیه‌سازی صدا</p>
        <div class="tool-features"><span class="feature-tag">طبیعی</span> <span class="feature-tag">چندزبانه</span> <span class="feature-tag">شبیه‌سازی</span>
        </div><a href="https://elevenlabs.io" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎵
         </div>
         <div class="tool-title">
          <h3>Suno AI</h3>
          <p class="tool-company">Suno</p>
         </div>
        </div>
        <p class="tool-description">تولید موسیقی کامل با خوانندگی و سازهای مختلف از متن</p>
        <div class="tool-features"><span class="feature-tag">موسیقی</span> <span class="feature-tag">خوانندگی</span> <span class="feature-tag">کامل</span>
        </div><a href="https://www.suno.ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎼
         </div>
         <div class="tool-title">
          <h3>Mubert</h3>
          <p class="tool-company">Mubert</p>
         </div>
        </div>
        <p class="tool-description">تولید موسیقی پس‌زمینه برای ویدیو، پادکست و استریم</p>
        <div class="tool-features"><span class="feature-tag">پس‌زمینه</span> <span class="feature-tag">رایالتی‌فری</span> <span class="feature-tag">سریع</span>
        </div><a href="https://mubert.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎹
         </div>
         <div class="tool-title">
          <h3>AIVA</h3>
          <p class="tool-company">AIVA</p>
         </div>
        </div>
        <p class="tool-description">آهنگسازی هوش مصنوعی برای موسیقی کلاسیک و سینمایی</p>
        <div class="tool-features"><span class="feature-tag">کلاسیک</span> <span class="feature-tag">سینمایی</span> <span class="feature-tag">حرفه‌ای</span>
        </div><a href="https://www.aiva.ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🔊
         </div>
         <div class="tool-title">
          <h3>Adobe Podcast</h3>
          <p class="tool-company">Adobe</p>
         </div>
        </div>
        <p class="tool-description">بهبود کیفیت صدا و حذف نویز برای پادکست‌ها</p>
        <div class="tool-features"><span class="feature-tag">نویززدایی</span> <span class="feature-tag">بهبود</span> <span class="feature-tag">استودیویی</span>
        </div><a href="https://podcast.adobe.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎧
         </div>
         <div class="tool-title">
          <h3>Soundraw</h3>
          <p class="tool-company">Soundraw</p>
         </div>
        </div>
        <p class="tool-description">تولید و سفارشی‌سازی موسیقی برای پروژه‌های تجاری</p>
        <div class="tool-features"><span class="feature-tag">سفارشی</span> <span class="feature-tag">تجاری</span> <span class="feature-tag">بدون کپی‌رایت</span>
        </div><a href="https://soundraw.io" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🗣️
         </div>
         <div class="tool-title">
          <h3>Resemble AI</h3>
          <p class="tool-company">Resemble</p>
         </div>
        </div>
        <p class="tool-description">شبیه‌سازی صدای واقعی و تولید گفتار برای بازی‌ها</p>
        <div class="tool-features"><span class="feature-tag">شبیه‌سازی</span> <span class="feature-tag">بازی</span> <span class="feature-tag">واقعی</span>
        </div><a href="https://www.resemble.ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          📢
         </div>
         <div class="tool-title">
          <h3>Play.ht</h3>
          <p class="tool-company">Play.ht</p>
         </div>
        </div>
        <p class="tool-description">تبدیل متن به گفتار برای مقالات و کتاب‌های صوتی</p>
        <div class="tool-features"><span class="feature-tag">کتاب صوتی</span> <span class="feature-tag">مقاله</span> <span class="feature-tag">طبیعی</span>
        </div><a href="https://play.ht" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎶
         </div>
         <div class="tool-title">
          <h3>Boomy</h3>
          <p class="tool-company">Boomy</p>
         </div>
        </div>
        <p class="tool-description">ساخت و انتشار موسیقی در پلتفرم‌های استریمینگ</p>
        <div class="tool-features"><span class="feature-tag">استریمینگ</span> <span class="feature-tag">انتشار</span> <span class="feature-tag">آسان</span>
        </div><a href="https://boomy.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎤
         </div>
         <div class="tool-title">
          <h3>Murf AI</h3>
          <p class="tool-company">Murf</p>
         </div>
        </div>
        <p class="tool-description">استودیوی صداگذاری با صداهای حرفه‌ای و کنترل احساسات</p>
        <div class="tool-features"><span class="feature-tag">صداگذاری</span> <span class="feature-tag">احساسات</span> <span class="feature-tag">حرفه‌ای</span>
        </div><a href="https://murf.ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
      </div>
     </div><!-- Category 5: Code -->
     <div class="category-content" data-category="code">
      <div class="tools-grid">
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          👨‍💻
         </div>
         <div class="tool-title">
          <h3>GitHub Copilot</h3>
          <p class="tool-company">GitHub</p>
         </div>
        </div>
        <p class="tool-description">دستیار برنامه‌نویسی هوشمند برای نوشتن و تکمیل کد در IDE</p>
        <div class="tool-features"><span class="feature-tag">تکمیل کد</span> <span class="feature-tag">چند زبانه</span> <span class="feature-tag">یکپارچه</span>
        </div><a href="https://github.com/features/copilot" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🚀
         </div>
         <div class="tool-title">
          <h3>Cursor</h3>
          <p class="tool-company">Cursor</p>
         </div>
        </div>
        <p class="tool-description">ویرایشگر کد مبتنی بر هوش مصنوعی با قابلیت چت و ویرایش</p>
        <div class="tool-features"><span class="feature-tag">ویرایشگر</span> <span class="feature-tag">چت</span> <span class="feature-tag">هوشمند</span>
        </div><a href="https://cursor.sh" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          ⚡
         </div>
         <div class="tool-title">
          <h3>Tabnine</h3>
          <p class="tool-company">Tabnine</p>
         </div>
        </div>
        <p class="tool-description">تکمیل خودکار کد با یادگیری از سبک کدنویسی شما</p>
        <div class="tool-features"><span class="feature-tag">سفارشی</span> <span class="feature-tag">خصوصی</span> <span class="feature-tag">سریع</span>
        </div><a href="https://www.tabnine.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🔧
         </div>
         <div class="tool-title">
          <h3>Replit Ghostwriter</h3>
          <p class="tool-company">Replit</p>
         </div>
        </div>
        <p class="tool-description">دستیار کدنویسی یکپارچه در محیط Replit آنلاین</p>
        <div class="tool-features"><span class="feature-tag">آنلاین</span> <span class="feature-tag">همکاری</span> <span class="feature-tag">یکپارچه</span>
        </div><a href="https://replit.com/site/ghostwriter" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🧠
         </div>
         <div class="tool-title">
          <h3>Codeium</h3>
          <p class="tool-company">Codeium</p>
         </div>
        </div>
        <p class="tool-description">تکمیل کد رایگان با پشتیبانی از ۷۰+ زبان برنامه‌نویسی</p>
        <div class="tool-features"><span class="feature-tag">رایگان</span> <span class="feature-tag">70+ زبان</span> <span class="feature-tag">سریع</span>
        </div><a href="https://codeium.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎯
         </div>
         <div class="tool-title">
          <h3>Amazon CodeWhisperer</h3>
          <p class="tool-company">AWS</p>
         </div>
        </div>
        <p class="tool-description">دستیار کدنویسی AWS با تمرکز بر امنیت و بهترین شیوه‌ها</p>
        <div class="tool-features"><span class="feature-tag">امن</span> <span class="feature-tag">AWS</span> <span class="feature-tag">اسکن امنیتی</span>
        </div><a href="https://aws.amazon.com/codewhisperer" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🔍
         </div>
         <div class="tool-title">
          <h3>Sourcegraph Cody</h3>
          <p class="tool-company">Sourcegraph</p>
         </div>
        </div>
        <p class="tool-description">دستیار هوش مصنوعی با درک عمیق از پایگاه کد شما</p>
        <div class="tool-features"><span class="feature-tag">جستجو</span> <span class="feature-tag">درک زمینه</span> <span class="feature-tag">قدرتمند</span>
        </div><a href="https://about.sourcegraph.com/cody" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🛠️
         </div>
         <div class="tool-title">
          <h3>Phind</h3>
          <p class="tool-company">Phind</p>
         </div>
        </div>
        <p class="tool-description">موتور جستجوی هوشمند برای برنامه‌نویسان با پاسخ‌های کدی</p>
        <div class="tool-features"><span class="feature-tag">جستجو</span> <span class="feature-tag">کد</span> <span class="feature-tag">توضیحات</span>
        </div><a href="https://www.phind.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🐛
         </div>
         <div class="tool-title">
          <h3>Snyk Code</h3>
          <p class="tool-company">Snyk</p>
         </div>
        </div>
        <p class="tool-description">تشخیص و رفع خودکار آسیب‌پذیری‌های امنیتی در کد</p>
        <div class="tool-features"><span class="feature-tag">امنیت</span> <span class="feature-tag">اسکن</span> <span class="feature-tag">رفع خودکار</span>
        </div><a href="https://snyk.io/product/snyk-code" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          📚
         </div>
         <div class="tool-title">
          <h3>MutableAI</h3>
          <p class="tool-company">Mutable</p>
         </div>
        </div>
        <p class="tool-description">تولید مستندات، تست و ریفکتورینگ خودکار کد</p>
        <div class="tool-features"><span class="feature-tag">مستندات</span> <span class="feature-tag">تست</span> <span class="feature-tag">ریفکتور</span>
        </div><a href="https://mutable.ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
      </div>
     </div><!-- Category 6: Business -->
     <div class="category-content" data-category="business">
      <div class="tools-grid">
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          💼
         </div>
         <div class="tool-title">
          <h3>Salesforce Einstein</h3>
          <p class="tool-company">Salesforce</p>
         </div>
        </div>
        <p class="tool-description">هوش مصنوعی یکپارچه در CRM برای پیش‌بینی فروش و خودکارسازی</p>
        <div class="tool-features"><span class="feature-tag">CRM</span> <span class="feature-tag">پیش‌بینی</span> <span class="feature-tag">خودکار</span>
        </div><a href="https://www.salesforce.com/einstein" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          📊
         </div>
         <div class="tool-title">
          <h3>Tableau AI</h3>
          <p class="tool-company">Salesforce</p>
         </div>
        </div>
        <p class="tool-description">تحلیل و تجسم داده با کمک هوش مصنوعی و پرسش زبان طبیعی</p>
        <div class="tool-features"><span class="feature-tag">داده</span> <span class="feature-tag">تحلیل</span> <span class="feature-tag">تجسم</span>
        </div><a href="https://www.tableau.com/products/tableau-ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎯
         </div>
         <div class="tool-title">
          <h3>HubSpot AI</h3>
          <p class="tool-company">HubSpot</p>
         </div>
        </div>
        <p class="tool-description">دستیار بازاریابی و فروش برای تولید محتوا و مدیریت مشتری</p>
        <div class="tool-features"><span class="feature-tag">بازاریابی</span> <span class="feature-tag">فروش</span> <span class="feature-tag">اتوماسیون</span>
        </div><a href="https://www.hubspot.com/artificial-intelligence" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          📧
         </div>
         <div class="tool-title">
          <h3>Grammarly Business</h3>
          <p class="tool-company">Grammarly</p>
         </div>
        </div>
        <p class="tool-description">بهبود نوشتار تجاری و ایمیل‌ها با پیشنهادات هوشمند</p>
        <div class="tool-features"><span class="feature-tag">نوشتار</span> <span class="feature-tag">ایمیل</span> <span class="feature-tag">حرفه‌ای</span>
        </div><a href="https://www.grammarly.com/business" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🤝
         </div>
         <div class="tool-title">
          <h3>Zoom AI Companion</h3>
          <p class="tool-company">Zoom</p>
         </div>
        </div>
        <p class="tool-description">خلاصه‌سازی جلسات، یادداشت‌برداری و اقدامات بعدی</p>
        <div class="tool-features"><span class="feature-tag">جلسات</span> <span class="feature-tag">خلاصه</span> <span class="feature-tag">یادداشت</span>
        </div><a href="https://www.zoom.com/en/ai-assistant" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          💬
         </div>
         <div class="tool-title">
          <h3>Intercom AI</h3>
          <p class="tool-company">Intercom</p>
         </div>
        </div>
        <p class="tool-description">ربات چت هوشمند برای پشتیبانی مشتری و پاسخگویی خودکار</p>
        <div class="tool-features"><span class="feature-tag">چت</span> <span class="feature-tag">پشتیبانی</span> <span class="feature-tag">24/7</span>
        </div><a href="https://www.intercom.com/ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          📈
         </div>
         <div class="tool-title">
          <h3>Microsoft Copilot</h3>
          <p class="tool-company">Microsoft</p>
         </div>
        </div>
        <p class="tool-description">دستیار هوشمند در Word, Excel, PowerPoint و Teams</p>
        <div class="tool-features"><span class="feature-tag">Office</span> <span class="feature-tag">یکپارچه</span> <span class="feature-tag">بهره‌وری</span>
        </div><a href="https://www.microsoft.com/microsoft-365/copilot" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎤
         </div>
         <div class="tool-title">
          <h3>Otter.ai</h3>
          <p class="tool-company">Otter</p>
         </div>
        </div>
        <p class="tool-description">تبدیل گفتار به متن و یادداشت‌برداری خودکار در جلسات</p>
        <div class="tool-features"><span class="feature-tag">رونویسی</span> <span class="feature-tag">یادداشت</span> <span class="feature-tag">جلسه</span>
        </div><a href="https://otter.ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          📋
         </div>
         <div class="tool-title">
          <h3>Monday AI</h3>
          <p class="tool-company">Monday.com</p>
         </div>
        </div>
        <p class="tool-description">خودکارسازی مدیریت پروژه و اولویت‌بندی وظایف</p>
        <div class="tool-features"><span class="feature-tag">پروژه</span> <span class="feature-tag">وظایف</span> <span class="feature-tag">خودکار</span>
        </div><a href="https://monday.com/ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🔐
         </div>
         <div class="tool-title">
          <h3>Shield AI</h3>
          <p class="tool-company">Shield</p>
         </div>
        </div>
        <p class="tool-description">تشخیص تقلب و امنیت تراکنش‌های مالی با هوش مصنوعی</p>
        <div class="tool-features"><span class="feature-tag">امنیت</span> <span class="feature-tag">تقلب</span> <span class="feature-tag">مالی</span>
        </div><a href="https://shield.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
      </div>
     </div><!-- Category 7: Design -->
     <div class="category-content" data-category="design">
      <div class="tools-grid">
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          ✨
         </div>
         <div class="tool-title">
          <h3>Figma AI</h3>
          <p class="tool-company">Figma</p>
         </div>
        </div>
        <p class="tool-description">طراحی رابط کاربری با کمک هوش مصنوعی و تولید خودکار</p>
        <div class="tool-features"><span class="feature-tag">UI/UX</span> <span class="feature-tag">طراحی</span> <span class="feature-tag">همکاری</span>
        </div><a href="https://www.figma.com/ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎨
         </div>
         <div class="tool-title">
          <h3>Uizard</h3>
          <p class="tool-company">Uizard</p>
         </div>
        </div>
        <p class="tool-description">تبدیل اسکچ دستی به طراحی دیجیتال و پروتوتایپ</p>
        <div class="tool-features"><span class="feature-tag">اسکچ</span> <span class="feature-tag">پروتوتایپ</span> <span class="feature-tag">سریع</span>
        </div><a href="https://uizard.io" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🖼️
         </div>
         <div class="tool-title">
          <h3>Remove.bg</h3>
          <p class="tool-company">Kaleido</p>
         </div>
        </div>
        <p class="tool-description">حذف خودکار پس‌زمینه تصاویر با دقت بالا</p>
        <div class="tool-features"><span class="feature-tag">حذف پس‌زمینه</span> <span class="feature-tag">سریع</span> <span class="feature-tag">دقیق</span>
        </div><a href="https://www.remove.bg" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🌈
         </div>
         <div class="tool-title">
          <h3>Khroma</h3>
          <p class="tool-company">Khroma</p>
         </div>
        </div>
        <p class="tool-description">تولید پالت رنگ شخصی‌سازی شده با یادگیری سلیقه شما</p>
        <div class="tool-features"><span class="feature-tag">رنگ</span> <span class="feature-tag">پالت</span> <span class="feature-tag">شخصی</span>
        </div><a href="https://www.khroma.co" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          📐
         </div>
         <div class="tool-title">
          <h3>AutoDraw</h3>
          <p class="tool-company">Google</p>
         </div>
        </div>
        <p class="tool-description">تبدیل اسکچ‌های ساده به نقاشی‌های حرفه‌ای</p>
        <div class="tool-features"><span class="feature-tag">نقاشی</span> <span class="feature-tag">ساده</span> <span class="feature-tag">رایگان</span>
        </div><a href="https://www.autodraw.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🔮
         </div>
         <div class="tool-title">
          <h3>Designs.ai</h3>
          <p class="tool-company">Inmagine</p>
         </div>
        </div>
        <p class="tool-description">پکیج کامل ابزارهای طراحی: لوگو، ویدیو، صدا و متن</p>
        <div class="tool-features"><span class="feature-tag">همه‌کاره</span> <span class="feature-tag">لوگو</span> <span class="feature-tag">ویدیو</span>
        </div><a href="https://designs.ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          ✏️
         </div>
         <div class="tool-title">
          <h3>Looka</h3>
          <p class="tool-company">Looka</p>
         </div>
        </div>
        <p class="tool-description">طراحی لوگو و برندینگ کامل با هوش مصنوعی</p>
        <div class="tool-features"><span class="feature-tag">لوگو</span> <span class="feature-tag">برند</span> <span class="feature-tag">کامل</span>
        </div><a href="https://looka.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎭
         </div>
         <div class="tool-title">
          <h3>Brandmark</h3>
          <p class="tool-company">Brandmark</p>
         </div>
        </div>
        <p class="tool-description">تولید لوگو، کارت ویزیت و هویت بصری برند</p>
        <div class="tool-features"><span class="feature-tag">هویت بصری</span> <span class="feature-tag">لوگو</span> <span class="feature-tag">کارت</span>
        </div><a href="https://brandmark.io" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🌟
         </div>
         <div class="tool-title">
          <h3>Framer AI</h3>
          <p class="tool-company">Framer</p>
         </div>
        </div>
        <p class="tool-description">طراحی و توسعه وب‌سایت با کمک هوش مصنوعی</p>
        <div class="tool-features"><span class="feature-tag">وب‌سایت</span> <span class="feature-tag">طراحی</span> <span class="feature-tag">کد</span>
        </div><a href="https://www.framer.com/ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎪
         </div>
         <div class="tool-title">
          <h3>Beautiful.ai</h3>
          <p class="tool-company">Beautiful.ai</p>
         </div>
        </div>
        <p class="tool-description">ساخت پرزنتیشن حرفه‌ای با طراحی خودکار اسلاید</p>
        <div class="tool-features"><span class="feature-tag">پرزنتیشن</span> <span class="feature-tag">اسلاید</span> <span class="feature-tag">زیبا</span>
        </div><a href="https://www.beautiful.ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
      </div>
     </div><!-- Category 8: Research -->
     <div class="category-content" data-category="research">
      <div class="tools-grid">
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🔬
         </div>
         <div class="tool-title">
          <h3>Consensus</h3>
          <p class="tool-company">Consensus</p>
         </div>
        </div>
        <p class="tool-description">جستجو در مقالات علمی و استخراج یافته‌های تحقیقاتی</p>
        <div class="tool-features"><span class="feature-tag">علمی</span> <span class="feature-tag">مقالات</span> <span class="feature-tag">تحقیق</span>
        </div><a href="https://consensus.app" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          📚
         </div>
         <div class="tool-title">
          <h3>Elicit</h3>
          <p class="tool-company">Elicit</p>
         </div>
        </div>
        <p class="tool-description">دستیار تحقیق برای تحلیل مقالات و استخراج داده</p>
        <div class="tool-features"><span class="feature-tag">تحلیل</span> <span class="feature-tag">استخراج</span> <span class="feature-tag">خلاصه</span>
        </div><a href="https://elicit.org" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🧪
         </div>
         <div class="tool-title">
          <h3>Scite</h3>
          <p class="tool-company">Scite</p>
         </div>
        </div>
        <p class="tool-description">بررسی استنادات و اعتبار مقالات علمی</p>
        <div class="tool-features"><span class="feature-tag">استناد</span> <span class="feature-tag">اعتبار</span> <span class="feature-tag">ارزیابی</span>
        </div><a href="https://scite.ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          📖
         </div>
         <div class="tool-title">
          <h3>Semantic Scholar</h3>
          <p class="tool-company">AI2</p>
         </div>
        </div>
        <p class="tool-description">موتور جستجوی هوشمند برای ادبیات علمی و تحقیقاتی</p>
        <div class="tool-features"><span class="feature-tag">جستجو</span> <span class="feature-tag">علمی</span> <span class="feature-tag">رایگان</span>
        </div><a href="https://www.semanticscholar.org" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🔍
         </div>
         <div class="tool-title">
          <h3>ResearchRabbit</h3>
          <p class="tool-company">ResearchRabbit</p>
         </div>
        </div>
        <p class="tool-description">کشف مقالات مرتبط و ساخت شبکه تحقیقاتی</p>
        <div class="tool-features"><span class="feature-tag">کشف</span> <span class="feature-tag">ارتباط</span> <span class="feature-tag">شبکه</span>
        </div><a href="https://www.researchrabbit.ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          📝
         </div>
         <div class="tool-title">
          <h3>Scholarcy</h3>
          <p class="tool-company">Scholarcy</p>
         </div>
        </div>
        <p class="tool-description">خلاصه‌سازی خودکار مقالات و استخراج نکات کلیدی</p>
        <div class="tool-features"><span class="feature-tag">خلاصه</span> <span class="feature-tag">نکات</span> <span class="feature-tag">سریع</span>
        </div><a href="https://www.scholarcy.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🧬
         </div>
         <div class="tool-title">
          <h3>AlphaFold</h3>
          <p class="tool-company">DeepMind</p>
         </div>
        </div>
        <p class="tool-description">پیش‌بینی ساختار سه‌بعدی پروتئین‌ها</p>
        <div class="tool-features"><span class="feature-tag">بیوانفورماتیک</span> <span class="feature-tag">پروتئین</span> <span class="feature-tag">پیش‌بینی</span>
        </div><a href="https://alphafold.ebi.ac.uk" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          💊
         </div>
         <div class="tool-title">
          <h3>Iris.ai</h3>
          <p class="tool-company">Iris</p>
         </div>
        </div>
        <p class="tool-description">جستجوی هوشمند در ادبیات علمی و پزشکی</p>
        <div class="tool-features"><span class="feature-tag">پزشکی</span> <span class="feature-tag">جستجو</span> <span class="feature-tag">هوشمند</span>
        </div><a href="https://iris.ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          📊
         </div>
         <div class="tool-title">
          <h3>Connected Papers</h3>
          <p class="tool-company">Connected Papers</p>
         </div>
        </div>
        <p class="tool-description">نمایش بصری ارتباط بین مقالات علمی</p>
        <div class="tool-features"><span class="feature-tag">بصری</span> <span class="feature-tag">ارتباط</span> <span class="feature-tag">نمودار</span>
        </div><a href="https://www.connectedpapers.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎓
         </div>
         <div class="tool-title">
          <h3>Litmaps</h3>
          <p class="tool-company">Litmaps</p>
         </div>
        </div>
        <p class="tool-description">نقشه‌برداری از ادبیات تحقیق و دنبال کردن به‌روزرسانی‌ها</p>
        <div class="tool-features"><span class="feature-tag">نقشه</span> <span class="feature-tag">دنبال کردن</span> <span class="feature-tag">به‌روز</span>
        </div><a href="https://www.litmaps.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
      </div>
     </div><!-- Category 9: Productivity -->
     <div class="category-content" data-category="productivity">
      <div class="tools-grid">
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          ⚡
         </div>
         <div class="tool-title">
          <h3>Motion</h3>
          <p class="tool-company">Motion</p>
         </div>
        </div>
        <p class="tool-description">برنامه‌ریزی هوشمند روزانه و مدیریت خودکار تقویم</p>
        <div class="tool-features"><span class="feature-tag">تقویم</span> <span class="feature-tag">برنامه‌ریزی</span> <span class="feature-tag">خودکار</span>
        </div><a href="https://www.usemotion.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          📧
         </div>
         <div class="tool-title">
          <h3>SaneBox</h3>
          <p class="tool-company">SaneBox</p>
         </div>
        </div>
        <p class="tool-description">مدیریت هوشمند ایمیل و فیلتر کردن پیام‌های مهم</p>
        <div class="tool-features"><span class="feature-tag">ایمیل</span> <span class="feature-tag">فیلتر</span> <span class="feature-tag">هوشمند</span>
        </div><a href="https://www.sanebox.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          ✍️
         </div>
         <div class="tool-title">
          <h3>Superhuman</h3>
          <p class="tool-company">Superhuman</p>
         </div>
        </div>
        <p class="tool-description">کلاینت ایمیل سریع با قابلیت‌های هوش مصنوعی</p>
        <div class="tool-features"><span class="feature-tag">سریع</span> <span class="feature-tag">ایمیل</span> <span class="feature-tag">کیبورد</span>
        </div><a href="https://superhuman.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          📝
         </div>
         <div class="tool-title">
          <h3>Mem</h3>
          <p class="tool-company">Mem</p>
         </div>
        </div>
        <p class="tool-description">یادداشت‌برداری هوشمند با سازماندهی خودکار</p>
        <div class="tool-features"><span class="feature-tag">یادداشت</span> <span class="feature-tag">سازماندهی</span> <span class="feature-tag">جستجو</span>
        </div><a href="https://get.mem.ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎯
         </div>
         <div class="tool-title">
          <h3>Reclaim AI</h3>
          <p class="tool-company">Reclaim</p>
         </div>
        </div>
        <p class="tool-description">بهینه‌سازی تقویم و ایجاد زمان برای کارهای مهم</p>
        <div class="tool-features"><span class="feature-tag">تقویم</span> <span class="feature-tag">بهینه‌سازی</span> <span class="feature-tag">زمان</span>
        </div><a href="https://reclaim.ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🤖
         </div>
         <div class="tool-title">
          <h3>Zapier AI</h3>
          <p class="tool-company">Zapier</p>
         </div>
        </div>
        <p class="tool-description">خودکارسازی هوشمند بین اپلیکیشن‌های مختلف</p>
        <div class="tool-features"><span class="feature-tag">اتوماسیون</span> <span class="feature-tag">یکپارچگی</span> <span class="feature-tag">هوشمند</span>
        </div><a href="https://zapier.com/ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          📊
         </div>
         <div class="tool-title">
          <h3>Timely</h3>
          <p class="tool-company">Timely</p>
         </div>
        </div>
        <p class="tool-description">ثبت خودکار زمان و تحلیل بهره‌وری</p>
        <div class="tool-features"><span class="feature-tag">زمان‌سنجی</span> <span class="feature-tag">خودکار</span> <span class="feature-tag">تحلیل</span>
        </div><a href="https://timelyapp.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🔔
         </div>
         <div class="tool-title">
          <h3>Todoist AI</h3>
          <p class="tool-company">Todoist</p>
         </div>
        </div>
        <p class="tool-description">مدیریت وظایف با پیشنهادات هوشمند و اولویت‌بندی</p>
        <div class="tool-features"><span class="feature-tag">وظایف</span> <span class="feature-tag">اولویت</span> <span class="feature-tag">یادآور</span>
        </div><a href="https://todoist.com/ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          💡
         </div>
         <div class="tool-title">
          <h3>Taskade</h3>
          <p class="tool-company">Taskade</p>
         </div>
        </div>
        <p class="tool-description">فضای کاری هوشمند با چت، وظایف و نقشه ذهنی</p>
        <div class="tool-features"><span class="feature-tag">همکاری</span> <span class="feature-tag">وظایف</span> <span class="feature-tag">نقشه ذهنی</span>
        </div><a href="https://www.taskade.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎨
         </div>
         <div class="tool-title">
          <h3>Magical</h3>
          <p class="tool-company">Magical</p>
         </div>
        </div>
        <p class="tool-description">خودکارسازی وظایف تکراری با میانبرهای متنی</p>
        <div class="tool-features"><span class="feature-tag">خودکار</span> <span class="feature-tag">میانبر</span> <span class="feature-tag">سریع</span>
        </div><a href="https://www.getmagical.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
      </div>
     </div><!-- Category 10: Creative -->
     <div class="category-content" data-category="creative">
      <div class="tools-grid">
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🌟
         </div>
         <div class="tool-title">
          <h3>Tome</h3>
          <p class="tool-company">Tome</p>
         </div>
        </div>
        <p class="tool-description">ساخت پرزنتیشن و استوری تعاملی با هوش مصنوعی</p>
        <div class="tool-features"><span class="feature-tag">پرزنتیشن</span> <span class="feature-tag">تعاملی</span> <span class="feature-tag">استوری</span>
        </div><a href="https://tome.app" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          ✨
         </div>
         <div class="tool-title">
          <h3>Gamma</h3>
          <p class="tool-company">Gamma</p>
         </div>
        </div>
        <p class="tool-description">تبدیل یادداشت‌ها به پرزنتیشن و مستندات زیبا</p>
        <div class="tool-features"><span class="feature-tag">مستندات</span> <span class="feature-tag">پرزنتیشن</span> <span class="feature-tag">سریع</span>
        </div><a href="https://gamma.app" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎭
         </div>
         <div class="tool-title">
          <h3>Lumen5</h3>
          <p class="tool-company">Lumen5</p>
         </div>
        </div>
        <p class="tool-description">تبدیل مقالات و پست‌های بلاگ به ویدیوهای جذاب</p>
        <div class="tool-features"><span class="feature-tag">مقاله به ویدیو</span> <span class="feature-tag">شبکه اجتماعی</span> <span class="feature-tag">سریع</span>
        </div><a href="https://lumen5.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎬
         </div>
         <div class="tool-title">
          <h3>InVideo AI</h3>
          <p class="tool-company">InVideo</p>
         </div>
        </div>
        <p class="tool-description">تولید ویدیوهای بازاریابی با قالب‌های حرفه‌ای</p>
        <div class="tool-features"><span class="feature-tag">ویدیو</span> <span class="feature-tag">قالب</span> <span class="feature-tag">بازاریابی</span>
        </div><a href="https://invideo.io/ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🖼️
         </div>
         <div class="tool-title">
          <h3>Visme AI</h3>
          <p class="tool-company">Visme</p>
         </div>
        </div>
        <p class="tool-description">ساخت اینفوگرافیک، پرزنتیشن و محتوای بصری</p>
        <div class="tool-features"><span class="feature-tag">اینفوگرافیک</span> <span class="feature-tag">بصری</span> <span class="feature-tag">متنوع</span>
        </div><a href="https://www.visme.co/ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎨
         </div>
         <div class="tool-title">
          <h3>Simplified</h3>
          <p class="tool-company">Simplified</p>
         </div>
        </div>
        <p class="tool-description">پلتفرم همه‌کاره برای طراحی، ویدیو و محتوای نوشتاری</p>
        <div class="tool-features"><span class="feature-tag">همه‌کاره</span> <span class="feature-tag">طراحی</span> <span class="feature-tag">محتوا</span>
        </div><a href="https://simplified.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎪
         </div>
         <div class="tool-title">
          <h3>Kapwing AI</h3>
          <p class="tool-company">Kapwing</p>
         </div>
        </div>
        <p class="tool-description">ویرایش ویدیو آنلاین با ابزارهای هوش مصنوعی</p>
        <div class="tool-features"><span class="feature-tag">ویرایش</span> <span class="feature-tag">ویدیو</span> <span class="feature-tag">آنلاین</span>
        </div><a href="https://www.kapwing.com/ai" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🌈
         </div>
         <div class="tool-title">
          <h3>Craiyon</h3>
          <p class="tool-company">Craiyon</p>
         </div>
        </div>
        <p class="tool-description">تولید سریع و رایگان تصویر از متن</p>
        <div class="tool-features"><span class="feature-tag">رایگان</span> <span class="feature-tag">سریع</span> <span class="feature-tag">ساده</span>
        </div><a href="https://www.craiyon.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          🎯
         </div>
         <div class="tool-title">
          <h3>Gencraft</h3>
          <p class="tool-company">Gencraft</p>
         </div>
        </div>
        <p class="tool-description">تولید هنر دیجیتال و عکس با استایل‌های متنوع</p>
        <div class="tool-features"><span class="feature-tag">هنری</span> <span class="feature-tag">استایل</span> <span class="feature-tag">عکس</span>
        </div><a href="https://gencraft.com" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
       <div class="tool-card">
        <div class="tool-header">
         <div class="tool-icon">
          ✨
         </div>
         <div class="tool-title">
          <h3>NightCafe</h3>
          <p class="tool-company">NightCafe</p>
         </div>
        </div>
        <p class="tool-description">تولید هنر با الگوریتم‌های مختلف و جامعه هنرمندان</p>
        <div class="tool-features"><span class="feature-tag">هنری</span> <span class="feature-tag">جامعه</span> <span class="feature-tag">متنوع</span>
        </div><a href="https://nightcafe.studio" target="_blank" rel="noopener noreferrer" class="tool-link">مشاهده →</a>
       </div>
      </div>
     </div>
    </main>
   </div>
  </div>
  <script>
        const defaultConfig = {
            site_title: "دایرکتوری جامع هوش مصنوعی",
            site_subtitle: "۱۰۰ ابزار هوش مصنوعی برتر دنیا در ۱۰ دسته‌بندی"
        };

        let config = { ...defaultConfig };

        const categoryButtons = document.querySelectorAll('.category-btn');
        const categoryContents = document.querySelectorAll('.category-content');

        categoryButtons.forEach(button => {
            button.addEventListener('click', () => {
                const category = button.getAttribute('data-category');
                
                categoryButtons.forEach(btn => btn.classList.remove('active'));
                categoryContents.forEach(content => content.classList.remove('active'));
                
                button.classList.add('active');
                document.querySelector(`.category-content[data-category="${category}"]`).classList.add('active');
                
                window.scrollTo({ top: 0, behavior: 'smooth' });
            });
        });

        async function onConfigChange(newConfig) {
            const titleElement = document.getElementById('site-title');
            const subtitleElement = document.getElementById('site-subtitle');
            
            if (titleElement) {
                titleElement.textContent = newConfig.site_title || defaultConfig.site_title;
            }
            
            if (subtitleElement) {
                subtitleElement.textContent = newConfig.site_subtitle || defaultConfig.site_subtitle;
            }
        }

        if (window.elementSdk) {
            window.elementSdk.init({
                defaultConfig,
                onConfigChange,
                mapToCapabilities: (config) => ({
                    recolorables: [],
                    borderables: [],
                    fontEditable: undefined,
                    fontSizeable: undefined
                }),
                mapToEditPanelValues: (config) => new Map([
                    ["site_title", config.site_title || defaultConfig.site_title],
                    ["site_subtitle", config.site_subtitle || defaultConfig.site_subtitle]
                ])
            });
        }
    </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9b8ad3fef011d2eb',t:'MTc2NzUzMDY3NS4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
