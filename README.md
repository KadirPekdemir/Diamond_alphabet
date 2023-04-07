# Diamond_alphabet
This program creates a diamond shape according to the entered letter.
import java.util.Scanner;

//Kadir PEKDEMİR
//This program creates a diamond shape according to the entered letter.

public class DiamondAlphabet {
	
	public static void main(String[] args) {
		//Create Scanner
		Scanner input = new Scanner(System.in);
		System.out.print("Enter a Letter: ");
		//Capitalizes
		String str = input.next();
		str = str.toUpperCase();
		char letter = str.charAt(0);
        //Separates invalid characters
		if (str.length() > 1 || ((str.charAt(0) < 65) || str.charAt(0) > 122)
				|| (str.charAt(0) < 97 && str.charAt(0) > 90)) {
			System.out.println("Invalid input!");
		//Call methods	
		} else
			printDiamond(constructDiamond(letter));

	}

	public static char[][] constructDiamond(char letter) {
         // Create array
		char[][] diamond = new char[((char) (letter) - 64) * 2 - 1][((char) (letter) - 64) * 2 - 1];
         //Forms the diamond shape
		for (int i = 0; i < diamond.length; i++) {
			for (int j = 0; j < diamond.length; j++) {

				if ((j == (diamond.length) / 2 - i) || (j == (diamond.length) / 2 + i)) {
					diamond[i][j] = (char) (65 + i);
				} else if ((i > (diamond.length) / 2) && ((j == (diamond.length / 2 + (diamond.length - 1 - i)))
						|| (j == (diamond.length / 2 - (diamond.length - 1 - i))))) {
					diamond[i][j] = (char) (65 + (diamond.length - 1 - i));
				} else
					diamond[i][j] = (char) (46);

			}

		}

		return diamond;

	}

	public static void printDiamond(char[][] diamond) {
		//Prints the array

		for (int i = 0; i < diamond.length; i++) {
			for (int j = 0; j < diamond.length; j++) {
				System.out.print(diamond[i][j]);
			}
			System.out.println(" ");
		}
	}


}
