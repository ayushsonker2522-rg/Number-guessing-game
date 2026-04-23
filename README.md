# Number-guessing-game
A Java-based number guessing game with score tracking..



import java.util.Scanner;

public class Main {

    public static void startGame() {
        Scanner sc = new Scanner(System.in);
        int myNumber = (int)(Math.random() * 100) + 1;

        int attempts = 7;   // max tries
        int score = 100;   // starting score

        System.out.println("🎮 Welcome to Number Guessing Game!");
        System.out.println("You have " + attempts + " attempts.\n");

        while (attempts > 0) {
            System.out.print("Guess the number (1-100): ");
            int userNumber = sc.nextInt();

            if (userNumber == myNumber) {
                System.out.println("🎉 Correct! You guessed it!");
                System.out.println("🏆 Your Score: " + score);
                return;
            }
            else if (userNumber > myNumber) {
                System.out.println("📉 Too high!");
            }
            else {
                System.out.println("📈 Too low!");
            }

            attempts--;
            score -= 10;

            System.out.println("Attempts left: " + attempts + "\n");
        }

        System.out.println("❌ Game Over!");
        System.out.println("The correct number was: " + myNumber);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        while (true) {
            startGame();

            System.out.print("\nDo you want to play again? (yes/no): ");
            String choice = sc.next();

            if (!choice.equalsIgnoreCase("yes")) {
                System.out.println("👋 Thanks for playing!");
                break;
            }
        }
    }
}
