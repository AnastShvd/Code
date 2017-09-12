# Code
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Шифр_Цезаря
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Enter text");
            string s = Console.ReadLine();
            char[] smas = s.ToCharArray();
            Console.WriteLine("Enter 1st key");
            int k1 = Convert.ToInt32(Console.ReadLine());
            Console.WriteLine("Enter 2nd key");
            int k2 = Convert.ToInt32(Console.ReadLine());


            string alf = "abcdefghijklmnopqrstuvwxyz";
            char[] abc = alf.ToCharArray();
            string code = "";
            int m = abc.Length;
            for (int i = 0; i < smas.Length; i++)
            {
                for (int j = 0; j < abc.Length; j++)
                {
                    if (s[i] == alf[j])
                    {
                        if ((s[i]==0) || (s[i] % 2 == 0))
                        {
                            int temp = j + k1;
                            while (temp >= m)
                            temp = temp - m;
                            code = code + alf[temp];

                        }
                        else
                        {
                            int temp = j + k2;
                            while (temp >= m)
                            temp = temp - m;
                            code = code + alf[temp];

                        }
                    }
                
                }

            }
            Console.WriteLine(code);
            Console.ReadLine();
        }
    }
}


