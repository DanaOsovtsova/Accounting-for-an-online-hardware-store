# Accounting-for-an-online-hardware-store

В проекте реализован абстрактный базовый класс Model, с виртуальными функциями, от которого наследуются два класса:
- Products
  * массив структур Product (Name,Date,Section,Count), в структуре реализованны перегрузки операторов ==, >>, <<
  * реализованны функции:
    1) count_lines //для подсчета считываемых строк
    2) GetData //для чтения строк из потока
    3) PutData //выводит все объекты Product, хранящиеся в массиве arr, в выходной поток out с переводом строки
  * базовые конструкторы и деструктор
    1) Products() //конструктор по умолчанию
    2) Products(int c) //конструктор с параметрами
    3) Products(const Products& other) //конструктор копирования
    4) ~Products() //деструктор
    5) Sort() //сортирует массив arr в порядке возрастания по полю Name объектов Product
  * касаемо графического интерфейса:
  
- Castumers
  * массив структур Customer (Name,email), в структуре реализованны перегрузки операторов ==, >>, <<
    1) count_lines //для подсчета считываемых строк
    2) GetData //для чтения строк из потока
    3) PutData //выводит все объекты Customer, хранящиеся в массиве arr, в выходной поток out с переводом строки
  * базовые конструкторы и деструктор
    1) Castomers() //конструктор по умолчанию
    2) Castomers(int c) //конструктор с параметрами
    3) Castomers(const Castomers& other) //конструктор копирования
    4) ~Castomers() //деструктор
    5) Sort() //сортирует массив arr в порядке возрастания по полю Name объектов Customer
  * касаемо графического интерфейса:
