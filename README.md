# ДЗ 3 · Завантаження даних і DQL: UCI Adult

Матеріали домашньої роботи з курсу **Relational Databases for Data Science**.

[Відкрити notebook у Google Colab](https://colab.research.google.com/github/humanistitel/goit-rdb-hw-03/blob/main/Diuryk_hw3_adult.ipynb) · [Завантажити `.ipynb`](https://raw.githubusercontent.com/humanistitel/goit-rdb-hw-03/main/Diuryk_hw3_adult.ipynb)

## Google Colab

1. Відкрийте посилання Colab вище у стандартному **Python 3 / CPU** runtime.
2. Виконайте **Runtime → Run all**. Notebook сам підготує залежності, власний PostgreSQL 16 і потрібні дані. Додаткові клітинки або ручне копіювання файлів не потрібні.

Перший запуск потребує інтернету й часу на встановлення PostgreSQL та отримання даних. Сумісні встановлені бібліотеки зберігаються; фактичні версії відображаються під час виконання. Після завершення збережіть notebook із результатами. Якщо виконання перервано після запуску PostgreSQL, виконайте останню клітинку cleanup.

Файл `.ipynb` також можна завантажити та відкрити через **File → Upload notebook**.

## Запуск і залежності

Notebook містить SQL, код отримання даних і графіки; генератор або зовнішні SQL-файли для запуску не потрібні.

У стандартному Colab з Python 3.13 PostgreSQL 16 встановлюється із системних пакетів Ubuntu й працює у власному кластері через локальний Unix socket. Зовнішня база або credentials не потрібні. Для локального запуску підтримується Python 3.9–3.12 з `pgserver==0.1.4`. Остання клітинка зупиняє власний PostgreSQL.

## Дані та відтворюваність

[UCI Adult](https://archive.ics.uci.edu/dataset/2/adult), Becker, B. і Kohavi, R. (1996), DOI [10.24432/C5XW20](https://doi.org/10.24432/C5XW20). Ліцензія джерела — [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Атрибуція не означає схвалення роботи авторами джерела.

Використано всі **32 561 записи `adult.data`** без sampling. `adult.test` не використовується. Notebook сам завантажує [офіційний ZIP](https://archive.ics.uci.edu/static/public/2/adult.zip) у `data/`, перевіряє SHA-256 архіву й сирого файла, додає заголовок та CSV quoting і пропускає лише завершальний порожній фізичний рядок. Очищення й аналітика виконуються в PostgreSQL; `fnlwgt` не використовується як вага наведених описових показників.

- SHA-256 ZIP: `7537312dd56c2b98035880805ce99e68183a30ee468aa5329d6df0fbb3cc21bb`.
- SHA-256 `adult.data`: `5b00264637dbfec36bdeaab5676b0b309ff9eb788d63554ca0a249491c86603d`.

Дані не зберігаються в Git. Зміна офіційного файла спричинить зупинку перевірки, а не непомітне використання іншої вибірки.
