Gorazd Miloshoski 245005


<img width="781" height="661" alt="slika1si drawio" src="https://github.com/user-attachments/assets/161302d9-8167-4d46-8236-46e9769e32e4" />
<img width="746" height="801" alt="Dijagram2 drawio" src="https://github.com/user-attachments/assets/d56ee398-eca9-41de-a96f-35c4c1eb58f4" />

Ciklomatskata kompleksnost za vtorata funkcija iznesuva 5. Ovaa vrednost ja presmetav so formulata P + 1, kade што P go pretstavuva brojot na predikatni jazli. Vo ovoj primer ima 4 predikatni jazli, pa kompleksnosta e:

V = 4 + 1 = 5

Test sluchai za kriteriumot Every Statement

Za da se pokrijat site naredbi vo funkcijata, potrebni se minimum 3 test primeri.

Prviot primer e koga kako vlez se prakja prazen string. Vo toj sluchaj funkcijata frla iskluchok poradi nevaliden naslov.
Vtoriot primer e koga vo bibliotekata postoi kniga so dadeniot naslov i taa ne e iznajmena. Togaš knigata uspešno se dodava vo listata results.
Tretiot primer e koga se bara kniga shto ne postoi vo bibliotekata. Vo toj sluchaj пребарувањето ne vrakja rezultat i se aktivira iskluchok za nenajdena kniga.

Test sluchai za kriteriumot Every Branch

Za pokrivanje na site grananja vo funkcijata se potrebni 4 test primeri.

Prviot test e so prazen string, pri shto uslovot za validacija vrakja true i se frla iskluchok.
Vtoriot test e koga knigata postoi i ne e iznajmena. Funkcijata gi pominuva site proverki i vrakja rezultat.
Tretiot test e koga knigata postoi, no e vekje iznajmena. Vo toj sluchaj uslovot za dostupnost ne se ispolnuva i knigata ne se dodava vo rezultatite.
Chetvrtiot test e koga vo bibliotekata nema kniga so baraniot naslov. Ciklusot zavrshuva bez pronajden rezultat i se frla RuntimeException("Book not found").

Test sluchai za kriteriumot Multiple Condition

Za uslovot:

if (title.isEmpty() || author.isEmpty())

potrebni se 3 kombinacii:

TRUE || TRUE – se frla iskluchok бидејќи dvata uslovi se vistiniti.
TRUE || FALSE – dovolno e prviot uslov da e vistinit za da se frli iskluchok.
FALSE || TRUE – i vo ovoj sluchaj se frla iskluchok.
FALSE || FALSE – funkcijata prodolzhuva so izvrshuvanje.

Za uslovot:

if (book.getTitle().equalsIgnoreCase(title) && !book.isBorrowed())

isto taka se dovolni 3 kombinacii:

TRUE && TRUE – uslovot e ispolnet i funkcijata prodolzhuva vo naredniot del.
TRUE && FALSE – naslovot se sovpagja, no knigata e iznajmena, pa uslovot ne se ispolnuva.
FALSE && * – naslovot ne odgovara i nema potreba da se proveruva vtoriot del od uslovot.
