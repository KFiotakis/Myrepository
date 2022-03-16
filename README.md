# Myrepository
using System;
using System.Collections.Generic;
using System.Collections.ObjectModel;

//80
namespace Methods_List_class
{
    public class Program
    {
        public static void Main()
        {


            Custmr customer1 = new Custmr()
            {
                ID = 101,
                Name = "Mark",
                Salary = 4000
            };

            Custmr customer2 = new Custmr()
            {
                ID = 110,
                Name = "Pam",
                Salary = 7000
            };

            Custmr customer3 = new Custmr()
            {
                ID = 119,
                Name = "John",
                Salary = 5500
            };

            List<Custmr> listcustomers = new List<Custmr>(100);
            listcustomers.Add(customer1);
            listcustomers.Add(customer2);
            listcustomers.Add(customer3);

            //sets the capacity to the actual number of elements in the list, if that number is less than a threshold value
            Console.WriteLine("Capacity before trimming = " + listcustomers.Capacity);
            listcustomers.TrimExcess();
            Console.WriteLine("Capacity after trimming = " + listcustomers.Capacity);


            //returns a read-only wrapper for the current collection and used in order not to modified by the client
            ReadOnlyCollection<Custmr> readonlycustomers = listcustomers.AsReadOnly();
           Console.WriteLine("Items = " + readonlycustomers.Count);


            //returns true or false depending on whether if every element in th list matches the conditions defined
            Console.WriteLine("Are all salaries greater than 3000 = "+listcustomers.TrueForAll(x => x.Salary > 3000));
        }
    }
    public class Custmr
    {
        public int ID { get; set; }
        public string Name { get; set; }
        public int Salary { get; set; }

    }
}
