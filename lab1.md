```javascript
// Задача 1: Расчет суммы вклада
function calculateDeposit() {
    let principal = parseFloat(prompt("Введите сумму вклада:"));
    let rate = parseFloat(prompt("Введите годовую процентную ставку:"));
    
    // A = P(1 + r)^t
    let amount = principal * Math.pow(1 + rate/100, 3);
    alert("Сумма на вкладе после 3 лет: " + amount.toFixed(2));
}

// Задача 2: Проверка на три нуля
function checkThreeZeros() {
    let number = parseInt(prompt("Введите число:"));
    let lastThreeDigits = number % 1000;
    if (lastThreeDigits === 0 && number >= 1000) {
        alert("Число заканчивается на три нуля");
    } else {
        alert("Число НЕ заканчивается на три нуля");
    }
}

// Задача 3: Время работы магазина
function shopHours() {
    let day = parseInt(prompt("Введите номер дня недели (1-7):"));
    
    if (day === 1 || day === 7) {
        alert("Выходной");
    } else if (day >= 2 && day <= 5) {
        alert("Время работы: 10:00 - 20:00");
    } else if (day === 6) {
        alert("Время работы: 11:00 - 18:00");
    } else {
        alert("Некорректный номер дня");
    }
}

function isValidDate() {
    let day = parseInt(prompt("Введите день:"));
    let month = parseInt(prompt("Введите месяц:"));
    let year = parseInt(prompt("Введите год:"));
    
    if (month < 1 || month > 12 || day < 1 || year < 1) {
        alert("Дата некорректна");
        return;
    }
    
    let maxDays;
    if (month === 2) {
        let isLeap = (year % 4 === 0 && year % 100 !== 0) || (year % 400 === 0);
        maxDays = isLeap ? 29 : 28;
    } else if (month === 4 || month === 6 || month === 9 || month === 11) {
        maxDays = 30;
    } else {
        maxDays = 31;
    }
    
    if (day <= maxDays) {
        alert("Дата корректна");
    } else {
        alert("Дата некорректна");
    }
}

async function main() {
    await calculateDeposit();
    await checkThreeZeros();
    await shopHours();
    await isValidDate();
}

main();
```

## Примеры вывода

### Пример 1

```plaintext
Введите сумму вклада: 1000
Введите годовую процентную ставку: 5
Сумма на вкладе после 3 лет: 1157.63
Введите число: 1000
Число заканчивается на три нуля
Введите номер дня недели (1-7): 2
Время работы: 10:00 - 20:00
Введите день: 31
Введите месяц: 12
Введите год: 2023
Дата корректна
```

### Пример 2

```plaintext
Введите сумму вклада: 5000
Введите годовую процентную ставку: 3
Сумма на вкладе после 3 лет: 5463.64
Введите число: 123
Число НЕ заканчивается на три нуля
Введите номер дня недели (1-7): 7
Выходной
Введите день: 29
Введите месяц: 2
Введите год: 2023
Дата некорректна
```
