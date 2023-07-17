# rkk
Dual Enrollment Project - C++

/*
Chapter 6 Project 1
Programming Challenge #24 - Rock, Paper, Scissors Game Author: <Rania Krourou>
Date: <04/10/2021>
*/
#include <iostream> #include <ctime> #include <cstdlib>
using namespace std;
//Constant Variables
const int rockChoice = 1; const int paperChoice = 2; const int scissorsChoice = 3;
//Function Prototypes
void displayCompChoice(int);
void showMenu();
void determineWinner(int, int, bool &); int getCompChoice(int);
int getUserChoice(int);
int inputValidation(int);
int main(){
int compChoice; int userChoice;
cout << "\nWelcome to the Rock, Paper, Scissors Game!\n" << endl; showMenu();
bool playAgain;
do {
compChoice = getCompChoice(compChoice); userChoice = getUserChoice(userChoice);
displayCompChoice(compChoice); determineWinner(compChoice, userChoice, playAgain);
} while (playAgain == 1); return 0;
}
void showMenu() {
cout << "The Game Menu\n";
cout << "---------------";
cout << "\n1. Rock" << endl; cout << "2. Paper" << endl; cout << "3. Scissors\n" << endl;
}
int getCompChoice(int compChoice) {
unsigned number = time(0); srand(number); return(rand()%(3+1));
}
int getUserChoice(int userChoice) {
cout << "Choose '1' for rock, '2' for paper, or '3' for scissors: ";
userChoice = inputValidation(userChoice);
return userChoice; }
int inputValidation(int userChoice) {
while (!(cin >> userChoice) || (userChoice < rockChoice || userChoice > scissorsChoice))
{
cout << "Invalid number, should be 1 or greater: "; cin.clear();
cin.ignore(5,'\n');
}
return userChoice; }
void displayCompChoice(int compChoice) {
if(compChoice == 1)
 
{
cout << "\nThe computer chose Rock." << endl;
 }
    else if (compChoice == 2)
    {
        cout << "\nThe computer chose Paper." << endl;
    }
else
    {
        cout << "\nThe computer chose Scissors." << endl;
}}
void determineWinner(int compChoice,int userChoice,bool &playAgain) {
cout << endl;
if
    (compChoice == rockChoice && userChoice == paperChoice)
    {
            cout << "Paper wraps rock.\n";
            cout << "You win! Congrats!\n";
            playAgain = 0;
    }
    else if (compChoice == rockChoice && userChoice == scissorsChoice)
    {
            cout << "The rock smashes the scissors.\n";
            cout << "Sorry, the computer wins.\n";
            playAgain = 0;
    }
        else if (compChoice == rockChoice && userChoice == rockChoice)
        {
            cout << "It's a tie between both. Try again.\n" << endl;
            playAgain = 1;
        }
        else if (compChoice == paperChoice && userChoice == rockChoice)
        {
            cout << "Paper wraps rock.\n";
            cout << "Sorry, the computer wins.\n";
            playAgain = 0;
        }
        else if (compChoice == paperChoice && userChoice == scissorsChoice)
        {
            cout << "Scissors cuts paper.\n";
            cout << "You win! Congrats!\n";
            playAgain = 0;
}
else if (compChoice == paperChoice && userChoice == paperChoice)
{
     cout << "It's a tie between both. Try again.\n" << endl;
     playAgain = 1;
 }
  else if (compChoice == scissorsChoice && userChoice == rockChoice)
 {
     cout << "The rock smashes scissors.\n";
     cout << "You win! Congrats!\n";
     playAgain = 0;
 }
 else if (compChoice == scissorsChoice && userChoice == paperChoice)
 {
     cout << "Scissors cuts paper.\n";
     cout << "Sorry, the computer wins.\n";
     playAgain = 0;
 }
 else if (compChoice == scissorsChoice && userChoice == scissorsChoice)
 {
     cout << "It's a tie between both. Try again.\n" << endl;
     playAgain = 1;
 }
}
