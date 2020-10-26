# Lab.nr1
# Laboratorul nr.1 APA
#Prima metoda

#include <iostream>
#include <chrono>
using namespace std::chrono;
using namespace std;
auto start = high_resolution_clock::now();
int fib1(int n)
{
    if(n < 2)
    {
        return n;
    }
    else
    {
        return fib1(n - 1) + fib1(n - 2);
    }
}

    int main()
    {
        int n = 30;
        cout<<fib1(n) << endl;
        auto stop = high_resolution_clock::now();
        auto duration = duration_cast<microseconds>(stop - start);
        cout << "Timpul: " << duration.count() << " ms" << endl;
    }

#Metoda 2

#include <iostream>
#include <chrono>
using namespace std::chrono;
using namespace std;
auto start = high_resolution_clock::now();
int fib2(int n)
{
    int i = 1;
    int j = 0;

        for(int k = 1; k <= n; k++)
        {
            j = i + j;
            i = j - i;
        }
        return j;
}

    int main()
    {
        int n = 30;
        cout<<fib2(n) << endl;
        auto stop = high_resolution_clock::now();
        auto duration = duration_cast<microseconds>(stop - start);
        cout << "Timpul: " << duration.count() << " ms" << endl;
    }

#Metoda 3

#include <iostream>
#include <chrono>
using namespace std::chrono;
using namespace std;
auto start = high_resolution_clock::now();
int fib3(int n)
{
    int i = 1;
    int j = 0;
    int k = 0;
    int h = 1;
    int t;

        while(n > 0)
        {
            if(n % 2 != 0)
            {
                t = j * h;
                j = i * h + j * k + t;
                i = i * k + t;
            }
            t = h * h;
            h = 2 * k * h + t;
            k = k * k + t;
            n = n / 2;
        }
        return j;
}

    int main()
    {
        int n = 9;
        cout<<fib3(n) << endl;
        auto stop = high_resolution_clock::now();
        auto duration = duration_cast<microseconds>(stop - start);
        cout << "Timpul: " << duration.count() << " ms" << endl;
    }
