# Задача: Управление системой логирования с использованием статических переменных и указателей на функции

## Условие

Вам необходимо разработать простую систему логирования для приложения. Эта система должна иметь несколько уровней логирования: `INFO`, `WARNING`, `ERROR`. Логирование должно осуществляться через функции, которые будут передаваться в систему в виде указателей на функции. 

Для того чтобы сохранять текущее состояние системы логирования (например, какой уровень логов включен), используйте **статическую переменную**.

## Требования

1. Напишите класс `Logger`, который будет:
   - Содержать статическую переменную для хранения текущего уровня логирования (`INFO`, `WARNING`, `ERROR`).
   - Содержать статические методы для установки уровня логирования и получения текущего уровня.
   - Содержать метод `logMessage`, который принимает указатель на функцию логирования и само сообщение. Если текущий уровень логирования соответствует уровню, установленному статической переменной, сообщение должно быть выведено на экран.

2. Напишите три функции:
   - `logInfo` — для вывода информационных сообщений (INFO).
   - `logWarning` — для вывода предупреждений (WARNING).
   - `logError` — для вывода ошибок (ERROR).

3. В основной функции создайте объекты и продемонстрируйте работу системы логирования:
   - Установите текущий уровень логирования.
   - Вызовите функции логирования для разных уровней через указатель на функцию, передавая их в метод `logMessage`.

## Подсказка

- Используйте статическую переменную, чтобы сохранить текущий уровень логирования.
- Передавайте указатели на функции `logInfo`, `logWarning`, `logError` в метод `logMessage`.

## Ожидаемый результат

- Сообщение с уровнем `INFO` не должно быть выведено, так как текущий уровень логирования установлен на `WARNING`.
- Сообщения с уровнями `WARNING` и `ERROR` должны быть выведены на экран.

## Скелет программы

```cpp
#include <iostream>
#include <string>

class Logger {
public:
    // Перечисление уровней логирования. 
    enum LogLevel { INFO, WARNING, ERROR };
    /* 
    enum (перечисление) — это специальный тип данных в C++, который позволяет задать набор именованных целочисленных констант. Перечисления полезны для повышения читаемости кода, так как они позволяют использовать осмысленные имена вместо числовых значений.
    Пример использования: 
    
    enum EnumName {
        VALUE1,  // по умолчанию присваивается 0
        VALUE2,  // 1
        VALUE3   // 2
    };

    EnumName en = VALUE2;
    */

    // Метод setLogLevel(???) для установки уровня логирования
    // Метод статический

    // Метод ??? getLogLevel() для получения текущего уровня логирования
    // Метод статический


    // Статический метод logMessage для логирования сообщений с помощью указателя на функцию
    // 1 параметр - указатель на функцию логирования
    // 2 параметр - уровень логирования
    // 3 параметр - сообщение
    // Ничего не возвращает
    // Метод статический
    ???? ???? (????, ????, ????) {
        if (level >= currentLogLevel) {
            logFunc(message);
        }
    }

private:
    // Статическая переменная currentLogLevel для хранения текущего уровня логирования
};

// Определение статической переменной возможно вне класса
Logger::LogLevel Logger::currentLogLevel = Logger::INFO; // Присваиваем уровень INFO - константное значение из enum, использованного ранее в классе

// Функция logInfo для логирования сообщений


// Функция logWarning для логирования сообщений


// Функция logError для логирования сообщений


int main() {
    // Устанавливаем уровень логирования на WARNING

    // Логирование сообщений с использованием указателей на функции

    return 0;
}
```

## Дополнительное задание

Добавьте возможность динамически менять уровень логирования во время выполнения программы, чтобы студенты могли увидеть, как статическая переменная сохраняет свое значение между вызовами функций.

---

Эта задача поможет закрепить знания о:

1. **Статических переменных**: для хранения состояния между вызовами методов.
2. **Указателях на функции**: для передачи функций в качестве аргументов.
