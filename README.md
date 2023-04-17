# Нарушения SOLID
1. В классе Purchase есть магическое число в 7 строке.
2. В том же классе нарушается принцип единственной ответственности: объединяет покупку и корзину покупок.
## Решение
1. Добавляем класс Basket, переносим туда методы добавления покупки и подсчет суммы корзины.
2. Заводим в Basket Purchase[] purchases, Map<String, Integer> prices. 
3. Создаем конструктор, через него убираем магическое число this.purchases = new Purchase[prices.size()]
4. В Main меняем Purchase purchase = new Purchase() на  Basket basket = new Basket(products) и дальше  basket.addPurchase(product, count); basket.sum(products).