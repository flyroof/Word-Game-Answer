# Word-Game-Answer
By Blaga. 

I use C# as a programming language. 

Here is the program for the task "Word Game" from Hack Bulgaria:

using System;

using System.Collections.Generic;

using System.Linq;

using System.Text;

using System.Threading.Tasks;


namespace ConsoleApplication3
{   

 
    class Program
    {
       
        static void Main(string[] args)
        {
            string[] table = Console.ReadLine().Split(' ').ToArray();
            int col = table[0].Length;
            int line = table.Count();
            string word = Console.ReadLine();
            int wc = 0;
            for (int i = 0; i < line; i++)
            {
                Console.WriteLine(table[i]);
            }
            for (int i = 0; i < col; i++)
            {
                for (int j=0; j< line; j++)
                {
                    
                    for (int del = 0; del < 6; del++)
                    {
                        int x = i;
                        int y = j;
                        int check = 0;
                        for (int k = 0; k < word.Count(); k++)
                        {


                            if (x>=0 && x < col && y>=0 && y < line)
                            {

                                if (word[k] == table[y][x])
                                {
                                    check++;
                                }
                                ;
                            }

                           switch (del)
                           {
                               case 0: x++; break;
                               case 1: y++; break;
                               case 2: x--; break;
                               case 3: y--; break;
                               case 4: x++; y++; break;
                               case 5: x--; y--; break;

                           }
                           if (check == word.Count()) { wc++; }
                           
                        }
                    }
                }

            }
            Console.WriteLine(wc);
        }
    }
}
