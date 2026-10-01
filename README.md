# number-guessing-game

#include <iostream>
#include <cstdlib>
#include <ctime>
using namespace std;

int main()
{
    int number, guess, attempts;
    char playAgain;

    srand(time(0));

    do
    {
        number = rand() % 100 + 1;
        attempts = 0;

        cout << "\n===== NUMBER GUESSING GAME =====\n";
        cout << "Guess a number between 1 and 100\n";

        do
        {
            cout << "\nEnter your guess: ";
            cin >> guess;

            attempts++;

            if (guess > number)
            {
                cout << "Too High! Try Again.\n";
            }
            else if (guess < number)
            {
                cout << "Too Low! Try Again.\n";
            }
            else
            {
                cout << "\nCongratulations! You guessed it!\n";
                cout << "Correct Number: " << number << endl;
                cout << "Total Attempts: " << attempts << endl;
            }

        } while (guess != number);

        cout << "\nYour Final Score: " << attempts << " attempts\n";

        cout << "\nDo you want to play again? (Y/N): ";
        cin >> playAgain;

    } while (playAgain == 'Y' || playAgain == 'y');

    cout << "\nThank you for playing!\n";

    return 0;
}
