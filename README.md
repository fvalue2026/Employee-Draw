<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>رسالة لأحد للفريق</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700;800&display=swap" rel="stylesheet">
  <style>
    :root {
      --primary: #4B2182;
      --primary-2: #5D35A5;
      --primary-3: #6A4FBF;
      --soft-bg: #F7F3FF;
      --soft-purple: #EFE8FA;
      --border: #D8CBF0;
      --text: #2A164D;
      --muted: #7A6A91;
      --white: #FFFFFF;
      --danger: #D94B72;
    }

    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      min-height: 100vh;
      font-family: "Tajawal", Arial, sans-serif;
      color: var(--text);
      background:
        radial-gradient(circle at 16% 50%, rgba(106, 79, 191, 0.14), transparent 30%),
        radial-gradient(circle at 85% 20%, rgba(75, 33, 130, 0.10), transparent 28%),
        linear-gradient(135deg, #FFFFFF 0%, var(--soft-bg) 100%);
      overflow-x: hidden;
    }

    .page {
      min-height: 100vh;
      display: grid;
      grid-template-columns: 0.85fr 1.15fr;
      align-items: center;
      gap: 56px;
      padding: 56px 9vw 44px;
      position: relative;
    }

    .brand-area {
      position: relative;
      min-height: 520px;
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: center;
      isolation: isolate;
    }

    .brand-mark {
      position: absolute;
      width: min(520px, 42vw);
      height: min(520px, 42vw);
      opacity: 0.12;
      z-index: -1;
      transform: translateY(-24px);
    }

    .brand-mark::before,
    .brand-mark::after {
      content: "";
      position: absolute;
      background: linear-gradient(135deg, var(--primary), var(--primary-3));
      filter: blur(0.2px);
    }

    .brand-mark::before {
      width: 44%;
      height: 74%;
      right: 23%;
      top: 9%;
      border-radius: 22px 120px 120px 80px;
      transform: rotate(-28deg);
    }

    .brand-mark::after {
      width: 36%;
      height: 22%;
      left: 9%;
      top: 16%;
      border-radius: 20px 90px 28px 80px;
      transform: rotate(-8deg);
    }

    .brand-copy h2 {
      margin: 0 0 14px;
      font-size: clamp(28px, 3vw, 44px);
      font-weight: 800;
      color: var(--primary);
      letter-spacing: -0.7px;
    }

    .brand-copy p {
      margin: 0;
      font-size: clamp(17px, 1.35vw, 24px);
      color: var(--muted);
      font-weight: 500;
    }

    .decor-line {
      width: 150px;
      height: 2px;
      margin: 28px auto 0;
      background: linear-gradient(90deg, transparent, var(--primary-3), transparent);
      position: relative;
    }

    .decor-line::after {
      content: "";
      width: 8px;
      height: 8px;
      background: var(--primary-3);
      position: absolute;
      left: 50%;
      top: 50%;
      transform: translate(-50%, -50%) rotate(45deg);
      border-radius: 2px;
    }

    .form-wrap {
      width: 100%;
      max-width: 760px;
      margin-inline: auto;
    }

    .card {
      background: var(--white);
      border-radius: 24px;
      overflow: hidden;
      box-shadow: 0 24px 70px rgba(75, 33, 130, 0.16);
      border: 1px solid rgba(216, 203, 240, 0.75);
    }

    .card-header {
      position: relative;
      min-height: 290px;
      padding: 36px 36px 32px;
      text-align: center;
      color: var(--white);
      background:
        radial-gradient(circle at 16% 0%, rgba(255,255,255,0.16), transparent 32%),
        radial-gradient(circle at 78% 8%, rgba(255,255,255,0.10), transparent 28%),
        linear-gradient(135deg, var(--primary-2) 0%, var(--primary) 52%, #35135F 100%);
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }

    .card-header::before,
    .card-header::after {
      content: "";
      position: absolute;
      border-radius: 50%;
      background: rgba(255, 255, 255, 0.06);
      pointer-events: none;
    }

    .card-header::before {
      width: 370px;
      height: 370px;
      right: -130px;
      top: -145px;
    }

    .card-header::after {
      width: 300px;
      height: 300px;
      left: -80px;
      bottom: -170px;
    }

    .icon-circle {
      width: 76px;
      height: 76px;
      border-radius: 50%;
      display: grid;
      place-items: center;
      background: rgba(255, 255, 255, 0.13);
      border: 1px solid rgba(255, 255, 255, 0.12);
      box-shadow: inset 0 0 0 1px rgba(255, 255, 255, 0.05);
      margin-bottom: 18px;
      position: relative;
      z-index: 1;
    }

    .icon-circle svg {
      width: 34px;
      height: 34px;
      stroke: white;
    }

    .card-header h1 {
      margin: 0;
      font-size: clamp(30px, 3vw, 44px);
      line-height: 1.25;
      font-weight: 800;
      letter-spacing: -0.9px;
      position: relative;
      z-index: 1;
    }

    .card-header p {
      margin: 10px 0 0;
      font-size: 17px;
      color: rgba(255, 255, 255, 0.88);
      font-weight: 500;
      position: relative;
      z-index: 1;
    }

    .pill {
      margin-top: 22px;
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 9px 22px;
      border-radius: 999px;
      background: rgba(255, 255, 255, 0.14);
      color: var(--white);
      font-size: 15px;
      font-weight: 700;
      border: 1px solid rgba(255, 255, 255, 0.12);
      position: relative;
      z-index: 1;
    }

    .pill svg {
      width: 18px;
      height: 18px;
    }

    .form-body {
      padding: 38px 46px 42px;
    }

    .field {
      margin-bottom: 26px;
    }

    label {
      display: block;
      margin-bottom: 10px;
      font-size: 17px;
      font-weight: 800;
      color: var(--text);
    }

    .required {
      color: var(--danger);
      margin-right: 4px;
    }

    input,
    textarea {
      width: 100%;
      border: 1px solid var(--border);
      border-radius: 12px;
      background: linear-gradient(180deg, #FFFFFF, #FCFAFF);
      color: var(--text);
      font-family: inherit;
      font-size: 17px;
      padding: 18px 20px;
      outline: none;
      transition: 0.2s ease;
      box-shadow: 0 6px 18px rgba(75, 33, 130, 0.04);
    }

    input {
      height: 58px;
    }

    textarea {
      min-height: 160px;
      resize: vertical;
      line-height: 1.8;
    }

    input::placeholder,
    textarea::placeholder {
      color: #A9A0B8;
    }

    input:focus,
    textarea:focus {
      border-color: var(--primary-3);
      box-shadow: 0 0 0 4px rgba(106, 79, 191, 0.12);
      background: #FFFFFF;
    }

    .counter {
      margin-top: -14px;
      margin-bottom: 22px;
      direction: ltr;
      text-align: left;
      color: var(--muted);
      font-size: 15px;
      font-weight: 700;
    }

    .submit-btn {
      width: 100%;
      height: 64px;
      border: 0;
      border-radius: 12px;
      cursor: pointer;
      font-family: inherit;
      font-size: 19px;
      font-weight: 800;
      color: white;
      background: linear-gradient(135deg, var(--primary-2), var(--primary));
      box-shadow: 0 14px 28px rgba(75, 33, 130, 0.26);
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 12px;
      transition: 0.2s ease;
    }

    .submit-btn:hover {
      transform: translateY(-1px);
      box-shadow: 0 18px 34px rgba(75, 33, 130, 0.32);
    }

    .submit-btn svg {
      width: 24px;
      height: 24px;
    }

    .footer {
      text-align: center;
      margin-top: 22px;
      color: #9A8CAC;
      font-weight: 600;
      font-size: 14px;
    }

    @media (max-width: 980px) {
      .page {
        grid-template-columns: 1fr;
        gap: 24px;
        padding: 32px 18px;
      }

      .brand-area {
        min-height: 250px;
      }

      .brand-mark {
        width: 280px;
        height: 280px;
      }

      .card-header {
        min-height: 250px;
        padding: 30px 24px;
      }

      .form-body {
        padding: 30px 22px 32px;
      }
    }

    @media (max-width: 560px) {
      .brand-area {
        display: none;
      }

      .card {
        border-radius: 20px;
      }

      .card-header h1 {
        font-size: 28px;
      }

      .card-header p {
        font-size: 15px;
      }
    }
  </style>
</head>
<body>
  <main class="page">
    <section class="brand-area" aria-label="منطقة الهوية">
      <div class="brand-mark" aria-hidden="true"></div>
      <div class="brand-copy">
        <h2>صوتك يضيف قيمة</h2>
        <p>شارك بما يلهم، ويقوّي روح الفريق</p>
        <div class="decor-line" aria-hidden="true"></div>
      </div>
    </section>

    <section class="form-wrap" aria-label="نموذج رسالة الأحد">
      <div class="card">
        <header class="card-header">
          <div class="icon-circle" aria-hidden="true">
            <svg viewBox="0 0 24 24" fill="none" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M21 15a4 4 0 0 1-4 4H8l-5 3V7a4 4 0 0 1 4-4h10a4 4 0 0 1 4 4z" />
            </svg>
          </div>
          <h1>رسالة لأحد للفريق</h1>
          <p>شارك الفريق بكلمة، فكرة، أو شكرًا لشيء تحب تعبّر عنه</p>
          <div class="pill">
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <rect x="3" y="4" width="18" height="18" rx="2" ry="2"></rect>
              <line x1="16" y1="2" x2="16" y2="6"></line>
              <line x1="8" y1="2" x2="8" y2="6"></line>
              <line x1="3" y1="10" x2="21" y2="10"></line>
            </svg>
            <span>كل يوم أحد</span>
          </div>
        </header>

        <form class="form-body">
          <div class="field">
            <label for="name">الاسم <span class="required">*</span></label>
            <input id="name" type="text" placeholder="اكتب اسمك الكامل" required />
          </div>

          <div class="field">
            <label for="message">رسالتك للفريق <span class="required">*</span></label>
            <textarea id="message" maxlength="500" placeholder="اكتب رسالتك هنا... قد تكون فكرة، شكرًا مميزًا، أو أي شيء تحب تشاركه مع الفريق" required></textarea>
          </div>

          <div class="counter"><span id="count">0</span> / 500</div>

          <button class="submit-btn" type="submit">
            <span>إرسال الرسالة</span>
            <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true">
              <line x1="22" y1="2" x2="11" y2="13"></line>
              <polygon points="22 2 15 22 11 13 2 9 22 2"></polygon>
            </svg>
          </button>
        </form>
      </div>
      <div class="footer">Value Capital | قيمة المالية</div>
    </section>
  </main>

  <script>
    const textarea = document.getElementById('message');
    const count = document.getElementById('count');

    textarea.addEventListener('input', () => {
      count.textContent = textarea.value.length;
    });
  </script>
</body>
</html>
