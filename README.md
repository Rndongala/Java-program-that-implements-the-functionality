# Java-program-that-implements-the-functionality
import java.util.Scanner;

public class QuizProgram {

    public static void main(String[] args) {
        // Scanner object for user input
        Scanner Scanner = new Scanner(System.in);

        // Array of questions
        String[] questions = {
            "What is the capital city of United State?",
            "What is the name of KC Chiefs Staduim?",
            "What animal is consider as the king of the jungle?",
            "Who is the president of the United State?",
            "Who is CEO of TESLA?"
        };

        // Array of answer options
        String[][] options = {
            {"A) Washington DC", "B) Madrid", "C) Paris", "D) Rome"},
            {"A) Children mercy park", "B) Wembley", "C) Arrow head", "D) Park of prince"},
            {"A) Elephant", "B) Tiger", "C) Giraffe", "D) Lion"},
            {"A) Emmanuel Macron", "B) Donald Trump", "C) Joe Biden", "D) Vladmir Putin"},
            {"A) Elon Musk", "B) Bill Gates", "C) Warren Buffet", "D) Jeff Bezos"}
        };

        // Array of correct answers
        char[] answers = {'A', 'C', 'D', 'C', 'A'};

        // Variable to keep track of the number of correct responses
        int correctCount = 0;

        // Loop through each question
        for (int i = 0; i < questions.length; i++) {
            // Display the question
            System.out.println((i + 1) + ". " + questions[i]);
            
            // Display the options
            for (String option : options[i]) {
                System.out.println(option);
            }

            // Prompt user for their answer
            System.out.print("Enter your answer (A, B, C, or D): ");
            char userAnswer = Scanner.next().charAt(0);

            // Input validation
            while (userAnswer != 'A' && userAnswer != 'B' && userAnswer != 'C' && userAnswer != 'D') {
                System.out.print("Invalid input. Please enter A, B, C, or D: ");
                userAnswer = Scanner.next().charAt(0);
            }

            // Compare the user's answer to the correct answer
            if (userAnswer == answers[i]) {
                correctCount++;
            }

            System.out.println();
        }

        // Compute the final score as a percentage
        double score = ((double) correctCount / questions.length) * 100;

        // Display the final score
        System.out.printf("Your final score is: %.2f%%\n", score);
    }
}
