using System;
using System.Collections.Generic;
using System.Linq;

namespace A3
{
    class Student
    {
        //float gpa;
        // String Name;[
        public int[] project { get; set; }
        

        public int marks { get; set; }
        public string Name { get; set; }
        public float gpa { get; set; }
      public override string  ToString( )
        {
           return  string.Format("Name: {0} GPA:{1}", Name, gpa);
        }
       
    }
    class Program
    {
        static void Main(string[] args)
        {

            List<Student> studList = new List<Student>
            {
                 new Student { Name = "kami",   gpa = 3.10f },
                 new Student { Name = "tomi",   gpa = 3.20f},
                 new Student { Name = "bilal",  gpa = 3.30f},
                 new Student { Name = "ramsha", gpa = 3.40f},
                 new Student { Name = "timi",   gpa = 3.70f},
                 new Student { Name = "pasha",  gpa = 3.60f},
                 new Student { Name = "palwisha",gpa = 3.80f},
                 new Student { Name = "dania",  gpa = 3.43f},
                 new Student { Name = "hassaan",gpa = 3.00f},
                 new Student { Name = "tayaba", gpa = 3.44f},
                 new Student { Name = "noor",   gpa = 3.45f},
                 new Student { Name = "rani",   gpa = 2.330f},
                 new Student { Name = "tayai",  gpa = 2.66f},
                 new Student { Name = "Chand",  gpa = 2.50f},
                 new Student { Name = "Mahesh", gpa = 2.60f},
                 new Student { Name = "lamb",   gpa = 2.90f}
            };

            //List<Student> filteredList = studList.Where(x => x.gpa >3.00).ToList();
            //task2 filter the students whose gpa greater than 3
            List<Student> candidatelist = new List<Student>();
            foreach (Student s in studList)
            {
                if (s.gpa > 3.00)
                {
                    // filtered.add(word);
                     candidatelist = studList.ToList();
                    Console.WriteLine("Student: {0} - {1} ", s.Name, s.gpa);
                }
            }
            //task3random.Next(10,50)
            //project[0] = random.Next(10, 50);
            //candidatelist.Add(project[0]);
            //task5
            Dictionary<string, List<Student>> numberNames = new Dictionary<string, List<Student>>();
            numberNames.Add("Rawalpindi",new List<Student> ());
            numberNames.Add("Lahore",new List<Student> ());
            numberNames.Add("Jhang", new List<Student>());
            numberNames["Rawalpindi"].Add(candidatelist[0]);
            numberNames["Rawalpindi"].Add(candidatelist[1]);
            numberNames["Rawalpindi"].Add(candidatelist[2]);
            numberNames["Lahore"].Add(candidatelist[3]);
            numberNames["Lahore"].Add(candidatelist[4]);
            numberNames["Lahore"].Add(candidatelist[5]);
            numberNames["Jhang"].Add(candidatelist[6]);
            numberNames["Jhang"].Add(candidatelist[7]);
            numberNames["Jhang"].Add(candidatelist[8]);
            numberNames["Rawalpindi"].Add(candidatelist[9]);
           var rawalpindiStudents= numberNames["Rawalpindi"];
            rawalpindiStudents.ForEach(x => Console.WriteLine(x));

            Console.ReadLine();
           

        }
    }
}
