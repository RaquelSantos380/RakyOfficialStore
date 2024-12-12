<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Livro de Pets</title>
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            overflow-x: hidden;
        }

        .book {
            width: 80%;
            margin: 50px auto;
            background: #fff;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            border-radius: 10px;
            overflow: hidden;
            position: relative;
        }

        .page {
            position: relative;
            padding: 50px;
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, #e0f7fa, #fff);
        }

        .pet {
            font-size: 24px;
            font-weight: bold;
            text-align: center;
            opacity: 0;
            transform: translateY(100px);
            transition: all 0.8s ease-out;
        }

        .pet.show {
            opacity: 1;
            transform: translateY(0);
        }

        .page:nth-child(odd) {
            background: linear-gradient(135deg, #ffecb3, #fff);
        }

        footer {
            text-align: center;
            padding: 20px;
            font-size: 14px;
            color: #666;
        }
    </style>
</head>
<body>

<div class="book">
    <div class="page">
        <div class="pet">🐶 Cachorrinho - Leal e amoroso!</div>
    </div>
    <div class="page">
        <div class="pet">🐱 Gatinho - Independente e elegante!</div>
    </div>
    <div class="page">
        <div class="pet">🐰 Coelhinho - Fofo e saltitante!</div>
    </div>
    <div class="page">
        <div class="pet">🦜 Papagaio - Colorido e falante!</div>
    </div>
    <div class="page">
        <div class="pet">🐠 Peixinho - Tranquilo e gracioso!</div>
    </div>
</div>

<footer>
    © 2024 Livro de Pets | Criado com ❤️
</footer>

<script>
    // Função para revelar os pets conforme o scroll
    window.addEventListener("scroll", () => {
        const pets = document.querySelectorAll(".pet");
        const triggerBottom = window.innerHeight * 0.8;

        pets.forEach(pet => {
            const petTop = pet.getBoundingClientRect().top;

            if (petTop < triggerBottom) {
                pet.classList.add("show");
            } else {
                pet.classList.remove("show");
            }
        });
    });
</script>

</body>
</html>
