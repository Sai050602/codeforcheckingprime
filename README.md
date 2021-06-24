#include <iostream>
using namespace std;

bool Prime(int x);

int main() {
    int x, i;
    bool a = false;

    cout << "Enter a positive  integer: ";
    cin >> x;

    for(i = 2; i <= x/2; i++) {
        if (Prime(i)) {
            if (Prime(x - i)) {
                cout << x << " = " << i << " + " << x-i << endl;
                a = true;
            }
        }
    }

    if (!a)
      cout << x << " can't be expressed as sum of two prime numbers.";

    return 0;
}


bool Prime(int x)
{
    int i;
    bool isPrime = true;

    
    if (x == 0 || x == 1) {
        isPrime = false;
    }
    else {
        for(i = 2; i <= x/2; ++i) {
            if(x % i == 0) {
                isPrime = false;
                break;
            }
        }
    }

    return isPrime;
}
