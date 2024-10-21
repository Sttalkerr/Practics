# Практическое занятие №3.
## Задача 1. Реализовать на Jsonnet приведенный ниже пример в формате JSON. Использовать в реализации свойство программируемости и принцип DRY.
```
local student(name, age, group) =
{
  name: name,
  age: age,
  group: group,
};
local groups = [
  "ИКБО-1-20",
  "ИКБО-2-20",
  "ИКБО-3-20",
  "ИКБО-4-20",
  "ИКБО-5-20",
  "ИКБО-6-20",
  "ИКБО-7-20",
  "ИКБО-8-20",
  "ИКБО-9-20",
  "ИКБО-10-20",
  "ИКБО-11-20",
  "ИКБО-12-20",
  "ИКБО-13-20",
  "ИКБО-14-20",
  "ИКБО-15-20",
  "ИКБО-16-20",
  "ИКБО-17-20",
  "ИКБО-18-20",
  "ИКБО-19-20",
  "ИКБО-20-20",
  "ИКБО-21-20",
  "ИКБО-22-20",
  "ИКБО-23-20",
  "ИКБО-24-20",
];
local students = [
  student("Иванов И.И.", 19, "ИКБО-4-20"),
  student("Петров П.П.", 18, "ИКБО-5-20"),
  student("Сидоров С.С.", 18, "ИКБО-5-20"),
  student("Скляр М.А.", 19, "ИКБО-6-20"), 
];
{
  groups: groups,
  students: students,
  subject: "Конфигурационное управление",
}
```

## Задача 2. Реализовать на Dhall приведенный ниже пример в формате JSON. Использовать в реализации свойство программируемости и принцип DRY.
```
let Student = { name: Text, age: Natural, group: Text }
let mkStudent : Text -> Natural -> Text -> Student =
      λ(name : Text) →
      λ(age : Natural) →
      λ(group : Text) →
      { name = name, age = age, group = group }
let groups : List Text =
      [ "ИКБО-1-20"
      , "ИКБО-2-20"
      , "ИКБО-3-20"
      , "ИКБО-4-20"
      , "ИКБО-5-20"
      , "ИКБО-6-20"
      , "ИКБО-7-20"
      , "ИКБО-8-20"
      , "ИКБО-9-20"
      , "ИКБО-10-20"
      , "ИКБО-11-20"
      , "ИКБО-12-20"
      , "ИКБО-13-20"
      , "ИКБО-14-20"
      , "ИКБО-15-20"
      , "ИКБО-16-20"
      , "ИКБО-17-20"
      , "ИКБО-18-20"
      , "ИКБО-19-20"
      , "ИКБО-20-20"
      , "ИКБО-21-20"
      , "ИКБО-22-20"
      , "ИКБО-23-20"
      , "ИКБО-24-20"
      ]
let students : List Student =
      [ mkStudent "Иванов И.И." 19 "ИКБО-4-20"
      , mkStudent "Петров П.П." 18 "ИКБО-5-20"
      , mkStudent "Сидоров С.С." 18 "ИКБО-5-20"
      , mkStudent "Скляр М.А." 19 "ИКБО-6-20" 
      ]


in  { groups = groups, students = students, subject = "Конфигурационное управление" }
```

## Задача 3.
```
import random


def parse_bnf(text):
    '''
    Преобразовать текстовую запись БНФ в словарь.
    '''
    grammar = {}
    rules = [line.split('=') for line in text.strip().split('\n')]
    for name, body in rules:
        grammar[name.strip()] = [alt.split() for alt in body.split('|')]
    return grammar


def generate_phrase(grammar, start):
    '''
    Сгенерировать случайную фразу.
    '''
    if start in grammar:
        seq = random.choice(grammar[start])
        return ''.join([generate_phrase(grammar, name) for name in seq])
    return str(start)


BNF = '''
E = 0 E | 1 E |
'''

for i in range(10):
    print(generate_phrase(parse_bnf(BNF), 'E'))

```
![image](https://github.com/user-attachments/assets/4da9f0d3-298e-4d1e-a131-50edc8d5aee0)
