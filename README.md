# aidTech_task1

Create a Password Generator

Steps to create the project:

1. Define the length of the password: Decide on the length of the password that you want to generate.

2. Define the character set: Decide on the character set you want to use to generate the password. This can include uppercase and lowercase letters, numbers, and special characters.

3. Create a function to generate the password: Write a function that takes in the length of the password and the character set as parameters and generates a random password.

4. Use random number generation: Use Java's built-in random number generator to generate random characters from the chosen character set.

5. Convert the password to a string: Convert the generated password to a string and return it from the function.

6. Add user input: Add functionality to allow the user to input the desired length of the password and the character set to be used.

7. Test the program: Test the program by generating passwords of different lengths and using different character sets.

CODE:
import java.util.Random;
import java.util.Scanner;

public class PasswordGenerator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.print("Enter the length of the password: ");
        int length = scanner.nextInt();
        
        String characterSet = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789!@#$%^&*()-_=+[{]};:',<.>/?";
        
        String password = generatePassword(length, characterSet);
        System.out.println("Generated Password: " + password);
        
        scanner.close();
    }
    
    public static String generatePassword(int length, String characterSet) {
        Random random = new Random();
        StringBuilder password = new StringBuilder(length);
        
        for (int i = 0; i < length; i++) {
            int randomIndex = random.nextInt(characterSet.length());
            char randomChar = characterSet.charAt(randomIndex);
            password.append(randomChar);
        }
        
        return password.toString();
    }
}

