# delimiter_matching
#include<stdio.h>
char stack[100],top=-1;
void push(int k)
{
        stack[++top]=k;
}
int pop()
{
        return stack[top--];
}
void main()
{
        char a[20],p,l;
        int flag,i=0;
        printf("enter a:");
        scanf("%S",&a);
        while(a[i]!='\0')
        {
                p=a[i];
                if(p=='(' ||p=='[' ||p=='{')
                {
                        push (a[i]);
                }
                else if (p==')' ||p==']' ||p=='}')
                {
                        if(top==-1)
                        {
                                flag=0;
                                break;
                                 }
                        else
                        {
                                l=pop();
                                if(l=='(' && p==')' ||l=='[' && p==']' ||l=='{' && p=='}')
                                {
                                        flag=1;
                                }
                                else
                                {
                                        flag=0;
                                        break;
                                }
                        }
                }
                i++;
        }
        if(top!=-1)
        {
                flag=0;
        }
        if(flag==1)
        {
                printf("matched");
        }
        else{
                printf("not matched");
        }
}        


OUTPUT:
enter a:{[()}
not matched
