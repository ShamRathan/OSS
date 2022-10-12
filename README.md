# OSS

2-d)
```
    #include<stdio.h>  
    #include<conio.h>  
      
    void main()  
    {  
   
        int i, NOP, sum=0,count=0, y, quant, wt=0, tat=0, at[10], bt[10], temp[10];  
        float avg_wt, avg_tat;  
        printf(" Enter number of process: ");  
        scanf("%d", &NOP);  
        y = NOP; 
   
    for(i=0; i<NOP; i++)  
    {  
    printf("\n P[%d]\n", i+1);  
    printf(" Arrival time: \t"); 
    scanf("%d", &at[i]);  
    printf(" \nBurst time: \t"); 
    scanf("%d", &bt[i]);  
    temp[i] = bt[i];  
    }  

    printf("Enter the Time Quantum: \t");  
    scanf("%d", &quant);  
 
    printf("\n Process No \t\t Burst Time \t\t TAT \t\t Waiting Time ");  
    for(sum=0, i = 0; y!=0; )  
    {  
    if(temp[i] <= quant && temp[i] > 0) 
    {  
        sum = sum + temp[i];  
        temp[i] = 0;  
        count=1;  
        }     
        else if(temp[i] > 0)  
        {  
            temp[i] = temp[i] - quant;  
            sum = sum + quant;    
        }  
        if(temp[i]==0 && count==1)  
        {  
            y--; 
            printf("\nProcess No[%d] \t\t %d\t\t\t\t %d\t\t\t %d", i+1, bt[i], sum-at[i], sum-at[i]-bt[i]);  
            wt = wt+sum-at[i]-bt[i];  
            tat = tat+sum-at[i];  
            count =0;     
        }  
        if(i==NOP-1)  
        {  
            i=0;  
        }  
        else if(at[i+1]<=sum)  
        {  
            i++;  
        }  
        else  
        {  
            i=0;  

        }  
    }  
  
    avg_wt = wt * 1.0/NOP;  
    avg_tat = tat * 1.0/NOP;  
    printf("\n Average Turn Around Time: \t%f", avg_wt);  
    printf("\n Average Waiting Time: \t%f", avg_tat);  
    getch();  
    }  
```

![Screenshot from 2022-10-12 11-45-45](https://user-images.githubusercontent.com/93587823/195264487-01cd030a-69e9-428a-a5a3-9aed36b9d6c7.png)

2-a)
```
#include<stdio.h>
int main()
{
int bt[20],p[20],wt[20],tat[20],i,j,n,total=0,pos,temp;
float avg_wt,avg_tat;
printf("Enter number of process:");
scanf("%d",&n);
printf("\nEnter burst time:\n");
for(i=0;i<n;i++) {
printf("p%d:",i+1);
scanf("%d",&bt[i]);
p[i]=i+1;
}
wt[0]=0;
for(i=1;i<n;i++) {
wt[i]=0;
wt[i]+=bt[j];
for(j=0;j<i;j++)
total+=wt[i];
}
avg_wt=(float)total;
total=0;
printf("\nProcess \t Burst time \t Waiting time \t Turnaround Time");
for(i=0;i<n;i++) {
tat[i]=bt[i]+wt[i];
total+= tat[i];
printf("\n p%d \t\t %d \t\t %d \t\t %d",p[i],bt[i],wt[i],tat[i]);
}
avg_tat = (float)total;
printf("\n\n Average waiting time =%f",avg_wt);
printf("\nAverage Turnaround time= %f \n",avg_tat);

}
```
![Screenshot from 2022-10-12 11-48-43](https://user-images.githubusercontent.com/93587823/195264893-c4267e86-f20f-41bf-9ea6-0b5a8cd2c064.png)

2-B)
```
#include <stdio.h>
int main()
{
    int bt[20],p[20],wt[20],tat[20],i,j,n,total=0,pos,temp;
    float avg_wt,avg_tat;
    printf("Enter number of process:");
    scanf("%d",&n);
    printf("\n Enter Burst Time:\n");
    for (i=0;i<n;i++)
    {
        printf("P%d:",i+1);
        scanf("%d",&bt[i]);
        p[i]=i+1;
    }
    for(i=0;i<n;i++)
    {
        pos=i;
        for(j=i+1;j<n;j++)
        {
            if(bt[j]<bt[pos])
            pos=j;
        }
        temp=bt[i];
        bt[i]=bt[pos];
        bt[pos]=temp;
        temp=p[i];
        p[i]=p[pos];
        p[pos]=temp;
    }
    wt[0]=0;
    for(i=1;i<n;i++)
    {
        wt[i]=20;
        for(j=0;j<i;j++)
        wt[i]+=bt[j];
        avg_wt=(float)total;
        total=0;
        printf("\n Process\t Burst Time\t Waiting Time\t Turnaround Time");
    }
    for(i=0;i<n;i++)
    {
        tat[i]=bt[i]+wt[i];
        total+=tat[i];
        printf("\n P%d \t\t %d\t\t %d\t\t\t %d",p[i],bt[i],wt[i],tat[i]);
        
    }
    avg_tat=(float)total;
    printf("\n\n Average Waiting Time =%f",avg_wt);
    printf("\n Average Turnaround Time = %f\n",avg_tat);
}

```

![Screenshot from 2022-10-12 11-50-20](https://user-images.githubusercontent.com/93587823/195265126-09b7550c-9c0b-49b1-9a44-4ab032c5443e.png)

2-C)
```
#include <stdio.h>
int main()
{
    int bt[20],p[20],wt[20],tat[20],pri[20],i,j,k,r,n,total=0,pos,temp;
    float avg_wt,avg_tat;
    printf("Enter number of process:");
    scanf("%d",&n);
    printf("\n Enter Burst Time:\n");
    for (i=0;i<n;i++)
    {
        printf("P%d:",i+1);
        scanf("%d",&bt[i]);
        p[i]=i+1;
    }
        printf("Enter Priority of the Process");
    
    for(i=0;i<n;i++)
    {
        p[i]=i;
        printf("\nP%d:",i+1);
        scanf("%d",&pri[i]);
    }
        for(i=0;i<n;i++)
          for(k=i+1;k<n;k++)
          if(pri[i]>pri[k])
          {
        
        temp=pri[i];
        pri[i]=pri[k];
        pri[k]=temp;
    }
    wt[0]=0;
    for(i=1;i<n;i++)
    {
        wt[i]=0;
        for(i=1;i<n;i++)
        wt[i]+=bt[j];
        total+=wt[i];
    }
        avg_wt=(float)total;
        total=0;
        printf("\n Process\t Burst Time\t Priority Time\t Waiting Time\t Turnaround Time");
    
    for(i=0;i<n;i++)
    {
        tat[i]=bt[i]+wt[i];
        total+=tat[i];
        printf("\n P%d \t\t %d\t\t %d\t\t\t %d",p[i],bt[i],pri[i],wt[i],tat[i]);
        
    }
    avg_tat=(float)total;
    printf("\n\n Average Waiting Time =%f",avg_wt);
    printf("\n Average Turnaround Time = %f\n",avg_tat);![Screenshot from 2022-10-12 11-49-45](https://user-images.githubusercontent.com/93587823/195265051-5ff3a835-030d-4124-a95f-286fc73e9f64.png)

}

```
![Screenshot from 2022-10-12 11-49-45](https://user-images.githubusercontent.com/93587823/195265051-5ff3a835-030d-4124-a95f-286fc73e9f64.png)
