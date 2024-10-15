# Лабораторная работа 2
1. Итак мы хотим, чтобы скрипт обеспечивал принятый на вход IPv4-адрес в двоичном формате.
Для начала добавим функцию, которая позволяет проверить корректность введённого IP-адреса:
```
validate_ip() {
    local ip=$1
    IFS="." read -r -a octets <<< "$ip"

    if [ "${#octets[@]}" -ne 4 ]; then  
        return 1 # Некорректный IP
    fi

    for octet in "${octets[@]}"; do
        if [ "$octet" -lt 0 ] || [ "$octet" -ge 256 ]; then
            return 1  # Некорректный IP
        fi
    done
    return 0  # Корректный IP
}
```
2. Далее напишем функцию, которая конвертирует IP из десятичного формата в двоичный:
   

На основе изученного материала лабораторной работы, лекций (2 и 3), дополнительных источников напишите скрипт, который на вход принимает IPv4-адрес в десятичном формате, а на выходе обеспечивает данный IP-адрес в двоичном формате.

Пример входных данных:

```192.168.10.1```

Пример выходныx данных:

```11000000.10101000.00001010.00000001```

### Как успешно сдать работу?

Создать свой репозиторий из шаблона этого. Как это делается - "Use this template" -> "Create a new repository" и сделайте его public. 

Находясь уже в своем репозитории - создайте новый файл формата .md и там оформляйте отчет. В отчете опишите все шаги которые вы делали, чтобы получить финальный результат работы. Необходимы только скриншоты скрипта и примера его выполнения!

Что вам нужно знать, чтобы успешно защитить работу:

Переменные; как выполнять операции; условные конструкции; функции; циклы; как работать с массивом; как посмотреть права доступа к файлам; как выдавать права доступа; что такое и зачем нужен ip адрес и маска подсети.
