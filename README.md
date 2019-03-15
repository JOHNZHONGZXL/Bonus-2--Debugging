# Bonus-2--Debugging
```
#               /**
#                 * This method is supposed to reverse each section of 4 characters in the string and build
#                 * a new string off of the results. This method has a bug though! Use the debugger to
#                 * figure out what's going on.
#                 */
#                 public static void funWithStrings(){'
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
