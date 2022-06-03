# Firman

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Threading;

namespace CobaThreads
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Mulai menghitung");
            Console.WriteLine();

            Thread tid1 = new Thread(new ThreadStart(MyThread.Thread1));
            Thread tid2 = new Thread(new ThreadStart(MyThread.Thread2));

            tid1.Start();
            tid2.Start();
        }
    }

    public class MyThread
    {

        public static void Thread1()
        {
            for (int i = 0; i < 10; i++)
            {
                Console.WriteLine("Ayam ke-{0}", i);
                Thread.Sleep(20);
            }
            Console.ReadKey();
        }

        public static void Thread2()
        {
            for (int i = 0; i < 10; i++)
            {
                Console.WriteLine("Bebek ke-{0}", i);
                Thread.Sleep(20);
            }
            Console.ReadKey();
        }
    }
}
