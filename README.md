# Softmg Coding Rules

## Phpstorm configs
* Для фреймворков используйте данный стиль кодирования, можно импортировать [http://joxi.ru/82380Y7Cv9GRAO](тут)
Берем отсюда [phpstorm/Sofmg PSR-2.xml](Sofmg PSR-2.xml) После импортирования можно отформатировать имеющийся код через пункт меню Code->Reformat Code (Ctrl+Alt+Z)

* Устанавливаем php code sniffer, который следит за стилем кода PSR-2 [https://www.jetbrains.com/help/phpstorm/2016.3/using-php-code-sniffer-tool.html](https://www.jetbrains.com/help/phpstorm/2016.3/using-php-code-sniffer-tool.html)
Пример его использования [http://joxi.ru/p27EzYqCaK6Or7](http://joxi.ru/p27EzYqCaK6Or7) при наведении подсвечивает рекомендации по стилю кода.

## Документация
* В каждом проекте должна быть документация в корневом файле README.md с указанием особенностей проекта и информацией о разворачивании проекта
* В коде большинство функций должно быть документировано в стиле [https://ru.wikipedia.org/wiki/PHPDoc](PHPDoc) . Для быстрой генерации после написания каркаса функции (входные параметры + возвращаемый) набрать перед функцией /** и нажать enter