1) OOPS PROBLEM
   package oop4;

class Box {
    double length;
    double breadth;
    Box(double length, double breadth) {
        this.length = length;
        this.breadth = breadth;
    }
    double area() {
        return length * breadth;
    }
}
class Box3D extends Box {
    double height;
    Box3D(double length, double breadth, double height) {
  super(length, breadth);
        this.height = height;
    }
    double volume() {
        return length * breadth * height;
    }
}

public class Main {
    public static void main(String[] args) {
        Box3D obj = new Box3D(5, 4, 3);
        System.out.println("Area = " + obj.area());
        System.out.println("Volume = " + obj.volume());
    }
}
OUTPUT:
Area = 20.0
Volume = 60.0

package oop4;
interface Test {
    int square(int n);
}

class Arithmetic implements Test {
    public int square(int n) {
       return n * n;
    }
}
public class ToTestInt {
    public static void main(String[] args) {
        Arithmetic obj = new Arithmetic();
        int result = obj.square(5);
        System.out.println("Square = " + result);
    }
}
 OUTPUT:
 Square = 25

 

