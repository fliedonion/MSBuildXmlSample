# MSBuildXmlSample
Sample of MSBuild Xml and run before / after project build.

## Use this sample with your project.

example to use `msbuildSample.targets` with your project do following steps:

* put file in solution directory
* open csproj in your favorite text editor
* insert following line after `<Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />` :
```
  <Import Project="$(SolutionDir)\msbuildSample.targets" />
```
* reopen solution
* option: add `msbuildSample.targets` as new solution item.
* rebuild project

then you can get text in output window like following:

```
1>  Hello, world.
1>  Hello, 0.
1>  Hello, .
1>  Hello, Inside.
1>  Hello, Inside.
1>  Hello, world!
1>C:\path\to\your\solution\msbuildSample.targets(72,5): error : Hello, world!
1>  This Is Parameter.
1>  The value of `_PropertyForStoreValue` BEFORE call _Adder is 111
1>  The value of `_PropertyForStoreValue` AFTER  call _Adder is 9
1>  YourProjectName -> C:\path\to\your\solution\YourProjectName\bin\Debug\YourProjectName.exe
1>  The value of `_ResultText` : 
1>      value in xml : a
1>      abs path     : C:\path\to\your\solution\
```