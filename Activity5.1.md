# DartPad
--Activity 5.1.md
main() 
{ print(getRecursive(0)); }
 
 int getRecursive(int number) { 
   if (number > 1) 
     return number + getRecursive(number - 1); 
   else return 1;
 }
