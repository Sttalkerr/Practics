# Практическое занятие №1.
## Задача 1. Вывести отсортированный в алфавитном порядке список имен пользователей в файле passwd (вам понадобится grep).
```
localhost:~# cut -d: -f1 /etc/passwd | sort

```
![image](https://github.com/user-attachments/assets/82dcd8df-c90a-44fc-a288-74bc0962d1b3)

## Задача 2. Вывести данные /etc/protocols в отформатированном и отсортированном порядке для 5 наибольших портов, как показано в примере.

```
localhost:~# cat /etc/protocols | awk '{print $2, $1}' | sort -n -r | head -n 5
```
![image](https://github.com/user-attachments/assets/fdfc1df1-b199-40ec-85f7-2fd9305844ae)

## Задача 3.Написать программу banner средствами bash для вывода текстов, как в следующем примере (размер баннера должен меняться!).

```
nano banner.sh                                          
#!/bin/bash
text=$1
length=${#text}
line="+-"
for ((i=0;i<length;i++))
do
line+="-"
done
line+="-+"
echo $line
echo "|" $text "|"
echo $line

localhost:~# chmod +x banner.sh

localhost:~# ./banner.sh "Hello from RTU MIREA!"
+-----------------------+
| Hello from RTU MIREA! |
+-----------------------+
```
![image](https://github.com/user-attachments/assets/8d49077b-a5da-495d-abc7-e07b8c6fa2f3)

## Задача 4. Написать программу для вывода всех идентификаторов (по правилам C/C++ или Java) в файле (без повторений).
![image](https://github.com/user-attachments/assets/81cf4e87-bc5a-4b69-982f-96d06b6ce620)


## Задача 5. Написать программу для регистрации пользовательской команды (правильные права доступа и копирование в /usr/local/bin).

```
#!/bin/bash
chmod u+rwx $1
cp $1 /usr/local/bin


localhost:~# sudo ./regger.sh mama.sh
localhost:~# cd /usr/local/bin
localhost:/usr/local/bin# ls
```
![image](https://github.com/user-attachments/assets/a0c1f520-1429-46a0-bc01-5a13ed0f2d12)
![image](https://github.com/user-attachments/assets/58f33e4c-aa39-4b5c-822f-fc8e9ec5ad5c)

## Задача 6. Написать программу для проверки наличия комментария в первой строке файлов с расширением c, js и py.
```
#!/bin/bash
line=$(head -1 $1)
if [[$line == "//"* ]] || [[$line == "#"* ]]; then
echo "First line have comment"
else
echo "First line dont have comment"
fi
```
![image](https://github.com/user-attachments/assets/d1457d26-5bb6-4685-91a8-b8a7ecdbcc00)

![image](https://github.com/user-attachments/assets/24b5a33b-ca09-43cd-9fc5-19e9e8c484cf)

![image](https://github.com/user-attachments/assets/01f2c3dd-71b6-44db-b128-7cbf9d77aef7)
![image](https://github.com/user-attachments/assets/06976972-00f8-451c-b36e-6793d7f6804a)



## Задача 7. Написать программу для нахождения файлов-дубликатов (имеющих 1 или более копий содержимого) по заданному пути (и подкаталогам).
```
#!/bin/bash
if [ $# -ne 1 ]; then
    echo "Использование: $0 <Путь к каталогу>"
    exit 1
fi
directory="$1"
 
find "$directory" -type f -print0 | xargs -0 md5sum | sort | uniq -d -w 32 | se>
    echo "Дубликат: $duplicate"
done
```
![image](https://github.com/user-attachments/assets/7442a48a-87e3-43e0-a636-d7fca572df30)

## Задача 8. Написать программу, которая находит все файлы в данном каталоге с расширением, указанным в качестве аргумента и архивирует все эти файлы в архив tar.
![image](https://github.com/user-attachments/assets/bbe434d7-7765-496d-aab1-dbe10ed7a150)

## Задача 9. Написать программу, которая заменяет в файле последовательности из 4 пробелов на символ табуляции. Входной и выходной файлы задаются аргументами.
```
#!/bin/bash
input_file="$1"
output_file="$2"
 
sed 's/ /\t/g' "$input_file" > "$output_file"
echo "Замена завершена. Результат сохранен в $output_file."
```
![image](https://github.com/user-attachments/assets/13c4472f-b913-4e68-824f-7b956ace2e39)

![image](https://github.com/user-attachments/assets/894746bb-b643-4d11-8179-3d5c3f4a62ff)

![image](https://github.com/user-attachments/assets/f41db448-a3c0-4270-a115-0c7e2e3b5db8)

## Задача 10.
