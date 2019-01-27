# timercpp
Javascript like timer for c++ developers

[![GitHub license](https://c5.patreon.com/external/logo/become_a_patron_button.png)](https://www.patreon.com/shalithasuranga)

This header only library has js equivalent `setTimeout()` and `setInterval()` for c++.

**DISCLAIMER - This implementation uses threads not a queue**

## `setTimeout(auto function, int delay)`

```c++
Timer t = Timer();
t.setTimeout([&]() {
    cout << "Hey.. After 1s." << endl;
}, 1000); 
```

## `setInterval(auto function, int interval)`

```c++
Timer t = Timer();
t.setInterval([&]() {
    cout << "Hey.. After each 1s..." << endl;
}, 1000); 
```

## Sample Program

```c++
#include <iostream>
#include "timercpp.h"

using namespace std;

int main() {
    Timer t = Timer();

    t.setInterval([&]() {
        cout << "Hey.. After each 1s..." << endl;
    }, 1000); 

    t.setTimeout([&]() {
        cout << "Hey.. After 5.2s. But I will stop the timer!" << endl;
        t.stop();
    }, 5200); 

    

    cout << "I am Timer" <<endl;


    while(true); // Keep main thread active
}
```

**Output**

```
I am Timer
Hey.. After each 1s...
Hey.. After each 1s...
Hey.. After each 1s...
Hey.. After each 1s...
Hey.. After each 1s...
Hey.. After 5.2s. But I will stop the timer!
```

### How to compile sample program?

```bash
g++ sample.cpp -std=c++14 -pthread
```

### License

[MIT](https://github.com/shalithasuranga/timercpp/edit/master/LICENSE)
