# 13-c-1
#include<stdio.h>
struct student
{
	long No;
	char name [10];
	float score[3];
};
int main()
{
	
	struct student stu[5],*p; int i,j; int rank[5];double temp[5];double flag;int cnt; double ave[5]; //i--people, rank--rank
	for(i=0;i<5;i++){
		scanf("%ld %s %f %f %f",
		 &stu[i].No, &stu[i].name, &stu[i].score[0], &stu[i].score[1], &stu[i].score[2]);
		 getchar();
	}
	for(i=0;i<5;i++){
		ave[i]=(stu[i].score[0]+stu[i].score[1]+stu[i].score[2])/(3.0);
	}
	for(i=0;i<5;i++){
		temp[i]=ave[i];
	}
	 
	for(i=0;i<5;i++){
		flag=temp[0];
		for(j=0;j<5;j++){
			if(temp[j]>flag){
				flag=temp[j]; cnt=j;
			}
			
		}
		rank[cnt]=(i+1); temp[cnt]=0;
		
		if(j==5&&flag==temp[0]){
			rank[0]=5; rank[cnt]--;
		}
		
	}
	
	
	printf("Number:  Name:        score:       Average：  rank:\n");
	for(i=0;i<5;i++){
		printf("%-9ld%-10s%-5.1f%-5.1f%-8.1f%-10.1f%-d\n",
		 stu[i].No, stu[i].name, stu[i].score[0], stu[i].score[1], stu[i].score[2], ave[i], rank[i]);
	}	
 } 

 
