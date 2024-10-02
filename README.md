#include <iostream>
#include <string>
#include <ctime>
using namespace std;

int main(){
    string opponent;
    string player;
    int playerscore = 0;
    int opponentscore = 0;
    cout << "Welcome! " << endl;
    cout << "To Exit press 'Enter'" << endl;
    string rps[] = {"rock","paper","scissor"};
    srand((unsigned int) time(NULL));
    while(true)
    {
        cout << " Enter rock paper or scissor =" ;
        getline(cin , player);
        if (player != "rock" && player != "paper" && player != "scissor"){
            break;
        }
        opponent = rps[rand() % 3];       //rps generates random number and % 3 divides that number with 3 to get 1,2,0 as remainder
        cout << "Opponent choose = " << opponent << "," << endl;    
        if (player == opponent){
            playerscore++;
            opponentscore++;
        }
        else if (player == "rock"){
          if (opponent == "paper") opponentscore++;
          else if (opponent == "scissor") playerscore++;
        }
        else if (player == "paper"){
          if (opponent == "rock") opponentscore++;
          else if (opponent == "scissor") opponentscore++;
        }
        else if (player == "scissor"){
            if (opponent == "paper") playerscore++;
            else if (opponent == "rock") opponentscore++;
        }
    }
    cout << "Final Score of player = " << playerscore << " Final score of opponent = " << opponentscore << " " << endl ;
    if (playerscore < opponentscore) cout << "Opponent wins! ";
    else if (playerscore > opponentscore) cout << "Player wins! ";
}
