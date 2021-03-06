# RunTimeTupleGet
Provides run-time tuple element access. Allows to iterate over tuple elements in a straightforward fashion.

## Build
This project is header-only. Hence, there is no need to build it. To build examples, simply execute the following commands:
	
	$ git clone https://github.com/AlexKiryushkin/rttg
	$ cd rttg
	$ mkdir build && cd build && cmake ..
	$ cmake --build ./

## Language requirements
This project relies on features from C++17 standard. Thus, compiler should support at least C++17.

## License
See the file [LICENSE](LICENSE).

## Example
```cpp
#include <iostream>
#include <string>

#include <rttg/rttg.h>

using TupleT = std::tuple<int, double, std::string>;

int main()
{
    const TupleT tuple{ 5, 3.0, "str"};
    for (std::size_t idx{}; idx < std::tuple_size_v<TupleT>; ++idx)
    {
        std::visit([](auto && tupleValue) { std::cout << tupleValue.get() << " "; }, rttg::get(tuple, idx));
    }
}
```
