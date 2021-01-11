# Question 1
Write the program for deleting an element from the beginning and from any position.

```
#include<stdio.h>
 
void main() 
{
    int a[10],i,n,pos;
    // Supposing array is filled by looping through length
    
    //
    //from any position and if for from the starting the pass index for the starting one
    printf("Enter the position from which the number has to be deleted : \n");
    scanf("%d",&pos);
    for(i=pos;i<n-1;i++)
    {
        a[i]=a[i+1];
    }
    n=n-1;
    printf("\nNew array : \n");
    for(i=0;i<n;i++) 
    {
        printf("a[%d] = %d\n",i,a[i]);
    }
}
```
# Question 2
Write the program for printing the array after rotating it k times towards left, where k would be
taken as user input.

``` 
#include <stdio.h>
#include <conio.h>
 
int leftrotate(int *a,int n,int k)
{ 
    int i,j,temp;
    for(i=0; i<k; i++)
    {
        temp=a[0];
        for(j=0; j<n-1; j++)
        {
           a[j]=a[j+1];
		}
 
         a[n-1]=temp;
    }
    
       
 }
 print(int *a,int n)
{ 
   
    int i;
    for(i=0; i<n; i++)
    {
       printf("%d ",a[i]);
    }
    
       
 }
 
  
int main()
{
    int a[10000],i,n,j,k,temp;
   
    printf("Enter size of the  array : ");
    scanf("%d", &n);
    printf("Enter elements in array : ");
    for(i=0; i<n; i++)
    {
        scanf("%d",&a[i]);
    }
    printf("Enter k (number of times to rotate) : ");
    scanf("%d", &k);
     
    leftrotate(a,n,k);
   
    printf("\narray elements after left rotate  : ");
 
      print(a,n);
 
     
    
}    
void printArray(int arr[], int n) 
{ 
	int i; 
	for (i = 0; i < n; i++) 
		printf("%d ", arr[i]); 
} 

