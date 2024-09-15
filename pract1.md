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



## Задача 7.



## Задача 8.



## Задача 9.


## Задача 10.
