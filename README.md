This is a work-in-progress class which combines random variate 
generation from Boost.Random with PDF calculation from Boost.Math, and 
serialization functions for use with Cereal. The intended use is in 
Monte Carlo simulations to give users a 'preview' of the distribution 
they are sampling from. 

To build, you may need to add a couple defines to increase the MPL type 
limit: 

```
-DBOOST_MPL_CFG_NO_PREPROCESSED_HEADERS
-DBOOST_MPL_LIMIT_LIST_SIZE=30
```

Replace QVector with std::vector if not using Qt.

Additional improvements are planned:

- Use std::variant from C++17
- Add additional operations from Boost.Math, e.g. CDF.
- Add histogram generation using the [Histogram](https://github.com/HDembinski/histogram) library, proposed for Boost.
- Currently this uses floating-point return type for all distributions. One solution to support integral types may be C++17 std::variant along with computed return types using Boost.MP11 (see [example](https://www.boost.org/doc/libs/1_67_0/libs/mp11/doc/html/mp11.html#computing_return_types) in the documentation).

