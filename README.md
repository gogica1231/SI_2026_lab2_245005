Gorazd Miloshoski 245005


<img width="781" height="661" alt="slika1si drawio" src="https://github.com/user-attachments/assets/161302d9-8167-4d46-8236-46e9769e32e4" />
<img width="746" height="801" alt="Dijagram2 drawio" src="https://github.com/user-attachments/assets/d56ee398-eca9-41de-a96f-35c4c1eb58f4" />

Цикломатска комплексност 
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


import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.*;
import java.util.List;
import java.util.ArrayList;

public class BookServiceEveryStatementTest {

    @Test
    public void searchBookEveryStatementTest() {
        // --- INITIAL SETUP ---
        List<Book> libraryBooks = new ArrayList<>();
        libraryBooks.add(new Book("978-0141187761", "1984"));
        libraryBooks.add(new Book("978-0743273565", "The Great Gatsby"));
        
        BookService service = new BookService(libraryBooks);

        // ==========================================
        // TEST 1: Statement coverage for validation
        // Covers: title == null || title.isEmpty() -> throw new IllegalArgumentException(...)
        // ==========================================
        assertThrows(IllegalArgumentException.class, () -> {
            service.searchBookByTitle(null);
        }, "Should trigger validation and throw IllegalArgumentException when title is null");


        // ==========================================
        // TEST 2: Statement coverage for successful match
        // Covers: for (Book book : books) -> book.getTitle().equalsIgnoreCase(title) -> return book;
        // ==========================================
        String targetTitle = "the great gatsby"; // Testing case insensitivity as per equalsIgnoreCase
        Book matchedBook = service.searchBookByTitle(targetTitle);
        
        assertNotNull(matchedBook, "Book should be successfully located in the list");
        assertEquals("978-0743273565", matchedBook.getIsbn(), "The system must return the correct matching book object");


        // ==========================================
        // TEST 3: Statement coverage for unmatched search
        // Covers: for (Book book : books) -> book.getTitle().equalsIgnoreCase(title) -> return null;
        // ==========================================
        String missingTitle = "To Kill a Mockingbird";
        Book unmatchedResult = service.searchBookByTitle(missingTitle);
        
        assertNull(unmatchedResult, "Should return null when the book title does not exist in the collection");
    }
}
