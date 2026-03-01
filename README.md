# UNIDAD-3-PRACTICA-1
using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        List<string> mayores = new List<string>();
        List<string> menores = new List<string>();

        Console.Write("Ingrese la cantidad de personas: ");
        int cantidad = int.Parse(Console.ReadLine());

        for (int i = 0; i < cantidad; i++)
        {
            Console.Write("\nNombre: ");
            string nombre = Console.ReadLine();

            int edad = PedirEdad(); // FUNCIÓN 1

            if (EsMayorDeEdad(edad)) // FUNCIÓN 2
                mayores.Add(nombre);
            else
                menores.Add(nombre);
        }

        MostrarResultados(mayores, menores); // PROCEDIMIENTO
    }

    // ================= FUNCIONES =================

    // Función que valida la edad (TIENE RETORNO)
    static int PedirEdad()
    {
        int edad;

        do
        {
            Console.Write("Edad: ");
            edad = int.Parse(Console.ReadLine());

            if (edad < 0)
                Console.WriteLine("Edad inválida. Intente nuevamente.");

        } while (edad < 0);

        return edad;
    }

    // Función que determina si es mayor de edad
    static bool EsMayorDeEdad(int edad)
    {
        return edad >= 18;
    }

    // ================= PROCEDIMIENTO =================

    // Procedimiento (void → sin retorno)
    static void MostrarResultados(List<string> mayores, List<string> menores)
    {
        Console.WriteLine("\n--- MAYORES DE EDAD ---");
        foreach (string persona in mayores)
            Console.WriteLine(persona);

        Console.WriteLine("\n--- MENORES DE EDAD ---");
        foreach (string persona in menores)
            Console.WriteLine(persona);
    }
}
