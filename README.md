# Softmg Coding Rules

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