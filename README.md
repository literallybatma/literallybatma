using System;

class PrimeNumberCheck
{
    static bool IsPrime(int number)
    {
        if (number <= 1) return false;
        if (number == 2) return true;
        if (number % 2 == 0) return false;

        var boundary = (int)Math.Floor(Math.Sqrt(number));

        for (int i = 3; i <= boundary; i += 2)
        {
            if (number % i == 0) 
                return false;
        }

        return true;
    }

    static void Main()
    {
        Console.Write("Enter a number to check if it's prime: ");
        if(int.TryParse(Console.ReadLine(), out int number))
        {
            bool isPrime = IsPrime(number);
            if(isPrime)
            {
                Console.WriteLine($"{number} is a prime number.");
            }
            else
            {
                Console.WriteLine($"{number} is not a prime number.");
            }
        }
        else
        {
            Console.WriteLine("Please enter a valid integer.");
        }
    }
}
