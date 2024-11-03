# lab5
1.
import java.util.regex.Pattern;
import java.util.regex.Matcher;

public class NumberFinder {

    public static void main(String[] args) {
        String text = "В этом тексте есть числа: 123, 456 и 789, а также 1.234, 56.789 и 0.987 - дробные." +
                "Есть еще отрицательные числа: -10, -2.5 и -345.678." +
                "И даже большие числа, например 1000000 и 1234567890.";

        // Регулярное выражение для поиска чисел, включающее целые и дробные
        String regex = "[-+]?\\d+(\\.\\d+)?";

        Pattern pattern = Pattern.compile(regex);
        Matcher matcher = pattern.matcher(text);

        System.out.println("Найденные числа:");
        while (matcher.find()) {
            System.out.println("Match found!"+matcher.group()); // Выводим найденное число
        }
    }
}

2.

import java.util.regex.Pattern;
import java.util.regex.Matcher;

public class checkWhether {

    public static void main(String[] args) {

        String password = "12345678";
        // Регулярное выражение, проверяющее, что пароль содержит
        // хотя бы одну заглавную букву, одну цифру и не менее 8 символов
        Pattern pattern = Pattern.compile("^(?=.*[A-Z])(?=.*\\d).{8,}$");
        Matcher matcher = pattern.matcher(password);
        if (matcher.matches()) {
            System.out.println("Valid password!");
        } else {
            System.out.println("Invalid password. Password must contain at least one uppercase letter, one digit and be at least 8 characters long.");

        }

    }
}

3.


import java.util.regex.Pattern;
import java.util.regex.Matcher;

public class FindCapitalAfterLowercase{

    public static void main(String[] args) {

        String text = "CaPS letTerS";
        Pattern pattern = Pattern.compile("[a-z][A-Z]");
        Matcher matcher = pattern.matcher(text);

        System.out.println("Найденные совпадения:");
        while (matcher.find()) {
            System.out.println("Совпадение найдено: " + matcher.group());
        }
    }

}

4.
import java.util.regex.Pattern;
import java.util.regex.Matcher;

public class IPValidator {
    public static void main(String[] args) {

        String text = "192.168.1.1 300.168.1.1 255.255.255.0";

        // Разделяем текст на отдельные IP-адреса по пробелам
        String[] ipAddresses = text.split("\\s+");

        String regex = "^((25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\\.){3}(25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)$";

        Pattern pattern = Pattern.compile(regex);

        System.out.println("Найденные IP-адреса:");
        for (String ipAddress : ipAddresses) { // Проверяем каждый IP-адрес
            Matcher matcher = pattern.matcher(ipAddress);
            if (matcher.matches()) {
                System.out.println("Найденные IP-адреса: " + ipAddress);
            }
        }
    }
}

5.

import java.util.regex.Pattern;
import java.util.regex.Matcher;

public class WordFinder {

    public static void main(String[] args) {

        String text = "The world is full of beauty, waiting to be discovered.";
        String letter = "w"; // Буква для поиска

        String[] words = text.split("\\s+"); // Разбиваем текст на слова

        System.out.println("Words starting with '" + letter + "':");

        for (String word : words) {
            String regex = "\\b" + letter + "\\w+\\b"; // Регулярное выражение
            Pattern pattern = Pattern.compile(regex);
            Matcher matcher = pattern.matcher(word);

            if (matcher.find()) {
                System.out.println(word);
            }
        }
    }
}
