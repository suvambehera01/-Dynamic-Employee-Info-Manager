import java.util.ArrayList;
import java.util.Scanner;

class Emp {
    int empid;
    String empname;
    double sal;
    String pos;

    @Override
    public String toString() {
        return "Emp ID : " + empid + "  Emp Name :  " + empname + "   Salary : " + sal + "  Designation is : " + pos;
    }

    public Emp(int empid, String empname, double sal, String pos) {
        this.empid = empid;
        this.empname = empname;
        this.sal = sal;
        this.pos = pos;
    }
}

public class Demo {
    static ArrayList<Emp> aa = new ArrayList<>();
    static Scanner sc = new Scanner(System.in);

    public static void main(String args[]) {
        while (true) {
            System.out.println("*See the Demo of Dynamic Array.");
            System.out.println("See the Option.");
            System.out.println("1>Add the element in dynamic Array.");
            System.out.println("2>Retrive the elements from dynamic Array.");
            System.out.println("3>Delete an element from dynamic array.");
            System.out.println("4>Update name in the dynamic array.");
            System.out.println("5>Quit.");
            System.out.println("Enter your choice.");
            int ch = get();
            switch (ch) {
                case 1:
                    addItem();
                    break;
                case 2:
                    retrive();
                    break;
                case 3:
                    delete();
                    break;
                case 4:
                    update();
                    break;
                case 5:
                    System.out.println("Thank you for using my application.");
                    System.exit(0);
                    break;
                default:
                    System.out.println("*Invalid Choice.*");
                    break;
            }
        }
    }

    public static int get() {
        return sc.nextInt();
    }

    public static void addItem() {
        System.out.println("Enter EMP ID.");
        int id = sc.nextInt();
        sc.nextLine(); // consume newline
        System.out.println("Enter emp name");
        String name = sc.nextLine();
        System.out.println("Enter salary");
        double sal = sc.nextDouble();
        sc.nextLine(); // consume newline
        System.out.println("Enter your position.");
        String pos = sc.nextLine();
        Emp ee1 = new Emp(id, name, sal, pos);
        aa.add(ee1);
    }

    public static void retrive() {
        System.out.println("See the data of the dynamic Array.");
        for (int i = 0; i < aa.size(); i++) {
            Emp kk = (Emp)aa.get(i);
            System.out.println(kk);
        }
    }

    public static void delete() {
        System.out.println("Enter the emp id whom u delete.");
        int id = get();
        for (int i = 0; i < aa.size(); i++) {
            Emp jj = aa.get(i);
            if (jj.empid == id) {
                System.out.println("Employee is deleted.");
                Emp ll = aa.remove(i);
                System.out.println(ll);
                break;
            }
        }
    }

    public static void update() {
        System.out.println("Enter the emp id whom u update.");
        int id = get();
        for (int i = 0; i < aa.size(); i++) {
            Emp jj = (Emp)aa.get(i);
            if (jj.empid == id) {
                System.out.println("Employee name is updated.");
                System.out.println("Enter employee name");
                sc.nextLine(); // consume leftover newline
                jj.empname = sc.nextLine();
                break;
            }
        }
    }
}
