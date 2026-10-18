# ДЗ 3 · Завантаження даних і DQL: UCI Adult

Завантаження UCI Adult через PostgreSQL COPY, очищення значень у SQL та десять аналітичних запитів із таблицями й графіками.

[Відкрити у Google Colab](https://colab.research.google.com/github/humanistitel/goit-rdb-hw-03/blob/main/Diuryk_hw3_adult.ipynb) · [Завантажити notebook](https://raw.githubusercontent.com/humanistitel/goit-rdb-hw-03/main/Diuryk_hw3_adult.ipynb)

## Запуск

У Colab оберіть CPU та натисніть **Runtime → Run all**. Перша клітинка готує залежності й тимчасовий PostgreSQL 16; остання зупиняє сервер. Перший запуск потребує інтернету. Якщо виконання перервано, запустіть останню клітинку для зупинки сервера.

Локально: Jupyter та Python 3.9–3.12.

## Дані та аналіз

[UCI Adult](https://archive.ics.uci.edu/dataset/2/adult), Becker, B., & Kohavi, R. (1996), DOI [10.24432/C5XW20](https://doi.org/10.24432/C5XW20), ліцензія [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

Використано всі **32 561 записи `adult.data`**; `adult.test` залишається поза аналізом. Notebook завантажує [офіційний ZIP](https://archive.ics.uci.edu/static/public/2/adult.zip), перевіряє контрольні суми та додає заголовок для COPY. Очищення пропусків і перетворення типів виконуються в PostgreSQL.

- SHA-256 ZIP: `7537312dd56c2b98035880805ce99e68183a30ee468aa5329d6df0fbb3cc21bb`.
- SHA-256 `adult.data`: `5b00264637dbfec36bdeaab5676b0b309ff9eb788d63554ca0a249491c86603d`.

Середні й частки незважені: `fnlwgt` не застосовується як вага. Запити описують асоціації в історичних записах Census 1994; повні збіги значень самі по собі не доводять повторного запису однієї людини.
