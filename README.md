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
namespace Autovechicle
{
    public class tyre
    {
        public tyre()
        {
            Console.WriteLine("Constructor tyre");
        }
        public virtual void Display()
        {
            Console.WriteLine("tyre");
        }
    }
    public class scooter : tyre
    {
        public scooter()
        {
            Console.WriteLine("Constructor scooter");
        }
        
        public override void Display()
        {
            base.Display();
            Console.WriteLine("scooter");
        }
    }

    public class car : tyre
    {
        public car()
        {
            Console.WriteLine("Constructor car");
        }
        public override void Display()
        {
            base.Display();
            Console.WriteLine("car");
        }
    }

    public class Program
    {
        public static void Main(string[] args)
        {
            car cd = new car();
            scooter cdd = new scooter();
            cd.Display();
            cdd.Display();
        }
    }
}
'''


