# Functions for my projects

Function for retrieving numbers from user:

```
int GetUserNumber()
{
    string s = Console.ReadLine()!;
    int res;

    while (!int.TryParse(s, out res))
    {
        Console.WriteLine($"Invalid number! Try again!");
        s = Console.ReadLine()!;
    }

    return res;
}
```

Same function, but with a lower bound:

```
int GetUserNumber(int lowerBound)
{
    string s = Console.ReadLine()!;
    int res;

    while (!int.TryParse(s, out res) || res < lowerBound)
    {
        Console.WriteLine($"Invalid number!\nMust be equal to or greater than {lowerBound}!\nTry again!");
        s = Console.ReadLine()!;
    }

    return res;
}
```

With lower and upper bounds:

```
int GetUserNumber(int lowerBound, int upperBound)
{
    string s = Console.ReadLine()!;
    int res;

    while (!int.TryParse(s, out res) || res < lowerBound || res > upperBound)
    {
        Console.WriteLine($"Invalid number!\nMust be between {lowerBound} and {upperBound} inclusive!\nTry again!");
        s = Console.ReadLine()!;
    }

    return res;
}
```

Function for printing an array:

```
void PrintArray(int[] array)
{
    if (array.Length == 0)
    {
        Console.WriteLine("An empty array");
        return;
    }

    int i = 0;
    for (; i < array.Length - 1; i++)
        Console.Write($"{array[i]}, ");

    Console.WriteLine($"{array[i]}");
}
```
