## Задача №3

### Условия

Есть продукты A, B, C, D, E, F, G, H, I, J, K, L, M. Каждый продукт стоит определенную сумму.

Есть набор правил расчета итоговой суммы:

- 1 - Если одновременно выбраны А и B, то их суммарная стоимость уменьшается на 10% (для каждой пары А и B)
- 2 - Если одновременно выбраны D и E, то их суммарная стоимость уменьшается на 5% (для каждой пары D и E)
- 3 - Если одновременно выбраны E,F,G, то их суммарная стоимость уменьшается на 5% (для каждой тройки E,F,G)
- 4 - Если одновременно выбраны А и один из [K,L,M], то стоимость выбранного продукта уменьшается на 5%
- 5 - Если пользователь выбрал одновременно 3 продукта, он получает скидку 5% от суммы заказа
- 6 - Если пользователь выбрал одновременно 4 продукта, он получает скидку 10% от суммы заказа
- 7 - Если пользователь выбрал одновременно 5 продуктов, он получает скидку 20% от суммы заказа
- 8 - Описанные скидки 5,6,7 не суммируются, применяется только одна из них
Продукты A и C не участвуют в скидках 5,6,7
Каждый товар может участвовать только в одной скидке. Скидки применяются последовательно в порядке описанном выше.


### "Алгоритм расчета расчета итоговой стоимости"

- Программа в input принимает список продуктов и заполняет сущность корзина(model-> Basket)
- Input принимается в виде json (чтением json из файла input.txt)
- У каждого продукта есть цена и название
- После функция CalculateTheDiscount (internal-->adapters-->calculator.go) принимает сущность корзина и применяет скидки которые заранее определены условиями задачи
- После прохождения по всему списку товаров в сервисе происходит основная логика применения скидок к товарам (если они есть в продуктовой корзине)
- Последнее условие скидка 20% применяется к корзине если в корзине количество продуктов равна 5 или больше 5
- К продукту применятся только одна скидка( к примеру если скидка применяется определенному продукту условием 1, то условия 2-8 к этому продукту или паре продуктов не будет применена) 
