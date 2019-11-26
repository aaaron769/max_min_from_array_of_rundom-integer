package algorithm1;

import java.util.ArrayList;
import java.util.Arrays;
import java.util.Random;

/*Collect the data on “time required” to solve the problem for different problem sizes.
For example, 1000, 2000, 3000, 4000, and so on.
Your “input data” must be generated using random function.
*/
/*
 * Find the largest distance between any two even integers in an integer array*/
public class Hmw1_algorithm1 {
	/*
	 * Create a new array consisting of even numbers only. Then use nested loops to
	 * solve the problem using the newly created array of even numbers only.
	 */ public int getLargestDistance(int[] array) {

		int sizeOfNewArray = 0;// index of the new Array
		// to get the size of array of even numbers
		for (int i = 0; i < array.length; i++) {
			if (array[i] % 2 == 0 && array[i] != 0) {
				sizeOfNewArray++;
			}
		}
		int newArray[] = new int[sizeOfNewArray];// even numbers will store here
		int indexNewArray = 0;
		// array of even numbers will fill here
		for (int i = 0; i < array.length; i++) {
			if (array[i] % 2 == 0 && array[i] != 0) {
				newArray[indexNewArray] = array[i];
				indexNewArray++;
			}
		}

		 System.out.println(Arrays.toString(newArray));
		// find the largest distance using nested loo
		
		int min =newArray[0];
		int max = newArray[0];
	
		int maxDis = 0;
		//int max = Integer.MAX_VALUE;
		for (int i = 0; i < newArray.length-1; i++) { 
		
			for (int k = i+1; k < newArray.length ; k++) {
				if(newArray[k]<=min) {
					min = newArray[k];
				}
				if(newArray[k]>=max) {
					max = newArray[k];
				}
				int dist= Math.abs(newArray[i]-newArray[k]);
				if(dist>=maxDis) {
					maxDis = dist;// maxDistance 
				}
				
		    }
		}
		System.out.println("min is  "+min +"  max is  "+ max+ " the maxDist "+ maxDis);
	


		return 0;// toDo..............
	}

	public static void main(String args[]) {
		Hmw1_algorithm1 hmw1 = new Hmw1_algorithm1();
		Random r = new Random();
		int randomSize = r.nextInt(4);
		int arrSize;
		if (randomSize == 0) {
			arrSize = 1000;
		} else {
			arrSize = 1000 * randomSize;
		}

		int array[] = new int[arrSize];
		for (int i = 0; i < arrSize; i++) {
			int randomInt = r.nextInt(1000) + 1;
			array[i] = randomInt;

		}
		int result = hmw1.getLargestDistance(array);
		// System.out.println("starting"+" "+result);

	}

}
