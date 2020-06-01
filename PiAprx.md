```c#
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Piaprx
{
    class Program
    {

        static void Main(string[] args)
        {
            Random rnd = new Random();

            float r = 200;

            int total = 0;
            int circle = 0;

            double recordPI = 0;

            for(int i = 0; i<10000; i++)
            {
                float x = rnd.Next(Convert.ToInt32(-r), Convert.ToInt32(r));
                float y = rnd.Next(Convert.ToInt32(-r), Convert.ToInt32(r));
                total++;


                double d = Convert.ToDouble(x) * Convert.ToDouble(x) + Convert.ToDouble(y) * Convert.ToDouble(y);
                if(d< Convert.ToDouble(r)* Convert.ToDouble(r))
                {
                    circle++;
                }
                else
                {

                }

                double pi = Convert.ToDouble(4) * (Convert.ToDouble(circle) / Convert.ToDouble(total));
                double recordDiff = Math.Abs(Math.PI - recordPI);
                double diff = Math.Abs(Math.PI - pi);
                if (diff < recordDiff)
                {
                    recordDiff = diff;
                    recordPI = pi;
                    Console.WriteLine(recordPI);
                }
            }

            

        }
    }
}
```

