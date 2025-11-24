# Getthedata
api for getthedata.com postcodes info and OSGB36 to WGS84 site
# main
```cpp
#include "Getthedata.h"
#include <iostream>

int main() {
   Getthedata api;

    auto WGS84 = api.OSGB36_to_WGS84(529090,179645).then([](json::value result) {
        std::cout << result<< std::endl;
    });
    WGS84.wait();
    
    return 0;
}
```

# Launch (your script)
```
g++ -std=c++11 -o main main.cpp -lcpprest -lssl -lcrypto -lpthread -lboost_system -lboost_chrono -lboost_thread
./main
```


