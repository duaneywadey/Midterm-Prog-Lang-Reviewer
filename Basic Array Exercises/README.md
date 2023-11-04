# Basic Array Exercises

* Adding a new element inside an array from scratch. 

```java  
public class addNewNumInArray {

	public static int[] addNumberToArray(int[] array, int numberToAdd) {

		// Create a new array here with extra size
		int [] newArray = new int[array.length + 1];

		// Copy each item inside the array
		for(int i=0; i<array.length; i++) {
			newArray[i] = array[i];
		}

		// Set the value of last index to numberToAdd
		newArray[array.length] = numberToAdd;

		// Print new array
		return newArray;
	}
	
	public static void printArray(int[] array) {

		// Printing each element inside the array 
		for (int i=0; i<array.length; i++) {
			System.out.print(array[i] + " ");
		}
		System.out.println();
	}


	public static void main(String[] args) {

		// Create an array
		int[] array = {1,2,3,4,5};
        System.out.println("Old Array: ");
        printArray(array);
        
		// Num to be added
		int numberToAdd = 10;

		// Store the result in this array
		int[] resultArray = addNumberToArray(array, numberToAdd);
        System.out.println("New Array: ");
        printArray(resultArray);


	}
}

```

* Updating an element inside an array from scratch.  

```java 
public class updatingNumFromArray {

	public static void updateArrayElement(int[] array, int index, int newValue) {
		// Check if index is valid
		if (index >=0 && index < array.length) {
			array[index] = newValue;
		}
		else {
			System.out.println("Invalid index!");
		} 
	}

	public static void printArray(int[] array) {
	    
		// Printing each element inside the array 
		for (int i=0; i<array.length; i++) {
			System.out.print(array[i] + " ");
		}
		System.out.println();
	}
	public static void main(String[] args) {

		// Print the old array here
		int[] numbers = {1, 2, 3, 4, 5};
		System.out.println("Original Array: ");
		printArray(numbers);

		// Updating the array
		int indexToUpdate = 2;
		int newValue = 1000;
		updateArrayElement(numbers, indexToUpdate, newValue);

		// Print the new array here
		System.out.println("Updated array: ");
		printArray(numbers);
	}
}

```

* Removing an element inside an array from scratch.  

```java
public class ArrayElementRemovalExample {

    public static int[] removeArrayElement(int[] array, int index) {
        // Check if the index is valid
        if (index >= 0 && index < array.length) {
            // Create a new array with size one less than the original array
            int[] newArray = new int[array.length - 1];

            // Copy the elements from the original array to the new array
            for (int i = 0, j = 0; i < array.length; i++) {
                // Skip the element at the given index
                if (i == index) {
                    continue;
                }
                newArray[j] = array[i];
                j++;
            }
            return newArray;
        } 
        else {
            System.out.println("Invalid index!");
            return array;
        }
    }

	public static void printArray(int[] array) {
	    
		// Printing each element inside the array 
		for (int i=0; i<array.length; i++) {
			System.out.print(array[i] + " ");
		}
		System.out.println();
	}


    public static void main(String[] args) {
        // Create an array
        int[] numbers = {1, 2, 3, 4, 5};

        // Print the original array
        System.out.println("Original Array:");
        printArray(numbers);

        // Remove the element at index 2
        int indexToRemove = 2;
        numbers = removeArrayElement(numbers, indexToRemove);

        // Print the updated array
        System.out.println("Updated Array:");
        printArray(numbers);
    }
}

```