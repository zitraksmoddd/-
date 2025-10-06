import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        String[] books = {"Tokyo ghoul", "Бедный папа богатый папа"};
        boolean[] free = {true, true, false};
        System.out.print("введите номер книги: ");
        String search = sc.nextLine().toLowerCase();

        for (int i = 0; i < books.length; i++) {
            if (books[i].toLowerCase().contains(search)) {
                System.out.println((i + 1) + ". " + books[i] + (free[i] ? " (доступна)" : " (занята)"));
            }
        }

        System.out.print(" книга для брони: ");
        int n = sc.nextInt() - 1;

        if (n >= 0 && n < books.length && free[n]) {
            free[n] = false;
            System.out.println("Книга забронирована!");
        } else {
            System.out.println("Нельзя забронировать.");
        }
    }
}
