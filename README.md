# baitap

#include<stdio.h>
int main(){
    int a,b;    
    printf("nhap nam va thang\n");    
    scanf("%d%d",&a,&b);   
    if((b>=1)||(b<=12)){       
        if ((b==1)||(b==3)||(b==5)||(b==7)||(b==8)||(b==10)||(b==12))       
             printf("Thang %d Nam %d co 31 ngay",b,a);    
        if ((b==4)||(b==6)||(b==9)||(b==11))       
             printf("Thang %d Nam %d co 30 ngay",b,a);    
        if (b==2){       
              if ((a%400==0) || (a%4==0)&&(a%100!=0))              
                   printf("Thang 2 Nam %d co 29 ngay",a);       
              else printf("Thang 2 Nam %d co 28 ngay",a);
        }
    }
    else
         printf("Thang %d khong hop le",b);
    return 0;
}
