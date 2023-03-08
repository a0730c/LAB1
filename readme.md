# Лабораторная работа №1

### Цель - изучение утилит для разраотки проектов

Для начала подключу git с помощью менеджера пакетов:<br />
```$ sudo apt install git```<br />
Далее создам локальнй репозиторий.<br />
Для этого создам директорию lab1.<br />
Находясь в /home/alina, ввожу в терминал: <br />
```$ mkdir lab1``` <br />
Перейду в созданную директорию:<br />
```$ cd lab1```<br />
Создам локальный репозиторий в этой папке:<br />
```$ git init```<br />
Терминал возвращает следующую строку:<br />
Инициализирован пустой репозиторий Git в /home/alina/lab1/.git/<br />
Создам файл readme.md:<br />
```$ touch readme.md```<br />
Перехожу в директорию /home/alina:<br />
```$ cd /home/alina```<br />

Приступаю к выполнению лабораторной работы. 

01. ```$ wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz``` <br />
    Вывод: 2023-03-08 20:48:18 (227 KB/s) - ‘boost_1_69_0.tar.gz’ сохранён [111710205/111710205]
    
02. ```$ tar -xzf boost_*```<br />

03. ```$ find . -maxdepth 1 -type f | wc -l```<br />
    Вывод: 12<br />
    
04. ```$ find . -type f | wc -l```<br />
    Вывод: 61191<br />
    
05. ```$ find . -type f -name "*.hpp" -o -name "*.h" | wc -l```<br />
    Вывод: 15208<br />
    ```$ find -name *.cpp | wc -l```<br />
    Вывод: 13774<br />
    ```$ find . -not -name "*.h" -not -name "*.hpp" -not -name "*.cpp" | wc -l```<br />
    Вывод: 37847<br />
    
06. ```$ find `pwd` -name any.hpp```<br />
    Вывод: <br />
/home/alina/boost_1_69_0/boost/fusion/algorithm/query/any.hpp<br />
/home/alina/boost_1_69_0/boost/fusion/algorithm/query/detail/any.hpp<br />
/home/alina/boost_1_69_0/boost/fusion/include/any.hpp<br />
/home/alina/boost_1_69_0/boost/spirit/home/support/algorithm/any.hpp<br />
/home/alina/boost_1_69_0/boost/type_erasure/any.hpp<br />
/home/alina/boost_1_69_0/boost/hana/fwd/any.hpp<br />
/home/alina/boost_1_69_0/boost/hana/any.hpp<br />
/home/alina/boost_1_69_0/boost/any.hpp<br />
/home/alina/boost_1_69_0/boost/proto/detail/any.hpp<br />
/home/alina/boost_1_69_0/boost/xpressive/detail/utility/any.hpp<br />
           
07. ```$ grep -Ril "boost::asio"```<br />
Вывод: "1763 файла"<br />
    
08. Установливаю пакеты libicu-dev и g++:<br />
    ```
    $ sudo apt install libicu-dev
    $ sudo apt install g++
    ```
    
    $ ./bootstrap.sh --prefix=boost_output<br />
    $ ./bootstrap.sh --prefix=boost_output --with-python=<br />
    $ ./bootstrap.sh --prefix=boost_output --with-python=python3<br />
    $ ./bootstrap.sh --prefix=boost_output --with-icu=<br />
    $ ./b2 install -j 8
    
09. ```
    $ cd ..
    $ mkdir boost-libs
    $ cd boost_1_69_0/boost_*/lib
    $ mv *.a /home/alina/boost-libs
    ```
    
10. ```
    $ cd /home/alina/boost-libs
    $ find . -type f -exec du -h {} +
    ```
    Вывод:<br />
504K	./libboost_math_c99l.a<br />
4,0K	./libboost_exception.a<br />
880K	./libboost_graph.a<br />
2,3M	./libboost_test_exec_monitor.a<br />
236K	./libboost_chrono.a<br />
780K	./libboost_wserialization.a<br />
2,3M	./libboost_unit_test_framework.a<br />
148K	./libboost_container.a<br />
1,6M	./libboost_program_options.a<br />
4,0K	./libboost_system.a<br />
240K	./libboost_fiber.a<br />
488K	./libboost_math_c99f.a<br />
344K	./libboost_contract.a<br />
24K	    ./libboost_context.a<br />
1,2M	./libboost_serialization.a<br />
24K	    ./libboost_stacktrace_addr2line.a<br />
172K	./libboost_iostreams.a<br />
3,1M	./libboost_regex.a<br />
4,6M	./libboost_wave.a<br />
4,0K	./libboost_atomic.a<br />
24K	    ./libboost_stacktrace_backtrace.a<br />
4,0K	./libboost_stacktrace_noop.a<br />
580K	./libboost_math_c99.a<br />
84K	    ./libboost_random.a<br />
2,8M	./libboost_math_tr1l.a<br />
216K	./libboost_prg_exec_monitor.a<br />
2,8M	./libboost_math_tr1f.a<br />
416K	./libboost_filesystem.a<br />
16K	    ./libboost_stacktrace_basic.a<br />
56K	    ./libboost_timer.a<br />
152K	./libboost_date_time.a<br />
2,8M	./libboost_math_tr1.a<br />

11. ```$ find . -type f -exec du {} +|sort -rh | head -n 10```<br />
    Вывод:<br />
4636	./libboost_wave.a<br />
3164	./libboost_regex.a<br />
2844	./libboost_math_tr1.a<br />
2812	./libboost_math_tr1l.a<br />
2768	./libboost_math_tr1f.a<br />
2344	./libboost_test_exec_monitor.a<br />
2324	./libboost_unit_test_framework.a<br />
1608	./libboost_program_options.a<br />
1184	./libboost_serialization.a<br />
880	    ./libboost_graph.a<br />

Вернусь в директорию репозитория:<br />
```$ cd /home/alina/lab1``` <br />
Добавлю readme.md в локальный репозиторий:<br />
```$ git add readme.md``` <br />
Укажу идентификационные данные аккаунта. <br />
Создам коммит:<br />
```$ git commit -m "added readme.md"```<br />
Добавлю удаленный репозиторий, созданный мною заранее на сайте github.com:<br />
```$ git remote add origin https://github.com/a0730c/LAB1.git```<br />
Внесу изменения, которые были сделаны в локальном репозитории на github:<br />
```$ git push -u origin master```<br />
