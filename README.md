# Job_scheduling problem 
Example of greedy algorithm
//writing code using c programming language
#include<stdio.h>

int main(){

     int i,j,temp, k=0;
     int n;
     int jb[20];
     int A[]={0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0,0};
     int s[20],f[20];
       printf("NO of jobs?\n");
       scanf("%d",&n);
     Printf("enter jobs consecutively\n");
     for(i=0;i<n;++i)
     scanf("%d",&jb[i]);
     printf("enter start time and finishing time of each jobs\n");
     for(i=0;i<n;++i){
     scanf("%d%d",&s[i],&f[i]);
           }
       for(i=0;i<n;i++){
         for(j=i+1;j<n;++j){
            if(f[i]>=f[j]){
                temp=f[i];
                f[i]=f[j];
                f[j]=temp;

            }
         }
      }

        A[0]=1;
        j=0;
       for(i=1;i<n;i++){

        if(s[i]>=f[j]||s[j]>=f[i]){
            A[++k]=jb[i];
           j=i;

        }
    }

   printf("optimal set is:\n");

   for(j=0;j<n;j++)
    printf("%d\t",A[j]);


        return 0;
}


