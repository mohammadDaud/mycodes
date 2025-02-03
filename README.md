package pro;

import java.util.Arrays;

public class ArrengingNumbers {

	/*
	 * Question : write a program in java if you take any four digit number
	 * (let'ssay 3281) and arrange its digits in descrnding order(8321) and
	 * asascending order(1238) and then subtract the smaller number from the large
	 * number
	 */
	
	
	public static void main(String[] args) {
		int number = 3281;

		// Convert the number to an array of digits
		int[] digits = toDigitsArray(number);

		// Sort the array in ascending and descending order
		int[] ascending = sortArray(digits, true);
		int[] descending = sortArray(digits, false);

		// Convert the sorted arrays back to numbers
		int ascendingNumber = toNumber(ascending);
		int descendingNumber = toNumber(descending);

		// Subtract the smaller number from the larger number
		int result = descendingNumber - ascendingNumber;

		System.out.println("Result: " + result);
	}

	// Helper function to convert a number to an array of digits
	private static int[] toDigitsArray(int number) {
		int[] digits = new int[4];
		for (int i = 3; i >= 0; i--) {
			digits[i] = number % 10;
			number /= 10;
		}
		return digits;
	}

	// Helper function to sort the array in ascending or descending order
	private static int[] sortArray(int[] array, boolean ascending) {
		int[] sorted = array.clone();
		Arrays.sort(sorted);
		return ascending ? sorted : reverseArray(sorted);
	}

	// Helper function to reverse an array
	private static int[] reverseArray(int[] array) {
		int length = array.length;
		int[] reversed = new int[length];
		for (int i = 0; i < length; i++) {
			reversed[i] = array[length - 1 - i];
		}
		return reversed;
	}

	// Helper function to convert an array of digits to a number
	private static int toNumber(int[] digits) {
		int number = 0;
		for (int digit : digits) {
			number = number * 10 + digit;
		}
		return number;
	}

}






public class MissingElement {
    public static void main(String[] args) {
        int[] arr = new int[]{1, 3, 8, 4, 9, 10};
        int n = arr.length;

        for (int i = 1; i <= n; i++) {
            boolean found = false;

            for (int j = 0; j < n; j++) {
                if (arr[j] == i) {
                    found = true;
                    break;
                }
            }

            if (!found) {
                System.out.println("Missing Element: " + i);
            }
        }
    }
}

