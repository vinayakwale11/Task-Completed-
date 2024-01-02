import java.util.ArrayList;
import java.util.Collections;
import java.util.Scanner;

public class StudentGradeTracker {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Create an ArrayList to store students' grades
        ArrayList<Integer> grades = new ArrayList<>();

        // Get the number of students from the user
        System.out.print("Enter the number of students: ");
        int numberOfStudents = scanner.nextInt();

        // Input grades for each student
        for (int i = 1; i <= numberOfStudents; i++) {
            System.out.print("Enter grade for student " + i + ": ");
            int grade = scanner.nextInt();
            grades.add(grade);
        }

        // Calculate and display average, highest, and lowest grades
        if (!grades.isEmpty()) {
            double average = calculateAverage(grades);
            int highest = findHighest(grades);
            int lowest = findLowest(grades);

            System.out.println("\nAverage Grade: " + average);
            System.out.println("Highest Grade: " + highest);
            System.out.println("Lowest Grade: " + lowest);
        } else {
            System.out.println("No grades entered.");
        }

        scanner.close();
    }

    private static double calculateAverage(ArrayList<Integer> grades) {
        int sum = 0;
        for (int grade : grades) {
            sum += grade;
        }
        return (double) sum / grades.size();
    }

    private static int findHighest(ArrayList<Integer> grades) {
        return Collections.max(grades);
    }

    private static int findLowest(ArrayList<Integer> grades) {
        return Collections.min(grades);
    }
}
