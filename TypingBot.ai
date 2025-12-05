using System;
using System.Collections.Generic;
using System.Linq;

namespace HackShowcase
{
    public class Program
    {
        public static void Main()
        {
            // 1. Null-coalescing with throw
            var user = new User("Gray");
            Console.WriteLine($"User created: {user.Name}");

            // 2. Pattern matching with switch expressions
            var inputs = new object[] { 42, -7, "Copilot", DateTime.Now, 3.14 };
            foreach (var input in inputs)
            {
                Console.WriteLine(Describe(input));
            }

            // 3. LINQ hack: chaining queries with deferred execution
            var numbers = Enumerable.Range(1, 20);
            var evensSquared = numbers
                .Where(n => n % 2 == 0)
                .Select(n => n * n)
                .ToList();

            Console.WriteLine("Even squares: " + string.Join(", ", evensSquared));

            // 4. Local functions + expression-bodied members
            Console.WriteLine($"Factorial(5) = {Factorial(5)}");

            // 5. Span<T> hack: blazing fast slicing without allocations
            var text = "Grow a Brainrot Mythos";
            var span = text.AsSpan();
            var slice = span.Slice(5, 9); // "a Brainro"
            Console.WriteLine($"Span slice: '{slice.ToString()}'");

            // 6. Dictionary initialization hack with index initializers
            var dict = new Dictionary<string, int>
            {
                ["apples"] = 5,
                ["bananas"] = 10,
                ["oranges"] = 3
            };
            Console.WriteLine($"Bananas count: {dict["bananas"]}");

            // 7. Records hack: immutable data with built-in equality
            var p1 = new Person("Cookie", 25);
            var p2 = new Person("Cookie", 25);
            Console.WriteLine($"Records equal? {p1 == p2}");

            // 8. Deconstruction hack
            var (name, age) = p1;
            Console.WriteLine($"Deconstructed: {name}, {age}");
        }

        // Expression-bodied method with pattern matching
        static string Describe(object input) => input switch
        {
            int n when n > 0 => $"Positive integer: {n}",
            int n => $"Non-positive integer: {n}",
            string s => $"String of length {s.Length}: \"{s}\"",
            DateTime dt => $"DateTime: {dt:dddd, MMMM d yyyy}",
            double d => $"Double value: {d:F2}",
            _ => "Unknown type"
        };

        // Local function hack: recursive factorial
        static int Factorial(int n)
        {
            int Inner(int x) => x <= 1 ? 1 : x * Inner(x - 1);
            return Inner(n);
        }
    }

    // Null-coalescing with throw hack
    public class User
    {
        public string Name { get; }
        public User(string name) => Name = name ?? throw new ArgumentNullException(nameof(name));
    }

    // Record hack
    public record Person(string Name, int Age);
}
