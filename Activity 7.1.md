# DartPad
--Activity 7.1.md
class math{ 
  int num_a; 
  int num_b; 
  math(this.num_a, this.num_b){
    this.num_a = num_a; 
    this.num_b = num_b; 
  }
  
  int setnum_a(int num_a) => num_a;
  int setnum_b(int num_b) => num_b; 
  int addnum(int num_a, int num_b) => num_a + num_b; 
  int subnum(int num_a, int num_b) => num_a - num_b; 
  int mulnum(int num_a, int num_b) => num_a * num_b; 
  double divnum(int num_a, int num_b)=> num_a / num_b;
}
  main(List<String> argment){
    var inputnumber = math(20,20);
    
    print("Input your number1:${inputnumber.setnum_a(inputnumber.num_a)}");     
    print("Input your number2:${inputnumber.setnum_b(inputnumber.num_b)}");
    
    
    print("Result of Addition = ${inputnumber.addnum(inputnumber.num_a,inputnumber.num_b)}");   
    print("Result of Subtraction = ${inputnumber.subnum(inputnumber.num_a,inputnumber.num_b)}"); 
    print("Result of Multiplication = ${inputnumber.mulnum(inputnumber.num_a,inputnumber.num_b)}"); 
    print("Result of Division = ${inputnumber.divnum(inputnumber.num_a,inputnumber.num_b)}");
    
  }
