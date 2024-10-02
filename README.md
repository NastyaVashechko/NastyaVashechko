HTML
```
<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Кафе "JavaScript Кава"</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #f0f0f0;
        }
        .menu-item {
            margin: 10px;
        }
        .highlight {
            color: red;
        }
    </style>
</head>
<body>

    <h1>Ласкаво просимо до кафе "JavaScript Кава"</h1>

    <h2>Меню</h2>
    <p class="menu-item">Кава: 50 грн</p>
    <p class="menu-item">Чай: 30 грн</p>
    <p class="menu-item">Сок: 40 грн</p>

    <button id="orderButton">Зробити замовлення</button>

    <div id="orderResult"></div>

    <script src="script.js"></script>

</body>
</html>
```
JavaScript
```
let orderButton = document.getElementById('orderButton');
let menuItems = document.getElementsByClassName('menu-item');
let orderResult = document.querySelector('#orderResult');

orderButton.addEventListener('click', function() {
    let randomItem = menuItems[Math.floor(Math.random() * menuItems.length)];
    orderResult.textContent = 'Ви замовили: ' + randomItem.textContent;
});

for (let i = 0; i < menuItems.length; i++) {
    menuItems[i].addEventListener('mouseover', function() {
        menuItems[i].classList.add('highlight');
    });

    menuItems[i].addEventListener('mouseout', function() {
        menuItems[i].classList.remove('highlight');
    });
}

document.addEventListener('keydown', function(event) {
    if (event.key === 'Enter') {
        orderResult.textContent = 'Ви натиснули Enter! Спробуйте ще раз замовити.';
    }
});
```
