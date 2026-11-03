<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Який формат допомоги найбільше відповідає вашому запиту?</title>
    <style>
        :root {
            --bg-color: #F9F8F3;
            --card-bg: #FFFFFF;
            --primary-color: #2F4F4F;
            --accent-green: #E8EFE3;
            --text-color: #333333;
            --border-color: #DDE5D6;
            --hover-color: #F0F4ED;
            --alert-bg: #FFF3E0;
            --alert-border: #FFE0B2;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            line-height: 1.6;
            margin: 0;
            padding: 20px;
        }

        .container {
            max-width: 750px;
            margin: 40px auto;
            background: var(--card-bg);
            padding: 40px;
            border-radius: 16px;
            box-shadow: 0 10px 30px rgba(47, 79, 79, 0.08);
            border: 1px solid var(--border-color);
        }

        h1 {
            color: var(--primary-color);
            font-size: 24px;
            margin-bottom: 10px;
            text-align: center;
        }

        .subtitle {
            text-align: center;
            color: #666;
            font-size: 14px;
            margin-bottom: 25px;
        }

        .privacy-note {
            background-color: var(--accent-green);
            padding: 10px 15px;
            border-radius: 8px;
            font-size: 13px;
            text-align: center;
            color: var(--primary-color);
            margin-bottom: 25px;
            font-weight: 500;
        }

        .question-card {
            display: none;
        }

        .question-card.active {
            display: block;
        }

        .question-title {
            font-size: 17px;
            font-weight: 600;
            color: var(--primary-color);
            margin-bottom: 20px;
        }

        .options {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        .option-label {
            background-color: var(--bg-color);
            border: 1px solid var(--border-color);
            padding: 14px 18px;
            border-radius: 10px;
            font-size: 14px;
            cursor: pointer;
            transition: all 0.2s ease;
            display: flex;
            align-items: flex-start;
            gap: 10px;
        }

        .option-label:hover {
            background-color: var(--accent-green);
            border-color: var(--primary-color);
        }

        .option-label input {
            margin-top: 3px;
            accent-color: var(--primary-color);
        }

        .nav-btn {
            margin-top: 25px;
            background-color: var(--primary-color);
            color: white;
            border: none;
            padding: 12px 24px;
            font-size: 15px;
            border-radius: 8px;
            cursor: pointer;
            float: right;
            transition: opacity 0.2s;
        }

        .nav-btn:hover {
            opacity: 0.9;
        }

        .results {
            display: none;
        }

        .results h2 {
            color: var(--primary-color);
            margin-bottom: 15px;
            text-align: center;
        }

        .result-block {
            background: var(--bg-color);
            padding: 20px;
            border-radius: 12px;
            margin-bottom: 15px;
            border-left: 5px solid var(--primary-color);
        }

        .result-block h3 {
            margin-top: 0;
            color: var(--primary-color);
            font-size: 18px;
        }

        .disclaimer {
            font-size: 13px;
            color: #666;
            margin-top: 25px;
            padding: 15px;
            background: #FAFAFA;
            border-radius: 8px;
            border: 1px solid #EEEEEE;
            text-align: center;
        }

        .cta-box {
            margin-top: 20px;
            text-align: center;
            background: var(--accent-green);
            padding: 20px;
            border-radius: 12px;
        }

        .cta-btn {
            background-color: var(--primary-color);
            color: white;
            border: none;
            padding: 12px 24px;
            font-size: 15px;
            border-radius: 8px;
            cursor: pointer;
            text-decoration: none;
            display: inline-block;
            margin-top: 10px;
            font-weight: 600;
        }

        .progress {
            font-size: 12px;
            color: #888;
            margin-bottom: 15px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .restart-container {
            text-align: center;
            margin-top: 20px;
        }

        .restart-btn {
            background: none;
            border: 1px solid var(--primary-color);
            color: var(--primary-color);
            padding: 8px 16px;
            border-radius: 6px;
            cursor: pointer;
            font-size: 13px;
        }
    </style>
</head>
<body>

<div class="container">
    <h1>Який формат допомоги найбільше відповідає вашому запиту?</h1>
    <div class="subtitle">Пройдіть короткий тест (це займе близько 2–3 хвилин)</div>
    <div class="privacy-note">🔒 Вся інформація є суто конфіденційною. Ваші відповіді нікуди не надсилаються і бачите їх лише ви на своєму екрані.</div>

    <div id="quiz-form">
        <!-- Питання 1 -->
        <div class="question-card active" data-step="1">
            <div class="progress">Питання 1 з 7</div>
            <div class="question-title">1. Що зараз відбувається у вашому житті?</div>
            <div class="options">
                <label class="option-label"><input type="radio" name="q1" value="coaching"> Я хочу змін, маю бажання або ціль, але не розумію, як рухатися далі.</label>
                <label class="option-label"><input type="radio" name="q1" value="therapy"> Мене турбують переживання, емоційний біль або досвід, який продовжує впливати на мене.</label>
                <label class="option-label" data-safety="psychiatry"><input type="radio" name="q1" value="psychiatry"> Я помічаю зміни психічного стану, які суттєво впливають на моє життя, і хочу оцінити потребу в медичній допомозі.</label>
                <label class="option-label"><input type="radio" name="q1" value="mentoring"> Я хочу розвиватися у певній сфері, використовуючи досвід людини, яка вже пройшла подібний шлях.</label>
                <label class="option-label"><input type="radio" name="q1" value="consulting"> Я зіткнувся/-лася з конкретною проблемою і потребую експертного аналізу та рекомендацій.</label>
                <label class="option-label"><input type="radio" name="q1" value="training"> Я хочу опанувати конкретну навичку або покращити якість її виконання.</label>
            </div>
            <button class="nav-btn" onclick="nextStep(1)">Далі ➔</button>
        </div>

        <!-- Питання 2 -->
        <div class="question-card" data-step="2">
            <div class="progress">Питання 2 з 7</div>
            <div class="question-title">2. Що найбільше заважає вам зараз?</div>
            <div class="options">
                <label class="option-label"><input type="radio" name="q2" value="coaching"> Невизначеність, складність із вибором, власними рішеннями або переходом до дій.</label>
                <label class="option-label"><input type="radio" name="q2" value="therapy"> Страхи, тривожні переживання, болісний досвід або повторювані емоційні реакції.</label>
                <label class="option-label" data-safety="psychiatry"><input type="radio" name="q2" value="psychiatry"> Стійкі або виражені зміни настрою, сну, мислення чи поведінки, які потребують оцінки лікаря.</label>
                <label class="option-label"><input type="radio" name="q2" value="mentoring"> Брак досвіду, орієнтирів і розуміння, як діяти в конкретній сфері.</label>
                <label class="option-label"><input type="radio" name="q2" value="consulting"> Відсутність фахового розуміння, як розв’язати конкретну проблему.</label>
                <label class="option-label"><input type="radio" name="q2" value="training"> Брак практики, системності та відпрацьованих навичок.</label>
            </div>
            <button class="nav-btn" onclick="nextStep(2)">Далі ➔</button>
        </div>

        <!-- Питання 3 -->
        <div class="question-card" data-step="3">
            <div class="progress">Питання 3 з 7</div>
            <div class="question-title">3. Якого результату ви очікуєте від роботи зі спеціалістом?</div>
            <div class="options">
                <label class="option-label"><input type="radio" name="q3" value="coaching"> Краще зрозуміти себе, побачити нові можливості, сформувати власне рішення та діяти.</label>
                <label class="option-label"><input type="radio" name="q3" value="therapy"> Розібратися з внутрішніми переживаннями, опрацювати психологічні труднощі.</label>
                <label class="option-label" data-safety="psychiatry"><input type="radio" name="q3" value="psychiatry"> Отримати медичну оцінку стану, визначити можливі причини симптомів і тактику лікування.</label>
                <label class="option-label"><input type="radio" name="q3" value="mentoring"> Отримати досвід, орієнтири та практичні рекомендації від людини з відповідною експертизою.</label>
                <label class="option-label"><input type="radio" name="q3" value="consulting"> Отримати професійну оцінку ситуації та конкретні рішення або рекомендації.</label>
                <label class="option-label"><input type="radio" name="q3" value="training"> Навчитися виконувати певні дії, закріпити знання та відпрацювати навички.</label>
            </div>
            <button class="nav-btn" onclick="nextStep(3)">Далі ➔</button>
        </div>

        <!-- Питання 4 -->
        <div class="question-card" data-step="4">
            <div class="progress">Питання 4 з 7</div>
            <div class="question-title">4. Як ви почуваєтеся у повсякденному житті?</div>
            <div class="options">
                <label class="option-label"><input type="radio" name="q4" value="coaching"> Загалом функціоную, але відчуваю потребу в змінах і хочу рухатися до бажаного.</label>
                <label class="option-label"><input type="radio" name="q4" value="therapy"> Мої переживання впливають на стосунки, самооцінку або повсякденне життя.</label>
                <label class="option-label" data-safety="psychiatry"><input type="radio" name="q4" value="psychiatry"> Мій стан помітно порушує повсякденне функціонування, і я хочу звернутися до лікаря.</label>
                <label class="option-label"><input type="radio" name="q4" value="mentoring"> Почуваюся достатньо добре, але хочу професійного розвитку.</label>
                <label class="option-label"><input type="radio" name="q4" value="consulting"> Маю конкретну ситуацію, яку самостійно не можу вирішити через брак експертизи.</label>
                <label class="option-label"><input type="radio" name="q4" value="training"> Маю сили та мотивацію навчатися, практикувати й покращувати результат.</label>
            </div>
            <button class="nav-btn" onclick="nextStep(4)">Далі ➔</button>
        </div>

        <!-- Питання 5 -->
        <div class="question-card" data-step="5">
            <div class="progress">Питання 5 з 7</div>
            <div class="question-title">5. Який спосіб взаємодії вам найбільше потрібен?</div>
            <div class="options">
                <label class="option-label"><input type="radio" name="q5" value="coaching"> Партнерський діалог, запитання, дослідження власних переконань і пошук своїх відповідей.</label>
                <label class="option-label"><input type="radio" name="q5" value="therapy"> Професійна психологічна робота з переживаннями, емоціями та минулим досвідом.</label>
                <label class="option-label" data-safety="psychiatry"><input type="radio" name="q5" value="psychiatry"> Медична консультація, діагностична оцінка та визначення потреби в лікуванні.</label>
                <label class="option-label"><input type="radio" name="q5" value="mentoring"> Обмін досвідом, розбір практичних ситуацій, поради та орієнтири.</label>
                <label class="option-label"><input type="radio" name="q5" value="consulting"> Аналіз проблеми, пошук причин і розробка професійних рекомендацій.</label>
                <label class="option-label"><input type="radio" name="q5" value="training"> Структуроване навчання, вправи, зворотний зв’язок і практика.</label>
            </div>
            <button class="nav-btn" onclick="nextStep(5)">Далі ➔</button>
        </div>

        <!-- Питання 6 -->
        <div class="question-card" data-step="6">
            <div class="progress">Питання 6 з 7</div>
            <div class="question-title">6. На чому ви хочете зосередитися?</div>
            <div class="options">
                <label class="option-label"><input type="radio" name="q6" value="coaching"> На теперішньому та майбутньому: що я хочу змінити, що мені заважає і які рішення можу прийняти.</label>
                <label class="option-label"><input type="radio" name="q6" value="therapy"> На тому, як минулий досвід і психологічні труднощі впливають на моє теперішнє життя.</label>
                <label class="option-label" data-safety="psychiatry"><input type="radio" name="q6" value="psychiatry"> На симптомах, змінах психічного стану та можливих медичних причинах.</label>
                <label class="option-label"><input type="radio" name="q6" value="mentoring"> На тому, як інші люди вирішували подібні завдання і що з їхнього досвіду можна застосувати.</label>
                <label class="option-label"><input type="radio" name="q6" value="consulting"> На пошуку найефективнішого рішення конкретної професійної чи життєвої задачі.</label>
                <label class="option-label"><input type="radio" name="q6" value="training"> На формуванні конкретних компетенцій та їх практичному застосуванні.</label>
            </div>
            <button class="nav-btn" onclick="nextStep(6)">Далі ➔</button>
        </div>

        <!-- Питання 7 -->
        <div class="question-card" data-step="7">
            <div class="progress">Питання 7 з 7</div>
            <div class="question-title">7. Що для вас буде ознакою успішної роботи?</div>
            <div class="options">
                <label class="option-label"><input type="radio" name="q7" value="coaching"> Я самостійно прийняв/-ла рішення, визначив/-ла напрям і почав/-ла діяти.</label>
                <label class="option-label"><input type="radio" name="q7" value="therapy"> Я краще розумію себе, маю більше можливостей справлятися з переживаннями та психологічними труднощами.</label>
                <label class="option-label" data-safety="psychiatry"><input type="radio" name="q7" value="psychiatry"> Я отримав/-ла фахову медичну оцінку та визначився/-лася з необхідною допомогою.</label>
                <label class="option-label"><input type="radio" name="q7" value="mentoring"> Я використовую отриманий досвід і впевненіше дію у своїй сфері.</label>
                <label class="option-label"><input type="radio" name="q7" value="consulting"> Я отримав/-ла обґрунтоване рішення або план вирішення конкретної проблеми.</label>
                <label class="option-label"><input type="radio" name="q7" value="training"> Я опанував/-ла потрібну навичку та можу самостійно її застосовувати.</label>
            </div>
            <button class="nav-btn" onclick="calculateResults()">Визначити найбільш відповідний інструмент</button>
        </div>
    </div>

    <!-- Екран результатів -->
    <div id="results-screen" class="results">
        <h2>Результати аналізу вашого запиту</h2>
        <div id="results-content"></div>

        <div class="disclaimer">
            ⚠️ <strong>Зверніть увагу:</strong> Цей тест носить інформаційний характер і не є медичним чи психотерапевтичним діагнозом. 
        </div>

        <div class="cta-box">
            <p style="margin: 0; font-weight: 500; color: var(--primary-color);">Хочете глибше розібрати свій запит та відчути коучинг на практиці?</p>
            <p style="font-size: 14px; color: #555; margin: 8px 0 15px 0;">Запишіться на пробну сесію, де ми зможемо особисто обговорити вашу ситуацію, надати зворотний зв'язок та зрозуміти, чи буде коучинг ефективним саме для вас.</p>
            <a href="#" class="cta-btn">Записатися на пробну сесію</a>
        </div>

        <div class="restart-container">
            <button class="restart-btn" onclick="restartQuiz()">Пройти тест наново</button>
        </div>
    </div>
</div>

<script>
    function nextStep(current) {
        const selected = document.querySelector(`input[name="q${current}"]:checked`);
        if (!selected) {
            alert('Будь ласка, оберіть один із варіантів.');
            return;
        }
        document.querySelector(`.question-card[data-step="${current}"]`).classList.remove('active');
        document.querySelector(`.question-card[data-step="${current + 1}"]`).classList.add('active');
    }

    function calculateResults() {
        const selected7 = document.querySelector('input[name="q7"]:checked');
        if (!selected7) {
            alert('Будь ласка, оберіть варіант у фінальному питанні.');
            return;
        }

        // Збір балів з урахуванням вагових коефіцієнтів
        const scores = {
            coaching: 0,
            therapy: 0,
            psychiatry: 0,
            mentoring: 0,
            consulting: 0,
            training: 0
        };

        for (let i = 1; i <= 7; i++) {
            const el = document.querySelector(`input[name="q${i}"]:checked`);
            if (el) {
                let val = el.value;
                // Правило безпеки: підвищена вага для психіатрії при виражених симптомах
                let weight = (val === 'psychiatry') ? 2.5 : 1;
                scores[val] += weight;
            }
        }

        // Правило безпеки: якщо є хоча б 2 бали на психіатрію — встановлюємо пріоритет безпеки
        let psychiatryPriority = scores.psychiatry >= 2.0;

        // Сортування результатів за балами
        let sortedFormats = Object.keys(scores).sort((a, b) => scores[b] - scores[a]);
        let topFormat = sortedFormats[0];
        let secondFormat = sortedFormats[1];

        let contentHtml = '';

        if (psychiatryPriority) {
            contentHtml += `
                <div class="result-block" style="border-left-color: #E65100; background: #FFF8E1;">
                    <h3 style="color: #E65100;">⚠️ Першочергова рекомендація: Психіатрія / Медична оцінка стану</h3>
                    <p>Ваші відповіді вказують на суттєві зміни у самопочутті чи функціонуванні. У таких ситуаціях найважливішим першим кроком є консультація профільних медичних фахівців (психіатра або психотерапевта-медика), щоб отримати безпечну діагностику та стабілізувати стан. Лише після цього можуть бути ефективними інші формати роботи.</p>
                </div>
            `;
        }

        // Опис результатів
        const formatDescriptions = {
            coaching: {
                title: "Коучинг",
                desc: "Фокусується на ваших цілях, розкритті внутрішнього потенціалу, пошуку рішень та переході від теперішнього стану (As Is) до бажаного (To Be) через партнерський діалог і запитання."
            },
            therapy: {
                title: "Психотерапія",
                desc: "Спрямована на опрацювання глибоких емоційних переживань, травматичного досвіду, тривожних станів та розуміння внутрішніх психологічних механізмів."
            },
            psychiatry: {
                title: "Психіатрія / Медична допомога",
                desc: "Забезпечує професійну діагностику стану здоров'я, визначення фізіологічних причин симптомів та призначення медикаментозної підтримки у разі потреби."
            },
            mentoring: {
                title: "Менторство",
                desc: "Передбачає передачу практичного досвіду, знань та орієнтирів від людини, яка вже пройшла схожий шлях і досягла успіху у вашій сфері."
            },
            consulting: {
                title: "Консультування",
                desc: "Націлене на експертний аналіз конкретної проблеми, пошук причин та надання чітких, обґрунтованих рекомендацій чи готових бізнес-рішень."
            },
            training: {
                title: "Тренерство",
                desc: "Фокусується на засвоєнні конкретних навичок, регулярній практиці, виконанні вправ та отриманні зворотного зв'язку для покращення результатів."
            }
        };

        // Головний результат
        let primary = psychiatryPriority && topFormat !== 'psychiatry' ? 'psychiatry' : topFormat;
        
        contentHtml += `
            <div class="result-block">
                <h3>Основний відповідний формат: ${formatDescriptions[primary].title}</h3>
                <p>${formatDescriptions[primary].desc}</p>
            </div>
        `;

        // Перевірка сумісності (якщо другий формат має близькі бали — показуємо комбінацію)
        if (scores[secondFormat] >= 3 && secondFormat !== primary && !psychiatryPriority) {
            contentHtml += `
                <div class="result-block" style="border-left-color: #689F38;">
                    <h3>💡 Можлива комбінація форматів: ${formatDescriptions[primary].title} + ${formatDescriptions[secondFormat].title}</h3>
                    <p>Ваші відповіді показують перетин потреб. Наприклад, поєднання <strong>${formatDescriptions[primary].title.toLowerCase()}</strong> та <strong>${formatDescriptions[secondFormat].title.toLowerCase()}</strong> може дати синергійний ефект: поки один формат вирішує одні завдання (наприклад, внутрішні бар'єри чи емоції), інший структурує навички або бізнес-стратегію.</p>
                </div>
            `;
        }

        document.getElementById('quiz-form').style.display = 'none';
        document.getElementById('results-content').innerHTML = contentHtml;
        document.getElementById('results-screen').style.display = 'block';
    }

    function restartQuiz() {
        document.getElementById('results-screen').style.display = 'none';
        document.getElementById('quiz-form').style.display = 'block';
        // Очистити радіокнопки
        document.querySelectorAll('input[type="radio"]').forEach(el => el.checked = false);
        // Повернути перше питання
        document.querySelectorAll('.question-card').forEach(card => card.classList.remove('active'));
        document.querySelector('.question-card[data-step="1"]').classList.add('active');
        window.scrollTo({ top: 0, behavior: 'smooth' });
    }
</script>

</body>
</html>
