``` ini

BenchmarkDotNet=v0.11.3, OS=Windows 10.0.17763.292 (1809/October2018Update/Redstone5)
Intel Core i7-6700HQ CPU 2.60GHz (Skylake), 1 CPU, 8 logical and 4 physical cores
.NET Core SDK=3.0.100-preview-010184
  [Host] : .NET Core 2.2.1 (CoreCLR 4.6.27207.03, CoreFX 4.6.27207.03), 64bit RyuJIT
  Core   : .NET Core 2.2.1 (CoreCLR 4.6.27207.03, CoreFX 4.6.27207.03), 64bit RyuJIT

Job=Core  Runtime=Core  InvocationCount=1  
UnrollFactor=1  

```
|                              Method | CountToIntersect | InitialSetSize |        Mean |     Error |    StdDev |      Median | Ratio | RatioSD | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|------------------------------------ |----------------- |--------------- |------------:|----------:|----------:|------------:|------:|--------:|------------:|------------:|------------:|--------------------:|
|     **HashSet_SymmetricExcept_Hashset** |            **32000** |        **8000000** |  **1,270.3 us** |  **20.89 us** |  **16.31 us** |  **1,278.2 us** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |                   **-** |
| PooledSet_SymmetricExcept_PooledSet |            32000 |        8000000 |    904.3 us |  17.98 us |  47.69 us |    881.4 us |  0.76 |    0.02 |           - |           - |           - |                   - |
|        HashSet_SymmetricExcept_Enum |            32000 |        8000000 |  3,295.2 us |  64.41 us | 111.10 us |  3,270.3 us |  2.67 |    0.08 |           - |           - |           - |             25176 B |
|      PooledSet_SymmetricExcept_Enum |            32000 |        8000000 |  2,411.4 us |  47.76 us |  96.48 us |  2,372.1 us |  1.94 |    0.08 |           - |           - |           - |             25096 B |
|       HashSet_SymmetricExcept_Array |            32000 |        8000000 |  3,283.4 us |  41.28 us |  32.23 us |  3,281.0 us |  2.59 |    0.05 |           - |           - |           - |             25168 B |
|     PooledSet_SymmetricExcept_Array |            32000 |        8000000 |  2,263.2 us |  45.08 us |  92.08 us |  2,205.7 us |  1.87 |    0.06 |           - |           - |           - |             25056 B |
|                                     |                  |                |             |           |           |             |       |         |             |             |             |                     |
|     **HashSet_SymmetricExcept_Hashset** |           **320000** |        **8000000** |  **3,325.9 us** |  **28.45 us** |  **23.75 us** |  **3,325.7 us** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |                   **-** |
| PooledSet_SymmetricExcept_PooledSet |           320000 |        8000000 |  2,914.1 us |  61.12 us | 165.23 us |  2,842.7 us |  0.94 |    0.03 |           - |           - |           - |                   - |
|        HashSet_SymmetricExcept_Enum |           320000 |        8000000 | 16,536.6 us | 387.88 us | 362.82 us | 16,394.5 us |  4.98 |    0.11 |           - |           - |           - |             25176 B |
|      PooledSet_SymmetricExcept_Enum |           320000 |        8000000 | 14,861.3 us | 144.53 us | 120.69 us | 14,891.7 us |  4.47 |    0.05 |           - |           - |           - |             25096 B |
|       HashSet_SymmetricExcept_Array |           320000 |        8000000 | 16,765.2 us | 122.73 us | 114.80 us | 16,730.8 us |  5.04 |    0.05 |           - |           - |           - |             25168 B |
|     PooledSet_SymmetricExcept_Array |           320000 |        8000000 | 14,444.8 us |  76.79 us |  68.07 us | 14,470.2 us |  4.34 |    0.04 |           - |           - |           - |             25056 B |
