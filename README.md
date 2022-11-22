![10](https://user-images.githubusercontent.com/93587823/203218507-aa22377d-e2a3-435b-853b-20e2348f1629.png)
![20](https://user-images.githubusercontent.com/93587823/203218522-a5174673-0d0b-4e21-b8a4-c24654ea03a9.png)

## Program:
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.SceneManagement;

public class CubeProg : MonoBehaviour
{
    Rigidbody rb;
    // Start is called before the first frame update
    void Start()
    {
        rb = GetComponent<Rigidbody>();
        
        
    }

    // Update is called once per frame
    void Update()
    {
        if(Input.GetKeyDown(KeyCode.R))
        {
            SceneManager.LoadScene("myscene");
        }
         
    }
    private void OnCollisionEnter(Collision collision)
    {
        if (collision.gameObject.tag == "Sphere")
            Destroy(collision.gameObject);
    }
}


using System;
namespace hello
{
    public class vehicle
    {
        public vehicle()
        {
            Console.Write("Tyre is attached");
        }

    }
    public class car : vehicle
    {
        public void display()
        {
            Console.WriteLine("to car");
        }
    }
    public class scooter : vehicle
    {
        public void display()
        {
            Console.WriteLine("to scooter");
        }
    }
    public class program
    {
        public static void Main(string[] args)
        {
            car car = new car();
            car.display();
            Console.WriteLine();
            scooter scooter = new scooter();
            scooter.display();
            Console.ReadKey();
        }
    }
}
'''


