# Лабораторная работа 5
## Предварительные требования:

1. Основы работы с Git.
2. Установленный Git на локальной машине (не обязательно Линукс, не обязательно на Виртуальной машине - т.е. где хотите).

Следуюшие разделы представлены как теория/примеры, по ним могут быть вопросы, но не нужно их писать в отчет!!!
  1. Введение
  2. Работа с ветками
  3. Работа с удаленным репозиторием
  4. Моделирование конфликта
  5. Разрешение конфликта

Разделы "Задание 1" и "Задание 2" в отчет уже включаем!!!

## 1. Введение

1. Создание репозитория на GitHub:

    Зайдите в свою учетную запись GitHub и создайте новый репозиторий, например, с именем git-practice.
    Скопируйте URL вашего репозитория.

2. Клонирование репозитория:

    Откройте терминал и перейдите в папку, где вы хотите сохранить локальную копию репозитория.
    Введите следующие команды, используя скопированный URL:

    ```
    git clone <URL-репозитория>
    cd git-lab
    ```

3. Добавление файла:

    Создайте новый текстовый файл, например, example.txt, и добавьте в него какой-то текст, например, структуру книги (главы, параграфы и т.п.)
    Вернитесь в терминал и введите:

    ```
    git add example.txt
    git commit -m "File added example.txt"
    git push origin main
    ```

4. Создание ветки:

    Создайте новую ветку с названием, например, ```feature-branch```, и переключитесь на нее:
    
    ```
    git branch feature-branch
    git checkout feature-branch
    ```

5. Отредактируйте файл example.txt, добавив еще текст.

    Повторите шаги, указанные в п. 3. Имя коммита должно отличаться!

6. Слияние изменений:

    Переключитесь обратно в основную ветку:
    
    ```
    git checkout main
    ```
    Слейте изменения из ветки ```feature-branch``` в основную ветку:

    ```
    git merge feature-branch
    git push origin main
    ```

7. Завершение:

    Проверьте, что изменения успешно слиты и отображаются в основной ветке на GitHub.
    Завершите работу с репозиторием.

## 2. Работа с ветками

1. Создайте новый текстовый файл с базовой структурой книги, например:

```
# Название книги

## Глава 1: Введение
Здесь будет введение в тему книги.

## Глава 2: Основы Git
Основные понятия и команды Git.

```

2. Создайте ветку "feature-login" для разработки новой функциональности:

```
git checkout -b feature-login
```

3. Внесите изменения в файл:

```
# Название книги

## Глава 1: Введение
Здесь будет введение в тему книги.

## Глава 2: Основы Git
Основные понятия и команды Git.

## Глава 3: Вход в систему
Раздел по новой функциональности входа в систему.
```

4. Завершите изменения, закоммитьте их и отправьте ветку на GitHub:

```
git add README.md
git commit -m "Добавлена глава 3: Вход в систему"
git push origin feature-login
```

## 3. Работа с удаленным репозиторием

1. Переключитесь на основную ветку (main) и внесите изменения:

```
git checkout main
```

2. Внесите изменения в основной ветке (например, добавьте описание книги):

```
# Название книги: Приключения в мире Git

## Глава 1: Введение
Здесь будет введение в удивительный мир Git.

## Глава 2: Основы Git
Основные понятия и команды Git.

```

3. Закоммитьте изменения и отправьте их на GitHub:

```
git add <filename>
git commit -m "Изменено название книги и введение"
git push origin main

```


## 4. Моделирование конфликта

1. Вернитесь в ветку "feature-login" и внесите изменения в том же участке:

```
git checkout feature-login
```

2. Измените главу 2 в файле

```
# Название книги: Приключения в мире Git

## Глава 1: Введение
Здесь будет введение в удивительный мир Git.

## Глава 2: Основы Git и магия конфликтов
Основные понятия и команды Git, а также волшебство разрешения конфликтов.

```

3. Закоммитьте изменения и отправьте их на GitHub:

```
git add README.md
git commit -m "Добавлен раздел о магии конфликтов"
git push origin feature-login

```

## 5. Разрешение конфликта

1. Вернитесь в основную ветку и попробуйте слить изменения:

```
git checkout main
git pull origin main
```

2. Возникнет конфликт. Разрешите его в файле

```
# Название книги: Приключения в мире Git

## Глава 1: Введение
Здесь будет введение в удивительный мир Git.

<<<<<<< HEAD
## Глава 2: Основы Git и магия конфликтов
Основные понятия и команды Git, а также волшебство разрешения конфликтов.
======= 
## Глава 2: Основы Git
Основные понятия и команды Git. 
>>>>>>> feature-login

```

3. Разрешите конфликт, удалив метки и оставив нужные изменения:

```
# Название книги: Приключения в мире Git

## Глава 1: Введение
Здесь будет введение в удивительный мир Git.

## Глава 2: Основы Git и магия конфликтов
Основные понятия и команды Git, а также волшебство разрешения конфликтов.
```

4. Закоммитьте разрешение конфликта и отправьте изменения на GitHub:

```
git add README.md
git commit -m "Resolved conflict in chapter 2"
git push origin main
```

## Задание 1 - Автоматизация проверки формата файлов при коммите
1. В директории .git/hooks нашла файл pre-commit.sample
![image](https://github.com/user-attachments/assets/4aebc1e5-2557-4bad-9651-7f919e8b8969)

2. Отредактировала скрипт
![image](https://github.com/user-attachments/assets/74c562d1-dc50-4af4-9f65-2b9e1712b2c3)

![image](https://github.com/user-attachments/assets/bbb8e5cf-ba98-4b27-a8a1-1cc2c5c6ca11)

3. Изменила название на pre-commit
![image](https://github.com/user-attachments/assets/42d5b8f6-e73a-4338-b416-b4fd8954a1aa)

4. Создала текстовый файл с невалидным содержимым
![image](https://github.com/user-attachments/assets/cb82ca86-ec56-4943-8a54-a3aa6ed76c5e)

5. Коммит выдает ошибку
![image](https://github.com/user-attachments/assets/053eb1d5-6bc6-491f-8be3-39e7d1dffb2a)

6. Изменила текст файла

7. Коммит удался

   
## Задание 2 - Использование Git Flow в проекте
 
Предположим, у вас есть задача на создание новой функциональности для вашего проекта с использованием Git Flow. Давайте рассмотрим конкретный пример. В примере важен не сам проект и его код (его тут вообще как такового нет), а принцип работы Git Flow.

1. Убедитесь, что Git Flow установлен на локальной машине:

```
sudo apt-get install git-flow
```

2. В корне репозитория выполните инициализацию Git Flow.

```
git flow init
```

3. Создайте ветку для новой функциональности, допустим она называется "task-management":

```
git flow feature start task-management
```

4. Внесите изменения в код для добавления функционала управления задачами (например, в файл task_manager.py):

```
def create_task(title, description):
    # Логика создания задачи
    print(f"Создана новая задача: {title}")
```

Выполните коммит изменения по мере разработки:

```
git add task_manager.py
git commit -m "Добавлен функционал управления задачами"


```

5. После завершения разработки функции завершите фичу и объедините ее с основной веткой:

```
git flow feature finish task-management

```

Git Flow автоматически переключится на ветку develop и выполнит слияние. Если есть конфликты, их нужно разрешить.

6. Переключитесь на ветку "develop" и начните создание релиза:

```
git checkout develop
git flow release start v1.0.0
```

7. Внесите изменения, связанные с релизом (например, обновите версию в файле version.txt):

```
echo "v1.0.0" > version.txt
git add version.txt
git commit -m "Обновлена версия для релиза v1.0.0"

```

8. Завершите релиз и объедините его с ветками "develop" и "main":

```
git flow release finish v1.0.0
```

9. Если в процессе использования выявлена критическая ошибка, создайте hotfix (у нас конечно же ошибки никакой не возникнет, но hotfix все равно создаем):

```
git flow hotfix start hotfix-1.0.1
```

10. Внесите изменения для исправления ошибки и коммитите:

```
# Исправление ошибки
git add file_with_error.py
git commit -m "Исправлена критическая ошибка"
```

11. Завершите hotfix и объедините его с ветками "develop" и "main":

```
git flow hotfix finish hotfix-1.0.1
```

12. Завершение работы и отправка изменений на удаленный репозиторий. Отправьте изменения на удаленный репозиторий:

```
git push origin develop
git push origin main

```
### Как успешно сдать работу?

Создать свой репозиторий из шаблона этого. Как это делается - "Use this template" -> "Create a new repository" и сделайте его public. 

Находясь уже в своем репозитории - создайте новый файл формата .md и там оформляйте отчет. В отчете опишите все шаги которые вы делали, чтобы получить финальный результат работы.

Что вам нужно знать, чтобы успешно защитить работу:

Основные команды Git, как возникают и как решать конфликты, Git Hooks, Git Flow. 

## Ресурсы

1. [Git Documentation](https://git-scm.com/doc)
2. [Atlassian Git Tutorial](https://www.atlassian.com/git/tutorials)
3. [Pro Git Book](https://git-scm.com/book/en/v2)
4. [Markdown Guidelines](https://docs.github.com/ru/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
