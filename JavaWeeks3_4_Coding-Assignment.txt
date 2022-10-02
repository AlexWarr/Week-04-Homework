import java.util.Scanner;

public class JavaWeeks3_4_Coding_Assignment {
	

	public static void main(String[] args) {
		Scanner kb = new Scanner(System.in);
		//1.	Create an array of int called ages that contains the following values: 3, 9, 23, 64, 2, 8, 28, 93.
				int ages[] = new int[] {3,9,23,64,2,8,28,93};
				System.out.println("This is an array of ages: ");
				printIArray(ages);
				
		//a.	Programmatically subtract the value of the first element in the array from the value in the last element of the array (i.e. do not use ages[7] in your code). Print the result to the console. 
				difference1stLast(ages);
				//int difference = ages[ages.length-1] - ages[0];
				//return difference;
				
				
		//b.	Add a new age to your array and repeat the step above to ensure it is dynamic (works for arrays of different lengths).
				System.out.println("Please add a number to the array: ");
				int uip = Integer.parseInt(kb.nextLine());
				int[] na = addInt2Array(ages,uip);
				//int[] newAges = new int[ages.length + 1];
				//for (int i = 0; i < ages.length; i++) {
				//	newAges[i] = ages[i];
				//}
				//newAges[newAges.length-1] = 33;

				difference1stLast(na);

		//c.	Use a loop to iterate through the array and calculate the average age. Print the result to the console.
				findAvInArr(na);
				//int temp = 0;
				//for (int age : newAges) {
				//	temp += age;
				//}
				//temp /= newAges.length;
				//System.out.println(temp);

	//2.	Create an array of String called names that contains the following values: “Sam”, “Tommy”, “Tim”, “Sally”, “Buck”, “Bob”.
				String[] names = new String[] { "Sam", "Tommy", "Tim", "Sally", "Buck", "Bob" };
				System.out.println("This is an array of names: ");
				printSArray(names);
				
		//a.	Use a loop to iterate through the array and calculate the average number of letters per name. Print the result to the console.
				System.out.println("The average name length in this array is: " + findAvLen(names));
				
		//b.	Use a loop to iterate through the array again and concatenate all the names together, separated by spaces, and print the result to the console.
				System.out.println("This is the names array as a string without punctuation: ");
				System.out.println(list2String(names));
				
	//3.	How do you access the last element of any array?
				// *anyArray[anyArray.length - 1];*
				System.out.println("the last element of the array of ages is: " + na[na.length-1]);
				System.out.println("the last element of the array of names is: " + names[names.length-1]);
				
	//4.	How do you access the first element of any array?
				// *anyArray[0];*
				System.out.println("the first element of the array of ages is: " + na[0]);
				System.out.println("the first element of the array of names is: " + names[0]);
				
	//5.	Create a new array of int called nameLengths. Write a loop to iterate over the previously created names array and add the length of each name to the nameLengths array.
				int[] nameLengths = nameLenArr(names);
				System.out.println("This is an array of name lengths in names: ");
				printIArray(nameLengths);
				
	//6.	Write a loop to iterate over the nameLengths array and calculate the sum of all the elements in the array. Print the result to the console.
				System.out.println("The total of the lengths of all names in the array is: " + totalChars(nameLengths));
				
	//7.	Write a method that takes a String, word, and an int, n, as arguments and returns the word concatenated to itself n number of times. (i.e. if I pass in “Hello” and 3, I expect the method to return “HelloHelloHello”).
				System.out.println("Please enter a word:");
				String word = kb.nextLine();
				System.out.println("your word is " + word);
				System.out.println("Please enter the amount of times you'd like to repeat the word: ");
				int n = Integer.parseInt(kb.nextLine());
				repeatString(word,n);
				
	//8.	Write a method that takes two Strings, firstName and lastName, and returns a full name (the full name should be the first and the last name as a String separated by a space).
				System.out.println("First Name: ");
				String firstName = kb.nextLine();
				System.out.println("Last Name: ");
				String lastName = kb.nextLine();
				System.out.println(makeFull(firstName,lastName));
				
	//9.	Write a method that takes an array of int and returns true if the sum of all the ints in the array is greater than 100.
				System.out.println("The sum of all ages in the array is over 100: " + isOverCent(na));
				
	//10.	Write a method that takes an array of double and returns the average of all the elements in the array.
				double prices[] = new double[] {3.99,49.0,23.55,6.4,12.8,89.7,28.11,9.3};
				System.out.println("This is an array of prices: ");
				printDArray(prices);
				System.out.println("the average price in this array is: " + findAvDoArr(prices));
				
	//11.	Write a method that takes two arrays of double and returns true if the average of the elements in the first array is greater than the average of the elements in the second array.
				double testArr[] = conv2Dub(na);
				System.out.println("This is another array of prices: ");
				printDArray(testArr);
				System.out.println("true or false: The average of the first array of prices is greater than the average of the other array: ");
				System.out.println(firstIsGreater(prices,testArr));
				
	//12.	Write a method called willBuyDrink that takes a boolean isHotOutside, and a double moneyInPocket, and returns true if it is hot outside and if moneyInPocket is greater than 10.50.
				System.out.println("This method will help to determine whether I will buy a drink");
				System.out.println("true or false: It is hot outside");
				boolean isHotOutside = Boolean.parseBoolean(kb.nextLine());
				System.out.println("How much money do I have?");
				double moneyInPocket = Double.parseDouble(kb.nextLine());
				System.out.println("I will buy a drink: " + willBuyDrink(isHotOutside, moneyInPocket));
				
	//13.	Create a method of your own that solves a problem. In comments, write what the method does and why you created it.
				System.out.println("This method is designed to determine how many cartons a farmer will need for his eggs");
				//this methods will print the response and return nothing 
				System.out.println("How many eggs did your hens lay today? ");
				int eggs = Integer.parseInt(kb.nextLine());
				System.out.println("How many spaces were left in your final carton yesterday? ");
				eggs = eggs - Integer.parseInt(kb.nextLine());
				cartonAmount(eggs);

	}
	//PRIMARY METHODS
	public static int difference1stLast(int[] a) {
		//See question 1.a.
		int difference = a[a.length-1] - a[0];
		System.out.println("The difference in " + a[0] + " and " + a[a.length-1] + " is: " + difference);
		return difference;
	}
	public static int[] addInt2Array(int[] b, int c) {
		//See question 1.b.
		int[] newAges = new int[b.length + 1];
		for (int i = 0; i < b.length; i++) {
			newAges[i] = b[i];
		}
		newAges[newAges.length-1] = c;
		return newAges;
	}
	public static int findAvInArr(int[] d) {
		//See question 1.c.
		int avg = 0;
		for (int num : d) {
			avg += num;
		}
		avg /= d.length;
		System.out.println("The average age in this array is: " + avg);
		return avg;
	}
	public static int findAvLen(String[] e) {
		//See question  2.a.
		int avg = 0;
		for (String name : e) {
			avg += name.length();
			//System.out.println(name);
		}
		//System.out.println(avg);
		avg = avg/e.length;
		//System.out.println(avg);
		return avg;
	}
	public static String list2String(String[] f) {
		//See question 2.b.
		StringBuilder namen = new StringBuilder();
		for (String name : f) {
			namen.append(name);
			namen.append(" ");
		}
		String newStr = namen.toString();
		return newStr;
	}
	public static int[] nameLenArr(String[] g) {
		//See question 5
		int[] namLen = new int[g.length];
		for (int i = 0; i < g.length; i++) {
			namLen[i] = g[i].length();
		}
		return namLen;
	}
	
	public static int totalChars(int[] h) {
		//See question 6
		int total = 0;
		for (int num:h) {
			total+=num;
		}
		return total;
	}
	public static String repeatString(String k, int l) {
		//See question 7
		StringBuilder fin = new StringBuilder();
		for (int i = 0; i < l; i++) {
			fin.append(k);
		}
		
		return fin.toString();
	}
	public static String makeFull(String m, String n) {
		//See question 8
		String fullName = m + " " + n;
		return fullName;
	}
	public static boolean isOverCent(int[] o) {
		//See question 9
		int temp = 0;
		for (int num : o) {
			temp+= num;
		}
		if (temp > 100)
			return true;
		else
			return false;
	}
	public static double findAvDoArr(double[] p) {
		//See question 10
		double avg = 0;
		for (double num : p) {
			avg += num;
		}
		avg /= p.length;
		return avg;
	}
	public static boolean firstIsGreater(double[] q, double[] r) {
		//See question 11
		if (findAvDoArr(q) > findAvDoArr(r)) return true;
		else return false;
	}
	public static boolean willBuyDrink(boolean s, double t) {
		//See question 12
		if (s == true && t >= 10.50) return true;
		else return false;
	}
	public static void cartonAmount(int u) {
		//See question 13
		int amt = u/12;
		int rem = u%12;
		if (rem > 0) {
			amt++;
			rem = 12-rem;
			System.out.println("You will need " + amt + " egg cartons.");
			System.out.println("You will have " + rem + " empty spaces in your final container for tommorrow's eggs");
		}
		else {
			System.out.println("You will need " + amt + " egg cartons.");
		}
	}
	
	//MISCELLENEOUS METHODS
	public static void printDArray(double[] w) {
		StringBuilder tArr = new StringBuilder();
		tArr.append("[ ");
		for (int i = 0; i < w.length - 1; i++) {
			tArr.append(w[i]);
			tArr.append(", ");
		}
		tArr.append(w[w.length - 1] + " ]");
		System.out.println(tArr);
	}
	public static double[] conv2Dub(int[] x) {
		double newR[] = new double[x.length];
		for (int j = 0; j < x.length; j++) {
			newR[j] = x[j];
		}
		return newR;
	}
	public static void printSArray(String[] y) {
		StringBuilder tArr = new StringBuilder();
		tArr.append("[ ");
		for (int i = 0; i < y.length - 1; i++) {
			tArr.append(y[i]);
			tArr.append(", ");
		}
		tArr.append(y[y.length - 1] + " ]");
		System.out.println(tArr);

	}
	public static void printIArray(int[] z) {
		StringBuilder tArr = new StringBuilder();
		tArr.append("[ ");
		for (int i = 0; i < z.length - 1; i++) {
			tArr.append(z[i]);
			tArr.append(", ");
		}
		tArr.append(z[z.length - 1] + " ]");
		System.out.println(tArr);
	}
	

}
