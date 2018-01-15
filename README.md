# ITShool_OOP

Test tasks in OOP basics 

## Task 1

1. Создать 3 класса, описывающие 2 типа некоего товара. Один из классов – базовый, второй и третий – описывают типы товаров. В первом – обязательны поля «цена» и «название». В наследниках должны быть объявлены новые поля. 
1.1. В классах должны быть два конструктора: пустой и параметризованный, методы get set  для каждого поля, метод public String toString(), возвращающий строковое представление объекта. 
1.2. Базовый класс должен быть абстрактным.  
1.3. При помощи статических полей и метода найти и отпечатать среднюю цену товара. 
2. Создать контейнер для хранения товаров. В нем должны быть реализованы методы Add, Count, метод доступа по индексу, сортировки по цене и печати содержимого. 
3. Заполнить контейнер, распечатать, отсортировать, распечатать. 

## Task 2

goal: проверка умения использовать парадигмы ООП;  
scope: paradigms OOP 
  
Есть два рода людей: женщины и мужчины. Они обладают одинаковым набором свойств за небольшим исключением (у кого как) и методов. 
Пусть будет определен следующий набор свойств: 
- признак пола (boolean, true - мужчина, false - женщина) 
- имя (String) 
- фамилия (String) 
- рост (float) 
- вес (float) 
И имеется общий набор методов, у которых в качестве аргумента принимается экземпляр человека: 
- говорить (возвращает boolean) 
- терпеть/выдерживать общество (возвращает boolean) 
- проводить время вместе (возвращает boolean) 
- иметь отношения (возвращает Человек) 
У женщин есть дополнительный метод - "родить человека" (возвращает экземпляр человека) 
  
Необходимо написать консольное приложение, в котором сначала нужно ввести значения свойств, 
для двух экземпляров людей (женщины и мужчины в произвольном порядке, возможны варианты ЖЖ, МЖ, ЖМ и ММ). 
Затем программа должна провести тест на совместимость и дать прогноз на результат отношений двух данных экземпляров.

Алгоритм следующий: 
1. Метод “тест на совместимость” принимает два экземпляра людей и должен возвратить экземпляр человека или null. 
2. Вызвать метод “иметь отношения” первого экземпляра человека с аргументом - второй экземпляр. 
3. Полученный результат вернуть как результат работы метода “тест на совместимость”. 
  
Известно, что: 
Для Человека методы имеют следующую реализацию: 
- "говорить" (возвращает boolean) 
Результат определяется по таблице , где первая колонка это пол собственного экземпляра, а вторая - пол аргумента:<br> 
Ж            Ж            всегда true<br>
Ж            М            true <br>
М            Ж            true <br>
М            М            с вероятностью 0.5<br><br> 
  
- "терпеть/выдерживать общество" (возвращает boolean) 
аналогично <br>
Ж            Ж            с вероятностью 0.05 <br>
Ж            М            с вероятностью 0.7 <br>
М            Ж            с вероятностью 0.7 <br>
М            М            с вероятностью 0.056 <br>
  
- проводить время вместе (возвращает boolean) 
если рост экземпляров отличается более чем на 10%, метод возвращает true с вероятностью 0.85 
если рост экземпляров отличается менее чем на 10%, метод возвращает true с вероятностью 0.95  
- иметь отношения (возвращает Человек) 
если “говорить” && “терпеть/выдерживать общество” && “проводить время вместе” равно true, 
то если свойство “пол” собственного экземпляра и пол аргумента одинаковые, то вернуть null, иначе 
создать экземпляр нового человека путем вызова метода “родить человека” у экземпляра с полом Ж. 
  
У женщин, как было указано выше, есть дополнительный метод “родить человека”. Он имеет следующую реализацию: 
Создать новый экземпляр женщины или мужчины с вероятностью 0.5 со следующими свойствами: 
- имя (String) - ввести с консоли 
- фамилия (String) - берется у экземпляра с мужским полом 
- рост (float) - копируется у соответствующего экземпляра с таким же полом + 0.1*(рост экземпляра противоположного рода минус рост однородного экземпляра) 
- вес (float) - аналогично росту 
В результате работы программы надо выдать на экран все свойства нового экземпляра человека или написать “ничего не вышло... разбежались”.
Желательно вызовы методов экземпляров классов женщин и мужчин сопровождать выводом на экран комментариев к процессу. 
