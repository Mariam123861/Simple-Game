#include <iostream>
#include <cstdlib> 
#include <ctime>
using namespace std;

int a1 = 0, a2 = 0, a3 = 0;
int randomNumber(int max) {
  return (rand() % max) + 1;
}
string Whowin(int c1,int c2)
{
  
  if (c1 == c2) 
  {
    system("color 60");  a3++; return "NO Winner";
  }
  else if (c1 == 1 && c2 == 2)
  {
    system("color 40"); a2++; return "Computer";
  }
  else if (c1 == 1 && c2 == 3)
  {
    system("color 2F"); a1++; return "Player";
  }
  else if (c1 == 2 && c2 == 1) 
  {
    system("color 2F"); a1++; return "Player";
  }

  else if (c1 == 3 && c2 == 1) 
  {
    system("color 40");  a2++;return "Computer";
  }
  else if (c1 == 3 && c2 == 2)
  {
    system("color 2F"); a1++; return "Player";
  }
  else if (c1 == 2 && c2 == 3)
  {
    system("color 40"); a2++; return "Computer";
  }
}
string choice(int c)
{
  if (c == 1)return "Stone";
  if (c == 2)return "Paper";
  if (c == 3)return "Scissors";
}
void Game(int i)
{
  cout << "Your choice: [1]:Stone, [2]Paper, [3]:Scissors ? ";
  int c1; cin >> c1; cout << endl;
  int c2= randomNumber(3);
  cout << "----------------------Round[" << i << "]----------------------" << endl;
  cout << "Player Choice: " << choice(c1) << endl;
  cout << "Computer Choice: " << choice(c2) << endl;
  cout << "The Winner: " << Whowin(c1,c2) << endl;
  cout << "---------------------------------------------------" << endl;
  
}
void AllRounds(int n)
{
  for (int i = 0; i < n; i++)
  {
    cout << "Round [" << i + 1 << "] begins:" << endl << endl;
    Game(i+1);
  }
}
int main()
{
  srand(time(0));
  int c = 'y';
  do
  {
    system("cls");
    system("Color 07");
    
    cout << "How many rounds do you want to play ? ";
    int n; cin >> n; cout << endl;
    AllRounds(n);
    cout << "                    ------------------------------------------------------" << endl;
    cout << "                                    +++ G a m e O v e r +++" << endl;
    cout << "                    ------------------------------------------------------" << endl;
    cout << "                    ---------------------[Game Results]-------------------" << endl;
    cout << "                    Game Rounds               : " << n << endl;
    cout << "                    Player won times               : " << a1 << endl;
    cout << "                    Computer won times               : " << a2 << endl;
    cout << "                    Draw times               : " << a3 << endl;
    if (a1 > a2)
    {
      system("color 2F"); cout << "                    Final Winner               : " << "Player" << endl;
    }
    else if (a1 < a2)
    {
      system("color 40");
      cout << "                    Final Winner               : " << "Computer" << endl;
    }
    else
    {
      system("color 60"); cout << "                    Final Winner               : " << "No Winner" << endl;
    }
    cout << "                    ------------------------------------------------------" << endl;
    cout << endl;
    cout << "Do you want to play again [Y] or [N]"; cout << endl;
    cin >> c;
  } while (c == 'y' || c == 'Y');
}
