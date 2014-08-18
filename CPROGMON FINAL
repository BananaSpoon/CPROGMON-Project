/*
Author: Ervin Lester G. Lu and Christian Leong
Title: CPROGMON
Description: A Turn based game similar to Pokemon <1 Player and 2 Player Option>
Major Learnings: How to use the random function
                 How to add colors
                 How to make the ASCII Art
                 How to use time header
                 Making a game is a difficult task (debugging)
                 
Last Date Modified: August 18, 2014

Edit Log:  Added font colors (August 2, 2014)
           Rendered appearance (August 2, 2014)
           Removed the bug <infinite loop> (August 4, 2014) 
           4th Skill can now pass thru SHIELD (August 4, 2014)
           Added Menu for Main Menu (August 5, 2014)
           Removed bug for exiting the game (August 5, 2014)
           Added Charizard and Blastoise (August 5, 2014)
           Added Title Screen (August 13, 2014)
           Added a working AI System (August 15, 2014)
           Removed bug with the moves (August 18, 2014)
*/

#include <stdio.h>
#include <stdlib.h>
#include <windows.h>
#include <time.h>

int p[2];
void displaymovelist1();
void displaymovelist2();
void displayinstructions();
void gamefor2players();
void gamefor1player();
void AI();
void titlescreen();
void displaycharizard();
void displayblastoise();

int main()
{
    HANDLE hConsole;
    hConsole = GetStdHandle (STD_OUTPUT_HANDLE);
    
    SetConsoleTextAttribute
        (hConsole, 11);  //CHANGES FONT COLOR TO LIGHT BLUE
    titlescreen();
    system("cls");
    int start;
    /*int start, exit, HP[2], PP[2], p[2];*/
    SetConsoleTextAttribute
        (hConsole, FOREGROUND_GREEN| FOREGROUND_INTENSITY);  //CHANGES FONT COLOR TO GREEN
    printf("\nCprogmon: Gotta Decode Them All!");
    printf("\n\t<A 2D Pokemon Battle Game>");
    printf("\n\n\t\t\tMAIN MENU");
    printf("\n1- Single Player");
    printf("\n2- Two Player");
    printf("\n3- Instructions");
    printf("\n4- Exit/Quit");
    printf("\n\nEnter Choice:\t");
    scanf("%d", &start);

    
    /*PP[0]=0;
    PP[1]=0;
    HP[0]=100;
    HP[1]=100;*/
    
    switch(start)
    {
       case 2:
            system("cls");
            gamefor2players();
            break;
            
       case 4:
            SetConsoleTextAttribute
               (hConsole, 9);  //CHANGES FONT COLOR TO BLUE
            printf("\nYou are now exiting the program\n\n");
            SetConsoleTextAttribute
               (hConsole, 15);  //CHANGES FONT COLOR TO WHITE
            system("PAUSE");
            break;
       default:
            SetConsoleTextAttribute
                (hConsole, FOREGROUND_RED | FOREGROUND_INTENSITY);  //CHANGES FONT COLOR TO RED
            printf("\nINVALID INPUT\n\n");
            SetConsoleTextAttribute
                (hConsole, 15);  //CHANGES FONT COLOR TO WHITE
            system("PAUSE");
            system("cls");
            main(); 
            getchar();
			break;  
       case 3:
            SetConsoleTextAttribute
               (hConsole, 9);  //CHENGES FONT COLOR TO BLUE
	   		displayinstructions();  
            SetConsoleTextAttribute
               (hConsole, 15);  //CHANGES FONT COLOR TO WHITE        
	   		system("PAUSE");
	   		system("cls");
	   		main(); 
	   		break;
	   		
       case 1:
            system("cls");
            gamefor1player();
            break;

    }//ENDSWITCH

}//ENDMAIN

void displaymovelist1()  //MOVE LIST FOR PLAYER 1
{
     printf("\n\nMOVE LIST FOR PLAYER 1");
     printf("\n1- REST \t\t +10 PP but vulnerable to attacks");
     printf("\n2- SCRATCH \t\t -10 PP and -10 HP to opponent");
     printf("\n3- FIRE BLAST \t\t -30 PP and -30 HP to opponent");
     printf("\n4- FLAME WHEEL \t\t -50 PP and -50 HP to opponent");
     printf("\n5- SHIELD \t\t -0 PP and the player is shielded from opponent's attack except from HYDRO PUMP");
     printf("\n6- REFLECT \t\t -10 PP and reflects any attack back to the opponent");
}

void displaymovelist2()  //MOVE LIST FOR PLAYER 2
{
     printf("\n\nMOVE LIST FOR PLAYER 2");
     printf("\n1- REST \t\t +10 PP but vulnerable to attacks");
     printf("\n2- SCRATCH \t\t -10 PP and -10 HP to opponent");
     printf("\n3- WATER PULSE \t\t -30 PP and -30 HP to opponent");
     printf("\n4- HYDRO PUMP \t\t -50 PP and -50 HP to opponent");
     printf("\n5- SHIELD \t\t -0 PP and the player is shielded from opponent's attack except from FLAME WHEEL");
     printf("\n6- REFLECT \t\t -10 PP and reflects any attack back to the opponent");
}

void displayinstructions()  //DISPLAY INSTRUCTIONS
{
	printf("\n\nINSTRUCTIONS:");
    printf("\n1.) Use REST to gain Power Points (PP). \n\t PP can be used to attack opponent");
    printf("\n\n2.) Each Cprogmon has 100 Hit Points (HP). \n\t The first player to reach 0 HP loses the match");
    printf("\n\n3.) Player 2 should not be looking at the monitor and keyboard while Player 1 is choosing a move.\n\n");
}

void gamefor2players()  //GAME FOR 2 PLAYERS
{
	HANDLE hConsole;
    hConsole = GetStdHandle (STD_OUTPUT_HANDLE);
      
    int exit, HP[2], PP[2];
    PP[0]=0;
    PP[1]=0;
    HP[0]=100;
    HP[1]=100;
    
	do
            {
                  SetConsoleTextAttribute
                      (hConsole, FOREGROUND_RED | FOREGROUND_INTENSITY);  //CHANGES FONT COLOR TO RED
                  displaycharizard();
                  SetConsoleTextAttribute
                      (hConsole, FOREGROUND_BLUE | FOREGROUND_GREEN | FOREGROUND_INTENSITY);  //CHANGES FONT COLOR TO CYAN
                  displaymovelist1();  //PLAYER 1 PROGRAM
                  printf("\n\n");
                  printf("\nPlayer 1:\tHP:%d \tPP:%d",HP[0],PP[0]);
                  printf("\nPlayer 2:\tHP:%d \tPP:%d",HP[1],PP[1]);
                  printf("\n\nPlayer 1, Enter Your Choice of Move Here:\t");
                  scanf("%d", &p[0]);
                  if(p[0] == 6){ p[0] = 4; }

                  if ((p[0] < 1) || p[0] > 6)  //p[0] = choice in attacking
                  do
                  {
                       printf("\nINVALID INPUT");
                       printf("\nPlease Enter Your Choice of Move Again Here:\t");
                       getchar();
                       scanf("%d", &p[0]);
                       if(p[0] == 6){ p[0] = 4; }
                  }
                  while ((p[0] < 1) || (p[0] > 6));
                  
                  else if ((p[0] == 4) && (PP[0] < 50))  //CHOICE IS MOVE 4
                  do
                  {
                       printf("\nPlayer 1, you lack PP to perform the move");
                       printf("\nPlease Enter Your Choice of Move Again Here:\t");
                       scanf("%d", &p[0]);
                       if(p[0] == 6 || p[0] == 2||p[0]== 3){ p[0] = 4; }
                  }
                  while (p[0] == 4);
                  
                  else if ((p[0] == 3) && (PP[0] < 30))  //CHOICE IS MOVE 3
                  do
                  {
                      printf("\nPlayer 1, you lack PP to perform the move");
                      printf("\nPlease Enter Your Choice of Move Again Here:\t");
                      scanf("%d", &p[0]); 
                      if(p[0] == 6 || p[0] == 2){ p[0] = 3; }
                  }
                  while ((p[0]==3)||(p[0]==4));
                  
                  else if ((p[0] == 2) && (PP[0] < 10))  //CHOICE IS MOVE 2
                  do
                  {
                      printf("\nPlayer 1, you lack PP to perform the move");
                      printf("\nPlease Enter Your Choice of Move Again Here:\t");
                      scanf("%d", &p[0]); 
                      if(p[0] == 6){ p[0] = 4; }
                  }
                  while ((p[0]==2)||(p[0]==6)||(p[0]==3)||(p[0]==4));
                  
                  else if ((p[0] == 6) && (PP[0] < 10))  //CHOICE IS MOVE 6
                  do
                  {
                      printf("\nPlayer 1, you lack PP to perform the move");
                      printf("\nPlease Enter Your Choice of Move Again Here:\t");
                      scanf("%d", &p[0]); 
                  }
                  while ((p[0]==2)||(p[0]==6)||(p[0]==3)||(p[0]==4));
                  
                  system("cls");
                  
                  SetConsoleTextAttribute
                      (hConsole, FOREGROUND_BLUE | FOREGROUND_INTENSITY);  //CHANGES FONT COLOR TO BLUE
                  displayblastoise();
                  SetConsoleTextAttribute
                      (hConsole, FOREGROUND_BLUE | FOREGROUND_RED | FOREGROUND_INTENSITY);  //CHANGES FONT COLOR TO VIOLET
                  displaymovelist2();  //PLAYER 2 PROGRAM
                  printf("\n\n");
                  printf("\nPlayer 1:\tHP:%d \tPP:%d",HP[0],PP[0]);
                  printf("\nPlayer 2:\tHP:%d \tPP:%d",HP[1],PP[1]);
                  printf("\n\nPlayer 2, Enter Your Choice of Move Here:\t");
                  scanf("%d", &p[1]);
                  
                  if ((p[1] < 1) || (p[1] > 6))  //p[0] = choice in attacking
                  do
                  {
                       printf("\nINVALID INPUT");
                       printf("\nPlease Enter Your Choice of Move Again Here:\t");
                       getchar();
                       scanf("%d", &p[1]);
                  }
                  while ((p[1] < 1) || (p[1] > 6));
                  
                  else if ((p[1] == 4) && (PP[1] < 50))  //CHOICE IS MOVE 4
                  do
                  {
                       printf("\nPlayer 2, you lack PP to perform the move");
                       printf("\nPlease Enter Your Choice of Move Again Here:\t");
                       scanf("%d", &p[1]);
                       if(p[1] == 6 || p[1] == 2||p[1]== 3){ p[1] = 4; }
                  }
                  while (p[1] == 4);
                  
                  else if ((p[1] == 3) && (PP[1] < 30))  //CHOICE IS MOVE 3
                  do
                  {
                      printf("\nPlayer 2, you lack PP to perform the move");
                      printf("\nPlease Enter Your Choice of Move Again Here:\t");
                      scanf("%d", &p[1]); 
                      if(p[1] == 6 || p[1] == 2){ p[1] = 3; }
                  }
                  while ((p[1]==3)||(p[1]==4));
                  
                  else if ((p[1] == 2) && (PP[1] < 10))  //CHOICE IS MOVE 2
                  do
                  {
                      printf("\nPlayer 2, you lack PP to perform the move");
                      printf("\nPlease Enter Your Choice of Move Again Here:\t");
                      scanf("%d", &p[1]); 
                  }
                  while ((p[1]==2)||(p[1]==6)||(p[1]==3)||(p[1]==4));
                  
                  else if ((p[1] == 6) && (PP[1] < 10))  //CHOICE IS MOVE 6
                  do
                  {
                      printf("\nPlayer 2, you lack PP to perform the move");
                      printf("\nPlease Enter Your Choice of Move Again Here:\t");
                      scanf("%d", &p[1]); 
                  }
                  while ((p[1]==2)||(p[1]==6)||(p[1]==3)||(p[1]==4));
                  
                  system("cls");
                  
                  if ((p[0]==1)&&(p[1]==1))  //ADD PP TO BOTH PLAYERS
                  {
                       PP[0] = PP[0] + 10;
                       PP[1] = PP[1] + 10;
                  }
                  
                  else if ((p[0]==1)&&(p[1]==2))  //PLAYER 1 TAKES 10 DAMAGE
                  {
                       PP[0] = PP[0] + 10;
                       PP[1] = PP[1] - 10;
                       HP[0] = HP[0] - 10;
                  }
                  
                  else if ((p[0]==1)&&(p[1]==3))  //PLAYER 1 TAKES 30 DAMAGE
                  {
                       PP[0] = PP[0] + 10;
                       PP[1] = PP[1] - 30;
                       HP[0] = HP[0] - 30;
                  }
                  
                  else if ((p[0]==1)&&(p[1]==4))  //PLAYER 1 TAKES 50 DAMAGE
                  {
                       PP[0] = PP[0] + 10;
                       PP[1] = PP[1] - 50;
                       HP[0] = HP[0] - 50;
                  }
                  
                  else if ((p[0]==1)&&(p[1]==5))  //PLAYER 1 INCREASES 10PP AND TAKES NO DAMAGE
                  {
                       PP[0] = PP[0] + 10;
                  }
                  
                  else if ((p[0]==1)&&(p[1]==6))  //PLAYER 1 INCREASES 10PP; PLAYER 2 DECREASES 10PP
                  {
                       PP[0] = PP[0] + 10;
                       PP[1] = PP[1] - 10;
                  }
                  
                  else if ((p[0]==2)&&(p[1]==1))  //PLAYER 1 -10PP; PLAYER 2 +10PP and -10PP
                  {
                       PP[0] = PP[0] - 10;
                       PP[1] = PP[1] + 10;
                       HP[1] = HP[1] - 10;  
                  }
                  
                  else if ((p[0]==2)&&(p[1]==2))  //PLAYER 1 -10PP and -10HP; PLAYER 2 -10PP and -10HP
                  {
                       PP[0] = PP[0] - 10;
                       PP[1] = PP[1] - 10;
                       HP[0] = HP[0] - 10;
                       HP[1] = HP[1] - 10;
                  }
                  
                  else if ((p[0]==2)&&(p[1]==3))  //PLAYER 1 -10PP and -30HP; PLAYER 2 -30PP and -10HP
                  {
                       PP[0] = PP[0] - 10;
                       HP[1] = HP[1] - 10;
                       PP[1] = PP[1] - 30;
                       HP[0] = HP[0] - 30;
                  }
                  
                  else if ((p[0]==2)&&(p[1]==4))  //PLAYER 1 -10PP and -50HP; PLAYER 2 -50PP and -10HP
                  {
                       PP[0] = PP[0] - 10;
                       HP[1] = HP[1] - 10;
                       PP[1] = PP[1] - 50;
                       HP[0] = HP[0] - 50;
                  }
                  
                  else if ((p[0]==2)&&(p[1]==5))  //PLAYER 1 -10PP 
                  {
                       PP[0] = PP[0] - 10;
                  }
                  
                  else if ((p[0]==2)&&(p[1]==6))  //PLAYER 1 -10PP and -10HP; PLAYER 2 -10PP
                  {
                       PP[0] = PP[0] - 10;
                       HP[0] = HP[0] - 10;
                       PP[1] = PP[1] - 10;
                  }
                  
                  else if ((p[0]==3)&&(p[1]==1))  //PLAYER 1 -30PP and -0HP; PLAYER 2 +10PP and -30HP
                  {
                       PP[0] = PP[0] - 30;
                       PP[1] = PP[1] + 10;
                       HP[1] = HP[1] - 30;
                  }
                  
                  else if ((p[0]==3)&&(p[1]==2))  //PLAYER 1 -30PP and -10HP; PLAYER 2 -10PP and -30HP
                  {
                       PP[0] = PP[0] - 30;
                       PP[1] = PP[1] - 10;
                       HP[0] = HP[0] - 10;
                       HP[1] = HP[1] - 30;
                  }
                  
                  else if ((p[0]==3)&&(p[1]==3))  //PLAYER 1 -30PP and -30HP; PLAYER 2 -30PP and -30HP
                  {
                       PP[0] = PP[0] - 30;
                       PP[1] = PP[1] - 30;
                       HP[0] = HP[0] - 30;
                       HP[1] = HP[1] - 30;
                  }
                  
                  else if ((p[0]==3)&&(p[1]==4))  //PLAYER 1 -10PP and -50HP; PLAYER 2 -50PP and -30HP
                  {
                       PP[0] = PP[0] - 30;
                       PP[1] = PP[1] - 50;
                       HP[0] = HP[0] - 50;
                       HP[1] = HP[1] - 30;
                  }
                  
                  else if ((p[0]==3)&&(p[1]==5))  //PLAYER 1 -30PP 
                  {
                       PP[0] = PP[0] - 30;
                  }
                  
                  else if ((p[0]==3)&&(p[1]==6))  //PLAYER 1 -30PP and -30HP; PLAYER 2 -10PP 
                  {
                       PP[0] = PP[0] - 30;
                       HP[0] = HP[0] - 30;
                       PP[1] = PP[1] - 10;
                  }
                  
                  else if ((p[0]==4)&&(p[1]==1))  //PLAYER 1 -50PP; PLAYER 2 +10PP and -50HP
                  {
                       PP[0] = PP[0] - 50;
                       PP[1] = PP[1] + 10;
                       HP[1] = HP[1] - 50; 
                  }
                  
                  else if ((p[0]==4)&&(p[1]==2))  //PLAYER 1 -50PP and -10HP; PLAYER 2 -10PP and -50HP
                  {
                       PP[0] = PP[0] - 50;
                       HP[1] = HP[1] - 50;
                       PP[1] = PP[1] - 10;
                       HP[0] = HP[0] - 10;
                  }
                  
                  else if ((p[0]==4)&&(p[1]==3))  //PLAYER 1 -50PP and -30HP; PLAYER 2 -30PP and -50HP
                  {
                       PP[0] = PP[0] - 50;
                       HP[1] = HP[1] - 50;
                       PP[1] = PP[1] - 30;
                       HP[0] = HP[0] - 30;
                  }
                  
                  else if ((p[0]==4)&&(p[1]==4))  //PLAYER 1 -50PP and -50HP; PLAYER 2 -50PP and -50HP
                  {
                       PP[0] = PP[0] - 50;
                       HP[1] = HP[1] - 50;
                       PP[1] = PP[1] - 50;
                       HP[0] = HP[0] - 50;
                  }
                  
                  else if ((p[0]==4)&&(p[1]==5))  //PLAYER 1 -50PP; PLAYER 2 -50HP
                  {
                       PP[0] = PP[0] - 50;
                       HP[1] = HP[1] - 50;
                  }
                  
                  else if ((p[0]==4)&&(p[1]==6))  //PLAYER 1 -50PP and -50HP; PLAYER 2 -10PP
                  {
                       PP[0] = PP[0] - 50;
                       PP[1] = PP[1] - 10;
                       HP[0] = HP[0] - 50;
                  }
                  
                  else if ((p[0]==5)&&(p[1]==1))  //PLAYER 2 +10PP
                  {
                       PP[1] = PP[1] + 10;
                  }
                  
                  else if ((p[0]==5)&&(p[1]==2))  //PLAYER 2 -10PP
                  {
                       PP[1] = PP[1] - 10;
                  }
                  
                  else if ((p[0]==5)&&(p[1]==3))  //PLAYER 2 -30PP
                  {
                       PP[1] = PP[1] - 30;
                  }
                  
                  else if ((p[0]==5)&&(p[1]==4))  //PLAYER 2 -50PP; PLAYER 1 -50HP
                  {
                       PP[1] = PP[1] - 50;
                       HP[0] = HP[0] - 50;
                  }
                  
                  else if ((p[0]==5)&&(p[1]==5))  //BOTH PLAYERS NO DAMAGE AND INCREASE IN PP
                  {
                       HP[0] = HP [0];
                  }
                  
                  else if ((p[0]==5)&&(p[1]==6))  //PLAYER 2 -10PP
                  {
                       PP[1] = PP[1] - 10;
                  }
                  
                  else if ((p[0]==6)&&(p[1]==1))  //PLAYER 1 -10PP; PLAYER 2 +10PP
                  {
                       PP[0] = PP[0] - 10;
                       PP[1] = PP[1] + 10;
                  }
                  
                  else if ((p[0]==6)&&(p[1]==2))  //PLAYER 1 -10PP; PLAYER 2 -10PP and -10HP
                  {
                       PP[0] = PP[0] - 10;
                       PP[1] = PP[1] - 10;
                       HP[1] = HP[1] - 10;
                  }
                  
                  else if ((p[0]==6)&&(p[1]==3))  //PLAYER 1 -10PP; PLAYER 2 -30PP and -30HP
                  {
                       PP[0] = PP[0] - 10;
                       PP[1] = PP[1] - 30;
                       HP[1] = HP[1] - 30;
                  }
                  
                  else if ((p[0]==6)&&(p[1]==4))  //PLAYER 1 -10PP; PLAYER 2 -50PP and -50HP
                  {
                       PP[0] = PP[0] - 10;
                       PP[1] = PP[1] - 50;
                       HP[1] = HP[1] - 50;
                  }
                  
                  else if ((p[0]==6)&&(p[1]==5))  //PLAYER 1 -10PP
                  {
                       PP[0] = PP[0] - 10;
                  }
                  
                  else if ((p[0]==6)&&(p[1]==6))  //PLAYER 1 -10PP; PLAYER 2 -10PP
                  {
                       PP[0] = PP[0] - 10;
                       PP[1] = PP[1] - 10;
                  }
            }//ENDDO
            while ((HP[0] > 0) && (HP[1] > 0));
            
            if ((HP[0] <= 0) && (HP[1] > 0))
            {
                 SetConsoleTextAttribute
                      (hConsole, FOREGROUND_RED | FOREGROUND_GREEN | FOREGROUND_INTENSITY);  //CHANGES FONT COLOR TO YELLOW
                 printf("\nCONGRATULATIONS PLAYER 2 FOR WINNING THE BATTLE!!!");
                 printf("\n1- EXIT\n2- TRY AGAIN\nExit or try again?:\t");
                 scanf("%d",&exit);
            }
            
            else if ((HP[1] <= 0) && (HP[0] > 0))
            {
                 SetConsoleTextAttribute
                      (hConsole, FOREGROUND_RED | FOREGROUND_GREEN | FOREGROUND_INTENSITY);  //CHANGES FONT COLOR TO YELLOW
                 printf("\nCONGRATULATIONS PLAYER 1 FOR WINNING THE BATTLE!!!");
                 printf("\n1- EXIT\n2- TRY AGAIN\nExit or try again?:\t");
                 scanf("%d",&exit);
            }
            
            else if ((HP[0] <= 0) && (HP[1] <= 0))
            {
                 SetConsoleTextAttribute
                      (hConsole, FOREGROUND_RED | FOREGROUND_GREEN | FOREGROUND_INTENSITY);  //CHANGES FONT COLOR TO YELLOW
                 printf("\nIT'S A DRAW!!!");
                 printf("\n1- EXIT\n2- TRY AGAIN\n\nExit or try again?:\t");
                 scanf("%d",&exit);
            }
            switch(exit)
            {
                 case 1:
                        printf("\nThank you for playing!!!\n\n");
                        SetConsoleTextAttribute
                          (hConsole, 15);  //CHANGES FONT COLOR TO WHITE
                        system("PAUSE");
                        break;
                 case 2:
                        system("cls");
                        main();
                        break;
            }
}






void displaycharizard()  //CHARIZARD
{
     printf("\n                 .\"-,.__\n");
     printf("                 `.     `.  ,\n");
     printf("              .--'  .._,'\"-' `.\n");
     printf("             .    .'         `'\n");
     printf("             `.   /          ,'\n");
     printf("               `  '--.   ,-\"'\n");
     printf("                `\"`   |  \\\n");
     printf("                   -. \\, |\n");
     printf("                    `--Y.'      ___.\n");
     printf("                         \\     L._, \\\n");
     printf("               _.,        `.   <  <\\                _\n");
     printf("             ,' '           `, `.   | \\            ( `\n");
     printf("          ../, `.            `  |    .\\`.           \\ \\_\n");
     printf("         ,' ,..  .           _.,'    ||\\l            )  '\".\n");
     printf("        , ,'   \\           ,'.-.`-._,'  |           .  _._`.\n");
     printf("      ,' /      \\ \\        `' ' `--/   | \\          / /   ..\\\n");
     printf("    .'  /        \\ .         |\\__ - _ ,'` `        / /     `.`.\n");
     printf("    |  '          ..         `-...-\"  |  `-'      / /        . `.\n");
     printf("    | /           |L__           |    |          / /          `. `.\n");
     printf("   , /            .   .          |    |         / /             ` `\n");
     printf("  / /          ,. ,`._ `-_       |    |  _   ,-' /               ` \\\n");
     printf(" / .           \\\"`_/. `-_ \\_,.  ,'    +-' `-'  _,        ..,-.    `.\n");
     printf(".  '         .-f    ,'   `    '.       \\__.---'     _   .'   '     \\ \\\n");
     printf("' /          `.'    l     .' /          \\..      ,_|/   `.  ,'`     L`\n");
     printf("|'      _.-\"\"` `.    \\ _,'  `            \\ `.___`.'\"`-.  , |   |    | \\\n");
     printf("||    ,'      `. `.   '       _,...._        `  |    `/ '  |   '     .|\n");
     printf("||  ,'          `. ;.,.---' ,'       `.   `.. `-'  .-' /_ .'    ;_   ||\n");
     printf("|| '              V      / /           `   | `   ,'   ,' '.    !  `. ||\n");
     printf("||/            _,-------7 '              . |  `-'    l         /    `||\n");
     printf(". |          ,' .-   ,' ||               | .-.        `.      .'     ||\n");
     printf(" `'        ,'    `\".'    |               |    `.        '. -.'       `'\n");
     printf("          /      ,'      |               |,'    \\-.._,.'/'\n");
     printf("          .     /        .               .       \\    .''\n");
     printf("        .`.    |         `.             /         :_,'.'\n");
     printf("          \\ `...\\   _     ,'-.        .'         /_.-'\n");
     printf("           `-.__ `,  `'   .  _.>----''.  _  __  /\n");
     printf("                .'        /\"'          |  \"'   '_\n");
     printf("               /_|.-'\\ ,\".             '.'`__'-( \\\n");
     printf("                 / ,\"'\"\\,'               `/  `-.|\"\n");
}

void displayblastoise()  //BLASTOISE
{
    printf("                       _\n");
	printf("            _,..-\"\"\"--' `,.-\".\n");
	printf("          ,\'      __.. --\',  |\n");
	printf("        _/   _.-\"\' |    .\' | |       ____\n");
	printf("  ,.-\"\"\'    `-\"+.._|     `.\' | `-..,\',--.`.\n");
	printf(" |   ,.                      \'    j 7    l \\__\n");
	printf(" |.-\'                            /| |    j||  .\n");
	printf(" `.                   |         / L`.`\"\"\',\'|\\  \\\n");
	printf("   `.,----..._       ,\'`\"\'-.  ,\'   \\ `\"\"\'  | |  l\n");
	printf("     Y        `-----\'       v\'    ,\'`,.__..\' |   .\n");
	printf("      `.                   /     /   /     `.|   |\n");
	printf("        `.                /     l   j       ,^.  |L\n");
	printf("          `._            L       +. |._   .\' \\|  | \\\n");
	printf("            .`--...__,..-\'\"\"\'-._  l L  \"\"\"    |  |  \\\n");
	printf("          .\'  ,`-......L_       \\  \\ \\     _.\'  ,\'.  l\n");
    printf("       ,-\"`. / ,-.---.\'  `.      \\  L..--\"\'  _.-^.|   l\n");
    printf(" .-\"\".\'\"`.  Y  `._\'   \'    `.     | | _,.--\'\"     |   |\n");
    printf("  `._\'   |  |,-\'|      l     `.   | |\"..          |   l\n");
    printf("  ,\'.    |  |`._\'      |      `.  | |_,...---\"\"\"\"\"`    L\n");
    printf(" /   |   j _|-\' `.     L       | j ,|              |   |\n");
    printf("`--,\"._,-+\' /`---^..../._____,.L\',\' `.             |\\  |\n");
    printf("   |,\'      L                   |     `-.          | \\j\n");
    printf("            .                    \\       `,        |  |\n");
    printf("             \\                __`.Y._      -.     j   |\n");
    printf("              \\           _.,\'       `._     \\    |  j\n");
    printf("              ,-\"`-----\"\"\"\"\'           |`.    \\  7   |\n");
    printf("             /  `.        \'            |  \\    \\ /   |\n");
    printf("            |     `      /             |   \\    Y    |\n");
    printf("            |      \\    .             ,\'    |   L_.-\')\n");
    printf("             L      `.  |            /      ]     _.-^._\n");
    printf("              \\   ,\'  `-7         ,-\'      / |  ,\'      `-._\n");
    printf("             _,`._       `.   _,-\'        ,\',^.-            `.\n");
    printf("          ,-\'     v....  _.`\"\',          _:\'--....._______,.-\'\n");
    printf("        ._______./     /\',,-\'\"\'`\'--.  ,-\'  `.\n");
    printf("                 \"\"\"\"\"`.,\'         _\\`----...\' \n");
    printf("                        --------\"\"\'\n");
}

void titlescreen()  //TITLE SCREEN
{
     printf("     *******  *********   *********    *****      *******  ****      ***   *****     ****    **\n");
     printf("   ********  *********** ***********  *******   ********  *****     ****  *******   ******   **\n");
     printf("   **         **    ****  **    **** ***   ***  **         ** **   *  ** ***   ***   ** **   **\n");
     printf("   **         **     ***  **     *** **     **  **         ** **  **  ** **     **   **  **  **\n");
     printf("   **         **     **   **     **  **     **  **    **   **  ** **  ** **     **   **  **  **\n");
     printf("   ***        **    ***   **    ***  **     **  ***   **   **   ***   ** **     **   **   ** **\n");
     printf("    ***       **   ***    **   ***   ***   ***   **   **   **   ***   ** ***   ***   **   *****\n");
     printf("    ******    **          **   ***    *******    *******   **    *    **  *******    **    ****\n");
     printf("     ****     **          **    ****   *****       ****    **    *    **   *****     **    ****\n");
     /*printf("                                                                                            ***\n");
     printf("                                                                                            *\n");*/
     printf("\n\t\t\tCreated by: Ervin Lester Lu   and   Chritian Josef Leong\n\n\n");
     system("PAUSE");
     system("cls");
}

void AI()  //AI CHOICE
{
    //int p[2];
	int aichoice;
	srand ( time(NULL) +1 );
	p[1] = 0;
	
	do{
			p[1] = rand()%7; //always randomizes
		}while (p[1] == 0 || p[1] >= 7);
		
/*	switch(aichoice)
    {
			case 1: printf("1\n\n"); break;
			case 2: printf("2\n\n"); break;
			case 3: printf("3\n\n"); break;
			case 4: printf("4\n\n"); break;
			case 5: printf("5\n\n"); break;
			case 6: printf("6\n\n"); break;
			
	}*/
}

void gamefor1player()  //GAME FOR 1 PLAYER
{
     HANDLE hConsole;
    hConsole = GetStdHandle (STD_OUTPUT_HANDLE);
      
    int exit, HP[2], PP[2];
    PP[0]=0;
    PP[1]=0;
    HP[0]=100;
    HP[1]=100;
    
	do
            {
                  SetConsoleTextAttribute
                      (hConsole, FOREGROUND_RED | FOREGROUND_INTENSITY);  //CHANGES FONT COLOR TO RED
                  displaycharizard();
                  SetConsoleTextAttribute
                      (hConsole, FOREGROUND_BLUE | FOREGROUND_GREEN | FOREGROUND_INTENSITY);  //CHANGES FONT COLOR TO CYAN
                  displaymovelist1();  //PLAYER 1 PROGRAM
                  printf("\n\n");
                  printf("\nPlayer 1:\tHP:%d \tPP:%d",HP[0],PP[0]);
                  printf("\nPlayer 2:\tHP:%d \tPP:%d",HP[1],PP[1]);
                  printf("\n\nPlayer 1, Enter Your Choice of Move Here:\t");
                  scanf("%d", &p[0]);

                  if ((p[0] < 1) || p[0] > 6) { //p[0] = choice in attacking
                  do
                  {
                       printf("\nINVALID INPUT");
                       printf("\nPlease Enter Your Choice of Move Again Here:\t");
                       getchar();
                       scanf("%d", &p[0]);
                  }
                  while ((p[0] < 1) || (p[0] > 6));
              }
                  else if ((p[0] == 4) && (PP[0] < 50)){  //CHOICE IS MOVE 4
                  do
                  {
                       printf("\nPlayer 1, you lack PP to perform the move");
                       printf("\nPlease Enter Your Choice of Move Again Here:\t");
                       scanf("%d", &p[0]);
                       if(p[0] == 6 || p[0] == 2 || p[0] == 3){ p[0] = 4; }
                       
                  }
                  while (p[0] == 4);
              }
                  else if ((p[0] == 3) && (PP[0] < 30)){  //CHOICE IS MOVE 3
                  do
                  {
                      printf("\nPlayer 1, you lack PP to perform the move");
                      printf("\nPlease Enter Your Choice of Move Again Here:\t");
                      scanf("%d", &p[0]);
                      if(p[0] == 6 || p[0] == 2){ p[0] = 3; }
                  }
                  while ((p[0]==3)||(p[0]==4));
              }
                  else if ((p[0] == 2) && (PP[0] < 10))  {//CHOICE IS MOVE 2
                  do
                  {
                      printf("\nPlayer 1, you lack PP to perform the move");
                      printf("\nPlease Enter Your Choice of Move Again Here:\t");
                      scanf("%d", &p[0]);
                  }
                  while ((p[0]==2)||(p[0]==6)||(p[0]==3)||(p[0]==4));
              }
                  else if ((p[0] == 6) && (PP[0] < 10)) { //CHOICE IS MOVE 6
                  do
                  {
                      printf("\nPlayer 1, you lack PP to perform the move");
                      printf("\nPlease Enter Your Choice of Move Again Here:\t");
                      scanf("%d", &p[0]); 
                  }
                  while ((p[0]==2)||(p[0]==6)||(p[0]==3)||(p[0]==4));
              }
                  //system("cls");
                  
                  SetConsoleTextAttribute
                      (hConsole, FOREGROUND_BLUE | FOREGROUND_INTENSITY);  //CHANGES FONT COLOR TO BLUE
                  displayblastoise();
                  SetConsoleTextAttribute
                      (hConsole, FOREGROUND_BLUE | FOREGROUND_RED | FOREGROUND_INTENSITY);  //CHANGES FONT COLOR TO VIOLET
                  displaymovelist2();  //PLAYER 2 PROGRAM
                  printf("\n\n");
                  printf("\nPlayer 1:\tHP:%d \tPP:%d",HP[0],PP[0]);
                  printf("\nPlayer 2:\tHP:%d \tPP:%d",HP[1],PP[1]);
                 // printf("\n\nPlayer 2, Enter Your Choice of Move Here:\t");
                  AI();
                  //scanf("%d", &p[1]); 
                  //printf("\nRANDOMIZER PICKED %d", p[1]);
                  if ((p[1] < 1) || (p[1] > 6))  //p[0] = choice in attacking
                  do
                  {
                     //  printf("\nINVALID INPUT");
                     //  printf("\nPlease Enter Your Choice of Move Again Here:\t");
                        AI();
                      // scanf("%d", &p[1]); 
                  }
                  while ((p[1] < 1) || (p[1] > 6));
                  
                  else if ((p[1] == 4) && (PP[1] < 50))  //CHOICE IS MOVE 4
                  do
                  {
                     //  printf("\nPlayer 2, you lack PP to perform the move");
                     ///  printf("\nPlease Enter Your Choice of Move Again Here:\t");
                        AI();
                        if(p[1] == 6 || p[1] == 2 || p[1] == 3){ p[1] = 4; }
                      // scanf("%d", &p[1]); 
                  }
                  while (p[1] == 4);
                  
                  else if ((p[1] == 3) && (PP[1] < 30))  //CHOICE IS MOVE 3
                  do
                  {
                    //  printf("\nPlayer 2, you lack PP to perform the move");
                    ///  printf("\nPlease Enter Your Choice of Move Again Here:\t");
                    AI();
                    if(p[1] == 6 || p[1] == 2){ p[1] = 3; }
                      //scanf("%d", &p[1]); 
                  }
                  while ((p[1]==3)||(p[1]==4));
                  
                  else if ((p[1] == 2) && (PP[1] < 10))  //CHOICE IS MOVE 2
                  do
                  {
                     // printf("\nPlayer 2, you lack PP to perform the move");
                     // printf("\nPlease Enter Your Choice of Move Again Here:\t");
                       AI();
                     // scanf("%d", &p[1]); 
                  }
                  while ((p[1]==2)||(p[1]==6)||(p[1]==3)||(p[1]==4));
                  
                  else if ((p[1] == 6) && (PP[1] < 10))  //CHOICE IS MOVE 6
                  do
                  {
                     // printf("\nPlayer 2, you lack PP to perform the move");
                      //printf("\nPlease Enter Your Choice of Move Again Here:\t");
                       AI();
                     // scanf("%d", &p[1]); 
                  }
                  while ((p[1]==2)||(p[1]==6)||(p[1]==3)||(p[1]==4));
                  
                  system("cls");
                  //printf What player 1 and player 2 did, System Pause for each if else.
                  if ((p[0]==1)&&(p[1]==1))  //ADD PP TO BOTH PLAYERS
                  {
                  	printf("Player 1 Rested!\nPlayer 2 Rested!\n"); system("pause");
                       PP[0] = PP[0] + 10;
                       PP[1] = PP[1] + 10;
                  }
                  
                  else if ((p[0]==1)&&(p[1]==2))  //PLAYER 1 TAKES 10 DAMAGE
                  {
                  		printf("Player 1 Rested!\nPlayer 2 Used Scratch!\n"); system("pause");
                       PP[0] = PP[0] + 10;
                       PP[1] = PP[1] - 10;
                       HP[0] = HP[0] - 10;
                  }
                  
                  else if ((p[0]==1)&&(p[1]==3))  //PLAYER 1 TAKES 30 DAMAGE
                  {
                  	printf("Player 1 Rested!\nPlayer 2 Used Water Pulse!\n"); system("pause");
                       PP[0] = PP[0] + 10;
                       PP[1] = PP[1] - 30;
                       HP[0] = HP[0] - 30;
                  }
                  
                  else if ((p[0]==1)&&(p[1]==4))  //PLAYER 1 TAKES 50 DAMAGE
                  {
                  	printf("Player 1 Rested!\nPlayer 2 Used Hydro Pump!\n"); system("pause");
                       PP[0] = PP[0] + 10;
                       PP[1] = PP[1] - 50;
                       HP[0] = HP[0] - 50;
                  }
                  
                  else if ((p[0]==1)&&(p[1]==5))  //PLAYER 1 INCREASES 10PP AND TAKES NO DAMAGE
                  {
                  		printf("Player 1 Rested!\nPlayer 2 used Shield!\n"); system("pause");
                       PP[0] = PP[0] + 10;
                  }
                  
                  else if ((p[0]==1)&&(p[1]==6))  //PLAYER 1 INCREASES 10PP; PLAYER 2 DECREASES 10PP
                  {
                  	printf("Player 1 Rested!\nPlayer 2 Used Reflect!\n"); system("pause");
                       PP[0] = PP[0] + 10;
                       PP[1] = PP[1] - 10;
                  }
                  
                  else if ((p[0]==2)&&(p[1]==1))  //PLAYER 1 -10PP; PLAYER 2 +10PP and -10PP
                  {
                  	  printf("Player 1 Scratch\nPlayer 2 Rested!\n"); system("pause");
                       PP[0] = PP[0] - 10;
                       PP[1] = PP[1] + 10;
                       HP[1] = HP[1] - 10;  
                  }
                  
                  else if ((p[0]==2)&&(p[1]==2))  //PLAYER 1 -10PP and -10HP; PLAYER 2 -10PP and -10HP
                  {
                  	printf("Player 1 used Scratch!\nPlayer 2 Used Scratch!\n"); system("pause");
                       PP[0] = PP[0] - 10;
                       PP[1] = PP[1] - 10;
                       HP[0] = HP[0] - 10;
                       HP[1] = HP[1] - 10;
                  }
                  
                  else if ((p[0]==2)&&(p[1]==3))  //PLAYER 1 -10PP and -30HP; PLAYER 2 -30PP and -10HP
                  {
                  	printf("Player 1 used Scratch!\nPlayer 2 Used Water Pulse!\n"); system("pause");
                       PP[0] = PP[0] - 10;
                       HP[1] = HP[1] - 10;
                       PP[1] = PP[1] - 30;
                       HP[0] = HP[0] - 30;
                  }
                  
                  else if ((p[0]==2)&&(p[1]==4))  //PLAYER 1 -10PP and -50HP; PLAYER 2 -50PP and -10HP
                  {
                  	printf("Player 1 used Scratch!\nPlayer 2 Used Hydro Pump!\n"); system("pause");
                       PP[0] = PP[0] - 10;
                       HP[1] = HP[1] - 10;
                       PP[1] = PP[1] - 50;
                       HP[0] = HP[0] - 50;
                  }
                  
                  else if ((p[0]==2)&&(p[1]==5))  //PLAYER 1 -10PP 
                  {
                  	printf("Player 1 used Scratch!\nPlayer 2 Used Shield!\n"); system("pause");
                       PP[0] = PP[0] - 10;
                  }
                  
                  else if ((p[0]==2)&&(p[1]==6))  //PLAYER 1 -10PP and -10HP; PLAYER 2 -10PP
                  {
    				printf("Player 1 used Scratch!\nPlayer 2 Used Reflect!\n"); system("pause");
                       PP[0] = PP[0] - 10;
                       HP[0] = HP[0] - 10;
                       PP[1] = PP[1] - 10;
                  }
                  
                  else if ((p[0]==3)&&(p[1]==1))  //PLAYER 1 -30PP and -0HP; PLAYER 2 +10PP and -30HP
                  {
                       printf("Player 1 used Fire Blast!\nPlayer 2 Rested!\n"); system("pause");
                       PP[0] = PP[0] - 30;
                       PP[1] = PP[1] + 10;
                       HP[1] = HP[1] - 30;
                  }
                  
                  else if ((p[0]==3)&&(p[1]==2))  //PLAYER 1 -30PP and -10HP; PLAYER 2 -10PP and -30HP
                  {
                       printf("Player 1 used Fire Blast!\nPlayer 2 used Scratch!\n"); system("pause");
                       PP[0] = PP[0] - 30;
                       PP[1] = PP[1] - 10;
                       HP[0] = HP[0] - 10;
                       HP[1] = HP[1] - 30;
                  }
                  
                  else if ((p[0]==3)&&(p[1]==3))  //PLAYER 1 -30PP and -30HP; PLAYER 2 -30PP and -30HP
                  {
                       printf("Player 1 used Fire Blast!\nPlayer 2 used Water Pulse!\n"); system("pause");
                       PP[0] = PP[0] - 30;
                       PP[1] = PP[1] - 30;
                       HP[0] = HP[0] - 30;
                       HP[1] = HP[1] - 30;
                  }
                  
                  else if ((p[0]==3)&&(p[1]==4))  //PLAYER 1 -10PP and -50HP; PLAYER 2 -50PP and -30HP
                  {
                       printf("Player 1 used Fire Blast!\nPlayer 2 used Hydro Pump!\n"); system("pause");
                       PP[0] = PP[0] - 30;
                       PP[1] = PP[1] - 50;
                       HP[0] = HP[0] - 50;
                       HP[1] = HP[1] - 30;
                  }
                  
                  else if ((p[0]==3)&&(p[1]==5))  //PLAYER 1 -30PP 
                  {
                       printf("Player 1 used Fire Blast!\nPlayer 2 used Shield!\n"); system("pause");
                       PP[0] = PP[0] - 30;
                  }
                  
                  else if ((p[0]==3)&&(p[1]==6))  //PLAYER 1 -30PP and -30HP; PLAYER 2 -10PP 
                  {
                       printf("Player 1 used Fire Blast!\nPlayer 2 used Reflect!\n"); system("pause");
                       PP[0] = PP[0] - 30;
                       HP[0] = HP[0] - 30;
                       PP[1] = PP[1] - 10;
                  }
                  
                  else if ((p[0]==4)&&(p[1]==1))  //PLAYER 1 -50PP; PLAYER 2 +10PP and -50HP
                  {
                       printf("Player 1 used Flame Wheel!\nPlayer 2 Rested!\n"); system("pause");
                       PP[0] = PP[0] - 50;
                       PP[1] = PP[1] + 10;
                       HP[1] = HP[1] - 50; 
                  }
                  
                  else if ((p[0]==4)&&(p[1]==2))  //PLAYER 1 -50PP and -10HP; PLAYER 2 -10PP and -50HP
                  {
                       printf("Player 1 used Flame Wheel!\nPlayer 2 used Scratch!\n"); system("pause");
                       PP[0] = PP[0] - 50;
                       HP[1] = HP[1] - 50;
                       PP[1] = PP[1] - 10;
                       HP[0] = HP[0] - 10;
                  }
                  
                  else if ((p[0]==4)&&(p[1]==3))  //PLAYER 1 -50PP and -30HP; PLAYER 2 -30PP and -50HP
                  {
                       printf("Player 1 used Flame Wheel!\nPlayer 2 used Water Pulse!\n"); system("pause");
                       PP[0] = PP[0] - 50;
                       HP[1] = HP[1] - 50;
                       PP[1] = PP[1] - 30;
                       HP[0] = HP[0] - 30;
                  }
                  
                  else if ((p[0]==4)&&(p[1]==4))  //PLAYER 1 -50PP and -50HP; PLAYER 2 -50PP and -50HP
                  {
                       printf("Player 1 used Flame Wheel!\nPlayer 2 used Hydro Pump!\n"); system("pause");
                       PP[0] = PP[0] - 50;
                       HP[1] = HP[1] - 50;
                       PP[1] = PP[1] - 50;
                       HP[0] = HP[0] - 50;
                  }
                  
                  else if ((p[0]==4)&&(p[1]==5))  //PLAYER 1 -50PP; PLAYER 2 -50HP
                  {
                       printf("Player 1 used Flame Wheel!\nPlayer 2 used Shield!\n"); system("pause");
                       PP[0] = PP[0] - 50;
                       HP[1] = HP[1] - 50;
                  }
                  
                  else if ((p[0]==4)&&(p[1]==6))  //PLAYER 1 -50PP and -50HP; PLAYER 2 -10PP
                  {
                       printf("Player 1 used Flame Wheel!\nPlayer 2 used Reflect!\n"); system("pause");
                       PP[0] = PP[0] - 50;
                       PP[1] = PP[1] - 10;
                       HP[0] = HP[0] - 50;
                  }
                  
                  else if ((p[0]==5)&&(p[1]==1))  //PLAYER 2 +10PP
                  {
                       printf("Player 1 used Shield!\nPlayer 2 Rested!\n"); system("pause");
                       PP[1] = PP[1] + 10;
                  }
                  
                  else if ((p[0]==5)&&(p[1]==2))  //PLAYER 2 -10PP
                  {
                       printf("Player 1 used Shield!\nPlayer 2 used Scratch!\n"); system("pause");
                       PP[1] = PP[1] - 10;
                  }
                  
                  else if ((p[0]==5)&&(p[1]==3))  //PLAYER 2 -30PP
                  {
                       printf("Player 1 used Shield!\n Player 2 used Water Pulse!\n"); system("pause");
                       PP[1] = PP[1] - 30;
                  }
                  
                  else if ((p[0]==5)&&(p[1]==4))  //PLAYER 2 -50PP; PLAYER 1 -50HP
                  {
                       printf("Player 1 used Shield!\n Player 2 used Hydro Pump!\n"); system("pause");
                       PP[1] = PP[1] - 50;
                       HP[0] = HP[0] - 50;
                  }
                  
                  else if ((p[0]==5)&&(p[1]==5))  //BOTH PLAYERS NO DAMAGE AND INCREASE IN PP
                  {
                       printf("Player 1 used Shield!\n Player 2 used Shield!\n"); system("pause");
                       HP[0] = HP [0];
                  }
                  
                  else if ((p[0]==5)&&(p[1]==6))  //PLAYER 2 -10PP
                  {
                       printf("Player 1 used Shield!\n Player 2 used Reflect!\n"); system("pause");
                       PP[1] = PP[1] - 10;
                  }
                  
                  else if ((p[0]==6)&&(p[1]==1))  //PLAYER 1 -10PP; PLAYER 2 +10PP
                  {
                       printf("Player 1 used Reflect!\n Player 2 Rested!\n"); system("pause");
                       PP[0] = PP[0] - 10;
                       PP[1] = PP[1] + 10;
                  }
                  
                  else if ((p[0]==6)&&(p[1]==2))  //PLAYER 1 -10PP; PLAYER 2 -10PP and -10HP
                  {
                       printf("Player 1 used Reflect!\n Player 2 used Scratch!\n"); system("pause");
                       PP[0] = PP[0] - 10;
                       PP[1] = PP[1] - 10;
                       HP[1] = HP[1] - 10;
                  }
                  
                  else if ((p[0]==6)&&(p[1]==3))  //PLAYER 1 -10PP; PLAYER 2 -30PP and -30HP
                  {
                       printf("Player 1 used Reflect!\n Player 2 used Water Pulse!\n"); system("pause");
                       PP[0] = PP[0] - 10;
                       PP[1] = PP[1] - 30;
                       HP[1] = HP[1] - 30;
                  }
                  
                  else if ((p[0]==6)&&(p[1]==4))  //PLAYER 1 -10PP; PLAYER 2 -50PP and -50HP
                  {
                       printf("Player 1 used Reflect!\n Player 2 used Hydro Pump!\n"); system("pause");
                       PP[0] = PP[0] - 10;
                       PP[1] = PP[1] - 50;
                       HP[1] = HP[1] - 50;
                  }
                  
                  else if ((p[0]==6)&&(p[1]==5))  //PLAYER 1 -10PP
                  {
                       printf("Player 1 used Reflect!\n Player 2 used Shield!\n"); system("pause");
                       PP[0] = PP[0] - 10;
                  }
                  
                  else if ((p[0]==6)&&(p[1]==6))  //PLAYER 1 -10PP; PLAYER 2 -10PP
                  {
                       printf("Player 1 used Reflect!\n Player 2 used Reflect!\n"); system("pause");
                       PP[0] = PP[0] - 10;
                       PP[1] = PP[1] - 10;
                  }
            }//ENDDO
            while ((HP[0] > 0) && (HP[1] > 0));
            
            if ((HP[0] <= 0) && (HP[1] > 0))
            {
                 SetConsoleTextAttribute
                      (hConsole, FOREGROUND_RED | FOREGROUND_GREEN | FOREGROUND_INTENSITY);  //CHANGES FONT COLOR TO YELLOW
                 printf("\nCONGRATULATIONS PLAYER 2 FOR WINNING THE BATTLE!!!");
                 printf("\n1- EXIT\n2- TRY AGAIN\nExit or try again?:\t");
                 scanf("%d",&exit);
            }
            
            else if ((HP[1] <= 0) && (HP[0] > 0))
            {
                 SetConsoleTextAttribute
                      (hConsole, FOREGROUND_RED | FOREGROUND_GREEN | FOREGROUND_INTENSITY);  //CHANGES FONT COLOR TO YELLOW
                 printf("\nCONGRATULATIONS PLAYER 1 FOR WINNING THE BATTLE!!!");
                 printf("\n1- EXIT\n2- TRY AGAIN\nExit or try again?:\t");
                 scanf("%d",&exit);
            }
            
            else if ((HP[0] <= 0) && (HP[1] <= 0))
            {
                 SetConsoleTextAttribute
                      (hConsole, FOREGROUND_RED | FOREGROUND_GREEN | FOREGROUND_INTENSITY);  //CHANGES FONT COLOR TO YELLOW
                 printf("\nIT'S A DRAW!!!");
                 printf("\n1- EXIT\n2- TRY AGAIN\n\nExit or try again?:\t");
                 scanf("%d",&exit);
            }
            switch(exit)
            {
                 case 1:
                        printf("\nThank you for playing!!!\n\n");
                        SetConsoleTextAttribute
                          (hConsole, 15);  //CHANGES FONT COLOR TO WHITE
                        system("PAUSE");
                        break;
                 case 2:
                        system("cls");
                        main();
                        break;
            }
}
