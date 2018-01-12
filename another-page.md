---
layout: minimal
---
# Another Page

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aenean euismod, arcu ut vestibulum luctus, dolor eros auctor arcu, sit amet porta magna dui a turpis. Proin eget porta magna. Pellentesque scelerisque nisi eget nulla mattis finibus. Maecenas nec rhoncus tellus, et euismod purus. Pellentesque volutpat ligula ac nisl elementum bibendum. Integer rutrum turpis id mi aliquet, varius feugiat purus vehicula. Etiam molestie sollicitudin faucibus. Aenean at lectus porttitor, eleifend purus ac, euismod ante. Mauris varius mi sit amet velit aliquet lacinia. Nunc eu tristique diam. Sed a felis ac ligula dictum aliquam at sed turpis.

Sed tristique vehicula dolor, id cursus eros iaculis non. Aenean sit amet tincidunt erat. Cras pellentesque pretium nisi nec eleifend. Mauris lobortis pretium sagittis. Curabitur id sem nisi. Etiam ut arcu ac ex ullamcorper mattis vitae a neque. Cras id tincidunt quam. Nulla elit ante, egestas eu urna a, sagittis sagittis nisl. Aliquam nec rhoncus justo. Maecenas eleifend ac ante sit amet feugiat. 

## Welcome to another page

```c++
 /*   
      A palindrome is a word, phrase, number, or other sequence of symbols or elements, 
  whose meaning may be interpreted the same way in either forward or reverse direction.
  This program will prompt the user to enter a word or a sentence and then confirms if 
  the user's entry is an palindrome or not.   
*/
#include <iostream>
#include <cstdlib>

bool isPalindrome( char [] );

int main( int argc, char *argv[] )
{
	char userString[300];
	std::cout << \"Type a word or phrase to see if it's a Palindrome.\" << \"\n\n\";
	std::cin.getline(userString, 300);		
	std::cout << \"\n\";
	if ( isPalindrome( userString ) )
			std::cout << \"\\"\" << userString << \"\\" is a Palindrome.\";
	else
			std::cout << \"\\"\" << userString << \"\\" is not a Palindrome.\";	
	std::cout << \"\n\n\";
	system( \"PAUSE\" );		
	return 0;
}
/*
  The following function will return true if the array parameter is a palindrome.
  
  Step 1: First it counts how many characters are in the parameter array and then creates a new 
	      array (array1) with that count size.

  Step 2: The contents of the parameter array are copied to array1 with no spaces or punctuations.
          - This is accomplished by checking the user's array for anything other than an 
		    alphetbet character. When an non-alpha character is found, that array element 
			postion is recorded. It then copies the user's array contents from the starting 
			element position to the position right before the non-alpha character to the new
			array (array1). The element position right after the non-alpha character then 
			becomes the new starting position and the process iterates until array1 has only 
			one element position left in which a null terminator will be assigned.

  Step 3: array1 is then tested to see if it's a palindrome. Instead of copying array1 into an 
		  another array in reverse order and then comparing the two, the test can be 
		  accomplished by comparing array1 within itself. 
		  - This is accomplished by comparing array1's first character with it's last character. 
		    if both those charcters are the same, whether uppercase or lowercase, it then compares 
			array1's second character with it'a second-to-last character....and so forth until the 
			middle of array1 is reached. If at anytime, however, a comparison is not the same then 
			the 'isPalindrome' flag is set to false and the loop ends. The 'isPalindrome' flag will 
			remain true if and only if all comparisons are the same.
			
  Step 4: The function then returns the boolean value of isPalindrome.
*/
bool isPalindrome( char array[] )
{
    bool isPalindrome = true;
    int size = 0, index = 0, startingPos = 0, count1 = 0;	
	// Step 1
	while ( array[size] != '\0' ) 
	{                              
			size++;
	}	
	char array1[size + 1];
	// Step 2
	while ( index < size ) 
	{                     
			while ( (array[index] >= 'A' and array[index] <= 'Z') or
                    (array[index] >= 'a' and array[index] <= 'z')    )
					index++;
			for ( int count = startingPos; count < index; count++ )
			{
					array1[count1] = array[count];
					count1++;
			}
			index++;
			startingPos = index;
	}
	array1[count1] = '\0';	
	//Step 3
	index = 0;
	while ( index <= (count1 - 1)/2 and isPalindrome )
	{
			if ( array1[index] != array1[count1 - index - 1]      and
				 array1[index] != array1[count1 - index - 1] - 32 and
				 array1[index] != array1[count1 - index - 1] + 32 and
				 array1[index] - 32 != array1[count1 - index - 1] and
				 array1[index] + 32 != array1[count1 - index - 1]     )
					isPalindrome = false;
			index++;
	}
	// Step 4
	return isPalindrome;
}
```

_yay_

[back](../)
