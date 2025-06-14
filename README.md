🕹️ OverTheWire Bandit — это популярный онлайн-игровой сервер для обучения основам Linux и информационной безопасности. Он предназначен для начинающих и позволяет освоить базовые команды Linux, работу с файлами, правами доступа, сетевыми инструментами и криптографией в интерактивном формате.

🔑 Level 0 → Level 1 (bandit0)

Задача: Войти на сервер под пользователем bandit0.

Подключение по SSH:

    ssh bandit0@bandit.labs.overthewire.org -p 2220

    ssh – команда для подключения к удалённому серверу.

    bandit0 – имя пользователя.

    -p 2220 – порт (по умолчанию SSH использует 22, но здесь 2220).

    Пароль: bandit0

Чтение файла readme в домашней директории:

    cat readme

    cat – выводит содержимое файла.

    readme – файл с паролем для bandit1.

Флаг (Пароль для bandit1): boJ9jbbUNNfktd78OOpsqOltutMc3MY1


🔑 Level 1 → Level 2 (bandit1)


Задача: Найти пароль в файле с названием - (минус).

Подключение:

    ssh bandit1@bandit.labs.overthewire.org -p 2220

    Пароль: boJ9jbbUNNfktd78OOpsqOltutMc3MY1

Чтение файла -:

    cat ./-

    ./- – указывает на файл с именем - в текущей директории (. /).

    Если просто написать cat -, Linux не сможять понять и обработать команду (стандартного ввода).

Флаг (Пароль для bandit2): CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9


🔑 Level 2 → Level 3 (bandit2)

Задача: Найти пароль в файле с пробелами в названии.

Подключение:

    ssh bandit2@bandit.labs.overthewire.org -p 2220

    Пароль: CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9

Чтение файла spaces in this filename:

    cat "spaces in this filename"

    Кавычки (" ") нужны, чтобы обойти пробелы в имени файла.

Флаг (Пароль для bandit3): UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK


🔑 Level 3 → Level 4 (bandit3)

Задача: Найти пароль в скрытом файле внутри директории inhere.

Подключение:

    ssh bandit3@bandit.labs.overthewire.org -p 2220
   
    Пароль: UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
   
Поиск скрытого файла:

    cd inhere  # Переходим в папку inhere
   
    ls -la     # Показывает все файлы, включая скрытые (начинающиеся с .)
   
    cat .hidden

Флаг (Пароль для bandit4): pIwrPrtPN36QITSp3EQaw936yaFoFgAB


🔑 Level 4 → Level 5 (bandit4)

Задача: Найти единственный человекочитаемый файл среди множества в inhere.

Подключение:

    ssh bandit4@bandit.labs.overthewire.org -p 2220
   
    Пароль: pIwrPrtPN36QITSp3EQaw936yaFoFgAB
   
Поиск читаемого файла:

    cd inhere
   
    file ./* | grep ASCII   # Ищем файлы с текстом (ASCII)
   
    cat ./-file07
   
Флаг (Пароль для bandit5): koReBOKuIDDepwhWk7jZC0RTdopnAYKh


🔑 Level 5 → Level 6 (bandit5)

Задача: Найти файл с размером 1033 байта, неисполняемый и принадлежащий bandit7.

Подключение:

    ssh bandit5@bandit.labs.overthewire.org -p 2220
   
    Пароль: koReBOKuIDDepwhWk7jZC0RTdopnAYKh
   
Поиск файла:

  find . -type f -size 1033c ! -executable -user bandit7 -group bandit6
  
  find . – ищет в текущей директории.
  
  -type f - ищет только файлы/
  
  -size 1033c – размер 1033 байта.
  
  ! -executable – не исполняемый.
  
  -user bandit7 - принадлежит пользователю bandit7
  
  -group bandit6 - принадлежит группе bandit6
   
Флаг (Пароль для bandit6): DXjZPULLxYr17uwoI01bNLQbtFemEgo7
