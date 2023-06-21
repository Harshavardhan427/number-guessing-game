# number-guessing-game
package NewGame;
import java.util.*;

public class gaming {
	public static void main(String[] args) {
		Scanner sc = new Scanner(System.in);
		System.out.println("WELCOME TO NUMBER GUESSING GAME");
		int r = (int)(Math.random()*100)+1;
		int guess = 0, score = 0, choice=0;
		boolean playagain = true;
		System.out.println("Enter in how many choices you need to guess the number: ");
		choice = sc.nextInt();
		while(playagain) {
			int guesscount=0;
			boolean correctguess = false;
			while(guesscount < choice && !correctguess) {
				System.out.println("Guess #"+(guesscount+1)+":");
				System.out.println("enter your guess no:");
				guess =sc.nextInt();
				guesscount++;
				if(guess == r) {
					System.out.println("Congratulations! you have won the Game");
					System.out.println("the number guessed by me is :"+r);
					score++;
					correctguess = true;
				}else if(guess > r) {
					System.out.println("its high, try another");
				}else {
					System.out.println("Its low, try another");
				}
			}
			if(!correctguess) {
				System.out.println("sorry you have loose the game"+"\n"+"the no guessed by me is : "+r);
			}
			System.out.println("Do you want to continue the Game: (y/n)");
			String p = sc.next();
			if(p.equals("n")) {
				playagain = false;
			}
			else {
				System.out.println("Do you want to increase your no.of choices: (y/n)");
				String s = sc.next();
				if(s.equals("y")) {
					System.out.println("enter no. of choices to be increase : ");
					int a = sc.nextInt();
					choice = choice + a;
				}
			}
		}
		System.out.println("Thank you for participation !\n" + "your score is:  "+score);
	}
}
