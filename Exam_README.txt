using System;

namespace ConsoleApp1
{
    internal abstract class Product
    {
        public string productId;
        public string name;
        public double price;
        public string producer;
        public Product(string productId, string name, double price, string producer)
        {
            this.productId = productId;
            this.name = name;
            this.price = price;
            this.producer = producer;
        }
        public abstract double computeTax();
    }
    internal class Book : Product
    {
        public Book(string productId, string name, double price, string producer)
            : base(productId, name, price, producer){ }
        public override double computeTax()
        { 
            return price * 0.08;
        }
    }
    internal class MobilePhone : Product
    {
        public MobilePhone(string productId, string name, double price, string producer)
            : base(productId, name, price, producer){ }
        public override double computeTax()
        {
            return price * 0.10;
        }
    }
    internal class Program
    {
        static void Main(string[] args)
        {
            Book book = new Book("B01", "Lost Horizon", 50.0, "James Hilton");
            MobilePhone phone = new MobilePhone("P01", "Z Flip3", 500.0, "Samsung");
            Book book2 = new Book("B02", "Life In Wood", 33.0, "Sarah John");
            MobilePhone phone2 = new MobilePhone("P02", "IPhone 10", 700.0, "Apple");
            Book book3 = new Book("B03", "One Piece", 12.0, "Eiichiro Oda");
            MobilePhone phone3 = new MobilePhone("P03", "IPhone 11", 1100.0, "Apple");

            Console.WriteLine($"The tax for book '{book.name}': {book.computeTax()}");
            Console.WriteLine($"The tax for '{phone.name}': {phone.computeTax()}");
            Console.WriteLine($"The tax for book '{book2.name}': {book2.computeTax()}");
            Console.WriteLine($"The tax for '{phone2.name}': {phone2.computeTax()}");
            Console.WriteLine($"The tax for book '{book3.name}': {book3.computeTax()}");
            Console.WriteLine($"The tax for '{phone3.name}': {phone3.computeTax()}");

            Console.ReadLine();
        }
    }
}
