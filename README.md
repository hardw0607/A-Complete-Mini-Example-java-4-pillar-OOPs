# A-Complete-Mini-Example-java-4-pillar-OOPs
# A Complete Mini Example java 4 pillar OOPs

// Abstraction + Interface
interface Vehicle {
    void start();
}

// Encapsulation
class Engine {
    private int horsepower;
    Engine(int hp) { this.horsepower = hp; }
    int getHp() { return horsepower; }
}

// Inheritance
abstract class Car implements Vehicle {
    protected Engine engine;
    protected String model;

    Car(String model, int hp) {
        this.model = model;
        this.engine = new Engine(hp);
    }

    public void start() {
        System.out.println(model + " started with " + engine.getHp() + " HP");
    }
}

// Polymorphism
class SportsCar extends Car {
    SportsCar(String m, int hp) { super(m, hp); }

    @Override
    public void start() {
        System.out.println("VROOM! " + model + " (" + engine.getHp() + " HP)");
    }
}

public class Main {
    public static void main(String[] args) {
        Vehicle v = new SportsCar("Ferrari", 700); // runtime polymorphism
        v.start();   // VROOM! Ferrari (700 HP)
    }
}
