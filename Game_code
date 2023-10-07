#include <iostream>
#include <ctime>
#include <cstdlib>
using namespace std;

class Random
{
public:
    static int RandomChar()
    {
        srand(time(0));

        int r = rand() % 2;
        if (r < 1)
            return (char)rand() % 25 + 65;
        return (char)rand() % 25 + 97;
    }
};

class Timer
{
public:
    static double GetDeltaTime(clock_t start, clock_t end)
    {
        double difference;
        difference = (double)(end - start) / CLOCKS_PER_SEC;
        return difference;
    }
};

class Scoreboard {
private:
    int _counter;
    double _timeSum;
public:

    Scoreboard() {
        _counter = 0;
        _timeSum = 0;
    }

    void AddNewScore(double time)
    {
        _counter++;
        _timeSum += time;
    }

    double GetMiddleResult()
    {
        return (double)_timeSum / _counter;
    }

    int GetCounter()
    {
        return _counter;
    }

    
};
class Game
{
public:
    Game() {}
    Game(Game& right) = delete;
    Game(Game&& right) = delete;

    Game& operator=(Game& right) = delete;


    double PlayGame()
    {
        cout << "New Game" << endl;

        bool closed = false;
        while (!closed)
            closed = GameLoop();

        double result = _score.GetMiddleResult();
        double number = _score.GetCounter();
        cout << "Session Over" << endl << "Your Middle Time Score: " << endl << result << endl;
        cout << "number of latters:" << number << endl;

        return result, number;
    }
private:
    Scoreboard _score;

    bool GameLoop()
    {
        clock_t t_start, t_end;

        char task = Random::RandomChar();
        char input;

        cout << task;
        t_start = clock();

        cin >> input;
        t_end = clock();

        if (input != task)
            return true;

        _score.AddNewScore(Timer::GetDeltaTime(t_start, t_end));
        return false;
    }
};

int main()
{
    double results[5];
    double number[5];
    for (int i = 0; i < 5; i++)
    {
        Game newGame;
        results[i] = newGame.PlayGame();
    }

    cout << "results" << endl;

    for (int i = 0; i < 5; i++) {
        
        Scoreboard newGame;
        number[i] = newGame.GetCounter();
        results[i] = newGame.GetMiddleResult();
        cout << "Time score: " << results[i] << endl;
        cout << "Number of letters: " << number[i] << endl;
    }


    return 0;
}
