# Ex.No:4(D) DESIGN PATTERN -- ABSTRACT FACTORY

## QUESTION:
Create a system that builds Car and Bike objects for two companies: "Honda" and "Yamaha". Use Abstract Factory Pattern to choose the brand and output the type and brand for each vehicle.

For example:

Input	Result
honda
Honda Car created
Honda Bike created



## AIM:
To create a Java program using the Abstract Factory Pattern to generate Car and Bike objects for two brands: Honda and Yamaha.


## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create interfaces Car and Bike with assemble() method.
4.	Create concrete classes-HondaCar, HondaBike,YamahaCar, YamahaBike
5. Create VehicleFactory interface with createCar() and createBike().
6. Create concrete factories:HondaFactory,YamahaFactory.
7. Read input brand name from user.
8. Based on the brand, create the corresponding factory.
9. Use the factory to create Car and Bike objects.
10. Print the assembled vehicle messages.
11. End the program.





## PROGRAM:
 ```
/*
Program to implement a Abstract Factory Pattern using Java
Developed by: LATHISH KANNA M
RegisterNumber:  212222230073
*/
```

## SOURCE CODE:

```
import java.util.Scanner;

interface Car {
    void assemble();
}
interface Bike {
    void assemble();
}

class HondaCar implements Car {
    public void assemble() { System.out.println("Honda Car created"); }
}
class YamahaCar implements Car {
    public void assemble() { System.out.println("Yamaha Car created"); }
}
class HondaBike implements Bike {
    public void assemble() { System.out.println("Honda Bike created"); }
}
class YamahaBike implements Bike {
    public void assemble() { System.out.println("Yamaha Bike created"); }
}

interface VehicleFactory {
    Car createCar();
    Bike createBike();
}

class HondaFactory implements VehicleFactory {
    public Car createCar() { return new HondaCar(); }
    public Bike createBike() { return new HondaBike(); }
}

class YamahaFactory implements VehicleFactory {
    public Car createCar() { return new YamahaCar(); }
    public Bike createBike() { return new YamahaBike(); }
}

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String brand = scanner.nextLine().toLowerCase();

        VehicleFactory factory;
        if (brand.equals("honda")) factory = new HondaFactory();
        else if (brand.equals("yamaha")) factory = new YamahaFactory();
        else {
            System.out.println("Invalid company");
            return;
        }

        factory.createCar().assemble();
        factory.createBike().assemble();
    }
}

```




## OUTPUT:



## RESULT:

Thus, the program successfully implements the Abstract Factory Pattern and creates Car and Bike objects for the chosen brand.


