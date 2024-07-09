<a name="readme-top"></a>

<!--
HOW TO USE:
This is an example of how you may give instructions on setting up your project locally.

Modify this file to match your project and remove sections that don't apply.

REQUIRED SECTIONS:
- Table of Contents
- About the Project
  - Built With
  - Live Demo
- Getting Started
- Authors
- Future Features
- Contributing
- Show your support
- Acknowledgements
- License

OPTIONAL SECTIONS:
- FAQ

After you're finished please remove all the comments and instructions!
-->

<div align="center">
  <!-- You are encouraged to replace this logo with your own! Otherwise you can also remove it. -->

  <br/>

  <h3><b>Salary System test</b></h3>

</div>

<!-- PROJECT DESCRIPTION -->

# 📖 A Class example <a name="a wonderful mathamtics calculator"></a>

>  Java 

``package com.mycompany.salarysystem; ``

الحزمة (Package): يتم استخدام هذا السطر لتعريف الحزمة التي تنتمي إليها الشيفرة. الحزم تستخدم لتنظيم الفئات (classes) والواجهات (interfaces) بطريقة منظمة.

``import java.util.List; ``
``import java.util.Scanner; ``

الاستيراد (Import): يستورد هذا السطر واجهة List وفئة Scanner من مكتبة Java القياسية. List تُستخدم لإدارة قوائم من العناصر، وScanner تُستخدم لقراءة المدخلات من المستخدم.

``public class SalarySystem { ``

تعريف الفئة (Class Definition): يبدأ تعريف الفئة SalarySystem. هذه الفئة تحتوي على كافة المنطق البرمجي لنظام الرواتب

```
    private static List<Employee> employees;
    private static List<Department> departments;
    private static List<Salary> salaries;

```
متغيرات الفئة (Class Variables): تعريف ثلاث قوائم ثابتة (static)، واحدة لكل من الموظفين (employees)، والأقسام (departments)، والرواتب (salaries). هذه القوائم ستُستخدم لتخزين البيانات المُدارة بواسطة النظام

``    public static void main(String[] args) {``

الطريقة الرئيسية (Main Method): هذه هي نقطة الدخول للبرنامج. عندما يتم تشغيل البرنامج، يتم تنفيذ هذه الطريقة.

```        employees = FileManager.readEmployees();
        departments = FileManager.readDepartments();
        salaries = FileManager.readSalaries();
```
قراءة البيانات (Data Reading): يتم قراءة بيانات الموظفين والأقسام والرواتب من مصدر البيانات (مثل ملفات) باستخدام طرق من فئة FileManager.

``        Scanner scanner = new Scanner(System.in);``

إنشاء كائن Scanner (Scanner Object): يتم إنشاء كائن Scanner لقراءة المدخلات من المستخدم عبر لوحة المفاتيح.

``        while (true) {``

حلقات التكرار (Loop): حلقة while تبدأ هنا وتستمر إلى أجل غير مسمى حتى يتم تنفيذ أمر الخروج (System.exit(0)).

```            System.out.println("Menu:");
            System.out.println("1. View Employees");
            System.out.println("2. View Departments");
            System.out.println("3. View Salaries");
            System.out.println("4. Add Employee");
            System.out.println("5. Add Department");
            System.out.println("6. Add Salary");
            System.out.println("7. Search Employee by ID");
            System.out.println("8. Search Department by ID");
            System.out.println("9. Search Salary by Employee ID");
            System.out.println("10. Exit");
            System.out.print("Enter choice: ");
```
عرض القائمة (Menu Display): يتم عرض قائمة من الخيارات على الشاشة ليختار المستخدم من بينها.

```            int choice = scanner.nextInt();
            scanner.nextLine(); // consume newline
```

قراءة اختيار المستخدم (User Input): يتم قراءة اختيار المستخدم وتخزينه في متغير choice. ثم يتم استهلاك السطر الجديد (newline) المتبقي في دفق الإدخال.

``            switch (choice) {``

بيان التبديل (Switch Statement): يبدأ هنا بيان التبديل الذي يتعامل مع اختيار المستخدم.

   ```             case 1:
                    viewEmployees();
                    break;
```

عرض الموظفين (View Employees): إذا كان اختيار المستخدم 1، يتم استدعاء طريقة viewEmployees() لعرض قائمة الموظفين.

```                case 2:
                    viewDepartments();
                    break;
```

عرض الأقسام (View Departments): إذا كان اختيار المستخدم 2، يتم استدعاء طريقة viewDepartments() لعرض قائمة الأقسام.


```                case 3:
                    viewSalaries();
                    break;
```
عرض الرواتب (View Salaries): إذا كان اختيار المستخدم 3، يتم استدعاء طريقة viewSalaries() لعرض قائمة الرواتب.

```                case 4:
                    addEmployee(scanner);
                    break;
```

إضافة موظف (Add Employee): إذا كان اختيار المستخدم 4، يتم استدعاء طريقة addEmployee(scanner) لإضافة موظف جديد، مع تمرير كائن Scanner لقراءة بيانات الموظف الجديد.

```                case 5:
                    addDepartment(scanner);
                    break;
```

إضافة قسم (Add Department): إذا كان اختيار المستخدم 5، يتم استدعاء طريقة addDepartment(scanner) لإضافة قسم جديد، مع تمرير كائن Scanner لقراءة بيانات القسم الجديد.

```                case 6:
                    addSalary(scanner);
                    break;
```
إضافة راتب (Add Salary): إذا كان اختيار المستخدم 6، يتم استدعاء طريقة addSalary(scanner) لإضافة راتب جديد، مع تمرير كائن Scanner لقراءة بيانات الراتب الجديد.

```
إ                case 7:
                    searchEmployeeById(scanner);
                    break;

```

البحث عن موظف بالمعرف (Search Employee by ID): إذا كان اختيار المستخدم 7، يتم استدعاء طريقة searchEmployeeById(scanner) للبحث عن موظف باستخدام معرفه، مع تمرير كائن Scanner لقراءة المعرف.

```                case 8:
                    searchDepartmentById(scanner);
                    break;
```

البحث عن قسم بالمعرف (Search Department by ID): إذا كان اختيار المستخدم 8، يتم استدعاء طريقة searchDepartmentById(scanner) للبحث عن قسم باستخدام معرفه، مع تمرير كائن Scanner لقراءة المعرف.

```                case 9:
                    searchSalaryByEmployeeId(scanner);
                    break;
```
البحث عن راتب باستخدام معرف الموظف (Search Salary by Employee ID): إذا كان اختيار المستخدم 9، يتم استدعاء طريقة searchSalaryByEmployeeId(scanner) للبحث عن راتب باستخدام معرف الموظف، مع تمرير كائن Scanner لقراءة المعرف.

```
                case 10:
                    FileManager.writeEmployees(employees);
                    FileManager.writeDepartments(departments);
                    FileManager.writeSalaries(salaries);
                    System.exit(0);
                    break;
```

حفظ البيانات وإنهاء البرنامج (Save Data and Exit): إذا كان اختيار المستخدم 10، يتم حفظ البيانات الحالية للموظفين والأقسام والرواتب باستخدام طرق FileManager، ثم يتم إنهاء البرنامج باستخدام System.exit(0).

```                default:
                    System.out.println("Invalid choice.");
            }
        }
    }
}
```

التعامل مع الاختيارات غير الصالحة (Invalid Choice): إذا كان اختيار المستخدم لا يتطابق مع أي حالة من الحالات المذكورة، يتم طباعة رسالة تفيد بأن الاختيار غير صالح.

```
private static void viewEmployees() {
    for (Employee employee : employees) {
        System.out.println(employee);
    }
}
```

عرض قائمة الموظفين (View Employees):

    هذه الطريقة تقوم بعرض جميع الموظفين في القائمة employees.
    تستخدم حلقة for-each للتكرار عبر جميع العناصر في قائمة employees وطباعة كل موظف.

    ```
    private static void viewDepartments() {
    for (Department department : departments) {
        System.out.println(department);
    }
}
```
عرض قائمة الأقسام (View Departments):

    هذه الطريقة تقوم بعرض جميع الأقسام في القائمة departments.
    تستخدم حلقة for-each للتكرار عبر جميع العناصر في قائمة departments وطباعة كل قسم.
    

    ```private static void viewSalaries() {
    for (Salary salary : salaries) {
        System.out.println(salary);
    }
}
```

عرض قائمة الرواتب (View Salaries):

    هذه الطريقة تقوم بعرض جميع الرواتب في القائمة salaries.
    تستخدم حلقة for-each للتكرار عبر جميع العناصر في قائمة salaries وطباعة كل راتب.

    ```private static void addEmployee(Scanner scanner) {
    System.out.print("Enter ID: ");
    String id = scanner.nextLine();
    System.out.print("Enter name: ");
    String name = scanner.nextLine();
    System.out.print("Enter position: ");
    String position = scanner.nextLine();
    System.out.print("Enter hire date: ");
    String hireDate = scanner.nextLine();
    System.out.print("Enter base salary: ");
    double baseSalary = scanner.nextDouble();
    System.out.print("Enter department ID: ");
    int departmentId = scanner.nextInt();
    scanner.nextLine(); // consume newline

    Employee employee = new Employee(id, name, position, hireDate, baseSalary, departmentId);
    employees.add(employee);
    FileManager.writeEmployees(employees);
}
```

إضافة موظف جديد (Add Employee):

    هذه الطريقة تقوم بإضافة موظف جديد إلى القائمة employees.
    تقوم بقراءة البيانات المختلفة للموظف من المستخدم مثل المعرف (id)، الاسم (name)، الوظيفة (position)، تاريخ التوظيف (hireDate)، الراتب الأساسي (baseSalary)، ومعرف القسم (departmentId).
    تنشئ كائن Employee جديد باستخدام البيانات المدخلة وتضيفه إلى القائمة employees.
    تقوم بحفظ القائمة المحدثة باستخدام طريقة FileManager.writeEmployees.

    ```

    private static void addDepartment(Scanner scanner) {
    System.out.print("Enter ID: ");
    String id = scanner.nextLine();
    System.out.print("Enter name: ");
    String name = scanner.nextLine();

    Department department = new Department(id, name);
    departments.add(department);
    FileManager.writeDepartments(departments);
}


```
    إضافة قسم جديد (Add Department):
        هذه الطريقة تقوم بإضافة قسم جديد إلى القائمة departments.
        تقوم بقراءة المعرف (id) والاسم (name) للقسم من المستخدم.
        تنشئ كائن Department جديد باستخدام البيانات المدخلة وتضيفه إلى القائمة departments.
        تقوم بحفظ القائمة المحدثة باستخدام طريقة FileManager.writeDepartments.

```

private static void addSalary(Scanner scanner) {
    System.out.print("Enter employee ID: ");
    String employeeId = scanner.nextLine();
    System.out.print("Enter month: ");
    String month = scanner.nextLine();
    System.out.print("Enter amount: ");
    double amount = scanner.nextDouble();
    System.out.print("Enter bonuses: ");
    double bonuses = scanner.nextDouble();
    scanner.nextLine(); // consume newline

    Salary salary = new Salary(employeeId, month, amount, bonuses);
    salaries.add(salary);
    FileManager.writeSalaries(salaries);
}
```
إضافة راتب جديد (Add Salary):

    هذه الطريقة تقوم بإضافة راتب جديد إلى القائمة salaries.
    تقوم بقراءة معرف الموظف (employeeId)، الشهر (month)، المبلغ (amount)، والمكافآت (bonuses) من المستخدم.
    تنشئ كائن Salary جديد باستخدام البيانات المدخلة وتضيفه إلى القائمة salaries.
    تقوم بحفظ القائمة المحدثة باستخدام طريقة FileManager.writeSalaries.



    ```
    private static void searchEmployeeById(Scanner scanner) {
    System.out.print("Enter Employee ID: ");
    String id = scanner.nextLine();
    for (Employee employee : employees) {
        if (employee.getId().equals(id)) {
            System.out.println(employee);
            return;
        }
    }
    System.out.println("Employee not found.");
}
```
البحث عن موظف باستخدام المعرف:

    تطلب الطريقة من المستخدم إدخال معرف الموظف (Employee ID).
    تتكرر الطريقة عبر قائمة الموظفين (employees) وتبحث عن الموظف الذي يتطابق معرفه (id) مع المعرف المدخل.
    إذا تم العثور على الموظف، يتم طباعته ويخرج من الطريقة (return).
    إذا لم يتم العثور على الموظف، تطبع رسالة "Employee not found".
    ```private static void searchDepartmentById(Scanner scanner) {
    System.out.print("Enter Department ID: ");
    String id = scanner.nextLine();
    for (Department department : departments) {
        if (department.getId().equals(id)) {
            System.out.println(department);
            return;
        }
    }
    System.out.println("Department not found.");
}
```

البحث عن قسم باستخدام المعرف:

    تطلب الطريقة من المستخدم إدخال معرف القسم (Department ID).
    تتكرر الطريقة عبر قائمة الأقسام (departments) وتبحث عن القسم الذي يتطابق معرفه (id) مع المعرف المدخل.
    إذا تم العثور على القسم، يتم طباعته ويخرج من الطريقة (return).
    إذا لم يتم العثور على القسم، تطبع رسالة "Department not found".

    ```private static void searchSalaryByEmployeeId(Scanner scanner) {
    System.out.print("Enter Employee ID: ");
    String employeeId = scanner.nextLine();
    boolean found = false;
    for (Salary salary : salaries) {
        if (salary.getEmployeeId().equals(employeeId)) {
            System.out.println(salary);
            found = true;
        }
    }
    if (!found) {
        System.out.println("Salary records not found for employee ID: " + employeeId);
    }
}
```
البحث عن راتب باستخدام معرف الموظف:

    تطلب الطريقة من المستخدم إدخال معرف الموظف (Employee ID).
    تتكرر الطريقة عبر قائمة الرواتب (salaries) وتبحث عن الرواتب التي تتطابق معرف الموظف (employeeId) مع المعرف المدخل.
    إذا تم العثور على أي رواتب، يتم طباعتها ويتم تعيين المتغير found إلى true.
    إذا لم يتم العثور على أي رواتب، تطبع رسالة "Salary records not found for employee ID: " متبوعة بمعرف الموظف المدخل.

    #كيفية عمل كل سطر:
    ```System.out.print("Enter Employee ID: ");
String id = scanner.nextLine();
```
تطلب من المستخدم إدخال المعرف وتقرأه باستخدام Scanner.

التكرار عبر القائمة:
```
for (Employee employee : employees) {
    if (employee.getId().equals(id)) {
        System.out.println(employee);
        return;
    }
}
```
تتكرر عبر كل عنصر في القائمة (employees في هذه الحالة).
تتحقق مما إذا كان المعرف المدخل يطابق معرف العنصر الحالي.
إذا كان هناك تطابق، تطبع العنصر وتخرج من الطريقة (return).

التعامل مع حالة عدم العثور على العنصر:
```System.out.println("Employee not found.");
```
إذا انتهت الحلقة دون العثور على تطابق، تطبع رسالة تفيد بأن العنصر لم يتم العثور عليه.
البحث عن الرواتب باستخدام معرف الموظف:

```boolean found = false;
for (Salary salary : salaries) {
    if (salary.getEmployeeId().equals(employeeId)) {
        System.out.println(salary);
        found = true;
    }
}
if (!found) {
    System.out.println("Salary records not found for employee ID: " + employeeId);
}
```

في حالة البحث عن الرواتب، يتم استخدام متغير found لتتبع ما إذا تم العثور على أي رواتب.
يتم تحديث found إلى true عند العثور على راتب مطابق.
بعد انتهاء الحلقة، إذا كان found لا يزال false، يتم طباعة رسالة تفيد بعدم العثور على سجلات الرواتب.

