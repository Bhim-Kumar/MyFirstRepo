public class Book {
    private String title;
    private String author;
    private String ISBN;
    private String publisher;
    private int year;

    // Constructor
    public Book(String title, String author, String ISBN, String publisher, int year) {
        this.title = title;
        this.author = author;
        this.ISBN = ISBN;
        this.publisher = publisher;
        this.year = year;
    }

    // Getters
    public String getTitle() {
        return title;
    }

    public String getAuthor() {
        return author;
    }

    public String getISBN() {
        return ISBN;
    }

    public String getPublisher() {
        return publisher;
    }

    public int getYear() {
        return year;
    }
}
================================================================

import java.util.ArrayList;
import java.util.List;

public class Library {
    private List<Book> books;

    // Constructor
    public Library() {
        this.books = new ArrayList<>();
    }

    // Method to add a book to the library
    public void addBook(Book book) {
        books.add(book);
    }

    // Method to search books based on different criteria
    public List<Book> searchBooksByTitle(String title) {
        List<Book> result = new ArrayList<>();
        for (Book book : books) {
            if (book.getTitle().equalsIgnoreCase(title)) {
                result.add(book);
            }
        }
        return result;
    }

    public List<Book> searchBooksByAuthor(String author) {
        List<Book> result = new ArrayList<>();
        for (Book book : books) {
            if (book.getAuthor().equalsIgnoreCase(author)) {
                result.add(book);
            }
        }
        return result;
    }

    public List<Book> searchBooksByISBN(String ISBN) {
        List<Book> result = new ArrayList<>();
        for (Book book : books) {
            if (book.getISBN().equalsIgnoreCase(ISBN)) {
                result.add(book);
            }
        }
        return result;
    }

    public List<Book> searchBooksByPublisher(String publisher) {
        List<Book> result = new ArrayList<>();
        for (Book book : books) {
            if (book.getPublisher().equalsIgnoreCase(publisher)) {
                result.add(book);
            }
        }
        return result;
    }

    public List<Book> searchBooksByYear(int year) {
        List<Book> result = new ArrayList<>();
        for (Book book : books) {
            if (book.getYear() == year) {
                result.add(book);
            }
        }
        return result;
    }
}
=======================================================

public class Main {
    public static void main(String[] args) {
        // Create the library and add some books
        Library library = new Library();
        library.addBook(new Book("Title1", "Author1", "ISBN111", "PublisherA", 2000));
        library.addBook(new Book("Title2", "Author2", "ISBN222", "PublisherB", 2010));
        library.addBook(new Book("Title3", "Author1", "ISBN333", "PublisherA", 2015));
        // Add more books as needed

        // Search and display books based on different criteria
        List<Book> booksByTitle = library.searchBooksByTitle("Title1");
        System.out.println("Books by Title:");
        displayBooks(booksByTitle);

        List<Book> booksByAuthor = library.searchBooksByAuthor("Author1");
        System.out.println("\nBooks by Author:");
        displayBooks(booksByAuthor);

        List<Book> booksByISBN = library.searchBooksByISBN("ISBN222");
        System.out.println("\nBooks by ISBN:");
        displayBooks(booksByISBN);

        List<Book> booksByPublisher = library.searchBooksByPublisher("PublisherA");
        System.out.println("\nBooks by Publisher:");
        displayBooks(booksByPublisher);

        List<Book> booksByYear = library.searchBooksByYear(2010);
        System.out.println("\nBooks by Year of Publishing:");
        displayBooks(booksByYear);
    }

    // Helper method to display the list of books
    public static void displayBooks(List<Book> books) {
        for (Book book : books) {
            System.out.println(book.getTitle() + " - " + book.getAuthor() +
                               " - " + book.getISBN() + " - " + book.getPublisher() +
                               " - " + book.getYear());
        }
    }
}
==============================================
