# java-one-dimensional-array

7-1
package number;

public class analyzenumber {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		java.util.Scanner input = new java.util.Scanner(System.in);
		System.out.print("Enter the number of items: ");
		int n= input.nextInt();
		double [] numbers = new double[n];
		double sum = 0;
		
		System.out.print("Enter the numbers: ");
		for(int i = 0; i < n; i++)
		{
			numbers[i] = input.nextDouble();
			sum += numbers[i];
		}
		
		double average = sum / n;
		
		int count = 0;
		for(int i = 0; i < n; i++)
		{
			if(numbers[i] > average)
			{
				count++;
			}
		}
		System.out.println("Average is " + average);
		System.out.println("Number of elements above the average is " + count);
	}

}

7-2
package number;

public class analyzenumber {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		int[] deck = new int[52];
		String[] suits = {"Spades", "Hearts", "Dimonds", "Clubs"};
		String[] ranks = {"ACE", "2", "3", "4", "5", "6", "7", "8", "9", "10", "JACK", "QUEEN", "KING"};
		
		for (int i = 0; i < deck.length; i++)
		{
			deck[i] = i;
		}
		
		for(int i = 0; i < deck.length; i++)
		{
			int index = (int)(Math.random() * deck.length);
			int temp = deck[i];
			deck[i] = deck[index];
			deck[index] = temp;
		}
		
		for(int i = 0; i < 4; i++)
		{
			String suit = suits[deck[i] / 13];
			String rank = ranks[deck[i] % 13];
			System.out.println("Card number " + deck[i] + ": " + rank + " of " + suit);
		}
	}

}

7-3
package number;

public class analyzenumber {
	
	public static void swap(int n1, int n2)
	{
		int temp = n1;
		n1 = n2;
		n2 = temp;
	}
	
	public static void swapfirsttwoinarray(int[] array)
	{
		int temp = array[0];
		array[0] = array[1];
		array[1] = temp;
	}

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		int[] a = {1, 2};
		System.out.println("before invoking swap");
		System.out.println("array is {" + a[0] + ", " + a[1] + "}");
		swap(a[0], a[1]);
		System.out.println("after invoking swap");
		System.out.println("array is {" + a[0] + ", " + a[1] + "}");
		
		System.out.println("before invoking swapfirsttwoinarray");
		System.out.println("array is {" + a[0] + ", " + a[1] + "}");
		swapfirsttwoinarray(a);
		System.out.println("after invoking swapfirsttwoinarray");
		System.out.println("array is {" + a[0] + ", " + a[1] + "}");
		
	}

}

7-4
package number;

public class analyzenumber {
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		char[] chars = createarray();
		
		System.out.println("the lowercase letters are:");
		displayarray(chars);
		
		int[] counts = countLetters(chars);
		
		System.out.println();
		System.out.println("the occurrences of each letter are:");
		displayCounts(counts);
	}
    public static char[] createarray(){
	  char[] chars = new char[100];
	  
	  for(int i = 0;i < chars.length; i++)
	  {
		  chars[i] = RandomCharacter.getRandomLowerCaseLetter();
	  }
	  return chars;
  }
     public static void displayarray(char[] chars){
	  for(int i = 0; i < chars.length; i++)
	  {
		  if((i + 1) % 20 == 0)
		  {
			  System.out.println(chars[i]);
		  }
		  else
			  System.out.println(chars[i] + " ");
	  }
  }
    public static int[] countLetters(char[] chars){
	int[] counts = new int[26];
	for(int i = 0;i < chars.length; i++)
	{
		counts[chars[i] - 'a']++;
	}
	return counts;
}

    public static void displayCounts(int[] counts){
	for (int i = 0; i < counts.length; i++)
	{
		if((i + 1) % 10 == 0)
			System.out.println(counts[i] + " " + (char)(i + 'a'));
		else
			System.out.print(counts[i] + " " +  (char)(i + 'a') + "");
	}
}
}

7-5
package number;

public class analyzenumber {
	public static void main(String[] args) {
		// TODO Auto-generated method stub
		printMax(34, 3, 3, 2, 56.5);
		printMax(new double[]{1,2,3});
	}
	
	public static void printMax(double... numbers){
		if(numbers.length == 0){
			System.out.println("nop argument passed");
			return;
		}
		
		double result = numbers[0];
		
		for(int i = 1;i < numbers.length; i++)
		{
			if(numbers[i] > result)
				result = numbers[i];
		}
		System.out.println("the max value is " + result);
	}
}

7-6
public class helloworld {

	public static int linearsearch(int[] list, int key) {
		for (int i = 0; i < list.length; i++)
		{
			if (key == list[i])
			{
				return i;
			}
		}
		return -1;
	}
}

7-7
public class helloworld {
	public static int binarySearch(int[] list, int key) {
		int low = 0;
		int high = list.length - 1;
		
		while (high >= low)
		{
			int mid = (low + high) / 2;
			if(key < list[mid])
			{
				high = mid - 1;
			}
			else if (key == list[mid])
			{
				return mid;
			}
			else 
				low = mid + 1;
		}
		return -low - 1;
	}
}

7-8
public class helloworld {

	public static void selectionsort(double[] list) {
		for (int i = 0; i <  list.length; i++)
		{
			double currentmin = list[i];
			int currentminindex = i;
			
			for (int j = i + 1; j < list.length; j++)
			{
				if(currentmin > list[j])
				{
					currentmin = list[j];
					currentminindex = j;
				}
			}
			
			if (currentminindex != i)
			{
				list[currentminindex] = list[i];
				list[i] = currentmin;
			}
		}
	}
}

7-9
public class helloworld {

	public static void main(String[] args) {
		if (args.length != 3)
		{
			System.out.println("usage:java calculator operandl operator operand2");
			System.exit(0);
		}
		
		int result = 0;
		
		switch (args[1].charAt(0))
		{
		case '+': result = Integer.parseInt(args[0]) +
				           Integer.parseInt(args[2]);
		          break;

		case '-': result = Integer.parseInt(args[0]) -
		                   Integer.parseInt(args[2]);
                  break;

		case '.': result = Integer.parseInt(args[0]) *
		                   Integer.parseInt(args[2]);
                  break; 
                  
		case '/': result = Integer.parseInt(args[0]) /
		                   Integer.parseInt(args[2]);
                  break;                  
		}
		
		System.out.println(args[0] + ' ' + args[1] + ' ' + args[2]+
				" = " + result);
	}
}
