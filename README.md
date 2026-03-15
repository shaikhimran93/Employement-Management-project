

import java.util.*;

// Employee class
class Employee {

    int id;
    String name;
    double salary;

    Employee(int id, String name, double salary) {
        this.id = id;
        this.name = name;
        this.salary = salary;
    }

    void display() {
        System.out.println(id + " " + name + " " + salary);
    }
}


// Main class
public class Main {

    static ArrayList<Employee> list = new ArrayList<>();

    static void addEmployee(Scanner sc) {

        System.out.println("Enter Employee id:");
        int id = sc.nextInt();
        sc.nextLine();

        System.out.println("Enter Employee name:");
        String name = sc.nextLine();

        System.out.println("Enter Employee salary:");
        double salary = sc.nextDouble();

        list.add(new Employee(id, name, salary));

        System.out.println("Employee Added");
    }

    static void viewEmployee() {

        for (Employee e : list) {
            e.display();
        }
    }

    static void deleteEmployee(Scanner sc) {

        System.out.println("Enter Employee id to delete:");
        int id = sc.nextInt();

        list.removeIf(e -> e.id == id);

        System.out.println("Deleted");
    }

    static void searchEmployee(Scanner sc) {

        System.out.println("Enter id:");
        int id = sc.nextInt();

        for (Employee e : list) {
            if (e.id == id) {
                e.display();
                return;
            }
        }

        System.out.println("Not found");
    }

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        while (true ) {

            System.out.println("1 Add");
            System.out.println("2 View");
            System.out.println("3 Delete");
            System.out.println("4 Search");
            System.out.println("5 Exit");

            int ch = sc.nextInt();

            switch (ch) {

                case 1:
                    addEmployee(sc);
                    break;

                case 2:
                    viewEmployee();
                    break;

                case 3:
                    deleteEmployee(sc);
                    break;

                case 4:
                    searchEmployee(sc);
                    break;

                case 5:
                    System.exit(0);
            }
        }
    }
}
