mport java.io.*; import java.util.Scanner;

class Employee { int id; String name; String designation; double salary;

public Employee(int id, String name, String designation, double salary) {
    this.id = id;
    this.name = name;
    this.designation = designation;
    this.salary = salary;
}

@Override
public String toString() {
    return id + "," + name + "," + designation + "," + salary;
}
}

public class EmployeeManagementSystem{ private static final String FILE_NAME = "employees.txt";

public static void main(String[] args) {
    Scanner sc = new Scanner(System.in);

    while (true) {
        System.out.println("\n=== Employee Management System ===");
        System.out.println("1. Add Employee");
        System.out.println("2. Display All Employees");
        System.out.println("3. Exit");
        System.out.print("Enter choice: ");
        int choice = sc.nextInt();
        sc.nextLine(); // consume newline

        switch (choice) {
            case 1:
                addEmployee(sc);
                break;
            case 2:
                displayEmployees();
                break;
            case 3:
                System.out.println("Exiting... Goodbye!");
                sc.close();
                System.exit(0);
            default:
                System.out.println("Invalid choice! Try again.");
        }
    }
}

private static void addEmployee(Scanner sc) {
    System.out.print("Enter Employee ID: ");
    int id = sc.nextInt();
    sc.nextLine(); // consume newline
    System.out.print("Enter Employee Name: ");
    String name = sc.nextLine();
    System.out.print("Enter Designation: ");
    String designation = sc.nextLine();
    System.out.print("Enter Salary: ");
    double salary = sc.nextDouble();

    Employee emp = new Employee(id, name, designation, salary);

    try (BufferedWriter writer = new BufferedWriter(new FileWriter(FILE_NAME, true))) {
        writer.write(emp.toString());
        writer.newLine();
        System.out.println("Employee added successfully!");
    } catch (IOException e) {
        e.printStackTrace();
    }
}

private static void displayEmployees() {
    System.out.println("\n--- Employee Records ---");
    try (BufferedReader reader = new BufferedReader(new FileReader(FILE_NAME))) {
        String line;
        while ((line = reader.readLine()) != null) {
            String[] data = line.split(",");
            System.out.println("ID: " + data[0] + ", Name: " + data[1] + 
                               ", Designation: " + data[2] + ", Salary: " + data[3]);
        }
    } catch (FileNotFoundException e) {
        System.out.println("No employees found. Add some first!");
    } catch (IOException e) {
        e.printStackTrace();
    }
}
} import java.io.*;

// Student class implementing Serializable class Student implements Serializable { private static final long serialVersionUID = 1L; // for version control int studentID; String name; String grade;

public Student(int studentID, String name, String grade) {
    this.studentID = studentID;
    this.name = name;
    this.grade = grade;
}

public void display() {
    System.out.println("ID: " + studentID + ", Name: " + name + ", Grade: " + grade);
}
} import java.util.ArrayList; import java.util.Scanner;

public class SumUsingAutoboxing { public static void main(String[] args) { Scanner sc = new Scanner(System.in); ArrayList numbers = new ArrayList<>();

    System.out.println("Enter integers (type 'done' to finish):");
    while (true) {
        String input = sc.nextLine();
        if (input.equalsIgnoreCase("done")) {
            break;
        }

        // Parsing string into int, then autoboxing into Integer
        int num = Integer.parseInt(input);
        numbers.add(num);  // Autoboxing happens here
    }

    int sum = 0;
    for (Integer n : numbers) {
        sum += n; // Unboxing happens here
    }

    System.out.println("Sum of integers = " + sum);
    sc.close();
}
}
