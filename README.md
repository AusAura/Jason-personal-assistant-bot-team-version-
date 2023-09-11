# Jason-personal-assistant-bot
Планувати криваву помсту ще ніколи не було так зручно.

## Address Book:
Підпрограма зберігає записи про твоїх майбутніх жертв: їх імена, номери, імейл та фізичну адресу. А також День народження, якщо ти бажаєш особливого привітання.
Має наступні команди-фукнції:


№1) Программа  корректно зберігає записи у save.json та зчитує їх при запуску.


№2) add <_name> <_phone_number> <_email> <_adress>
Дозволяє додавати новий запис до адресної книги.

<_name> = str, 1 слово
<_phone_number> = Must contain 10-13 symbols and must match the one of the current '
'formats: +380001112233 or 80001112233 or 0001112233
<_email> = Must contain min 2 characters before "@" and 2-3 symbols in TLD! '
'Example: aa@example.net or aa@example.com.ua
<_adress> = str

1) Не працює без будь-яких параметрів
2) Не працює, якщо параметри перевищують кількість заданих у шаблоні
3) Обов'язковим є тільки <_name> і <_phone_number>
4) Якщо одного або більше із додаткових параметрів не вистачає, все одно створюває запис з пустими значеннями для цих параметрів.
5) Телефон невірного формату викликає помилку.
6) Імейл невірного формату викликає помилку.
7) Якщо запис з введеним таким ім'ям вже існує - перезапис вже існуючого новим є нормальною поведінкою.


№3) add phone <_name> <_phone_number>
Дозволяє додавати новий телефон до створеного запису.

<_name> = str, 1 слово
<_phone_number> = Must contain 10-13 symbols and must match the one of the current '
'formats: +380001112233 or 80001112233 or 0001112233 

1) Не працює без будь-яких параметрів
2) Не працює, якщо параметри перевищують кількість заданих у шаблоні
3) Обов'язковими є <_name> і <_phone_number>
4) Якщо одного із додаткових параметрів не вистачає, видає відповідну помилку.
5) Телефон невірного формату викликає помилку.
6) Якщо запис з введеним таким ім'ям не існує - видає помилку.
7) Якщо доданий телефон вже існує у записі - видає помилку.


№4) edit phone <_name> <_phone_number>
Дозволяє редагувати телефон у створеному записі.

<_name> = str, 1 слово
<_phone_number> = Must contain 10-13 symbols and must match the one of the current '
'formats: +380001112233 or 80001112233 or 0001112233 

1) Не працює без будь-яких параметрів
2) Не працює, якщо параметри перевищують кількість заданих у шаблоні
3) Обов'язковими є <_name> і <_phone_number>
4) Якщо одного із додаткових параметрів не вистачає, видає відповідну помилку.
5) Якщо запис з введеним ім'ям не існує - видає помилку.
6) Якщо введеного телефону не існує у записі - видає помилку.
7) Якщо існує - запитує яким телефоном замінити.
8) Новий телефон невірного формату викликає помилку.
8) Якщо новий телефон співпадає зі старим у записі - все одно зміняє.


№5) show all
Виводить всі існуючі у книзі записи зі всією інформацією у них.

1) Не працює, якщо має будь-які параметри.
2) Якщо є параметри, видає відповідну помилку.
3) Виводить всі існуючі записи та всю наявну інформацію щодо них.
4) Якщо деяке поле пусте - виводить пустоту.
5) Якщо книга пуста - виводить відповідне повідомлення.


№6) show some
Виводить всі існуючі у книзі записи зі всією інформацією у них, але покроково у заданій кількості.

1) Не працює, якщо має будь-які параметри.
2) Якщо є параметри, видає відповідну помилку.
3) Запитує, скільки записів виводити за 1 ітерацію.
4) Якщо кількість < 0, виводить помилку.
5) Якщо введене значення != int, виводить помилку.
6) Якщо введена кількість перевищує загальну кількість записів у книзі - виводить відповідне повідомлення та показує записи всі, що є.
7) Виводить всі існуючі записи та всю наявну інформацію щодо них.
8) Якщо у адресній книзі ще залишаються не виведені записи - запитує чи виводити іх.
9) Якщо введено 'y' (команда не є регістрозалежною), то показує наступну порцію записів.
10) Якщо введено 'n', функція завершує виконання та повертається до меню підпрограми.
11) Якщо деяке поле пусте - виводить пустоту.
12) Якщо книга пуста - виводить відповідне повідомлення.


№7) delete phone <_name> <_phone_number>
Видаляє вказаний телефон із створеного запису.

<_name> = str, 1 слово
<_phone_number> = Must contain 10-13 symbols and must match the one of the current '
'formats: +380001112233 or 80001112233 or 0001112233

1) Не працює без будь-яких параметрів
2) Не працює, якщо параметри перевищують кількість заданих у шаблоні
3) Обов'язковими є <_name> і <_phone_number>
4) Якщо одного із додаткових параметрів не вистачає, видає відповідну помилку.
5) Якщо запис з введеним ім'ям не існує - видає помилку.
6) Якщо введеного телефону не існує у записі - видає помилку.
7) Телефон невірного формату викликає помилку.
8) Якщо телефон співпадає зі знайденим у записі - видаляє.


№8) delete contact <_name>
Видаляє вказаний запис повністю.

1) Не працює без будь-яких параметрів
2) Не працює, якщо параметри перевищують кількість заданих у шаблоні
3) Обов'язковими є <_name>.
4) Якщо одного із додаткових параметрів не вистачає, видає відповідну помилку.
5) Якщо запис з введеним ім'ям не існує - видає помилку.
6) Якщо назва співпадає зі знайденим записом - видаляє запис із об'єкту адресної книги.


№9) set bday <_name>
Дозволяє додавати день народження до існуючого запису.

<_name> = str, 1 слово

1) Не працює без будь-яких параметрів
2) Не працює, якщо параметри перевищують кількість заданих у шаблоні
3) Обов'язковими є <_name>.
4) Якщо одного із додаткових параметрів не вистачає, видає відповідну помилку.
5) Якщо запис з введеним таким ім'ям не існує - видає помилку.
6) Якщо існує - просить ввести дату дня народження по шаблону (10 January 2020).
7) Шаблон невірного формату повинен викликати помилку.
8) Вірно введений шаблон повинен додати відновідний запис у Record та видавати повідомлення про успіх.
9) Якщо запис про день народження вже існує - перезаписує.


№10) set email <_name>
Дозволяє додавати імейл-адресу до існуючого запису.

1) Не працює без будь-яких параметрів
2) Не працює, якщо параметри перевищують кількість заданих у шаблоні
3) Обов'язковими є <_name>.
4) Якщо одного із додаткових параметрів не вистачає, видає відповідну помилку.
5) Якщо запис з введеним таким ім'ям не існує - видає помилку.
6) Якщо існує - просить ввести імейл по шаблону (myemail@google.com).
7) Шаблон невірного формату повинен викликати помилку:
Must contain min 2 characters before "@" and 2-3 symbols in TLD!

8) Вірно введений шаблон повинен додати відновідний запис у Record та видавати повідомлення про успіх.
9) Якщо запис про імейл вже існує - перезаписує.


№11) set address <_name>
Дозволяє додавати фізичну адресу до існуючого запису.

<_name> = str, 1 слово

1) Не працює без будь-яких параметрів
2) Не працює, якщо параметри перевищують кількість заданих у шаблоні
3) Обов'язковими є <_name>.
4) Якщо одного із додаткових параметрів не вистачає, видає відповідну помилку.
5) Якщо запис з введеним таким ім'ям не існує - видає помилку.
6) Якщо існує - просить ввести адресу (немає шаблону).
8) Повинен додати відновідний запис у Record та видавати повідомлення про успіх.
9) Якщо запис про адресу вже існує - перезаписує.


№12) show bday <_name>
Виводить дату дня народження та кількість днів до нього для заданого запису.

<_name> = str, 1 слово

1) Не працює без будь-яких параметрів
2) Не працює, якщо параметри перевищують кількість заданих у шаблоні
3) Обов'язковими є <_name>.
4) Якщо запис з введеним ім'ям не існує - видає помилку.
5) Якщо є - виводить дату дня народження із запису та вірну кількість днів до нього.
6) Якщо дата не встановлена - виводить відповідне повідомлення.


№13) show email <_name>
Виводить імейл для заданого запису.

<_name> = str, 1 слово

1) Не працює без будь-яких параметрів
2) Не працює, якщо параметри перевищують кількість заданих у шаблоні
3) Обов'язковими є <_name>.
4) Якщо запис з введеним ім'ям не існує - видає помилку.
5) Якщо є - виводить вірний імейл для нього.
6) Якщо імейл не встановлений - виводить відповідне повідомлення.


№14) show address <_name>
Виводить фізичну адресу для заданого запису.

<_name> = str, 1 слово

1) Не працює без будь-яких параметрів
2) Не працює, якщо параметри перевищують кількість заданих у шаблоні
3) Обов'язковими є <_name>.
4) Якщо запис з введеним ім'ям не існує - видає помилку.
5) Якщо є - виводить вірну адресу для нього.
6) Якщо адресу не встановлена - виводить відповідне повідомлення.


№15) find <_something>
Шукає вказану строку у імені, номерах, імейлі та фізичній адресі. Виводить повний список співпадінь.

<_something> = str, 1 слово

1) Не працює без будь-яких параметрів
2) Не працює, якщо параметри перевищують кількість заданих у шаблоні
3) Обов'язковими є <_something>.
4) Якщо у всіх існуючих записах <_something> не знайдено у ім'ї, телефонах, адресі, імейлі - видає помилку.
5) Якщо є - виводить записи, що мають <_something>.


№16) help
Виводить всі існуючі команди.

1) Не працює, якщо має будь-які параметри.
2) Якщо є параметри, видає відповідну помилку.
3) Виводить всі існуючі команди.


№17) bday in <_days>
Виводить всі існуючі у книзі записи, в яких дні народження будуть через задану кількість днів.

<_days> = int > 0

1) Не працює без параметрів.
1) Не працює, якщо має додаткові параметри.
2) Обов'язковим є <_days>.
3) Якщо <_days> не є числом, видає помилку.
4) Якщо <_days> <= 0, виводить помилку. 
5) Виводить всі існуючі записи із іменем, датою та кількістю днів до дня народження, якщо вони є раніше або дорівнюють <_days>.
6) Якщо таких немає - виводить відповідне повідомлення.


№18) good bye
Завершує роботу, зберігаючи зміни.

1) Не працює, якщо має будь-які параметри.
2) Якщо є параметри,видає відповідну помилку.
3) Завершує роботу адресної книги, повертаючись до мейн-програми.
4) Всі записи будуть корректно збережені до файлу save.json.


№19) close
Завершує роботу, зберігаючи зміни.

1) Не працює, якщо має будь-які параметри.
2) Якщо є параметри, видає відповідну помилку.
3) Завершує роботу адресної книги, повертаючись до мейн-програми.
4) Всі записи будуть корректно збережені до файлу save.json.


№20) hello
Виводить привітання. Бо навіть кривава помста не є завадою ввічливості.

1) Не працює, якщо має будь-які параметри.
2) Якщо є параметри, видає відповідну помилку.
3) Видає привітання.


№21) not save
Завершує роботу, БЕЗ ЗБЕРЕЖЕННЯ ЗМІН.

1) Не працює, якщо має будь-які параметри.
2) Якщо є параметри, видає відповідну помилку.
3) Завершує роботу адресної книги, повертаючись до мейн-програми.
4) Всі зміни НЕ БУДУТЬ збережені до файлу save.json.


## Notebook: 
Програма для створення, редагування та керування нотатками.
Ця програма дозволяє створювати, редагувати, видаляти та переглядати нотатки. Кожна нотатка
має назву, вміст та список тегів. Крім того, можна додавати теги до існуючих нотаток, та змінювати їх вміст.

Використання:
    Для використання блокноту запустіть функцію main(), яка надає командний інтерфейс для взаємодії з вашими нотатками. Ви можете додавати, редагувати, видаляти, додавати теги, шукати, перелічувати, зберігати та завантажувати нотатки, використовуючи підтримані команди.

Підтримувані команди:
№1) add (Додати нотатку)
    Функція add_note() дозволяє користувачам створювати нові нотатки. Користувач вводить назву нотатки (мінімум 5 символів), вміст нотатки (мінімум 10 символів) та теги, розділені комою або пробілом (від 1 до 20 символів).
    1) Не працює без будь-яких параметрів
    2) Не працює, якщо введені дані не відповідають умовам, таким як довжина назви, вмісту або тег.
    3) Обов'язковим є тільки Title і Content.

№2) edit (Редагувати нотатку)
    Функція edit_note() дозволяє користувачам редагувати існуючі нотатки. Користувач вводить назву нотатки, яку він хоче редагувати, а потім вводить новий вміст нотатки.
    1) Не працює, якщо нотатки з введеною назвою не існує.
    2) Не працює, якщо введені дані не відповідаю умовам на довжину вмісту.

№3) delete (Видалити нотатку)
    Функція delete_note() дозволяє користувачам видаляти нотатки. Користувач вводить назву нотатки, яку він хоче видалити.
    1) Не працює, якщо нотатки з введеною назвою не існує.

№4) tag (Додати тег до нотатки)
    Функція add_tag_to_note() дозволяє користувачам додавати теги до існуючих нотаток. Користувач вводить назву нотатки, до якої він хоче додати тег, а потім вводить нові теги, розділені комою або пробілом.
    1) Не працює, якщо нотатки з введеною назвою не існує.
    2) Не працює, якщо додати теги, які вже існують для цієї нотатки.
    3) Не працює, якщо введені дані не відповідаю умовам на довжину тег.

№5) sort (Сортування нотаток)
    Функція sort_notes() дозволяє користувачам сортувати нотатки за наявністю ключових слів у тегах, заголовку або вмісті.


№6) list (Вивести список нотаток)
    Функція display_notes() виводить усі наявні нотатки.

№7) search (Пошук нотаток)
    Функція search_notes() дозволяє користувачам шукати нотатки за наявністю ключових слів у заголовку, вмісті або тегах.

№8) load (Завантаження нотаток)
    Функція load_notes() дозволяє користувачам завантажувати нотатки з файлу. Користувач вводить ім'я файлу для завантаження нотаток. Файл повинен бути у форматі JSON.
    1) Не працює, якщо файл з нотатками ( .json) не існує або має неправильний формат.

№9) save (Збереження нотаток)
    Функція save_notes() зберігає всі нотатки в файл у форматі JSON. #! Та створює новий, якщо файл був видалений або не створений раніше.?

№10) exit (Вихід)
    Завершує виконання програми, #! зберігаючи нотатки у файл.?



## File sorter:
Підпрограма являється вашою власною покоївкою із чорним поясом по сортуванню та прибиранню.

Звісно, у вас є папка у яку постійно скидається мотлох у вигляді старих фотографій усунених цілей, старих відео допитів,
колись популярних російських пісень, секретних старих архівів із документами та всяких інших файлів. У такому разі на
сцену виходить ваша кишенькова покоївка. 

Все що потрібно - це просто вказати шлях до папки з усім мотлохом і дана програма відсортує усі файли та перемістить їх
у нову папку, всередині якої будуть знаходитись папки із відповідними назвами які міститимуть відповідні до формату 
відсортовані файли, архіви ж будуть розпаковані та знаходитимуться у папках із назвами відповідними до назв архівів. 

Також у процесі сортування усі назви файлів, які були написані кириличними символами будуть замінені на латинські 
символи зі збереженням назв.
