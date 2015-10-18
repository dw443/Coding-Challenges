September 2015 Challenge Part 0 Description from DevDraft:

Single-Player word game
Premise:
Player is an alchemist who takes elemental crystals and forms compounds
Each crystal is a specific type of element: F, I, Z, B, A, R
Crystals are presented in a line
Basic compounds are formed when crystals are adjacent in specific orders: FIZ, BAR, BAZ, ZIF, RAB, ZAB
If adjacent compounds overlap, then the entire sequence is treated as one large compound.
Once formed, they are removed.
Player can make swaps if a compound will be formed.
Once compounds are removed, remaining elements slide to the left to fill gaps.

Input:
-integer C representing the number of letters/crystals (0<C<100)
-string of C characters the length of the integer inputted previously
-integer S representing the number of swaps to be made (0 <= S < 50)
-S space separated integers for the index of the letter to be swapped with the right neighbor

Output:
-letters remaining


Solution Analysis:
    I realized that the solution would need to check for crystals and then remove them, eliminate blank spaces / make sure the string does not have any openings between crystals, and swap the crystals as per user specification. Then repeat the process until no more swaps are made by the user. 
    My solution comprises of an array dictionary of valid compounds, a function to check groups of elements against the dictionary's valid compounds, a function to swap elements, and lastly a function to delete compounds from the string of elemental crystals. 
    I wanted to make my code look clean so I created an array dictionary for me to check the crystals against the valid compounds instead of listing them in an if statement over and over again. To make my code even cleaner and more understandable, I created the function of swapping elements even if it's just a simple matter of swapping indexes and the contents. 
    How my solution works is checking for and deleting compounds all happen in one function. The deleteCompounds function takes in a string of elemental crystals and loops through the string to check if there are any compounds. Since compounds are only comprised of 3 crystals, the function checks 3 crystals at a time starting from index 0. Because the compounds can be formed multiple times through adjacent crystals, the function accounts for this using a while loop. If the last crystal in the compound formation and the next two letters in the string form another compound, then the while loop continues. The function keeps track of the starting index of the compound and also the last index of the multiple compounds. This allows the function to replace the substring of compounds with an empty string when it exits the while loop. This while loop is nested inside another while loop because using a for loop would've advanced the index when it should not have been advanced, such as if a compound formed within indexes 0-2 and exited the while loop - the for loop would've started checking from index 1 instead of index 0. 
    Lastly a for loop looped through the array of integers that the user specified would be the swaps and within each iteration of the for loop, the function deleteCompounds would be called.
    
Time Complexity:
Space Complexity:
