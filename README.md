# timercpp
Javascript like timer for c++ developers

This header only library has js equivalent `setTimeout()` and `setInterval()` for c++ (multithreaded).

## setTimeout(auto function, int delay)

```c++
Timer t = Timer();
t.setTimeout([&]() {
    cout << "Hey.. After 1s." << endl;
}, 1000); 
```

## setInterval(auto function, int interval)

```c++
Timer t = Timer();
t.setInterval([&]() {
    cout << "Hey.. After each 1s..." << endl;
}, 1000); 
```
