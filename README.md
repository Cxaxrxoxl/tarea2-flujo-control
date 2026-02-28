# Sistema de Registro y Evaluación de Estudiantes
Actividad_2_Flujo_de_Control

    class Program
    {
        static void Main()
        {
            int cantidad;

            
            while (true)
            {
                Console.Write("Ingrese la cantidad de estudiantes: ");
                if (int.TryParse(Console.ReadLine(), out cantidad) && cantidad > 0)
                    break;

                Console.WriteLine("⚠ Debe ingresar un número entero válido mayor que 0.\n");
            }

            Console.WriteLine("\n---------------------------------------------------------------------------------------------------");
            Console.WriteLine("{0,-25} {1,8} {2,8} {3,8} {4,8} {5,10} {6,12}",
                "Estudiante", "P1", "P2", "P3", "P4", "PROMEDIO", "CONDICION");
            Console.WriteLine("---------------------------------------------------------------------------------------------------");

            for (int i = 1; i <= cantidad; i++)
            {
                Console.WriteLine($"\n--- Estudiante {i} ---");

                Console.Write("Nombre: ");
                string nombre = Console.ReadLine();

                double n1 = LeerNota("Nota 1");
                double n2 = LeerNota("Nota 2");
                double n3 = LeerNota("Nota 3");
                double n4 = LeerNota("Nota 4");

                double promedio = (n1 + n2 + n3 + n4) / 4;
                string estatus = promedio >= 70 ? "Aprobado" : "Reprobado";

                Console.WriteLine("{0,-25} {1,8:F2} {2,8:F2} {3,8:F2} {4,8:F2} {5,10:F2} {6,12}",
                    nombre, n1, n2, n3, n4, promedio, estatus);
            }

            Console.WriteLine("---------------------------------------------------------------------------------------------------");
        }

        static double LeerNota(string mensaje)
        {
            double nota;

            while (true)
            {
                Console.Write($"{mensaje}: ");
                if (double.TryParse(Console.ReadLine(), out nota) && nota >= 0 && nota <= 100)
                    return nota;

                Console.WriteLine("⚠ La nota debe estar entre 0 y 100.\n");
            }
        }
    }

<img width="1100" height="613" alt="Captura de pantalla 2026-02-27 224737" src="https://github.com/user-attachments/assets/23d5906d-ca89-478f-bb67-c3c065ae1ea8" />
<img width="1176" height="650" alt="Captura de pantalla 2026-02-27 224814" src="https://github.com/user-attachments/assets/1116a229-e0b7-4800-8ccb-23fd6f7b1938" />
