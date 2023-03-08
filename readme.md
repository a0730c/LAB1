Лабораторная работа №1

Цель - изучение утилит для разраотки проектов

Для начала подключу git с помощью менеджера пакетов:
$ sudo apt install git 
Далее создам локальнй репозиторий.
Для этого создам директорию lab1.
Находясь в /home/alina ввожу в терминал: 
$ mkdir lab1 
Перейду в созданную директорию:
$ cd lab1
Создам локальный репозиторий в этой папке:
$ git init
Терминал возвращает следующую строку:
Инициализирован пустой репозиторий Git в /home/alina/lab1/.git/
Создам файл readme.md:
$ touch readme.md
Перехожу в директорию /home/alina:
$ cd /home/alina

Приступаю к выполнению лабораторной работы. 

01. $ wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
    Вывод: 2023-03-08 20:48:18 (227 KB/s) - ‘boost_1_69_0.tar.gz’ сохранён [111710205/111710205]
    
02. $ tar -xzf boost_*

03. $ find . -maxdepth 1 -type f | wc -l
    Вывод: 12
    
04. $ find . -type f | wc -l
    Вывод: 61191
    
05. $ find . -type f -name "*.hpp" -o -name "*.h" | wc -l
    Вывод: 15208
    $ find -name *.cpp | wc -l
    Вывод: 13774
    $ find . -not -name "*.h" -not -name "*.hpp" -not -name "*.cpp" | wc -l
    Вывод: 37847
    
06. $ find `pwd` -name any.hpp
    Вывод: 
/home/alina/boost_1_69_0/boost/fusion/algorithm/query/any.hpp
/home/alina/boost_1_69_0/boost/fusion/algorithm/query/detail/any.hpp
/home/alina/boost_1_69_0/boost/fusion/include/any.hpp
/home/alina/boost_1_69_0/boost/spirit/home/support/algorithm/any.hpp
/home/alina/boost_1_69_0/boost/type_erasure/any.hpp
/home/alina/boost_1_69_0/boost/hana/fwd/any.hpp
/home/alina/boost_1_69_0/boost/hana/any.hpp
/home/alina/boost_1_69_0/boost/any.hpp
/home/alina/boost_1_69_0/boost/proto/detail/any.hpp
/home/alina/boost_1_69_0/boost/xpressive/detail/utility/any.hpp
           
07. $ grep -Ril "boost::asio"
    Вывод: "1763 файла"
    
08. Установливаю пакеты libicu-dev и g++:
    $ sudo apt install libicu-dev
    $ sudo apt install g++
    
    $ ./bootstrap.sh --prefix=boost_output
    $ ./bootstrap.sh --prefix=boost_output --with-python=
    $ ./bootstrap.sh --prefix=boost_output --with-python=python3
    $ ./bootstrap.sh --prefix=boost_output --with-icu=
    $ ./b2 install -j 8
    
09. $ cd ..
    $ mkdir boost-libs
    $ cd boost_1_69_0/boost_*/lib
    $ mv *.a /home/alina/boost-libs
    
10. $ cd /home/alina/boost-libs
    $ find . -type f -exec du -h {} +
504K	./libboost_math_c99l.a
4,0K	./libboost_exception.a
880K	./libboost_graph.a
2,3M	./libboost_test_exec_monitor.a
236K	./libboost_chrono.a
780K	./libboost_wserialization.a
2,3M	./libboost_unit_test_framework.a
148K	./libboost_container.a
1,6M	./libboost_program_options.a
4,0K	./libboost_system.a
240K	./libboost_fiber.a
488K	./libboost_math_c99f.a
344K	./libboost_contract.a
24K	./libboost_context.a
1,2M	./libboost_serialization.a
24K	./libboost_stacktrace_addr2line.a
172K	./libboost_iostreams.a
3,1M	./libboost_regex.a
4,6M	./libboost_wave.a
4,0K	./libboost_atomic.a
24K	./libboost_stacktrace_backtrace.a
4,0K	./libboost_stacktrace_noop.a
580K	./libboost_math_c99.a
84K	./libboost_random.a
2,8M	./libboost_math_tr1l.a
216K	./libboost_prg_exec_monitor.a
2,8M	./libboost_math_tr1f.a
416K	./libboost_filesystem.a
16K	./libboost_stacktrace_basic.a
56K	./libboost_timer.a
152K	./libboost_date_time.a
2,8M	./libboost_math_tr1.a

11. $ find . -type f -exec du {} +|sort -rh | head -n 10
4636	./libboost_wave.a
3164	./libboost_regex.a
2844	./libboost_math_tr1.a
2812	./libboost_math_tr1l.a
2768	./libboost_math_tr1f.a
2344	./libboost_test_exec_monitor.a
2324	./libboost_unit_test_framework.a
1608	./libboost_program_options.a
1184	./libboost_serialization.a
880	./libboost_graph.a

Вернусь в директорию репозитория:
$ cd /home/alina/lab1
Добавлю readme.md в локальный репозиторий:
$ git add readme.md
Укажу идентификационные данные аккаунта:
$ git config --global user.email "a0730c@gmail.com"
$ git config --global user.name "a0730c"
Создам коммит:
$ git commit -m "added readme.md"
Добавлю удаленный репозиторий, созданный мною заранее на сайте github.com:
$ git remote add origin https://github.com/a0730c/LAB1.git
Внесу изменения, которые были сделаны в локальном репозитории на github:
$ git push -u origin master
