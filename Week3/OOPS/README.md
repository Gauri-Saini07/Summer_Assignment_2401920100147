OOPS PROBLEM
package oops3;
import java.util.Random;
    abstract class Compartment {
        public abstract String notice();
    }
    class FirstClass extends Compartment {
        @Override
        public String notice() {
            return "First Class: Please maintain silence and keep the compartment clean.";
        }
    }
    class Ladies extends Compartment {
        @Override
        public String notice() {
            return "Ladies Compartment: Reserved only for women passengers.";
        }
    }
    class General extends Compartment {
        @Override
        public String notice() {
            return "General Compartment: Please cooperate with fellow passengers.";
        }
    }
    class Luggage extends Compartment {
        @Override
        public String notice() {
            return "Luggage Compartment: Only luggage is allowed here.";
        }
    }
    public class TestCompartment {
   public static void main(String[] args) {
            Random random = new Random();
            // Array of size 10
            Compartment[] compartments = new Compartment[10];
            for (int i = 0; i < 10; i++) {
                int num = random.nextInt(4) + 1; // 1 to 4
                switch (num) {
                    case 1:
                        compartments[i] = new FirstClass();
                        break;
                    case 2:
                        compartments[i] = new Ladies();
                        break;
                    case 3:
                        compartments[i] = new General();
                        break;
                    case 4:
                        compartments[i] = new Luggage();
                        break;
                }
            }
            for (int i = 0; i < 10; i++) {
                System.out.println("Compartment " + (i + 1));
                System.out.println(compartments[i].notice());
                System.out.println();
            }
        }
    }

OUTPUT:
Compartment 1
Luggage Compartment: Only luggage is allowed here.

Compartment 2
Luggage Compartment: Only luggage is allowed here.

Compartment 3
Ladies Compartment: Reserved only for women passengers.

Compartment 4
First Class: Please maintain silence and keep the compartment clean.

Compartment 5
Luggage Compartment: Only luggage is allowed here.

Compartment 6
Ladies Compartment: Reserved only for women passengers.

Compartment 7
First Class: Please maintain silence and keep the compartment clean.

Compartment 8
Ladies Compartment: Reserved only for women passengers.

Compartment 9
First Class: Please maintain silence and keep the compartment clean.

Compartment 10
General Compartment: Please cooperate with fellow passengers.


