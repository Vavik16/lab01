# lab01
После команды wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
1.	tar -xf boost_1_69_0.tar.gz – разархивирование
rm -rf boost_1_69_0.tar.gz – удалил архив
cd boost_1_69_0 – открыл папку boost
2. tree -a -L 1 – список файлов, не включая директории (6 директорий, 12 файлов)
3. tree -a - все файлы (61191)
4. find -name "*.cpp" -not -type d|wc -l - все файлы с расширением .срр
5. find -name "*.hpp" -o -name "*.h" -not -type d|wc -l – все заголовочные файлы 15208 штук
6. find -not -name "*.cpp" -not -name "*.hpp" -not -name "*.h" -not -type d|wc -l – файлы не .срр и заголовочные  - 32209 штук
7. /home/kali/boost_1_69_0/any.hpp
8. grep -r "boost::asio"|wc -l 17424 файлов с этим упоминанием
9. ./bootstrap.sh --prefix=boost_output  , затем ./b2 install
..failed updating 30 targets...
...skipped 48 targets...
...updated 15160 targets...

10. mkdir ~/boost-libs  
cd /home/kali/boost_1_69_0/boost_output/lib
mv *.* ~/boost-libs
11. cd ~/boost-libs/ 
du -ah
12. find . -xdev -type f -not -type d -print | xargs ls -lh | sort -k5,5 -h -r | head – команда и вывод:
-rw-r--r-- 1 root root 4.5M Mar  9 02:51 ./libboost_wave.a
-rw-r--r-- 1 root root 3.1M Mar  9 02:51 ./libboost_regex.a
-rw-r--r-- 1 root root 2.8M Mar  9 02:51 ./libboost_math_tr1l.a
-rw-r--r-- 1 root root 2.8M Mar  9 02:51 ./libboost_math_tr1.a
-rw-r--r-- 1 root root 2.7M Mar  9 02:51 ./libboost_math_tr1f.a
-rw-r--r-- 1 root root 2.3M Mar  9 02:55 ./libboost_test_exec_monitor.a
-rw-r--r-- 1 root root 2.3M Mar  9 02:51 ./libboost_unit_test_framework.a
-rw-r--r-- 1 root root 1.6M Mar  9 02:51 ./libboost_program_options.a
-rwxr-xr-x 1 root root 1.3M Mar  9 02:51 ./libboost_regex.so.1.69.0
-rw-r--r-- 1 root root 1.2M Mar  9 02:51 ./libboost_serialization.a
