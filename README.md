# Sorting_6_Numbers 


## Introduction 
This is the program were we are going to sort six numbers in ascending numbers using an array.

## Project Outline
```java
// Call the sorting algorithm
// generate a set of random numbers to sort
// sort the array of numbers
// populate the array
// Test the array to see if there are duplicates.
```


##  References & Literature
*   Liang, Y. (2014). *Introduction to Java programming: Comprehensive version* (Tenth ed.). 

## Source Code
```java
public class Sorting_6_Numbers {
	public static void main(String[] args) {
		System.out.print("Hello Team, "); 
		System.out.println("This is a sorting algorithm using arrays.");
		
		// call the sorting algorithm
		SortAlgorithm();
		}
	public static void SortAlgorithm() {

		// generate a set of random numbers to sort
		int listSize = 6;
		int[] numberArray = new int[listSize];
		numberArray = buildRandomArray(listSize);
		System.out.print("Our random array is: ( ");
		for (int i = 0; i < listSize; i++ ){
			System.out.print(numberArray[i] + " ");
		}
		System.out.println(").");
		
		
		// sort our array of numbers
		numberArray = sortOurArray(numberArray, listSize);
		System.out.print("Our sorted array is: ( ");
		for (int i = 0; i < listSize; i++ ){
			System.out.print(numberArray[i] + " ");
		}
		System.out.println(").");
		
	}
	public static int[] buildRandomArray(int listSize) {
		int[] numberArray = new int[listSize];
		// populate the array
		numberArray = populateRandomArray(numberArray, listSize);
		
		// Test the array to see if there are duplicates.
		
		return numberArray;
	}
	public static int[] populateRandomArray(int[] numberArray, int listSize) {
		
		int randomRange = listSize * 1000;
		for (int i = 0; i < listSize; i++ ){
			numberArray[i] = (int)(Math.random()*randomRange);
		}
		return numberArray;
	}
	
	public static int[] sortOurArray(int[] numberArray, int listSize) {
		
		int holder_1;
		int holder_2;
		for (int passCounter = 1; passCounter <= listSize; passCounter++ ){
			
			for (int i = 0; i < listSize-1; i++ ){
				
				holder_1 = numberArray[i];
				holder_2 = numberArray[i+1];
				
				if(holder_2 < holder_1){
					numberArray[i] = holder_2;
					numberArray[i+1] = holder_1;
					/* Remove our printing block
					System.out.print("We had a switch, the new array is: /n( ");
					
					for(int j = 0; j < listSize; j++){
						
						if (j == i){
							System.out.print(" " + numberArray[j] + " ");
						}else if (j == (i+1)){
							System.out.print(" " + numberArray[j] + " ");
						}else{
							System.out.print(numberArray[j] + "  ");
						}
					}
					System.out.println(")");
					*/
				}
				
			}
		}
		return numberArray;
	}
}
    
  }
}
```

## Console Output
```
Hello Team, This is a sorting algorithm using arrays.
Our random array is: ( 4312 1979 5084 5022 4570 5832 ).
Our sorted array is: ( 1979 4312 4570 5022 5084 5832 ).

```

## Command Prompt Output
```
E:\>Dir
 Volume in drive E is PRASUN
 Volume Serial Number is B0CF-9DF4

 Directory of E:\

10/09/2015  10:22 AM    <DIR>          .metadata
10/09/2015  10:22 AM    <DIR>          Prasun
10/26/2015  10:05 AM        12,563,873 introduction-to-java-programming-comprehe
nsive-version-10th-edition.zip
10/26/2015  10:13 AM    <DIR>          Fun_With_Functions
10/26/2015  10:42 AM             2,706 Comment_Line_md.txt
11/02/2015  10:30 AM    <DIR>          Listing_Project
11/03/2015  10:07 PM             3,394 Command.txt
02/11/2015  11:05 PM    <DIR>          workspace
11/04/2015  04:27 PM             9,982 README.md
11/19/2015  10:38 AM    <DIR>          Addition_array
11/20/2015  04:16 PM    <DIR>          Sorting_6_Numbers

               4 File(s)     12,579,955 bytes
               6 Dir(s)  15,405,072,384 bytes free

E:\>cd Sorting_6_Numbers

E:\Sorting_6_Numbers>echo # HW_10_Sorting_6_Numbers >> README.md

E:\Sorting_6_Numbers>git init
Initialized empty Git repository in E:/Sorting_6_Numbers/.git/

E:\Sorting_6_Numbers>git add README.md

E:\Sorting_6_Numbers>git config user.name "Prasun Thapa"

E:\Sorting_6_Numbers>git config user.email thapap@student.swosu.edu

E:\Sorting_6_Numbers>git commit -m "First commit"
[master (root-commit) 6f92b53] First commit
 1 file changed, 1 insertion(+)
 create mode 100644 README.md

E:\Sorting_6_Numbers>git remote add origin https://github.com/prasunth
apa10/ HW_10_Sorting_6_Numbers.git

E:\Sorting_6_Numbers>git push -u origin master
Username for 'https://github.com': prasunthapa10
Password for 'https://prasunthapa10@github.com':
Counting objects: 3, done.
Writing objects: 100% (3/3), 238 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/prasunthapa10/ HW_10_Sorting_6_Numbers.git
 * [new branch]      master -> master
Branch master set up to track remote branch master from origin.

E:\Sorting_6_Numbers>git add .

E:\Sorting_6_Numbers>git commit -m "Some codes"
[master 5f8e2d3] Some codes
 4 files changed, 96 insertions(+)
 create mode 100644 .classpath
 create mode 100644 .project
 create mode 100644 bin/Sorting_6_Numbers.class
 create mode 100644 src/Sorting_6_Numbers.java

E:\Sorting_6_Numbers>git push	
warning: push.default is unset; its implicit value has changed in
Git 2.0 from 'matching' to 'simple'. To squelch this message
and maintain the traditional behavior, use:

  git config --global push.default matching

To squelch this message and adopt the new behavior now, use:

  git config --global push.default simple

When push.default is set to 'matching', git will push local branches
to the remote branches that already exist with the same name.

Since Git 2.0, Git defaults to the more conservative 'simple'
behavior, which only pushes the current branch to the corresponding
remote branch that 'git pull' uses to update the current branch.

See 'git help config' and search for 'push.default' for further information.
(the 'simple' mode was introduced in Git 1.7.11. Use the similar mode
'current' instead of 'simple' if you sometimes use older versions of Git)

Username for 'https://github.com': prasunthapa10
Password for 'https://prasunthapa10@github.com':
Counting objects: 8, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (6/6), done.
Writing objects: 100% (8/8), 2.83 KiB | 0 bytes/s, done.
Total 8 (delta 0), reused 0 (delta 0)
To https://github.com/prasunthapa10/ HW_10_Sorting_6_Numbers.git
   6f92b53..5f8e2d3  master -> master

E:\Sorting_6_Numbers>


```

## Summary
In this assignment we sorted the six different random numbers in an ascending order. We have used the methods to call the sorting algorithm. There are no input and output variables. The internal variables used in the program is numberArray. We have also used the for loop for the reducement of code repetition. We can use the same concept to sort the numbers in descending orders. 


