
using System;
using System.Collections.Generic;
using System.Linq;

namespace MaxElementColor
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.Write("Enter the value of n: ");
            int n = Convert.ToInt32(Console.ReadLine());

            int[,] matrix = new int[n, n];
            List<int> maxElements = new List<int>();

            Random random = new Random();

            for (int i = 0; i < n; i++)
            {
                for (int j = 0; j < n; j++)
                {
                    matrix[i, j] = random.Next(-99, 100);
                    Console.Write(matrix[i, j] + "t");

                    if (j == 0 || Math.Abs(matrix[i, j]) > Math.Abs(maxElements[i]))
                    {
                        maxElements.Add(matrix[i, j]);
                    }
                }
                Console.WriteLine();
            }

            int minMaxElement = maxElements.Min();

            Console.WriteLine("nMax elements in each row:");
            for (int i = 0; i < maxElements.Count; i++)
            {
                if (maxElements[i] == minMaxElement)
                {
                    Console.ForegroundColor = ConsoleColor.Red;
                }
                Console.Write(maxElements[i] + " ");
                Console.ResetColor();
            }

            Console.WriteLine("nMin max element in the vector: " + minMaxElement);
        }
    }
}
