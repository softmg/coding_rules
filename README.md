Рекомендации по стилю для команды Soft Media Group.
---

Мотивация
---

Уважаемые коллеги, цел этого материала привить команде определенный единый стил программирование.

- Почему?: Чтобы мы все понимали код коллег без лишних действий.
- Почему?: Чтобы внести изменения в код было проще(это важно!).

![Чистый код? кого волнует?][clean-code-who-cares]

Список рекомендации
---
- [early return](#early-return)

Early Return
---
- Что?: Ранный выход из функции|метода.
- Почему?: Чтобы повисить читаемость кода.
- Почему?: Чтобы было меньше вложенности.

Лучше если в начале метода сразу прописаны условия при которых он возвращает значение или бросает исключения.

Примеры:
```
// Плохо

function something() {
   if (expression) {
       //...
       //...
       //...
       //...
       //...
       //...
       //...
       //...
   } else {
       doSomething()
   }
}
```

```
// Хорошо

function something() {
   if (!expression) {
       doSomething()
       return;
   }
   
   //...
   //...
   //...
   //...
   //...
   //...
   //...
   //...
}

```

```
# Ужасно

function something1() {
   if (expression1) {
      //111
      //111
      
      if (expression2) {
          //222
          //222
          
          if (expression3) {
             //333
             //333
             if (expression4) {
                 //444
                 //444
                 
                 if (expression5) {
                     //555
                     //555
                     
                     if (expression6) {
                        //666
                     }
                 }
             } else {
                //777
                //777
             }
          }
      }
   }
}

```


```
# Хорошо

function something1() {
   if (!expression1) {
       return;
   }
   
   //111
   //111
   
   if (!expression2) {
       return;
   }
   
   //222
   //222
   
   if (!expression3) {
       return;
   }
   
   //333
   //333
   
   if (!expression4) {
       //777
       //777
      
       return;
   }
   
   //444
   //444
   
   if (!expression5) {
       return;
   }
   
   //555
   //555
   
   if (!expression6) {
       return;
   }
   
   //666
}

```


[clean-code-who-cares]: https://habrastorage.org/files/3db/03a/0a2/3db03a0a21064342a85ca886692bcc54.png
[cyclomatic-complexity]: https://ru.wikipedia.org/wiki/%D0%A6%D0%B8%D0%BA%D0%BB%D0%BE%D0%BC%D0%B0%D1%82%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B0%D1%8F_%D1%81%D0%BB%D0%BE%D0%B6%D0%BD%D0%BE%D1%81%D1%82%D1%8C

## Phpstorm configs
* Должен соблюдаться следующий стиль кода [PSR-2](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md)

* Для фреймворков используйте данный стиль кодирования, можно импортировать [тут](http://joxi.ru/82380Y7Cv9GRAO)
Берем отсюда [Sofmg PSR-2.xml](https://github.com/softmg/coding_rules/blob/master/phpstorm/Sofmg%20PSR-2.xml) После импортирования можно отформатировать имеющийся код через пункт меню Code->Reformat Code (Ctrl+Alt+Z)

* Устанавливаем php code sniffer, который следит за стилем кода PSR-2 [https://www.jetbrains.com/help/phpstorm/2016.3/using-php-code-sniffer-tool.html](https://www.jetbrains.com/help/phpstorm/2016.3/using-php-code-sniffer-tool.html)
Пример его использования [тут](http://joxi.ru/p27EzYqCaK6Or7) при наведении подсвечивает рекомендации по стилю кода.

## Рекомендации по работе с git
* Смотрим [тут]([https://github.com/softmg/coding_rules/blob/master/git/common.md)

## Документация
* В каждом проекте должна быть документация в корневом файле README.md с указанием особенностей проекта и информацией о разворачивании проекта
* В коде большинство функций должно быть документировано в стиле [PHPDoc](https://ru.wikipedia.org/wiki/PHPDoc) . Для быстрой генерации после написания каркаса функции (входные параметры + возвращаемый) набрать перед функцией /** и нажать enter

## Рекомендации по Symfony
* Смотрим [тут](https://github.com/softmg/coding_rules/blob/master/symfony/common.md)
