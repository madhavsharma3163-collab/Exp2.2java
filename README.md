import java.io.*; import java.util.Scanner;

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

        
}
}

