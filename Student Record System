#include <stdio.h>
#include <conio.h>
#include <windows.h>
#include <stdlib.h>
#include <string.h>
void gotoxy(int, int);
void menu();
void add();
void view();
void modify();
void deleterec();
void search();
void view_result();
void remarks(int,int,int,int);
void modify_result();
struct student
{
    char name[20];
    char mobile[10];
    int roll;
    char course[20];
    char branch[20];
    char subject1[30];
    char marks1[4];
    char subject2[30];
    char marks2[4];
    char subject3[30];
    char marks3[4];
    char subject4[30];
    char marks4[4];
};
int main()
{
    system("color b4");
    gotoxy(15,8);
    printf("<--:Student Record Management System:-->");
    gotoxy(19,15);
    printf("Press any key to continue.");
    getch();
    menu();
    return 0;
}
void menu()
{
    int choice;
    system("cls");
    gotoxy(10,3);
    printf("<-:MENU:->");
    gotoxy(10,5);
    printf("Please enter a valid option.");
    gotoxy(10,7);
    printf("1.Add a record");
    gotoxy(10,8);
    printf("2.View record");
    gotoxy(10,9);
    printf("3.Search record");
    gotoxy(10,10);
    printf("4.Modify record");
    gotoxy(10,11);
    printf("5.Delete record");
    gotoxy(10,12);
    printf("6.View result");
    gotoxy(10,13);
    printf("7.Modify result");
    gotoxy(10,14);
    printf("8.Exit");
    gotoxy(10,16);
    printf("Enter your Choice : ");
    scanf("%d",&choice);
    switch(choice)
    {
    case 1:
        add();
        break;
    case 2:
        view();
        break;
    case 3:
        search();
        break;
    case 4:
        modify();
        break;
    case 5:
        deleterec();
    case 6:
        view_result();
        break;
    case 7:
        modify_result();
        break;
    case 8:
        exit(1);
        break;
    default:
        gotoxy(10,17);
        printf("Invalid Choice");
        gotoxy(10,18);
        printf("Press any key to continue.");
        getch();
        system("cls");
        menu();
        break;
    }
}
void add()
{
    FILE *fp;
    struct student std;
    char another = 'y';
    system("cls");
    fp = fopen("record.txt","ab+");
    if(fp==NULL)
    {
        gotoxy(10,5);
        printf("Error in opening file");
        exit(1);
    }
    fflush(stdin);
    while(another=='y')
    {
        gotoxy(10,3);
        printf("<--:ADD RECORD:-->");
        gotoxy(10,5);
        printf("Enter the details of the student");
        gotoxy(10,7);
        printf("Enter Name : ");
        gets(std.name);
        gotoxy(10,8);
        printf("Enter mobile number : ");
        gets(std.mobile);
        gotoxy(10,9);
        printf("Enter the roll no. : ");
        scanf("%d",&std.roll);
        fflush(stdin);
        gotoxy(10,10);
        printf("Enter Course : ");
        gets(std.course);
        gotoxy(10,11);
        printf("Enter Branch : ");
        gets(std.branch);
        system("cls");
        gotoxy(10,3);
        printf("<--:ADD RECORD FOR RESULT:-->");
        gotoxy(10,5);
        printf("Enter the details of the student for result");
        gotoxy(10,7);
        printf("Subject 1 : ");
        gets(std.subject1);
        gotoxy(10,8);
        printf("Enter marks : ");
        gets(std.marks1);
        gotoxy(10,9);
        printf("Subject 2 : ");
        gets(std.subject2);
        gotoxy(10,10);
        printf("Enter marks : ");
        gets(std.marks2);
        gotoxy(10,11);
        printf("Subject 3 : ");
        gets(std.subject3);
        gotoxy(10,12);
        printf("Enter marks : ");
        gets(std.marks3);
        gotoxy(10,13);
        printf("Subject 4 :");
        gets(std.subject4);
        gotoxy(10,14);
        printf("Enter marks : ");
        gets(std.marks4);
        fwrite(&std,sizeof(std),1,fp);
        gotoxy(10,18);
        printf("Want to enter another record? Then press 'y' else 'n'. ");
        fflush(stdin);
        another=getch();
        system("cls");
        fflush(stdin);
    }
    fclose(fp);
    gotoxy(10,18);
    printf("Press any key to continue.");
    getch();
    menu();
}
void view()
{
    FILE *fp;
    int i =1,j;
    struct student std;
    system("cls");
    gotoxy(10,3);
    printf("<--:VIEW RECORD:-->");
    gotoxy(10,5);
    printf("S.No   Name of Student       Mobile No   Roll No  Course    Branch");
    gotoxy(10,6);
    printf("------------------------------------------------------------------");
    fp = fopen("record.txt","rb+");
    if(fp==NULL)
    {
        gotoxy(10,8);
        printf("Error in opening the file.");
        exit(1);
    }
    j=8;
    while(fread(&std,sizeof(std),1,fp) == 1){
        gotoxy(10,j);
        printf("%-7d%-22s%-12s%-9d%-12s%-12s",i,std.name,std.mobile,std.roll,std.course,std.branch);
        i++;
        j++;
    }
    fclose(fp);
    gotoxy(10,j+3);
    printf("Press any key to continue.");
    getch();
    menu();
}
void search()
{
    FILE *fp;
    struct student std;
    int rollno;
    system("cls");
    gotoxy(10,3);
    printf("<--:SEARCH RECORD:-->");
    gotoxy(10,5);
    printf("Enter the roll no. of student : ");
    fflush(stdin);
    scanf("%d",&rollno);
    fp=fopen("record.txt","rb+");
    if(fp==NULL)
    {
        gotoxy(10,6);
        printf("Error in opening the file.");
        exit(1);
    }
    while(fread(&std,sizeof(std),1,fp)==1)
    {
        if(rollno==std.roll)
        {
            gotoxy(10,8);
            printf("Name : %s",std.name);
            gotoxy(10,9);
            printf("Mobile Number : %s",std.mobile);
            gotoxy(10,10);
            printf("Roll No. : %d",std.roll);
            gotoxy(10,11);
            printf("Course : %s",std.course);
            gotoxy(10,12);
            printf("Branch : %s",std.branch);
        }
    }
    fclose(fp);
    gotoxy(10,16);
    printf("Press any key to continue.");
    getch();
    menu();
}
void modify()
{
    char stname[20];
    FILE *fp;
    struct student std;
    system("cls");
    gotoxy(10,3);
    printf("<--:MODIFY RECORD:-->");
    gotoxy(10,5);
    printf("Enter the name of the student to modify : ");
    fflush(stdin);
    gets(stname);
    fp=fopen("record.txt","rb+");
    if(fp==NULL)
    {
        gotoxy(10,6);
        printf("Error in opening the file");
        exit(1);
    }
    rewind(fp);
    fflush(stdin);
    while(fread(&std,sizeof(std),1,fp)==1)
    {
        if(strcmp(stname,std.name)==0)
        {
            gotoxy(10,7);
            printf("Enter Name : ");
            gets(std.name);
            gotoxy(10,8);
            printf("Enter mobile number : ");
            gets(std.mobile);
            gotoxy(10,9);
            printf("Enter roll no : ");
            scanf("%d",&std.roll);
            gotoxy(10,10);
            printf("Enter Course : ");
            fflush(stdin);
            gets(std.course);
            gotoxy(10,11);
            printf("Enter branch : ");
            fflush(stdin);
            gets(std.branch);
            fseek(fp,-sizeof(std),SEEK_CUR);
            fwrite(&std,sizeof(std),1,fp);
            break;
        }
    }
    fclose(fp);
    gotoxy(10,16);
    printf("Press any key to continue.");
    getch();
    menu();
}
void deleterec()
{
    int stname[20];
    FILE *fp,*ft;
    struct student std;
    system("cls");
    gotoxy(10,3);
    printf("<--:DELETE RECORD:-->");
    gotoxy(10,5);
    printf("Enter the name to be deleted from record : ");
    fflush(stdin);
    gets(stname);
    fp=fopen("record.txt","rb+");
    if(fp==NULL)
    {
        gotoxy(10,6);
        printf("Error in opening the file.");
        exit(1);
    }
    ft=fopen("temp.txt","wb+");
    if(ft==NULL)
    {
        gotoxy(10,7);
        printf("Error in opening the file.");
        exit(1);
    }
    while(fread(&std,sizeof(std),1,fp)==1)
    {
        if(strcmp(stname,std.name)!=0)
        {
            fwrite(&std,sizeof(std),1,ft);
        }
    }
    fclose(fp);
    fclose(ft);
    remove("record.txt");
    rename("temp.txt","record.txt");
    gotoxy(10,10);
    printf("Press any key to continue");
    getch();
    menu();
}
void view_result()
{
    FILE *fp;
    struct student std;
    int rollno;
    system("cls");
    gotoxy(10,3);
    printf("<--:SEARCH RECORD:-->");
    gotoxy(10,5);
    printf("Enter the roll no. of student : ");
    fflush(stdin);
    scanf("%d",&rollno);
    fp=fopen("record.txt","rb+");
    if(fp==NULL)
    {
        gotoxy(10,6);
        printf("Error in opening the file.");
        exit(1);
    }
    while(fread(&std,sizeof(std),1,fp)==1)
    {
        if(rollno==std.roll)
        {
            gotoxy(10,8);
            printf("Name : %s",std.name);
            gotoxy(10,9);
            printf("%s : %s",std.subject1,std.marks1);
            gotoxy(10,10);
            printf("%s : %s",std.subject2,std.marks2);
            gotoxy(10,11);
            printf("%s : %s",std.subject3,std.marks3);
            gotoxy(10,12);
            printf("%s : %s",std.subject4,std.marks4);
            gotoxy(10,13);
            remarks(atoi(std.marks1),atoi(std.marks2), atoi(std.marks3), atoi(std.marks4));
        }
    }
    fclose(fp);
    gotoxy(10,16);
    printf("Press any key to continue.");
    getch();
    menu();
}
void remarks(int a,int b,int c,int d)
{
    int percent;
    percent = (a+b+c+d)/4;
    if(percent<=100 && percent>=95)
        printf("Remarks : Outstanding!");
    else if(percent<95 && percent>=85)
    {
        printf("Remarks : Distiction");
    }
    else if(percent<85 && percent>=75)
        printf("Remarks : Keep it Up");
    else
        printf("Improvement Required");

}
void modify_result()
{
    char stname[20];
    FILE *fp;
    struct student std;
    system("cls");
    gotoxy(10,3);
    printf("<--:MODIFY RECORD:-->");
    gotoxy(10,5);
    printf("Enter the name of the student to modify : ");
    fflush(stdin);
    gets(stname);
    fp=fopen("record.txt","rb+");
    if(fp==NULL)
    {
        gotoxy(10,6);
        printf("Error in opening the file");
        exit(1);
    }
    rewind(fp);
    fflush(stdin);
    while(fread(&std,sizeof(std),1,fp)==1)
    {
        if(strcmp(stname,std.name)==0)
        {
            gotoxy(10,7);
            printf("Subject 1 : ");
            gets(std.subject1);
            gotoxy(10,8);
            printf("Enter marks : ");
            gets(std.marks1);
            gotoxy(10,9);
            printf("Subject 2 : ");
            gets(std.subject2);
            gotoxy(10,10);
            printf("Enter marks : ");
            gets(std.marks2);
            gotoxy(10,11);
            printf("Subject 3 : ");
            gets(std.subject3);
            gotoxy(10,12);
            printf("Enter marks : ");
            gets(std.marks3);
            gotoxy(10,13);
            printf("Subject 4 : ");
            gets(std.subject4);
            gotoxy(10,14);
            printf("Enter marks : ");
            gets(std.marks4);
            fflush(stdin);
            fseek(fp,-sizeof(std),SEEK_CUR);
            fwrite(&std,sizeof(std),1,fp);
            break;
        }
    }
    fclose(fp);
    gotoxy(10,16);
    printf("Press any key to continue.");
    getch();
    menu();
}
void gotoxy(int x, int y)
{
    COORD c;
    c.X=x;
    c.Y=y;
    SetConsoleCursorPosition(GetStdHandle(STD_OUTPUT_HANDLE),c);
}
