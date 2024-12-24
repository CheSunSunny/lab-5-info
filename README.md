# Лабораторная работа 5
## Задание 1 - Автоматизация проверки формата файлов при коммите
1. В директории .git/hooks нашла файл pre-commit.sample, отредактировала, изменила название на pre-commit

![image](https://github.com/user-attachments/assets/cb82ca86-ec56-4943-8a54-a3aa6ed76c5e)
![image](https://github.com/user-attachments/assets/42d5b8f6-e73a-4338-b416-b4fd8954a1aa)

3. Создала текстовый файл с невалидным содержимым

![image](https://github.com/user-attachments/assets/74c562d1-dc50-4af4-9f65-2b9e1712b2c3)

4. Коммит выдает ошибку

![image](https://github.com/user-attachments/assets/bbb8e5cf-ba98-4b27-a8a1-1cc2c5c6ca11)

7. Изменила текст файла

![image](https://github.com/user-attachments/assets/33aa8199-4eca-47f3-850d-1428d8618eb8)

8. Коммит удался

![image](https://github.com/user-attachments/assets/bbb8e5cf-ba98-4b27-a8a1-1cc2c5c6ca11)
   
## Задание 2 - Использование Git Flow в проекте

1. В корне репозитория выполнила инициализацию Git Flow.
![image](https://github.com/user-attachments/assets/b0618e4b-9705-4a8f-885a-ada0ad19d92a)

2. Создала ветку для новой функциональности "task-management":
![image](https://github.com/user-attachments/assets/c4a0877e-390b-43b8-b98e-8cd74d604c04)

3. Добавила файл task_manager.py и выполнила коммит изменения:
![image](https://github.com/user-attachments/assets/319fb722-a13f-4d7f-a145-bd20e367522a)

4. После завершения разработки функции завершила фичу и объединила ее с основной веткой:
![image](https://github.com/user-attachments/assets/38be48c0-15ae-465e-959f-64dab1419cf0)

5. Автоматически переключилась на ветку "develop" и начала создание релиза:
![image](https://github.com/user-attachments/assets/0f35df43-189f-4963-83fe-7acf928659b6)

6. Внесла изменения, связанные с релизом (обновила версию в файле version.txt):
![image](https://github.com/user-attachments/assets/d5c0258c-502c-4b16-9e0f-cd4b3a3408c8)

7. Завершила релиз и объединила его с ветками "develop" и "main":
![image](https://github.com/user-attachments/assets/403c1c18-8514-4324-8c56-80b600f44bf2)

8. Cоздала hotfix:
![image](https://github.com/user-attachments/assets/19a9880a-f11a-4e66-b4d8-49fbe09f19a4)

9. Внесла изменения для исправления ошибки и закоммитила, завершила hotfix и объединила его с ветками "develop" и "main":
![image](https://github.com/user-attachments/assets/0693a78d-7448-483c-bff3-40fdb626fb1c)

10. Отправила изменения на удаленный репозиторий:
![image](https://github.com/user-attachments/assets/c2a65611-d6de-4069-a6fe-596ec8745789)
