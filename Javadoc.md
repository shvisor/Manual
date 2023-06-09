При написании комментариев к кодам Java используют три типа комментариев:
```
// однострочный комментарий;
/* многострочный комментарий */
/** комментирование документации */
```

Комментарии документации применяют для документирования классов, интерфейсов, полей (переменных), конструкторов и методов. В каждом случае комментарий должен находиться перед документируемым элементом.

### javadoc дескрипторы : @author, @version, @since, @see, @param, @return

| Дескриптор | Применение | Описание |
:---:                          | :---:                         | :---:
@author                        | Класс, интерфейс              | Автор
@version                       | Класс, интерфейс              | Версия. Не более одного дескриптора на класс
@since                         | Класс, интерфейс, поле, метод | Указывает, с какой версии доступно
@see                           | Класс, интерфейс, поле, метод | Ссылка на другое место в документации
@param                         | Метод                         | Входной параметр метода
@return                        | Метод                         | Описание возвращаемого значения
@exception имя_класса описание | Метод                         | Описание исключения, которое может быть послано из метода
@throws имя_класса описание    | Метод                         | Описание исключения, которое может быть послано из метода
@deprecated                    | Класс, интерфейс, поле, метод | Описание устаревших блоков кода
{@link reference}              | Класс, интерфейс, поле, метод | Ссылка
{@value}                       | Статичное поле                | Описание значения переменной
