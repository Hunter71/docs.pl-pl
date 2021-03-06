---
title: Korzystanie z wariancji w interfejsach dla kolekcji (C#)
ms.date: 07/20/2015
ms.assetid: a44f0708-10fa-4c76-82cd-daa6e6b31e8e
ms.openlocfilehash: 7f1c44ecc831a7eb35541a432bc776c512bd10a3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="using-variance-in-interfaces-for-generic-collections-c"></a>Korzystanie z wariancji w interfejsach dla kolekcji (C#)
Interfejs kowariantnego umożliwia jego metody do zwrócenia więcej typów pochodnych niż określone w interfejsie. Interfejs kontrawariantnego umożliwia jego metody zaakceptować parametry typu mniej pochodnego niż warunki określone w interfejsie.  
  
 W programie .NET Framework 4, kilka istniejących interfejsów stał się kowariantnego i kontrawariantny. Obejmują one <xref:System.Collections.Generic.IEnumerable%601> i <xref:System.IComparable%601>. Dzięki temu można ponownie użyć metody, które pracują z kolekcji typów podstawowych, kolekcji typów pochodnych.  
  
 Aby uzyskać listę interfejsów typu variant w programie .NET Framework, zobacz [wariancje w interfejsach (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).  
  
## <a name="converting-generic-collections"></a>Konwertowanie na kolekcje ogólne  
 Poniższy przykład przedstawia zalet obsługę Kowariancja w <xref:System.Collections.Generic.IEnumerable%601> interfejsu. `PrintFullName` Metoda przyjmuje Kolekcja `IEnumerable<Person>` typu jako parametr. Jednak można użyć ponownie go z kolekcji `IEnumerable<Employee>` typu, ponieważ `Employee` dziedziczy `Person`.  
  
```csharp  
// Simple hierarchy of classes.  
public class Person  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
}  
  
public class Employee : Person { }  
  
class Program  
{  
    // The method has a parameter of the IEnumerable<Person> type.  
    public static void PrintFullName(IEnumerable<Person> persons)  
    {  
        foreach (Person person in persons)  
        {  
            Console.WriteLine("Name: {0} {1}",  
            person.FirstName, person.LastName);  
        }  
    }  
  
    public static void Test()  
    {  
        IEnumerable<Employee> employees = new List<Employee>();  
  
        // You can pass IEnumerable<Employee>,   
        // although the method expects IEnumerable<Person>.  
  
        PrintFullName(employees);  
  
    }  
}  
```  
  
## <a name="comparing-generic-collections"></a>Porównywanie kolekcji ogólnych  
 Poniższy przykład przedstawia świadczenia pomocy technicznej kontrawariancja w <xref:System.Collections.Generic.IComparer%601> interfejsu. `PersonComparer` Klasa implementuje `IComparer<Person>` interfejsu. Jednak można ponownie użyć tej klasy, aby porównać sekwencję obiektów `Employee` typu, ponieważ `Employee` dziedziczy `Person`.  
  
```csharp  
// Simple hierarchy of classes.  
public class Person  
{  
    public string FirstName { get; set; }  
    public string LastName { get; set; }  
}  
  
public class Employee : Person { }  
  
// The custom comparer for the Person type  
// with standard implementations of Equals()  
// and GetHashCode() methods.  
class PersonComparer : IEqualityComparer<Person>  
{  
    public bool Equals(Person x, Person y)  
    {              
        if (Object.ReferenceEquals(x, y)) return true;  
        if (Object.ReferenceEquals(x, null) ||  
            Object.ReferenceEquals(y, null))  
            return false;              
        return x.FirstName == y.FirstName && x.LastName == y.LastName;  
    }  
    public int GetHashCode(Person person)  
    {  
        if (Object.ReferenceEquals(person, null)) return 0;  
        int hashFirstName = person.FirstName == null  
            ? 0 : person.FirstName.GetHashCode();  
        int hashLastName = person.LastName.GetHashCode();  
        return hashFirstName ^ hashLastName;  
    }  
}  
  
class Program  
{  
  
    public static void Test()  
    {  
        List<Employee> employees = new List<Employee> {  
               new Employee() {FirstName = "Michael", LastName = "Alexander"},  
               new Employee() {FirstName = "Jeff", LastName = "Price"}  
            };  
  
        // You can pass PersonComparer,   
        // which implements IEqualityComparer<Person>,  
        // although the method expects IEqualityComparer<Employee>.  
  
        IEnumerable<Employee> noduplicates =  
            employees.Distinct<Employee>(new PersonComparer());  
  
        foreach (var employee in noduplicates)  
            Console.WriteLine(employee.FirstName + " " + employee.LastName);  
    }  
}  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Wariancje w interfejsach (C#)](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
