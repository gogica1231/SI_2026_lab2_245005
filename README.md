Gorazd Miloshoski 245005


<img width="781" height="661" alt="slika1si drawio" src="https://github.com/user-attachments/assets/161302d9-8167-4d46-8236-46e9769e32e4" />
<img width="746" height="801" alt="Dijagram2 drawio" src="https://github.com/user-attachments/assets/d56ee398-eca9-41de-a96f-35c4c1eb58f4" />

Цикломатска комплексност. 

     Комплексноста е пресметана преку бројот на предикатни јазли (места каде што кодот се дели на две патеки) со формулата:
     
     V(G) = P + 1
     
     За searchBookByTitle:
     
     Тука имаме 2 предикатни јазли (точки на разгранување):
     
     Првиот if услов (проверка за празен текст).
     
     Последниот if услов (проверка дали листата со резултати е празна).
     
     Пресметка: $V(G) = 2 + 1 = 3
     
     Краен резултат: Цикломатската комплексност е 3.
     
     За borrowBook:
     
     Кај оваа функција имаме 3 предикатни јазли:
     
     Почетниот if услов (проверка за празен внес).
     
     Самиот for циклус (проверка за продолжување на вртењето). 
     
     Внатрешниот if услов (проверка дали книгата е веќе позајмена).
     
     Пресметка: V(G) = 3 + 1 = 4
     
     Краен резултат: 
     
     Цикломатската комплексност е 4.



### 5. Тест случаи според критериумот Every statement за searchBookByTitle

| | test 1 | test 2 | test 3 |
| :--- | :---: | :---: | :---: |
| title == null \|\| title.isEmpty() | \* | | |
| throw new IllegalArgumentException(...) | \* | | |
| for (Book book : books) | | \* | \* |
| book.getTitle().equalsIgnoreCase(title) | | \* | \* |
| return book; | | \* | |
| return null; | | | \* |

Минимален број на тест случаи за оваа функција според Every statement критериумот е 3.



