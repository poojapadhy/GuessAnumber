#include <stdio.h>
#include <stdlib.h>
#include<time.h>

int main()
{
int randomNumber = 0;
int guess = 0;
int numberofGuesses;
time_t t;

//intialisation of randomNumber generator
srand((unsigned ) time(&t));

//randomnumber initialisation
randomNumber = rand() % 21;

printf ("\nHi! This Is a Guessing Game.\n");
printf ("\nI have chosen a number between 0 to 20 which you must guess\n");


for(numberofGuesses = 5; numberofGuesses > 0; --numberofGuesses)

{

printf("\nYou have %d tr%s left\n", numberofGuesses, numberofGuesses == 1 ? "y" : "ies");

printf ("\nEnter a guess: ");
scanf("%d", &guess);

    if(guess  == randomNumber)
    {
    printf ("\n Congratulations you have guessed it correct\n");
    break;
    }
    else if(guess  < 0 || guess > 20)
    printf ("\nI said the number is between 0 and 20\n");
    else if(randomNumber > guess )
    printf ("\n Sorry %d number is wrong. My number is greater than that\n",guess);
    else if(randomNumber < guess )
    printf ("\n Sorry %d number is wrong. My number is less than that\n", guess );
     
}
printf ("You have had 5 tries left but you failed. The number is %d", randomNumber );


    return 0;
}
