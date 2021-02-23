# DartPad
import 'dart:math'; 
class operators7_1{ 
  int numX; 
  int numY; 
  operators7_1(this.numX,this.numY){ 
    this.numX = numX; 
    this.numY = numY; } 
  
  setnumX(int numX) => numX; 
  setnumY(int numY) => numY; 
  addnum(int numX, int numY) => numX + numY; 
  subnum(int numX, int numY) => numX - numY; 
  mulnum(int numX, int numY) => numX * numY; 
  divnum(int numX, int numY) => numX / numY; 
  powernum(int numX, int numY) => pow(numY, numX); 
  showResult(){ }
}
  class calculation8_1 extends operators7_1{ 
    int x; 
    int y; 
  calculation8_1():super(10,2){ } 
    @override void showResult(){ 
      super.powernum(10,2); 
      print ("Result of y raised to the x power (yˣ) = ${pow(this.numY,this.numX)}");} 
      circumference(numX, numY){ 
      x = numX; 
      y = numY; }
  }

class findinglenght8_2 extends calculation8_1{ 
 findinglenght8_2 ():super(){ } 
  @override 
  void showResult(){ 
  super.circumference(4,5); 
  print("Width: ${x}"); 
  print("Length: ${y}"); 
  print("Circumference of square or rectangle = ${2*x*y}");
  print("--------------------------------------------");}
}
  main(List<String> arguments){ 
    var inputnumber = operators7_1(10,2);
    print("Activity 8.1 \n--------------------------------------------");
    print("InputNumber1: ${inputnumber.setnumX(inputnumber.numX)}");
    print("InputNumber2: ${inputnumber.setnumY(inputnumber.numY)}"); 
    
    print("Result of Addition (+) = ${inputnumber.addnum(inputnumber.numX, inputnumber.numY)}"); 
    print("Result of subtraction (-) = ${inputnumber.subnum (inputnumber.numX, inputnumber.numY)}");
    print ("Result of Multiplication (*) = ${inputnumber.mulnum(inputnumber.numX, inputnumber.numY)}"); 
    print ("Result of Division (/) = ${inputnumber.divnum(inputnumber.numX, inputnumber.numY)}"); 
    var cal = calculation8_1(); 
    inputnumber.showResult(); 
    cal.showResult(); 
    var finding = findinglenght8_2(); 
    inputnumber.showResult(); 
    finding.showResult();
  }
    
