import java.util.Scanner;
import java.util.Random;
import java.util.Arrays;

public class RandomNum {

    // User-defined method to generate a random array of integers
    public static int[] generateRandomArray(int size, int max) {
        Random random = new Random();
        int[] numbers = new int[size];
        for (int i = 0; i < size; i++) {
            numbers[i] = random.nextInt(max) + 1; // Generate random numbers between 1 and max
        }
        return numbers;
    }

    // User-defined method to display the array based on user choice
    public static void displayArray(int[] numbers, int choice) {
        Arrays.sort(numbers); // Sort the array in ascending order

        switch (choice) {
            case 1: // Ascending order
                System.out.println("Generated random numbers (ascending order):");
                for (int num : numbers) {
                    System.out.print(num + " ");
                }
                break;
            case 2: // Descending order
                System.out.println("Generated random numbers (descending order):");
                for (int i = numbers.length - 1; i >= 0; i--) {
                    System.out.print(numbers[i] + " ");
                }
                break;
            default:
                System.out.println("Invalid choice.");
        }
        System.out.println(); // Newline for better formatting
    }

    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);

        System.out.print("Enter the size of the array: ");
        int size = input.nextInt();

        System.out.print("Enter the maximum value for random numbers: ");
        int max = input.nextInt();

        // Generate the random array using the user-defined method
        int[] randomNumbers = generateRandomArray(size, max);

        System.out.println("How do you want to display the array?");
        System.out.println("1. Ascending order");
        System.out.println("2. Descending order");
        System.out.print("Enter your choice: ");
        int choice = input.nextInt();

        // Display the array based on user choice using the switch statement
        displayArray(randomNumbers, choice);

        input.close();
    }
}
