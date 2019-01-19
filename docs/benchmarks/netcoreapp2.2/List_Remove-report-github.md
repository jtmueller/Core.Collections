``` ini

BenchmarkDotNet=v0.11.3, OS=Windows 10.0.17763.288 (1809/October2018Update/Redstone5)
Intel Core i7-6700HQ CPU 2.60GHz (Skylake), 1 CPU, 8 logical and 4 physical cores
.NET Core SDK=3.0.100-preview-009812
  [Host] : .NET Core 2.2.1 (CoreCLR 4.6.27207.03, CoreFX 4.6.27207.03), 64bit RyuJIT
  Core   : .NET Core 2.2.1 (CoreCLR 4.6.27207.03, CoreFX 4.6.27207.03), 64bit RyuJIT

Job=Core  Runtime=Core  InvocationCount=1  
UnrollFactor=1  

```
|              Method |     N |       Mean |     Error |    StdDev |     Median | Ratio | RatioSD | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|-------------------- |------ |-----------:|----------:|----------:|-----------:|------:|--------:|------------:|------------:|------------:|--------------------:|
|      **ListRemove_Int** |  **3000** |   **2.622 ms** | **0.0533 ms** | **0.1487 ms** |   **2.575 ms** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |                   **-** |
|    PooledRemove_Int |  3000 |   2.669 ms | 0.0611 ms | 0.1792 ms |   2.627 ms |  1.02 |    0.09 |           - |           - |           - |                   - |
|   ListRemove_String |  3000 |  25.204 ms | 0.4704 ms | 0.4170 ms |  25.145 ms |  9.68 |    0.59 |           - |           - |           - |                   - |
| PooledRemove_String |  3000 |  24.159 ms | 0.4805 ms | 1.1232 ms |  24.143 ms |  9.24 |    0.68 |           - |           - |           - |                   - |
|                     |       |            |           |           |            |       |         |             |             |             |                     |
|      **ListRemove_Int** | **10000** |  **27.963 ms** | **0.2471 ms** | **0.2312 ms** |  **27.995 ms** |  **1.00** |    **0.00** |           **-** |           **-** |           **-** |                   **-** |
|    PooledRemove_Int | 10000 |  29.377 ms | 0.5770 ms | 1.1916 ms |  29.393 ms |  1.03 |    0.03 |           - |           - |           - |                   - |
|   ListRemove_String | 10000 | 272.959 ms | 5.3967 ms | 5.3003 ms | 272.982 ms |  9.76 |    0.23 |           - |           - |           - |                   - |
| PooledRemove_String | 10000 | 275.767 ms | 3.2306 ms | 3.0219 ms | 275.372 ms |  9.86 |    0.17 |           - |           - |           - |                   - |