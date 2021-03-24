#include <stdio.h>
#include <math.h>
#define e 2.718281 // Exponent
#define pi 3.14159265359 // Pi
#define y 61 // Length of y-axis 
#define x 61 // Length of x-axis 

// Function for calculate formula
float fun(float c)
{
    return pow(e, -c) * sin(c); // You can change formula here 
}

// Function for print graph
void printGr(char gr[y][x], float a, float b)
{
    for(int i = 0; i < y; i++)
    {
        for(int j = 0; j < x; j++)
        {
            printf("%c", gr[i][j]);
        }
        printf("\n");
    }
}

// Function for making y and x axis
void makeGr(char gr[y][x], float a, float b)
{
    if(a > 0 || b < 0)
    {
        for(int i = 0; i < y; i++)
        {
            for(int j = 0; j < x; j++)
            {
                if(i == y / 2)
                    gr[i][j] = '-';
                else
                    gr[i][j] = '1';
            }
        }
    }
    else
    {
        float n = a;
        float h = (b - a) / x;
        for(int i = 0; i < y; i++)
        {
            n = a;
            for(int j = 0; j < x; j++)
            {
                if(i == y / 2)
                    gr[i][j] = '-';
                else if((n < 0 && n + h > 0) || n == 0)
                    gr[i][j] = '!';
                else
                    gr[i][j] = ' ';
                n += h;
            }
        }
    }
}

// Function for calculate point in right position
void finalGr(char gr[y][x], float a, float b)
{
    float n = a;
    float h = (b - a) / y;        
    for(int i = 0; i < y; i++)
    {
        n = a;
        for(int j = 0; j < x; j++)
        {
            if(fun(n) < ((y / 2) - i) * h && fun(n) > ((y / 2) - i - 1) * h)
                gr[i][j] = '*';
            n += h;
        }
    }
}

int main()
{
    float a, b;
    char gr[y][x];
    printf("Please input a and b: ");
    scanf("%f %f", &a, &b);
    printf("Segment y = %f\n Segment x = %f\n", (b - a) / y, (b - a) / x);
    makeGr(gr, a, b);
    finalGr(gr, a, b);
    printGr(gr, a, b);
    return 0;
}
