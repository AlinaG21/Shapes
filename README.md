using System;

namespace ConsoleApp15
{
    class Program
    {
        static void Main(string[] args)
        {
        Start:
            Console.WriteLine("What shapes do you want ?: ");
            Console.WriteLine("square");
            Console.WriteLine("circle");
            Console.WriteLine("rectangle");
            Console.WriteLine("triangle");
            Console.WriteLine("----------------------------------------------------------------------");



            string Kujund = Console.ReadLine();

            switch (Kujund)


            {


                case "square":
                    int squareSize;

                    Console.WriteLine("Enter the size of the square: ");
                    squareSize = Int32.Parse(Console.ReadLine());

                    for (int row = 1; row <= squareSize; row++)
                    {
                        for (int column = 1; column < squareSize; column++)
                        {
                            string string1;

                            string1 = (row == column || row + column == squareSize + 1) ? "*" : "*";



                            Console.Write(string1);

                        }
                        Console.WriteLine();

                    }
                    int squareSide = squareSize;

                    int Circumference = 4 * squareSide;
                    int Area = squareSide * squareSide;

                    Console.WriteLine("The circumference is {0} and the Area is {1} units ", Circumference, Area);


                Decide1:
                    Console.WriteLine("Do you want to enter a new shape- Yes, No?");
                    string UserDecition = Console.ReadLine();

                    switch (UserDecition.ToUpper())
                    {
                        case "YES":
                            goto Start;
                        case "NO":
                            break;
                        default:
                            Console.WriteLine("Wrong answer, please try again", UserDecition);
                            goto Decide1;
                    }

                    break;

                case "circle":
                    {
                        int circleSize;

                        Console.WriteLine("Enter circle size: ");
                        circleSize = Int32.Parse(Console.ReadLine());

                        Action<int, int> write = (xp, yp) => { Console.SetCursorPosition(xp, yp); Console.Write("*"); };

                        int centerX = 20, centerY = 10, radius = 8, x = -radius;
                        while (x < radius)
                        {
                            var y = (int)Math.Floor(Math.Sqrt(radius * radius - x * x));

                            write(x + centerX, y + centerY);
                            y = -y;
                            write(x + centerX, y + centerY);
                            x++;
                        }


                    Decide2:
                        Console.WriteLine("Do you want to enter a new shape- Yes, No?");
                        string UserDecition2 = Console.ReadLine();

                        switch (UserDecition2.ToUpper())
                        {
                            case "YES":
                                goto Start;
                            case "NO":
                                break;
                            default:
                                Console.WriteLine("Wrong answer, please try again", UserDecition2);
                                goto Decide2;
                        }




                    }


                    break;


                case "rectangle":

                    {

                        Console.WriteLine("Enter the height of the rectangle: ");
                        int height = int.Parse(Console.ReadLine());

                        Console.WriteLine("Internal Rectangle Width: ");
                        int width = int.Parse(Console.ReadLine());


                        for (int j = 0; j < height; j++)
                        {
                            for (int i = 0; i < width; i++)
                            {

                                Console.Write("*");

                            }
                            Console.WriteLine();
                        }

                        int rectangleCircumference = (height + width) * 2;
                        int rectangleArea = height * width;

                        Console.WriteLine("The circumference is {0} and the Area is {1} units ", rectangleCircumference, rectangleArea);
                    }

                Decide:
                    Console.WriteLine("Do you want to enter a new shape- Yes, No?");
                    string UserDecition1 = Console.ReadLine();

                    switch (UserDecition1.ToUpper())
                    {
                        case "YES":
                            goto Start;
                        case "NO":
                            break;
                        default:
                            Console.WriteLine("Wrong answer, please try again", UserDecition1);
                            goto Decide;
                    }

                    break;



                case "triangle":
                    {

                        Console.Write("Enter the height of the triangle: ");
                        int height = int.Parse(Console.ReadLine());



                        for (int i = 0; i < height; i++)
                        {
                            for (int j = 0; j <= i; j++)
                            {
                                Console.Write("*");
                            }

                            Console.WriteLine();


                        }
                         
                    Decide3:
                        Console.WriteLine("Do you want to enter a new shape- Yes, No?");
                        string UserDecition3 = Console.ReadLine();

                        switch (UserDecition3.ToUpper())
                        {
                            case "YES":
                                goto Start;
                            case "NO":
                                break;
                            default:
                                Console.WriteLine("Wrong answer, please try again", UserDecition3);
                                goto Decide3;
                        }




                        break;
                    }


            }


        }
    }
}

   
