1) OOPs problem
   
package oops;
public class main {
    public static void main(String[] args) {
        KidUsers kid = new KidUsers();
        kid.age = 10;
        kid.registerAccount();
        kid.age = 18;
        kid.registerAccount();
        kid.bookType = "Kids";
        kid.requestBook();
        kid.bookType = "Fiction";
        kid.requestBook();
        AdultUsers adult = new AdultUsers();
        adult.age = 5;
        adult.registerAccount();
        adult.age = 23;
        adult.registerAccount();
        adult.bookType = "Kids";
        adult.requestBook()
        adult.bookType = "Fiction";
        adult.requestBook();
    }
}

package oops;
public interface LibraryUser {
    void registerAccount();
    void requestBook();
}

package oops;
public class KidUsers implements LibraryUser {
    int age;
    String bookType;
    @Override
    public void registerAccount() {
        if (age < 12) {
            System.out.println("You have successfully registered under a Kids Account");
        } else {
            System.out.println("Sorry, Age must be less than 12 to register as a kid");
        }
    }
    @Override
    public void requestBook() {
        if (bookType.equalsIgnoreCase("Kids")) {
            System.out.println("Book Issued successfully, please return the book within 10 days");
        } else {
            System.out.println("Oops, you are allowed to take only kids books");
        }
    }
}

package oops;
public class AdultUsers implements LibraryUser {
    int age;
    String bookType;
    @Override
    public void registerAccount() {
        if (age > 12) {
            System.out.println("You have successfully registered under an Adult Account");
        } else {
            System.out.println("Sorry, Age must be greater than 12 to register as an adult");
        }
    }
    @Override
    public void requestBook() {
        if (bookType.equalsIgnoreCase("Fiction")) {
            System.out.println("Book Issued successfully, please return the book within 7 days");
        } else {
            System.out.println("Oops, you are allowed to take only adult Fiction books");
        }
    }
}

OUTPUT:
You have successfully registered under a Kids Account
Sorry, Age must be less than 12 to register as a kid
Book Issued successfully, please return the book within 10 days
Oops, you are allowed to take only kids books
Sorry, Age must be greater than 12 to register as an adult
You have successfully registered under an Adult Account
Oops, you are allowed to take only adult Fiction books
Book Issued successfully, please return the book within 7 days




