# Пути
Одно окно терминала подразумевает, что вы можете в один момент времени находиться только в одном каталоге, который называется Current Working Directory (текущий каталог), так же как и в одном открытом окне проводника Windows.

Вы можете выполнять команды относительно текущего каталога или относительно абсолютного пути.

Абсолютный путь - это путь, начинающийся от корня файловой системы. Корень файловой системы обозначается символом /.

Например, в Git Bash (Windows) абсолютный путь для каталога Program Files, будет чаще всего выглядеть следующим образом: /c/Program Files/.

Bash (Git Bash в том числе) используют символ / для разделения каталогов.

Ещё два специальных обозначения помимо корня файловой системы:

.  - обозначает текущий каталог;
.. - обозначает родительский каталог.

__Важно: в терминале символ ` ` (пробел) является символом, разделяющим команды и опции.__

Поэтому если в пути есть пробел, то варианта два:

* заключать путь в кавычки, то есть "Program Files";
* использовать символ backslash для экранирования пробела: Program\ Files.

# Переменные окружения

Командная оболочка устанавливает ряд переменных, которые выполняют специфические функции. Так, переменная с именем PATH содержит список путей, в которых будет производиться поиск программы, если вы наберёте её название в терминале.

    1. Для вывода содержимого конкретной переменной используется команда -> echo $PATH

    2. Команда printenv позволяет отобразить все переменные окружения: -> printenv


# Автодополнение:

В командных оболочках работает автодополнение по клавише Tab:

* дополняются имена команд
* дополняются пути.

Используйте автодополнение, так как оно позволяет сократить время на набор команды.

# Ключевые команды

Текущий рабочий каталог: pwd - сокращение от “Print Working Directory”.

    1. Отображение текущего рабочего каталога: команда -> pwd

Смена рабочего каталога: cd - сокращение от “Change Directory”.

    2. Переход в определённый каталог: команда -> cd <указываем путь>

path может быть как абсолютным, так и относительным путём.

Например, перейти на каталог выше: cd ..

Перейти в подкаталог src: cd src 

Если перед путём нет слеша - он трактуется как относительный (относительно текущего каталога).

Листинг каталога: ls - сокращение от “List”.

    3. отображает листинг (содержимое каталога): команда -> ls

    По умолчанию, ls не отображает файлы, начинающиеся с ., например, .gitignore. 

    Для отображения таких файлов нужно использовать флаг -a: команда -> ls -a

# Работа с каталогами

mkdir - сокращения от “Make Directory”.

    1. Позволяет создавать каталоги : команда -> mkdir teftelka (создаст каталог teftelka в текущем каталоге)
    
Стоит обратить внимание на поведение при создании нового каталога в текущей директории. После команды mkdir name ваше текущее расположение в терминале не изменится. Для того, чтобы работать внутри созданного каталога, в него требуется перейти командой cd name. Это справедливо и при клонировании удалённого репозитория с помощью команды *git clone <url репозитория>.* Полностью склонированный репозиторий создаст каталог в текущей директории с именем проекта, в который нужно перейти командой *cd имя репозитория*.

Перемещение файлов и каталогов: mv - сокращение от “Move”.

    2. Перемещение (переименование) файлов и каталогов: команда -> mv tmp temp

Удаление файлов и каталогов: rm - сокращение от “Remove”.

    3. Удаление конкретного файла: rm README.txt

    4. Удаление непустого каталога: rm -rf temp

Для удаления непустого каталога необходимо указать флаги:

* -r - удалять рекурсивно (автоматическое удаление всего, что было приказано удалить);
* -f - не спрашивать подтверждения.(не возвращать код ошибочного завершения, если ошибки были вызваны несуществующими файлами; не запрашивать подтверждения операций.)