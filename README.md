
package javaapplication87;

import java.util.Random;
import java.util.Scanner;

public class JavaApplication87 {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();

        System.out.println("Bem-vindo ao Jogo de Adivinhação!");
        System.out.print("Qual é o seu nome? ");
        String playerName = scanner.nextLine();
        System.out.println("Olá, " + playerName + "! Vamos começar.");

        int secretNumber = random.nextInt(10) + 1;
        int attempts = 0;
        boolean guessedCorrectly = false;

        while (!guessedCorrectly) {
            System.out.print("Tente adivinhar o número (entre 1 e 10): ");
            int guess = scanner.nextInt();
            attempts++;

            if (guess == secretNumber) {
                guessedCorrectly = true;
                System.out.println("Parabéns, " + playerName + "! Você acertou o número " + secretNumber + " em " + attempts + " tentativas.");
            } else {
                if (guess < secretNumber) {
                    System.out.println("Ops, " + playerName + ", errado o número é maior que " + guess + ".");
                } else {
                    System.out.println("Ops, " + playerName + ", errado o número é menor que " + guess + ".");
                }
                System.out.println("Tente novamente!");
            }
        }

        scanner.close();
    }
}
