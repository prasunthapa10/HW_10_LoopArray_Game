# HW_10_LoopArray_Game 

# Addition Game using loops, methods and arrays 
# Introduction
We are going to customize our addition game code using the methods, loops and arrays. This helps to make our code
shorter and more effective.It consists of four rounds. The user is asked to add two random numbers. Each correct answer is followed by 10 points and incorrect answer is followed by simpler question. At last, the final score is printed on the console screen.

# Project Outline
```
//Call the addition game method.
// Assign the value for hardness, score and hardness setup.
// Set up my for loop to go through the number of rounds
// Use the arrays to sort the nmbers
//  Use the boolean data type to verify the answer
// Use the if statement to compare the answers and Print statement to print the result.
```
##  References & Literature
*   Liang, Y. (2014). *Introduction to Java programming: Comprehensive version* (Tenth ed.).

## Source Code
```java
import java.util.Scanner;

public class Addition_array  {
	public static void main(String[] args) {
		//System.out.println("Hello class.");
		
		//Call the addition game method.
		AdditonGameMethod();
	}
	public static void AdditonGameMethod() {
		//System.out.println("Inside the addition game method.");
		
		int[] gameVariables = new int[4];
		gameVariables[0] = 5; //hardness;
		//int hardness = gameVariables[0];
		gameVariables[1] = 2; //hardnessStep;
		//int hardnessStep = 2;
		gameVariables[2] = 0; //score;
		//int score = 0;
		gameVariables[3] = 0; // 1 for true, 0 for false
		
		// Set up my for loop to go through the number of rounds
		int numberOfRounds = 3;
		for(int roundNumber = 1; 
		roundNumber <= numberOfRounds;  
		roundNumber = roundNumber + 1){
			//System.out.println("Inside the for loop. Round: " + roundNumber);
			System.out.print("Round " + roundNumber + " of " + numberOfRounds + ". ");
			gameVariables = getAndCheckStudentAnswer(gameVariables);
			if(gameVariables[3] == 1){
				System.out.print("Your score was " + gameVariables[2] + " and is now ");
				gameVariables[2] = gameVariables[2] + gameVariables[0];
				System.out.print(gameVariables[2] + ". ");
				
				if(roundNumber<numberOfRounds){
					System.out.print("Your hardness was " + gameVariables[0] + " and is now ");
					gameVariables[0] = gameVariables[0] * gameVariables[1];
					System.out.println(gameVariables[0] + ".");
				}
			}else{
				System.out.print("Your score is " + gameVariables[2] + ". ");
				if(roundNumber<numberOfRounds){
					System.out.print("Your hardness was " + gameVariables[0] + " and is now ");
					if(gameVariables[0]>5){
						gameVariables[0] = gameVariables[0] / gameVariables[1];
					}
					System.out.println(gameVariables[0] + ".");
					
				}
				
			}
		}
		System.out.print("\nThe game is complete. ");
		System.out.println("Your final score was " + gameVariables[2] );
	}
	
	public static int[] getAndCheckStudentAnswer(int[] gameVariables) {
		//System.out.println("Inside get and check student answer method.");
		int number1 = (int)(Math.random()*gameVariables[0]);
		int number2 = (int)(Math.random()*gameVariables[0]);
		System.out.print("Add " + number1 + " and " + number2 +": ");
		//Scanner input = new Scanner(System.in);
		//int studentAnswer = input.nextInt();
		Scanner get = new Scanner(System.in);
		int studentAnswer = get.nextInt();
		if(studentAnswer == (number1 + number2)){
			System.out.print("Correct. ");
			gameVariables[3] = 1;
			
		}else{
			System.out.println("Nice try, but the correct answer was " 
					+ (number1 + number2) + ".");
			gameVariables[3] = 0;
		}
		return gameVariables;
	}
}
 
	
```
	


## Console Output
```

Round 1 of 3. Add 4 and 3: 7
Correct. Your score was 0 and is now 5. Your hardness was 5 and is now 10.
Round 2 of 3. Add 3 and 5: 8
Correct. Your score was 5 and is now 15. Your hardness was 10 and is now 20.
Round 3 of 3. Add 17 and 7: 24
Correct. Your score was 15 and is now 35. 
The game is complete. Your final score was 35
```


# Command Prompt
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
               4 File(s)     12,579,955 bytes
               6 Dir(s)  15,405,072,384 bytes free

E:\>cd Addition_array

E:\Addition_array>echo # HW_10_LoopArray_Game >> README.md

E:\Addition_array>git init
Initialized empty Git repository in E:/Addition_array/.git/

E:\Addition_array>git add README.md

E:\Addition_array>git config user.name "Prasun Thapa"

E:\Addition_array>git config user.email thapap@student.swosu.edu

E:\Addition_array>git commit -m "First commit"
[master (root-commit) 6f92b53] First commit
 1 file changed, 1 insertion(+)
 create mode 100644 README.md

E:\Addition_array>git remote add origin https://github.com/prasunth
apa10/HW_10_LoopArray_Game.git

E:\Addition_array>git push -u origin master
Username for 'https://github.com': prasunthapa10
Password for 'https://prasunthapa10@github.com':
Counting objects: 3, done.
Writing objects: 100% (3/3), 238 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/prasunthapa10/HW_10_LoopArray_Game.git
 * [new branch]      master -> master
Branch master set up to track remote branch master from origin.

E:\Addition_array>git add .

E:\Addition_array>git commit -m "Some codes"
[master 5f8e2d3] Some codes
 4 files changed, 96 insertions(+)
 create mode 100644 .classpath
 create mode 100644 .project
 create mode 100644 bin/Loop_Game.class
 create mode 100644 src/Loop_Game.java

E:\Addition_array>git push
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
To https://github.com/prasunthapa10/HW_10_LoopArray_Game.git
   6f92b53..5f8e2d3  master -> master

E:\Addition_array>

```
## Summary
In the print statement, the main method calls a greeting method in the print statement. The main method also calls the addition game method. The main method has no outut and input variables. Additiob game method has internal variable called gameVariables. From this source code we can easily figure out how the methods and arrays have made our life easier. We have also used the for loop that has helped to generate the same loop for four times. The pevious addition gam without loops and methods was too long, but now the code has become short and sweet. Instead of typing the same code for four rounds, we used the for loop. We use the public static void method and public static boolean method to make our code easier in the above program. We can use the same concept to find the otput of other programs in the upcoming days.  
