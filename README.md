# Student-result-analyzer-
import java.util.Scanner;

public class StudentResultAnalyzer {

    // Method to calculate total marks
    static int calculateTotal(int[] marks) {
        int total = 0;

        for (int mark : marks) {
            total += mark;
        }

        return total;
    }

    // Method to calculate grade
    static String calculateGrade(double average) {
        if (average >= 90)
            return "A+";
        else if (average >= 80)
            return "A";
        else if (average >= 70)
            return "B";
        else if (average >= 60)
            return "C";
        else if (average >= 50)
            return "D";
        else
            return "F";
    }

    // Method to find highest mark
    static int findHighest(int[] marks) {
        int highest = marks[0];

        for (int mark : marks) {
            if (mark > highest)
                highest = mark;
        }

        return highest;
    }

    // Method to find lowest mark
    static int findLowest(int[] marks) {
        int lowest = marks[0];

        for (int mark : marks) {
            if (mark < lowest)
                lowest = mark;
        }

        return lowest;
    }

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        String[] subjects = {
            "Mathematics",
            "Java",
            "Data Structures",
            "Physics",
            "English"
        };

        System.out.print("Enter Student Name: ");
        String name = sc.nextLine();

        int[] marks = new int[subjects.length];

        System.out.println("\nEnter marks out of 100:");

        for (int i = 0; i < subjects.length; i++) {
            System.out.print(subjects[i] + ": ");
            marks[i] = sc.nextInt();
        }

        int total = calculateTotal(marks);
        double average = total / (double) subjects.length;

        String grade = calculateGrade(average);

        int highest = findHighest(marks);
        int lowest = findLowest(marks);

        System.out.println("\n==================================");
        System.out.println("        STUDENT RESULT");
        System.out.println("==================================");

        System.out.println("Student Name : " + name);

        System.out.println("\nSubject-wise Marks:");

        for (int i = 0; i < subjects.length; i++) {
            System.out.println(subjects[i] + " : " + marks[i]);
        }

        System.out.println("\nTotal Marks  : " + total + "/500");
        System.out.printf("Average      : %.2f%n", average);
        System.out.println("Grade        : " + grade);
        System.out.println("Highest Mark : " + highest);
        System.out.println("Lowest Mark  : " + lowest);

        if (grade.equals("F"))
            System.out.println("Result       : FAIL");
        else
            System.out.println("Result       : PASS");

        System.out.println("==================================");

        sc.close();
    }
}
