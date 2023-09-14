#include <bits/stdc++.h>
using namespace std;

class Spacecraft
{
private:
    int x, y, z;    // Current position (x, y, z)
    char direction; // Current direction (N, S, E, W, U, D)
    char origin;

public:
    // Declaring Constructor SpaceCraft with x,y,z co-ordinates and directon.
    Spacecraft(int &initialX, int &initialY, int &initialZ, char &initialDirection, char org)
    {
        x = initialX;
        y = initialY;
        z = initialZ;
        direction = initialDirection;
        origin = org;
    }

    // Moving Backward SpaceCraft
    void Backward() // b
    {
        switch (direction)
        {
        case 'N':
            y--;
            break;
        case 'S':
            y++;
            break;
        case 'E':
            x--;
            break;
        case 'W':
            x++;
            break;
        case 'U':
            z--;
            break;
        case 'D':
            z++;
            break;
        }
    }

    // Moving Forward SpaceCraft
    void Forward() // f
    {
        switch (direction)
        {
        case 'N':
            y++;
            break;
        case 'S':
            y--;
            break;
        case 'E':
            x++;
            break;
        case 'W':
            x--;
            break;
        case 'U':
            z++;
            break;
        case 'D':
            z--;
            break;
        }
    }

    // Moving SpaceCraft left
    void takeLeft() // l
    {
        switch (direction)
        {
        case 'N':
            direction = 'W';
            origin = 'W';
            break;
        case 'S':
            direction = 'E';
            origin = 'E';
            break;
        case 'E':
            direction = 'N';
            origin = 'N';
            break;
        case 'W':
            direction = 'S';
            origin = 'S';
            break;
        case 'D':
            if (origin == 'N')
            {
                direction = 'W';
                origin = 'W';
                break;
            }
            else if (origin == 'S')
            {
                direction = 'E';
                origin = 'E';
                break;
            }
            else if (origin == 'E')
            {
                direction = 'N';
                origin = 'N';
                break;
            }
            else
            {
                direction = 'S';
                origin = 'S';
                break;
            }
        case 'U':
            if (origin == 'N')
            {
                direction = 'W';
                origin = 'W';
                break;
            }
            else if (origin == 'S')
            {
                direction = 'E';
                origin = 'E';
                break;
            }
            else if (origin == 'E')
            {
                direction = 'N';
                origin = 'N';
                break;
            }
            else
            {
                direction = 'S';
                origin = 'S';
                break;
            }
        }
    }

    // Moving SpaceCraft Right
    void takeRight() // r
    {

        switch (direction)
        {
        case 'N':
            direction = 'E';
            origin = 'E';
            break;
        case 'S':
            direction = 'W';
            origin = 'W';
            break;
        case 'E':
            direction = 'S';
            origin = 'S';
            break;
        case 'W':
            direction = 'N';
            origin = 'N';
            break;
        case 'D':
            if (origin == 'N')
            {
                direction = 'E';
                origin = 'E';
                break;
            }
            else if (origin == 'S')
            {
                direction = 'W';
                origin = 'W';
                break;
            }
            else if (origin == 'E')
            {
                direction = 'S';
                origin = 'S';
                break;
            }
            else
            {
                direction = 'N';
                origin = 'N';
                break;
            }
        case 'U':
            if (origin == 'N')
            {
                direction = 'E';
                origin = 'E';
                break;
            }
            else if (origin == 'S')
            {
                direction = 'W';
                origin = 'W';
                break;
            }
            else if (origin == 'E')
            {
                direction = 'S';
                origin = 'S';
                break;
            }
            else
            {
                direction = 'N';
                origin = 'N';
                break;
            }
        }
    }

    // Moving SpaceCraft Up
    void takeUp() // u
    {
        if (direction != 'U')
        {
            direction = 'U';
        }
    }

    // Moving SpaceCraft Down
    void takeDown() // d
    {
        if (direction != 'D')
        {
            direction = 'D';
        }
    }

    // Printing x,y,z co-ordinates and direction
    void PrintPosition()
    {
        cout << "Current Position: (" << x << ", " << y << ", " << z << "), Direction: " << direction << endl;
    }

    // Printing Final Position of SpaceCraft
    void FinalPosition()
    {
        cout << "Final Position: (" << x << ", " << y << ", " << z << ")" << endl;
    }

    // Printing Final Direction of SpaceCraft
    void FinalDirection()
    {
        cout << "Final Direction: " << direction << endl;
    }
};

int main()
{
    int x = 0, y = 0, z = 0;
    char dir = 'N';
    Spacecraft Chandrayaan3(x, y, z, dir, 'N');

    string instruct;
    cin >> instruct;
    cout << endl;
    // Chandrayaan3.PrintPosition();
    for (int i = 0; i < instruct.length(); i++)
    {
        char code = instruct[i];
        switch (code)
        {
        case 'f':
            Chandrayaan3.Forward();
            Chandrayaan3.PrintPosition();
            break;
        case 'b':
            Chandrayaan3.Backward();
            Chandrayaan3.PrintPosition();
            break;
        case 'l':
            Chandrayaan3.takeLeft();
            Chandrayaan3.PrintPosition();
            break;
        case 'r':
            Chandrayaan3.takeRight();
            Chandrayaan3.PrintPosition();
            break;
        case 'u':
            Chandrayaan3.takeUp();
            Chandrayaan3.PrintPosition();
            break;
        case 'd':
            Chandrayaan3.takeDown();
            Chandrayaan3.PrintPosition();
            break;
        }
    }

    // Chandrayaan3.PrintPosition();
    cout << endl;

    Chandrayaan3.FinalPosition();
    cout << endl;

    Chandrayaan3.FinalDirection();
    cout << endl;
    return 0;
}