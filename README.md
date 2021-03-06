﻿# Расширение для Google Chrome для Maxdone

Выглядит это так:
![Screenshot](https://raw.githubusercontent.com/alatyshau/maxdone-chrome-extension/master/web/screenshot.png "Screenshot")

Список фич:
* Категориям назначаются цвета, и задачки получают слева тоненькие полосочки (шевроны) соответствующего цвета -- у меня в жизни все дела поделены ровно на четыре категории, соответственно четыре цвета на все задачи (ваши цвета вы можете настроить подредактировав CSS файл)
* Для каждой задачи слева указывается день недели (ПН, ВТ, СР, и т.д.) -- это соответствует полю "Срок" (Due date) -- я так лучше ориентируюсь в неделе
* Если кликнуть по дню недели, то задачка подсветиться жёлтеньким -- я так выделяю над чем работаю прямо сейчас
* В случае когда дня недели нету -- то можно провести мышкой слева от чекбокса и кликнуть на появившееся жёлтенькое личико.
* Текст в названии задачи можно выделить если обрамить его звёздочками, например `*8:00*` Начало дня -- "8:00" станет жирненьким -- я такими задачами делю день на блоки и программирую примерный режим дня (обычно это рутины типа отдохнуть, сделать табату, забрать детей со школы, просмотреть инбоксы и сделать дневной обзор).
* Если выбрана опция 'Подсчитывать фактическое время', то при подсвечивании текущей задачи запомнится время старта и при выключении подсветки, время между этими событиями запишется в квадратных скобках в конце имени таска. В секции выполненные сегодня, соответственно будет показывать итоги запланированного и фактически потраченного времени. Внимание! Таймер работает только в пределах сессии, т.е. принудительное обновление страницы таймер сбросит, впрочем как и подсветку задачи.
 
## Как установить и настроить
### Этап 1. Скачать
1. Если у вас сейчас открыт Github, то вы должны видеть справа зелёненькую кнопочку «Clone or download»
2. Нажимаете её, и помто Download ZIP
3. Решите где у вас будет храниться это расширение (его нету на маркете в гугл)
4. Распакуйте ZIP в то место, где у вас будет храниться расширение

### Этап 2. Настроить цвета
1. Заходим в папку, куда распаковали расширение
2. Там внутри будет папочка web (внутри maxdone-chrome-extension-master)
3. В папочке web весь исходный код расширения
4. Нужно скопировать файл `maxdone-local-sample.css` и переименовать его в `maxdone-local.css`
5. При будущих обновлениях расширения, вы сможете переписывать все файлы, а этот файлик maxdone-local.css останется вашим с вашими настройками стилей категорий
6. Открываем в каком-либо текстовом редакторе `maxdone-local.css` (кодировка UTF-8)
7. В этом файле определены стили для полосочек (шевронов) и для надписей категорий (смотрите скриншот)
8. `div.taskBlock-<имя категории> div.project-label { <стили> }` -- это стиль для надписей категорий 
9. `div.taskBlock-<имя категории> div.taskChevron { <стили> }` -- это стиль для шеврона
10. Важно: имена категорий могут содержать пробелы, запятые, знаки '!', '?' и '#', фигурные скобочки '{', '}', но эти символы в файле maxdone-local.css должны быть заменены на дефис '-'. Буквы могут быть на русском (и их подменять не надо). Пример: Категория «`..#{Тест, тест, тест}#..`» --> «`div.taskBlock-----Тест--тест--тест----`»
11. Меняем цвет `rgb(22, 167, 101)` -- чтобы понять что вводить, можно открыть Paint и там в свойста цвета когда заходите, там Red, Green Blue
12. После редактирования стилей, сохраняем `maxdone-local.css`

### Этап 3. Установить в Chrome
1. Открываем Google Chrome
2. Открываем страницу с расширениями (chrome://extensions/)
3. Включаем режим разработчика отмечая галочку в правом верхнем углу (Developer mode / Режим разработчика)
4. Появится новая кнопочка "Load unpacked extension..." ("Загрузить распакованное расширение...")
5. Вводите путь к папке web (которая внутри maxdone-chrome-extension-master)
6. Нажимаете OK, и всё -- перегрузите страницу https://maxdone.micromiles.co
