# zoj-site
https://github.io/zoj-site/
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ЗОЖ — Здоровый образ жизни</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Roboto', sans-serif;
            line-height: 1.6;
            color: #333;
        }

        header {
            background: url('https://images.unsplash.com/photo-1508923567004-3a6b8004f3d5?auto=format&fit=crop&w=1350&q=80') center/cover no-repeat;
            color: white;
            text-align: center;
            padding: 100px 20px;
        }

        header h1 {
            font-size: 3em;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
        }

        header p {
            font-size: 1.2em;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.5);
        }

        nav {
            display: flex;
            justify-content: center;
            background-color: #4caf50;
        }

        nav a {
            color: white;
            padding: 14px 20px;
            text-decoration: none;
            font-weight: bold;
            transition: background 0.3s;
        }

        nav a:hover {
            background-color: #3e8e41;
        }

        section {
            padding: 80px 20px;
            text-align: center;
        }

        section:nth-child(even) {
            background-color: #f0f8ff;
        }

        section h2 {
            font-size: 2em;
            margin-bottom: 20px;
            color: #4caf50;
        }

        section p {
            max-width: 700px;
            margin: 0 auto 30px;
        }

        .icon {
            font-size: 50px;
            margin-bottom: 20px;
            color: #4caf50;
        }

        .button {
            display: inline-block;
            padding: 10px 20px;
            margin-top: 10px;
            background-color: #4caf50;
            color: white;
            border: none;
            border-radius: 25px;
            cursor: pointer;
            transition: background 0.3s, transform 0.3s;
            text-decoration: none;
        }

        .button:hover {
            background-color: #3e8e41;
            transform: scale(1.05);
        }

        footer {
            background-color: #4caf50;
            color: white;
            text-align: center;
            padding: 20px 0;
        }

        /* Анимация при скролле */
        .fade-in {
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 1s ease-out, transform 1s ease-out;
        }

        .fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>

    <header>
        <h1>Здоровый образ жизни</h1>
        <p>Простые шаги к здоровью, энергии и счастью</p>
    </header>

    <nav>
        <a href="#nutrition">Питание</a>
        <a href="#exercise">Упражнения</a>
        <a href="#sleep">Сон</a>
    </nav>

    <section id="nutrition" class="fade-in">
        <div class="icon">🥗</div>
        <h2>Питание</h2>
        <p>Ешьте больше овощей, фруктов и цельнозерновых продуктов. Избегайте чрезмерного сахара и соли, пейте много воды.</p>
        <a href="#" class="button">Узнать больше</a>
    </section>

    <section id="exercise" class="fade-in">
        <div class="icon">🏋️‍♂️</div>
        <h2>Физическая активность</h2>
        <p>Регулярные упражнения укрепляют сердце, мышцы и кости. Ходьба, бег, йога и силовые тренировки помогут вам быть в форме.</p>
        <a href="#" class="button">Начать тренироваться</a>
    </section>

    <section id="sleep" class="fade-in">
        <div class="icon">🛌</div>
        <h2>Сон</h2>
        <p>Соблюдайте режим сна, старайтесь спать 7-9 часов в сутки и избегайте гаджетов перед сном для полноценного отдыха.</p>
        <a href="#" class="button">Советы по сну</a>
    </section>

    <footer>
        <p>© 2025 ЗОЖ — Здоровый образ жизни. Все права защищены.</p>
    </footer>

    <script>
        // Появление элементов при скролле
        const faders = document.querySelectorAll('.fade-in');

        const appearOptions = {
            threshold: 0.2,
            rootMargin: "0px 0px -50px 0px"
        };

        const appearOnScroll = new IntersectionObserver(function(entries, appearOnScroll){
            entries.forEach(entry => {
                if(!entry.isIntersecting){
                    return;
                } else {
                    entry.target.classList.add('visible');
                    appearOnScroll.unobserve(entry.target);
                }
            });
        }, appearOptions);

        faders.forEach(fader => {
            appearOnScroll.observe(fader);
        });
    </script>

</body>
</html>
