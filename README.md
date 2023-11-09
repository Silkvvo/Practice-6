import java.util.*;
import java.lang.*;
import java.io.*;

interface CanHavePizza { void eatPizza(); }

interface Movable { void move(); } class Animal { }

class Cat extends Animal implements CanHavePizza { public void eatPizza() { System.out.println("The cat is eating pizza!"); } }

class Student extends Person implements CanHavePizza, Movable { public Student(String name) { super(name); }

public void eatPizza() {
    System.out.println("The student is eating pizza!");
}

public void move() {
    System.out.println("The student is moving to class.");
}
}

class Person { private String name;

public Person(String name) {
    this.name = name;
}

}

class Restaurant { public boolean servePizza(CanHavePizza eater) { eater.eatPizza(); if (eater instanceof Person) { System.out.println("Processing payments for the person."); } return true; } }

public class Main { public static void main(String[] args) { Cat cat = new Cat(); Student student = new Student("Alice");

    Restaurant restaurant = new Restaurant();

    restaurant.servePizza(cat);

    restaurant.servePizza(student);

    student.move();
}
}
