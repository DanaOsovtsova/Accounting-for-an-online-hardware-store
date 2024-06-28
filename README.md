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
    1) При взаимодействии с CheckBox "checkBoxProducts" информация с исходного текстового файла "products.txt" выводится в QTableView "output1" в виде отформатированной таблицы, используя QStandardItemModel
    2) В функции on_sortButton_clicked при нажатии PushButton "sortButton" реализованна сортировка порядке возрастания по полю Name объектов с выводом в QTableView "output1" в виде отформатированной таблицы
    3) В функции on_SaveTableChangesButton_clicked при нажатии кнопки SaveTableChangesButton реализована возможность редактировать данные в ячейках напрямую в графическом интерфейсе, с возможностью сохранения изменений в исходном текстовом файле "products.txt". Также при успешном открытии файла и добавлении в него корректировок появляется QMessageBox "Success", в противном случае - "Error"
    4) В функции on_pushButton_clicked реализована возможность добавить новый элемент в таблицу, написав новую информацию в LineEdit "lineEditNewForTable", которая при нажатии на pushButton транслируется в QTableView "output1" и сохраняется в исходном текстовом файле "products.txt", также присутствуют QMessageBox. Реализованно с помощью qobject_cast - специальной функций, предоставляемой Qt, которая используется для безопасного динамического приведения типов между классами, производными от QObject
    5) В функции on_searchButton_clicked реализована возможность ввести в LineEdit "lineEditSearch" текст, и найти совпадения в таблице, ВСЕ строки, в которых текст совпал с вводимым для поиска, выведутся на экран сообщением через запятую, такжже и в обратном случае
    6) В функции on_saveToTXTButton_clicked реализована возможность сохранить данные в текстовом файле с разрешением .txt , при том с возможностью выбора папки для размещения и названия файла, с выводом сообщениий. Реализованно с помощью QFileDialog::getSaveFileName, QStringList и QModelIndex
    7) В функции on_saveToBinButton_clicked реализована возможность сохранить данные в бинарном файле с разрешением .bin , при том с возможностью выбора папки для размещения и названия файла, с выводом сообщениий
    8) В функции on_saveToJsonButton_clicked реализована возможность сохранить данные в файле с разрешением .json , при том с возможностью выбора папки для размещения и названия файла, с выводом сообщениий. Реализованно с помощью QJsonDocument, QJsonArray, QJsonObject и toJson()
  
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
    1) При взаимодействии с CheckBox "checkBoxCastumers" информация с исходного текстового файла "customers.txt" выводится в QTableView "output1_2" в виде отформатированной таблицы, используя QStandardItemModel
    2) В функции on_sortButton_2_clicked при нажатии PushButton "sortButton_2" реализованна сортировка порядке возрастания по полю Name объектов с выводом в QTableView "output1_2" в виде отформатированной таблицы
    3) В функции on_SaveTableChangesButton_2_clicked при нажатии кнопки SaveTableChangesButton_2 реализована возможность редактировать данные в ячейках напрямую в графическом интерфейсе, с возможностью сохранения изменений в исходном текстовом файле "customers.txt". Также при успешном открытии файла и добавлении в него корректировок появляется QMessageBox "Success", в противном случае - "Error"
    4) В функции on_pushButton_2_clicked реализована возможность добавить новый элемент в таблицу, написав новую информацию в LineEdit "lineEditNewForTable_2", которая при нажатии на pushButton транслируется в QTableView "output1_2" и сохраняется в исходном текстовом файле "customers.txt", также присутствуют QMessageBox. Реализованно с помощью qobject_cast - специальной функций, предоставляемой Qt, которая используется для безопасного динамического приведения типов между классами, производными от QObject
    5) В функции on_searchButton_2_clicked реализована возможность ввести в LineEdit "lineEditSearch_2" текст, и найти совпадения в таблице, ВСЕ строки, в которых текст совпал с вводимым для поиска, выведутся на экран сообщением через запятую, такжже и в обратном случае
    6) В функции on_saveToTXTButton_2_clicked реализована возможность сохранить данные в текстовом файле с разрешением .txt , при том с возможностью выбора папки для размещения и названия файла, с выводом сообщениий. Реализованно с помощью QFileDialog::getSaveFileName, QStringList и QModelIndex
    7) В функции on_saveToBinButton_2_clicked реализована возможность сохранить данные в бинарном файле с разрешением .bin , при том с возможностью выбора папки для размещения и названия файла, с выводом сообщениий
    8) В функции on_saveToJsonButton_2_clicked реализована возможность сохранить данные в файле с разрешением .json , при том с возможностью выбора папки для размещения и названия файла, с выводом сообщениий. Реализованно с помощью QJsonDocument, QJsonArray, QJsonObject и toJson()

       также реализована кнопка "close" для закрытия приложения
