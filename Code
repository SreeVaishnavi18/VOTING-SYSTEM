/*Election System*/
#include<stdio.h>
int V_Count[4] = {0, 0, 0, 0};
void getinput();
//int append();
struct Candidate{
    int Id;
    char Name[30];
    char House_Name[30];
}Cand[8];
int main()
{
    struct Candidate *ptr;
    ptr = &Cand[8];
    int V_Id, choice, i, max, V_Choice=1, v_choice=1, Voted=1, n, c;
    int VID[25] = {0};
    //getinput();
    FILE *filePointer;
    filePointer = fopen("Election","rb");
    while(fread(&Cand,sizeof(Cand),1,filePointer)==1)
    {
        printf("\nThe Candidate Details are:");
        for(int i=0;i<4;i++)
        {
            printf("\nCandidate ID %d\n", i+1);
            printf(" Name: %s", Cand[i].Name);
            printf ( " House Name: %s", Cand[i].House_Name);
        }
        printf("\n");
    }
    fclose(filePointer);
    /*printf("\nDo you wish to append?(y=1/n=0) : ");
    scanf("%d", &c);
    if(c == 1)
    {
        n = append();
        filePointer = fopen("Election","ab+");
        while(fread(&Cand,sizeof(Cand),1,filePointer)==1)
        {
            printf("\nThe Candidate Details are:");
            for(int i=4;i<(4+n);i++)
            {
                printf("\nCandidate ID %d\n", i+1);
                printf(" Name: %s", Cand[i].Name);
                printf ( " House Name: %s", Cand[i].House_Name);
            }
            printf("\n");
        }
        fclose(filePointer);
    }*/
    do{
    printf("      \n\t\t\tWelcome to the Election");
    printf("\nEnter your Voter ID : ");
    scanf("%d", &V_Id);
    for(i=0;i<25;i++)
    {
        if(V_Id == VID[i])
        {
            printf("\nYou have already cast your vote.");
            V_Id = 0;
        }
        else
        {
            VID[i] = V_Id;
        }
    }
    if((V_Id>=100) && (V_Id<=150) && (V_Id != 0))
    {
        do{
        printf("\nEnter your choice:\n");
        printf("1. Casting your vote\n2. Vote Count\n3. Candidate with maximum votes\n4. Exit\n");
        scanf("%d", &choice);
        switch(choice)
        {
            case 1:
                while(Voted == 1)
                {
                        printf("You can cast your vote now!");
                        printf("\nEnter the Id of the candidate you wish to vote:");
                        scanf("%d", &Cand->Id);
                        V_Count[Cand->Id]++;
                        Voted = 0;
                }
                break;
            case 2:
                printf("\nVote Count");
                printf("\nCandidate 1 has %d votes", V_Count[1]);
                printf("\nCandidate 2 has %d votes", V_Count[2]);
                printf("\nCandidate 3 has %d votes", V_Count[3]);
                printf("\nCandidate 4 has %d votes", V_Count[4]-1);
                /*if(c == 1)
                {
                    printf("\nCandidate 5 has %d votes", V_Count[5]);
                    printf("\nCandidate 6 has %d votes", V_Count[6]);
                }*/
                break;
            case 3:
                printf("Candidate with maximum votes!");
                max = 0;
                for(i=0;i<4;i++)
                {
                    if(V_Count[i] > max)
                    {
                        max = V_Count[i];
                        Cand->Id = i;
                        ptr++;
                    }
                }
                printf("\nThe maximum number of votes is %d and the Candidate ID is %d", max, Cand->Id);
                break;
            case 4:
                return 0;
            default:
                printf("Not a choice");
        }
     printf("\n\nDo you wish to continue(yes=1/no=0)?");
     scanf("%d", &v_choice);
    }while(v_choice == 1);
    }
    else if(V_Id != 0)
    {
        printf("\nThis is not your ward. Do recheck your Voter ID");
    }
    printf("\n\nAre you a new voter?(yes=1/no=0)");
    scanf("%d", &V_Choice);
    if(V_Choice == 1)
    {
        Voted = 1;
    }
    }while(V_Choice == 1);
}
void getinput()
{
    FILE *filePointer;
    filePointer = fopen("Election", "wb");
    if(filePointer == NULL)
    {
        printf("Election file has failed to open");
    }
    else
    {
        printf("Enter the Candidate Details:");
        for(int i=0;i<4;i++)
        {
            printf("\nCandidate ID %d\n", i+1);
            Cand[i].Id = i+1;
            printf(" Name: ");
            gets(Cand[i].Name);
            printf ( " House Name: " );
            gets(Cand[i].House_Name);
        }
        fwrite(&Cand,sizeof(Cand),1,filePointer);
        fclose(filePointer);
    }
}
/*int append()
{
    int n;
    printf("\nEnter the no. of candidates you wish to add : \n");
    scanf("%d", &n);
    FILE *filePointer;
    filePointer = fopen("Election", "a+");
    if(filePointer == NULL)
    {
        printf("Election file has failed to open");
    }
    else
    {
        printf("Enter the Candidate Details:");
        for(int i=4;i<(4+n);i++)
        {
            printf("\nCandidate ID %d\n", i+1);
            Cand[i].Id = i+1;
            fflush(stdin);
            printf(" Name: ");
            gets(Cand[i].Name);
            printf ( " House Name: " );
            gets(Cand[i].House_Name);
        }
        fwrite(&Cand,sizeof(Cand),1,filePointer);
        fclose(filePointer);
    }
    return n;
}*/
