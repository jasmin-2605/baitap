// Bài 1.

#include <stdio.h>
#include <stdlib.h>


void output(int arr[],int n)
{
	for(int i=0;i<n;i++)
	{
		scanf("%d",&arr[i]);
	}
	printf("\nb. \nMang : ");
	for(int i=0;i<n;i++)
	{
		printf("%d ",arr[i]);
	}
}

void gtd(int arr[],int n)
{
	printf("\nc. \n");
	for(int i=0;i<n;i++)
	{
		if(arr[i] > 0)
		{
			printf("Vi tri gia tri duong dau tien : %d\n",i+1);
			printf("Gia tri phan tu duong dau tien : %d\n",arr[i]);
			break;
		}
	}
}

void gtdc(int arr[],int n)
{
	printf("\nd. \n");
	for(int i=n-1;i>=0;i--)
	{
		if(arr[i] > 0)
		{
			printf("Vi tri gia tri duong cuoi cung : %d\n",i+1);
			printf("Gia tri phan tu duong cuoi cung : %d\n",arr[i]);
			break;
		}
	}
}

void GTMin(int arr[],int n)
{
	int k=0,count=0;
	for(int i=0;i<n;i++)
	{
		if(k < arr[i]) k = arr[i];
	}
	printf("\ne. \nGia tri phan tu lon nhat : %d\n",k);
	for(int i =0;i<n;i++)
	{
		if(arr[i]==k) count++;
	}
	printf("\nf. \nSo phan tu lon nhat : %d\n",count);
	printf("\ng. \nCac vi tri phan tu lon nhat : ");
	for(int i=0;i<n;i++)
	{
		if(arr[i]==k) printf("%d ",i+1);
	}
	printf("\n");
}

void plus(int arr[],int n)
{
	int brr[102],k;
	for(int i=1;i<=n;i++)
	{
		brr[i]=arr[i-1];
	}
	printf("\nh. \nNhap gia tri them vao dau mang : ");
	scanf("%d",&k);
	brr[0]=k;
	printf("Mang sau khi them gia tri vao dau mang : ");
	for(int i=0;i<=n;i++)
	{
		printf("%d ",brr[i]);
	}
	printf("\n");
}
void pluss(int arr[],int n)
{
	int brr[102],crr[101],k,l;
	for(int i=0;i<n;i++)
	{
		brr[i]=arr[i];
	}
	printf("\ni. \nNhap gia tri them vao mang : ");
	scanf("%d",&k);
	printf("Chen gia tri vao vi tri k (0 < k <= %d) : ",n);
	scanf("%d",&l);
	for(int i=0;i<l-1;i++) crr[i]=brr[i];
	crr[l-1]=k;
	for(int i=l;i<=n;i++) crr[i]=brr[i-1];
	printf("Mang sau khi them gia tri vao vi tri k : ");
	for(int i=0;i<=n;i++)
	{
		printf("%d ",crr[i]);
	}
	printf("\n");
}
void clear(int arr[],int n)
{
	printf("\nj. \n'Xoa phan tu dau mang : ");
	for(int i=1;i<n;i++) printf("%d ",arr[i]);
}
void clearK(int arr[],int n)
{
	int k;
	printf("\n\nk. \nXoa phan tu vi tri k (0 < k <= %d): ",n);
	scanf("%d",&k);
	printf("Mang sau khi xoa : ");
	for(int i=0;i<k-1;i++) printf("%d ",arr[i]);
	for(int i=k;i<n;i++) printf("%d ",arr[i]);
}
void check(int arr[],int n)
{
	printf("\n\nl. \nKiem tra mang co chua so le : ");
	int count=0;
	for(int i=0;i<n;i++)
	{
		if(arr[i] % 2 == 1)
		{
			printf("YES\n");
			break;
		} else count++;
	}
	if(count == n) printf("NO\n");
}
void check1(int arr[],int n)
{
	int brr[101];
	int k=0;
	for(int i=0;i<n;i++)
	{
		if(arr[i] % 2 == 0 )
		{
			brr[k]=arr[i];
			k++;
		}
	}
	printf("\nm. \nCac phan tu chan cua mang : ");
	for(int i=0;i<k;i++)
	{
		if(brr[i] > 0)
		{
			printf("%d ",brr[i]);
		}
	}
	if(k==0) printf("khong co");
}
int main ()
{
	int a[101],n;
	printf("a. \nNhap mang so nguyen gom n phan tu : ");
	scanf("%d",&n);
	output(a,n);
	gtd(a,n);
	gtdc(a,n);
	GTMin(a,n);
	plus(a,n);
	pluss(a,n);
	clear(a,n);
	clearK(a,n);
	check(a,n);
	check1(a,n);
}

// Bài 2

#include <stdio.h>
#include <string.h>

int main ()
{
	char s1[1000],s2[1000],s3[1000];
	printf("a+b. \nNhap chuoi s1 : ");
	gets(s1);
	int len = strlen(s1);
	printf("Nhap chuoi s2 : ");
	gets(s2);
	int len1= strlen(s2);
	printf("\n\nc. \nDo dai chuoi s1 : %d",len);
	printf("\nDo dai chuoi s2 : %d",len1);
	printf("\n\nd. \nSo sanh s1 va s2 : ");
	if(strlen(s1) > strlen(s2)) printf("s1 > s2");
	else if(strlen(s1) == strlen(s2)) printf("s1 = s2");
	else if(strlen(s1) < strlen(s2)) printf("s1 < s2");
	strcpy(s3,s1);
	strcat(s3,s2);
	printf("\n\ne. \nNoi chuoi s1 va s2 : %s\n",s3);
	char *first = strstr(s1,s2);
	if(first != NULL)
	{


		printf("\nf. \nChuoi s1 co chua chuoi s2 \n");
	} else printf("\nf. \nChuoi s1 khong chua chuoi s2 \n");
	first=strstr(s2,s1);
	if(first != NULL)
	{
		printf("\ng. \nChuoi s2 co chua chuoi s1 \n");
	} else printf("\ng. \nChuoi s2 khong chua chuoi s1 \n");
}

// Bài 3

#include <stdio.h>
#include <math.h>
int counter=0,a[1000];
int kt(int n)
{
	if(counter > 0)
	{
		for(int i=0;i<counter;i++)
		{
			if(n == a[i])
			{
				return 0;
			}
		}
	}
	return 1;
}
int check(int n)
{
	if(n==1 || n==2) return 0;
	int k=sqrt(n);
	if(k*k==n) return 1;
	return 0;
}
void import(int a[],int n)
{
	for(int i=0;i<n;i++)
	{
		printf("Phan tu thu %d : ",i+1);
		scanf("%d",&a[i]);
		if(kt(a[i]==0))
		{
			while(kt(a[i]) != 1)
			{
				printf("Nhap bi trung , yeu cau nhap lai");
				printf("\nPhan tu thu %d : ",i+1);
				scanf("%d",&a[i]);
			}
		}
		counter++;
	}
}
void output(int a[],int n)
{
	printf("Mang A : ");
	for(int i=0;i<n;i++)
	{
		printf("%d ",a[i]);
	}
}
void check1(int a[],int n)
{
	int kt=0;
	printf("Cac so chinh phuong o vi tri le : ");
	for(int i=0;i<n;i+=2)
	{
		if(check(a[i])==1)
		{
			printf("%d ",a[i]);
		} else kt++;
		if(n % 2 == 0 && kt == n/2) printf("NO\n");
		else if(n % 2 != 0 && kt == (n/2 +1)) printf("NO\n");
	}
}
void check2(int a[],int n)
{
	printf("Cac vi tri cua phan tu co gia tri max : ");
	int max = 0;
	for(int i=0;i<n;i++)
	{
		if(max < a[i]) max = a[i];
	}

	for(int i=0;i<n;i++)
	{
		if(a[i]==max) printf("%d ",i+1);
	}
}
void check3(int a[],int n)
{
	int b[1000],c[1000];
	int x=0,y=0;
	for(int i=0;i<n;i++)
	{
		if(a[i] < 0)
		{
			b[x++]=a[i];
		}
		if(a[i] > 0)
		{
			c[y++]=a[i];
		}
	}
	printf("Phan tu am lon nhat : ");
	if(x==0) printf("Khong co");
	else
	{
		int max=-10000;
		for(int i=0;i<x;i++)
		{
			if(max < b[i]) max = b[i];
		}
		printf("%d",max);
	}
	printf("\nPhan tu duong nho nhat : ");
	if(y==0) printf("Khong co");
	else
	{
		int min=10000;
		for(int i=0;i<y;i++)
		{
			if(min > c[i]) min = c[i];
		}
		printf("%d ",min);
	}
}
void check4(int a[],int n)
{
	int sum=0;
	for(int i=1;i<n;i+=2)
	{
		sum+=a[i];
	}
	printf("Tong cac phan tu o vi tri chan trong mang : %d",sum);
}
void soft(int a[],int n)
{
	for(int i=0;i<n-1;i++)
	{
		for(int j=i+1;j<n;j++)
		{
			if(a[i] > a[j])
			{
				int tmp = a[i];
				a[i] = a[j];
				a[j] = tmp;
			}
		}
	}
	printf("Sap xep mang theo thu tu tang dan : ");
	for(int i=0;i<n;i++)
	{
		printf("%d ",a[i]);
	}
}
int main ()
{
	int n;
	printf("a. \nNhap so phan tu mang A : ");
	scanf("%d",&n);
	import(a,n);
	printf("\n\nb. \n");
	output(a,n);
	printf("\n\nc. \n");
	check1(a,n);
	printf("\n\nd. \n");
	check2(a,n);
	printf("\n\ne. \n");
	check3(a,n);
	printf("\n\nf. \n");
	check4(a,n);
	printf("\n\ng. \n");
	soft(a,n);
}


// Bài 4


#include<stdio.h>
#include<string.h>
#include <stdlib.h>
void doithuong(char s[])
{
    int p=0;

  for (int i=0; i<strlen(s);i++){
  while(s[p]!=(' ')&&p<strlen(s)){
                if('A'<=s[p+1]&&s[p+1]<='Z'){
                s[p+1]+=32;
                }
              p++;

        }
        p++;

        }
}

void doihoa(char s[])
{

    for(int j=0; j<strlen(s); j++)
    {
        if ('a'<=s[j]&&s[j]<='z'&&j==0)
        { 
            s[j]-=32;

        }
    }
    for (int j=0; j<strlen(s); j++)
    {
        if(s[j]==(' '))
        {
            if('a'<=s[j+1]&&s[j+1]<='z')
            {
                s[j+1]-=32;
            }
        }
    }
}

int main()
{
    char st[20];

    fgets(st,sizeof st,stdin);

    doihoa(st);
   doithuong(st);
    printf("%s",st);
    return 0;

}


// Bài 5 


#include <stdio.h>
#include <math.h>




void NhapMaTran(int a[][100], int m, int n)
{
   for(int i = 0; i < m; i++)
      for(int j = 0; j < n; j++)
      {
         printf("A[%d][%d] = ", i, j);
         scanf("%d", &a[i][j]);
      }
}

void XuatMaTran(int a[][100], int m, int n)
{
   for(int i = 0; i < m; i++)
   {
      for(int j = 0; j < n; j++)
         printf("%d\t", a[i][j]);
      printf("\n");
   }
}
 void tongpt(int a[][100],int m, int n){
 int sum=0;
 for(int i=0;i<m;i++){
    for(int j=0;j<n;j++){
        sum+=a[i][j];
    }
  }
  printf("\n c. \ntong phan tu: %d",sum);
 }
 void tbc(int a[][100],int m, int n){
 float sum=0;
 for(int i=0;i<m;i++){
    for(int j=0;j<n;j++){
        sum+=a[i][j];
    }
 }
 int k=m*n;

 printf("\n d. \n trung binh cong: %.2f",sum/k);
 }

 void tbcptduong(int a[][100],int m, int n){
 float sum=0;
 int k=0;
 for(int i=0;i<m;i++){
    for(int j=0;j<n;j++){
        if(a[i][j]>0)
        {
            sum+=a[i][j];
             k++;
         }
    }
 }
 printf("\n e. \n trung binh cong: %.2f",sum/k);
 }

 void xuatdongk(int a[][100],int m,int n){
    int k;
    printf("\n f. \nmoi ban nhap dong can xuat: ");
    scanf("%d",&k);
    for (int i=0;i<n;i++) printf("%d ",a[k-1][i]);
 }

 void tongptcot(int a[][100],int m, int n)
 {
     printf("\n g. \nmoi ban nhap cot can tinh tong: ");
     int k; scanf("%d",&k);
     int s=0;
     for (int i=0;i<m;i++){
        s+=a[i][k-1];
     }
     printf("Tong cac phan tu tren cot %d la: %d",k,s);

 }

 void Max(int a[][100], int m, int n){
     int max=0;
     for(int i=0; i<m;i++){
        for(int j=0;j<n;j++){
            if(abs(a[i][j])>max) max=a[i][j];
     }
     }
     printf("\n h.\n Gia tri lon nhat : %d", max);

 }
 int main(){
  int a[100][100];
  int m,n;
  printf("a.\n Moi ban nhap ma tran: ");
  scanf("%d%d",&m,&n);
  NhapMaTran(a,m,n);
  printf("\n b.\n");
  XuatMaTran(a,m,n);
  tongpt(a,m,n);
  tbc(a,m,n);
  tbcptduong(a,m,n);
  xuatdongk(a,m,n);
  tongptcot(a,m,n);
  Max(a,m,n);
 }

// Bai 6 


#include <stdio.h>
#include <math.h>




void NhapMaTran(int a[][100],int n)
{
   for(int i = 0; i < n; i++)
      for(int j = 0; j < n; j++)
      {
         printf("A[%d][%d] = ", i, j);
         scanf("%d", &a[i][j]);
      }
}

void XuatMaTran(int a[][100],int n)
{
   for(int i = 0; i < n; i++)
   {
      for(int j = 0; j < n; j++)
         printf("%d\t", a[i][j]);
      printf("\n");
   }
}
void ptcheochinh(int a[][100],int n){
   printf("\n c. \nCac phan tu cheo chinh: ");
   for( int i=0;i<n;i++){
    printf("%d ", a[i][i]);
   }
}
void ptcheophu(int a[][100], int n){
    printf("\n d. \nCac phan tu cheo phu: ");
       int m=0;
       int l=n-1;
        for(int i=0;i<n;i++){
        printf("%d ",a[m][l]);
        m++;l--;
    }
}



void tongptdong(int a[][100], int n)
 {
     printf("\n e. \nmoi ban nhap dong can tinh tong: ");
     int k; scanf("%d",&k);
     int s=0;
     for (int i=0;i<n;i++){
        s+=a[k-1][i];
     }
     printf("Tong cac phan tu tren dong %d la: %d",k,s);

 }

 void tongptmoidong(int a[][100], int n)
 {
     printf("\n f. \n");


     for (int i=0;i<n;i++){
            int s=0;
            for(int j=0;j<n;j++){
                 s+=a[i][j];
            }
       printf("Tong cac phan tu tren dong %d la: %d\n",i+1,s);
     }


 }
 int tonghang(int a[][100],int i, int n){
    int s=0;
    for (int j=0;j<n;j++) s+=a[i][j];

    return s;
 }
 int hangmax(int a[][100],int n){
   int max=tonghang(a,1,n);
   int k=1;
   for(int i=0;i<n;i++)
   {
       if(max<tonghang(a,i,n)){
        max=tonghang(a,i,n);
        k=i;
       }
   }
   return k+1;
 }



 int main(){
  int a[100][100];
  int n;
  printf("a.\n Moi ban nhap ma tran: ");
  scanf("%d",&n);
  NhapMaTran(a,n);
  printf("\n b.\n");
  XuatMaTran(a,n);
  ptcheochinh(a,n);
  ptcheophu(a,n);
  tongptdong(a,n);
  tongptmoidong(a,n);
  printf("\n g. \nHang co tong lon nhat la %d", hangmax(a,n));
 }

// Bai 7





