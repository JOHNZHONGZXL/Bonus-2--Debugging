# Bonus-2--Debugging
1. Demo
```
#               /**
#                 * This method is supposed to reverse each section of 4 characters in the string and build
#                 * a new string off of the results. This method has a bug though! Use the debugger to
#                 * figure out what's going on.
#                 */
#                 public static void funWithStrings(){
#                    String letters = "YyaYiFuoTdexuBehTnIgeMehdoht";
#                    String newLetters = "";
#                    for(int i = 0; i < letters.length()/4; ++i){
#                        String tempString = "";
#                        for(int j = 3; j >0; --j){
#                            tempString += letters.charAt((4*i) + j);
#                        }
#                        newLetters += tempString;
#                    }
#                    System.out.println(newLetters);
#                }
```
2. Your turn to debug! Good luck!
```
import java.util.Scanner;

public class BuggyPigLatinTranslator {

    public static final String VOWELS = "AEIOUY";    //characters that are considered vowels

    public static void main(String[] args) {
        Scanner keyboard = new Scanner(System.in);
        System.out.println("Enter one word:");
        String phrase = keyboard.nextLine();
        System.out.println(phrase + " in Pig Latin is " + convertWord(phrase));
    }

    /**
     * convertWord
     * This method converts a single word to pig latin.
     * @param word - one word of the user inputted phrase
     * @return the converted word in pig latin
     */
    public static String convertWord(String word) {
        String pigLatin = "";//holds the converted word
        boolean done = false;//sentinel for stopping loop
        int i = 0;//tracks position in string

        //goes through word character by character looking for first vowel
        while (!done) {
            char x = word.charAt(i);
            if (isVowel(x)) { //found a vowel!
                //if the first letter is a vowel
                if (i==0) {
                    pigLatin = word.substring(0,word.length()) + word.charAt(0) + "WAY";
                }
                //if the first letter is not a vowel
                else {
                    pigLatin = word.substring(i+1) + word.substring(0, i) + "AY";
                }
            }

            if (i<word.length()-1) {
                i++;//move to next character in word if i is less than the word length
            } else {
                done = true;//ends loop
            }
        }

        //doesn't change the word if there are no vowels
        if (pigLatin.isEmpty()) {
            pigLatin = word;
        }

        return pigLatin.toUpperCase();
    }

    /**
     * isVowel
     * This method checks if a letter is a vowel
     * @param x - the letter to be checked
     * @return true or false depending on if the character is a vowel or not
     */
    public static boolean isVowel(char x) {
        String X = Character.toString(x); //changes the character to a string
        X = X.toUpperCase(); //converts string to upper case

        boolean vowel = true;

        //loop through all possible vowels and see if there's a match
        for (int i = 0; i <= VOWELS.length()-1; i++)
            if (VOWELS.contains(X)) {   //yes, this is a vowel
                vowel = true;
            } else {
                vowel = false;
            } //went through all vowels and determined this is not a vowel
        return vowel;
    }
}
```

