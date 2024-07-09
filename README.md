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

