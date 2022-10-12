uusing System;
using System.Collections.Generic;
using System.Linq;

namespace Assignment3
{
    class Student
    { //float gpa; // String Name;
        //public int [] project { get; set; }

        public int[] project = new int[2];
       // public int marks { get; set; }

        public string Name { get; set; }//getter setter

        public float gpa { get; set; }
        public override string ToString() //override to string 
        {
            return string.Format("Name: {0} GPA:{1}", Name, gpa);
        }

    }
    class Program
    {
        static void Main(string[] args)
        {

            List<Student> studList = new List<Student>//hard coded information
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
            foreach (Student s in studList) //filtered list 
            {
                if (s.gpa > 3.00)
                {
                    // filtered.add(word);
                    candidatelist = studList.ToList();
                    Console.WriteLine("Student whoes  gpa is greater than 3: {0} - {1} ", s.Name, s.gpa);
                }
            }
            //task3random.Next(10,50)
           
            Random rnd = new Random();
            candidatelist[0].project=new int [2];//array of 2 project1 and project2
            for (int i = 0; i < candidatelist.Count;i++ )
            {
                candidatelist[i].project = new int[2];//array of 2 project1 and project2
                int mark = rnd.Next(80, 100);
                //Console.WriteLine(mark);
                candidatelist[i].project[0] = mark;
                mark = rnd.Next(80, 100);
                //Console.WriteLine(mark);
                candidatelist[i].project[1] = mark;

                
            } 
          

            //task4
            //students whose score greater than 90 %
           List<Student> newcandidatelist = new List<Student>();
           for (int i = 0; i < candidatelist.Count; i++)
            {
                double sum = candidatelist[i].project[0] + candidatelist[i].project[1];//CALCULATE MARKS COLLECTIVELY
                sum = sum / 200;
                sum = sum * 100;
                if(sum>90)
                {
                    newcandidatelist.Add(candidatelist[i]);
                    //Console.WriteLine(newcandidatelist[i].Name);
                }
               
            }

            Console.WriteLine("task4");
            foreach (Student a in newcandidatelist)
            {
                Console.WriteLine("studen with greater 90%:" + a);
            }
            
            //task5
            Dictionary<string, List<Student>> numberNames = new Dictionary<string, List<Student>>();
            numberNames.Add("Rawalpindi", new List<Student>());//assign randomly 3 students cities rawalapindi
            numberNames.Add("Lahore", new List<Student>());//assign randomly 3 students cities lahore
            numberNames.Add("Jhang", new List<Student>());//assign randomly 3 students cities jhang
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
            var rawalpindiStudents = numberNames["Rawalpindi"];
            rawalpindiStudents.ForEach(x => Console.WriteLine("candidate who live in rawalpindi "+x));

            Console.ReadLine();


        }
    }
}
