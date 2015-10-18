/* package whatever; // don't place package name! */

import java.util.*;

import java.lang.*;

import java.io.*;

/* Name of the class has to be "Main" only if the class is public. */
class MyClass
{
    public static void main (String[] args) throws java.lang.Exception
    {
        int numElements; //1st input, number of elements
        String elements; //2nd input, string of elements
        int numSwaps;    //3rd input, number of swaps
        int[] swaps;     //4th input, left index to be swap
        
        Scanner in = new Scanner(System.in);
        
        numElements = in.nextInt();
        
        elements = in.next();
        
        numSwaps = in.nextInt();
        
        swaps = new int[numSwaps];
        for(int i = 0; i<numSwaps; i++){
            swaps[i] = in.nextInt();
        }
        String result = deleteCompounds(elements);
        for(int k = 0; k<numSwaps; k++) {
           	result = swapElements(result, swaps[k]);
            result = deleteCompounds(result);
        }
        
        System.out.println(result);
    }

    public static String[] COMPOUNDS = {"FIZ","BAR","BAZ","ZIF","RAB","ZAB"};
    
    //checks if the crystals are a compound
    static boolean IsCompound(String testCrystal){
        if (Arrays.asList(COMPOUNDS).contains(testCrystal))
            return true;
        return false;
    }

    //swap the elements in the string per user specification
    public static String swapElements(String crystals, int left){
       char[] c = crystals.toCharArray();
       char temp = c[left];
       c[left] = c[left+1];
       c[left+1] = temp;
       
       String swappedElements = new String(c);
        
       return swappedElements;
    }



    //remove compounds
    public static String deleteCompounds(String crystals){
        
        int numCrystals = crystals.length();

        int i = 0;
        while (i < numCrystals-2){
            int current = i+2;
            if (IsCompound(crystals.substring(i, i+3))){
                
                boolean cont = true;
                
                while (cont && (current+3 <= numCrystals)){
                    if (IsCompound(crystals.substring(current, current+3))){
                        current = current + 2;
                        cont = true;
                    }
                    else {
                        cont = false;
                    }
                }
                
                crystals = crystals.replace(crystals.substring(i,current+1),"");
                numCrystals = crystals.length();
            }
            else {
                i++;
            }
        }
        return crystals;
    }
}
