c sharp  成神

[TOC]

## 基础篇

### `out`、`ref` 和 `params`参数

在 C# 中，`out`、`ref` 和 `params` 是用于传递参数的关键字，它们分别具有以下作用:

1. `out` 参数：将值返回给调用者，可以在方法内部修改该参数的值，但不能在方法外部修改该参数的值。使用 `out` 参数可以使方法更高效，因为方法内部可以直接修改参数的值，而不必返回一个新的值。
2. `ref` 参数：将值传递给调用者，可以在方法内部修改该参数的值，可以在方法外部修改该参数的值。与 `out` 参数不同的是，`ref` 参数会将修改的结果返回给调用者，因此使用 `ref` 参数可以提高性能，因为方法内部可以直接修改参数的值，不必返回一个新的值。
3. `params` 参数：用于指定一组参数，这些参数可以是任意类型，且可以包含重复的参数。使用 `params` 参数可以使方法更简短，更易于阅读和维护，因为它允许在方法内部使用同名参数。当使用 `params` 参数时，每个参数必须以逗号分隔。



params参数代码示例

```c#
// 定义 params 关键字修饰的参数列表  
public void PrintNumbers(int a, params int[] b)  
{
    Console.WriteLine("a = " + a);  
    for (int i = 0; i < b.Length; i++)  
    {  
        Console.WriteLine("b[" + i + "] = " + b[i]);  
    }  
}

// 调用 params 关键字修饰的参数列表  
PrintNumbers(1, 2, 3, 4, 5);  
```

需要注意的是，`out`、`ref` 和 `params` 参数只能在方法内部使用，不能在类、结构或接口等公共类型中使用。

### socket协议

Socket 是一种应用程序编程接口 (API),它允许应用程序在计算机之间进行网络通信。Socket 协议是网络通信中最广泛使用的协议之一，它被广泛用于客户端和服务器之间的通信。

Socket 协议采用客户端/服务器模型进行通信。在客户端/服务器模型中,有一个客户端和一个服务器,客户端发送请求,服务器接收请求并返回响应。客户端和服务器之间的通信使用套接字(socket)进行。

套接字是一个唯一的标识符，用于标识客户端或服务器的网络连接。客户端使用套接字连接到服务器，服务器使用套接字接收来自客户端的请求。通过套接字，客户端和服务器可以交换数据包，这些数据包可以包含任何类型的数据，如文本、图像、音频或视频。

Socket 协议支持多种通信模式，包括数据传输模式、面向连接模式和无连接模式。

数据传输模式是指客户端和服务器之间的通信是基于数据包的，数据包可以随机发送和接收。

连接模式是指客户端和服务器之间建立连接，在进行通信之前必须建立连接，通信结束后连接自动关闭。

无连接模式是指客户端和服务器之间不建立连接，数据包随机发送和接收。

Socket 协议的数据传输采用数据包的形式进行。数据包由头部和数据部分组成。头部包含数据包的标识、长度、类型等信息，用于指导服务器正确解析数据包。数据部分包含实际数据，用于传输数据。

Socket 协议的头部格式如下:

```html
Copy code<头部长度>          =<头部长度字节数>  
<头部标识>         =<头部标识符>  
<头部类型>         =<头部类型码>  
<数据长度>        =<数据长度字节数>  
<数据部分>       =<数据部分字节数>  
<数据部分>       =<实际数据部分>  
```

Socket 协议的三种模式有不同的头部格式:

- 数据传输模式：头部长度为 1，头部标识为 0，头部类型为 0，数据长度为 0，数据部分为 0。
- 面向连接模式：头部长度为 2，头部标识为 1，头部类型为 1，数据长度为 0，数据部分为协议数据部分。
- 无连接模式：头部长度为 2，头部标识为 1，头部类型为 1，数据长度为 0，数据部分为协议数据部分。

Socket 协议采用 TCP(传输控制协议) 或 UDP(用户数据报协议) 进行数据传输。TCP 协议提供可靠的数据传输，确保数据的完整性和正确性，而 UDP 协议则不提供可靠的数据传输，因此 UDP 协议通常用于数据量较小且对数据传输可靠性要求不高的应用场景。

### c sharp静态和非静态的对象

1. 静态变量和成员：静态变量和成员是在类中被定义的，而不是在对象中被定义的。它们属于类，而不是对象，并且可以在类的不同对象之间共享。静态变量和成员在类加载时就被初始化，并且始终在内存中保留。
2. 非静态变量和成员：非静态变量和成员是在对象中被定义的，它们属于对象，并且只能在对象中被访问。非静态变量和成员在创建对象时就被初始化，并且对象死亡时，它们会被自动销毁。

总结：

- 静态函数中，只能访问静态成员，不允许访问实例对象。

- 实例对象中，即可以使用静态成员，也可以使用实例成员。

### c sharp基本数据类型

1. 整型:byte、short、int、long 四种。
2. 浮点型:float、double 两种。
3. 字符型:char。
4. 布尔型:bool。
5. 复数型:complex。
6. 数组：指向整数或浮点数的指针 (int[]、double[] 等) 可以表示数组。
7. 结构体 (struct):一种特殊的数据类型，可以包含多个成员变量，其类型可以是整型、浮点型、字符型、布尔型等。
8. 枚举 (enum):一种用于表示一组预定义值的数据类型，可以使用命名常量来表示。
9. 委托 (delegate):一种用于表示函数指针的数据类型，可以用于传递函数对象。
10. 字符串 string

值类型:int，double，bool，char，decimal，struct，enum。存储在内存栈

引用：string，自定义类。存储在内存堆中

1. 值类型直接存储数据，而引用类型存储指向数据的引用。
2. 值类型的变量存储的是数据本身，而引用类型的变量存储的是数据的引用。
3. 引用类型是动态绑定的，而值类型是静态绑定的。
4. 值类型可以直接赋值给引用类型，而引用类型不能直接赋值给值类型。

例如，一个 string 类型的对象需要一个内存地址来存储，而一个 byte 类型的对象则直接存储数据本身。因此，当多个值类型共享相同的内存地址时，它们不会相互影响，而引用类型则会因为它们引用不同的对象而相互影响。

![image-20230427180457116](E:\typora\Csharpnote\img\image-20230427180457116.png)

对于应用类型它的值存储在堆上，在栈上只会存储他引用的

### 委托，lambda表达式和事件

#### 什么是委托?

​		C#中的委托(Delegate)是一种用于封装方法的类型,它可以看做是函数指针(Function Pointer) 的一种高级形式。委托是一种能够将方法作为参数传递、存储方法并且调用方法的类型，它可以让我们写出更加灵活和可扩展的代码。

​		委托通常用于回调 (Callback) 机制，比如在事件处理、异步编程、LINQ 查询等场景中常常会使用委托。它可以将方法作为参数传递给其他方法，从而在需要的时候执行该方法。

### 异步任务

C#中的异步任务(Asynchronous Task) 是一种通过异步方式执行任务的方式，它可以让程序在执行异步任务的时候暂停执行，转而执行其他任务，直到异步任务完成再继续执行。这种方式可以大幅提高程序的性能和响应速度，尤其是在处理大量 I/O 操作的时候。

下面是异步任务的详细介绍:

1. 异步任务的定义： 异步任务是一个委托 (delegate),该委托在执行时能够暂停或恢复执行，可以在执行异步任务的时候转而执行其他任务。异步任务可以使用 async/await 关键字来创建。
2. 异步任务的基本概念： 异步任务包含两个重要的概念:Task 和 async/await。

- Task 是一个类，它代表异步任务的执行结果。Task 类包含了异步任务的执行状态、进度、错误等信息。
- async/await是C#中用于创建异步任务的关键字,它可以让程序在执行异步任务的时候暂停执行,转而执行其他任务,直到异步任务完成再继续执行。

1. 异步任务的使用方式： 要使用异步任务，需要先使用 Task 类或 async/await 关键字创建一个异步任务，然后执行该异步任务。

- 使用 Task 类创建异步任务:Task task = new Task( delegate { /* 异步任务代码 */ });
- 使用async/await关键字创建异步任务:async Task<int> MyTask(int i) { await Task.Delay(1000); return i + 1; }
  int result = MyTask(10).Result;

1. 异步任务的优点： 异步任务可以大幅提高程序的性能和响应速度，尤其是在处理大量 I/O 操作的时候。使用异步任务可以让程序在执行异步任务的时候暂停执行，转而执行其他任务，直到异步任务完成再继续执行，这样可以避免阻塞主线程，提高程序的性能和响应速度。
2. 异步任务的应用场景： 异步任务可以用于处理网络请求、文件读写、数据库操作、UI 渲染等场景，可以在处理这些操作的时候提高程序的性能和响应速度。同时，异步任务也可以用于处理长时间的计算任务，例如排序、聚类等计算任务，可以避免阻塞主线程，提高程序的性能和响应速度。

### 反射

C#中的反射(Reflection)是一种机制,它允许程序在运行时获取、检查和修改对象的类型、属性、方法等信息,使得程序可以在运行时动态地创建、调用和处理对象。下面是反射的详细介绍:

1. 反射的定义： 反射是一种机制，它允许程序在运行时获取、检查和修改对象的类型、属性、方法等信息，使得程序可以在运行时动态地创建、调用和处理对象。
2. 反射的使用方式： 要使用反射，需要先使用 Assembly 类或 Type 类获取程序集中的类型信息，然后使用 object 类或 Type 类获取对象实例或类型信息。

- 获取程序集中的类型信息:Assembly assembly = Assembly.GetExecutingAssembly();
- 获取对象实例:object obj = Activator.CreateInstance(type);
- 获取类型信息:Type type = typeof(MyClass);

1. 反射的优点： 反射可以使得程序在运行时动态地创建、调用和处理对象，避免了编译时的类型检查和代码生成，提高了程序的灵活性和可扩展性。
2. 反射的应用场景： 反射可以用于创建对象实例、调用私有方法、获取类属性、检查对象类型等信息。

- 创建对象实例:object obj = Activator.CreateInstance(type);
- 调用私有方法:MethodInfo method = type.GetMethod("PrivateMethod");
- 获取类属性:PropertyInfo property = type.GetProperty("PropName");
- 检查对象类型:Type type = obj.GetType();

反射是C#中非常强大的机制,它使得程序可以在运行时动态地创建、调用和处理对象,提高了程序的灵活性和可扩展性。在实际应用中,反射可以被用于创建动态的UI界面、动态生成代码等场景。

### .net core发展

NET Framework历 史包袱，ASP.NET MVC表面挺好，底层有很多老技术。

- 带着手铐脚镣长大的ASP.NET MVC
- ASP.NET底层不支持很好的单元测试

##### NET Core的优点

- 支持独立部署，不互相影响:
- 彻底模块化:
- 没有历史包袱，运行效率高
- 不依赖于IIS
- 跨平台符合现代开发理念:依赖注入、单元测试等

##### NET Core和.NET Framework不同:

- 不支持:ASP.NET WebForms、WCF服务器端、WF、.NET Remoting、
  Appdomain
- 部分Windows-only的特性.NET core，但是无法跨平台: winForm、WPF、注册表、Event Log、AD等。在window下使用.net core除了不能跨平台其他的优点都很nice。

##### .NET Standard 

创建.net standard 2.0标准的库，打印FIleStream地址

```c#
public static void TestLog()
{
     Console.WriteLine(typeof(FileStream).Assembly.Location);
}
```

在.net core 6.0项目中调用 `TestLog()`

输出：C:\Program Files\dotnet\shared\Microsoft.NETCore.App\6.0.16\System.Private.CoreLib.dll

在.net framework 4.7项目中调用`Testlog()`

输出: C:\Windows\Microsoft.NET\Framework\v4.0.30319\mscorlib.dll

调用了相同的库函数但是却是不同的库文件，因为这些库文件实现了同一个`.net standard 2.0`的标准。

- .NET Standard只是规范,一个.NET Standard类库可以被支持其版本的.NET Framework、.co:NET Core、 Xamarin等引用。而. NET Core类
- 库、.NET FramewOI类厍则不可以。asa acce如果编写一个公用的类库,尽量选择. NET
  Standard，尽量用低版本Standard。

.NET Standard和.NET Core 以及.NET Framework支持情况

| .NET Standard  | 1.0  | 1.1  | .... | 2.0   | 2.1                              |
| -------------- | ---- | ---- | ---- | ----- | -------------------------------- |
| .NET Core      | 1.0  | 1.0  |      | 2.0   | 3.0(最新的net8也是这个标准)      |
| .NET Framework | 4.5  | 4.5  |      | 4.6.1 | 不支持(最新的4.8也不支持2.1标准) |

### .net中的异步编程

“异步方法”:用async关键字修饰的方法

- 异步方法的返回值一般是Task<T>，T泛型是真正的返回值类型，Task<int>。惯例:异步方法名字以Async结尾。
- 即使方法没有返回值，也最好把返回值声明为非泛型的Task
- 调用泛型方法时，一般在方法前加上await关，这样拿到的返回值就是泛型指定的T类型;4)异步方法的“传染性”:一个方法中如果有await调用，则这个方法也必须修饰为async

异步读写文件不加await关键字

```C#
string fileName = @"C:\Users\ZZX\Desktop\test\a.txt";
StringBuilder sb = new StringBuilder();
for (int i = 0; i < 10000; i++)
{
    sb.AppendLine("best pig");
}
//不调用await的话这里就是一个异步任务 不会等待这个任务完成，会继续执行主线程的任务。 
File.WriteAllTextAsync(fileName,sb.ToString());
//在这里会触发一个“System.IO.IOException”类型的异常。因为异步任务在写文件，写文件是线程阻塞的操作。
string s = await File.ReadAllTextAsync(fileName);
Console.WriteLine(s);

```

增加await关键词

```c#
//增加await关键词会把await关键词后面的一个调用当做同步任务。 
await File.WriteAllTextAsync(fileName,sb.ToString());
//正常读入文件不会报错
string s = await File.ReadAllTextAsync(fileName);
Console.WriteLine(s);

```

如果同样的功能，既有同步方法，又有异步方法，那么首先使用异步方法。.很多框架中的方法也都支持异步: Main、WinForm事件处理函数。
对于不支持的异步方法怎么办? Wait()(无返回值）;Result(有返回值）。Wait()和Result()方法有风险:死锁。尽量不用。

**异步委托**

其实很简单在在委托方法前面加async即可

```c#
ThreadPool.QueueUserWorkItem(async (obj) =>
 {
	await File.WriteAllTextAsync(@"C:\Users\ZZX\Desktop\test\c.txt", "hello world");
  });
```

##### async await背后原理

下面的异步任务都使用了await，虽然await从效果上来讲是等待异步任务的执行，但从源码层面上讲，C#编译器会把async方法编译成一个类，会主要根据await调用进行切分为多个状态，对于async方法的调用会被拆分为对MoveNext的调用，用await看似等待，经过编译器编译后并没有"wait"

```c#
async Task<int> DownloadHtmlAsync()
{
    //using语句通常用于管理对象的生命周期，确保在使用完对象后及时释放资源。
    //使用using语句可以自动调用对象的Dispose方法，从而释放对象所占用的资源。
    using (HttpClient client = new HttpClient())
    {
        string html = await client.GetStringAsync("https://www.youzack.com");
        string fileName = @"C:\Users\ZZX\Desktop\test\b.txt";
        await File.WriteAllTextAsync(fileName, html);

        string s = await File.ReadAllTextAsync(fileName);
        Console.WriteLine($"hello:{s}");
        return html.Length;
    }     
}
await DownloadHtmlAsync();
```

##### async 和await背后的线程切换

在使用await等待一个异步任务时可能会发生线程切换，在await之前的线程和await之后线程可能发生切换。await调用的等待时间，.net会把当前的线程返回给线程池，等异步方法调用执行完毕后，框架会从线程池再取出来一个线程执行后续的代码。

```
 Console.WriteLine("xiaoming"); //线程1
 await aAsync();//await 等待一个异步任务
  Console.WriteLine("xiaohon"); //线程2
```

示例：两次打印线程ID不一样说明发生了线程切换

```c#
Console.WriteLine(Thread.CurrentThread.ManagedThreadId);
StringBuilder sb = new StringBuilder();
for (int i = 0; i < 100000; i++)
{
    sb.AppendLine("hello xiaoming");
}
await File.WriteAllTextAsync(@"C:\Users\ZZX\Desktop\test\c.txt", sb.ToString());
Console.WriteLine(Thread.CurrentThread.ManagedThreadId);

// 1
// 5
```

但是如果await等待时间非常少，来不及切换线程。那么await前后的会是同一个线程。这是CLR一个优化避免频繁的线程切换浪费性能。

```c#
Console.WriteLine(Thread.CurrentThread.ManagedThreadId);
StringBuilder sb = new StringBuilder();
for (int i = 0; i < 2; i++)
{
    sb.AppendLine("hello xiaoming");
}
await File.WriteAllTextAsync(@"C:\Users\ZZX\Desktop\test\c.txt", sb.ToString());
Console.WriteLine(Thread.CurrentThread.ManagedThreadId);
//1
//1
```

##### 异步方法并不等于多线程

异步方法的代码并不会自动在新线程中执行，除非把代码放在新线程中执行。下面的代码是把异步方法在放新的线程中执行，从结果看出异步任务是在新线程中执行，并且异步在新的线程中执行的话，在await前后也会发生线程切换。

```c#
async Task<double> doubleAsync(int n)
{
    return await Task.Run(() =>
    {
        Console.WriteLine($"async:{Thread.CurrentThread.ManagedThreadId}");
        var rand = new Random();
        double result = 0;
        for (int i = 0; i < n; i++)
        {

            result += rand.NextDouble();
        }
        return result;
    });

}
Console.WriteLine($"前面:{Thread.CurrentThread.ManagedThreadId}");
double r =await doubleAsync(10000);
Console.WriteLine($"r:{r}");
Console.WriteLine($"后面:{Thread.CurrentThread.ManagedThreadId}");
// 前面:1
// async:5
// r:5002.9135722626215
// 后面:8

```

如果异步方法不在新线程中执行可以发现，异步任务中并没有发生线程的切换。并且await前后没有发生线程切换。

```c#
async Task<double> doubleAsync(int n)
{
        Console.WriteLine($"async:{Thread.CurrentThread.ManagedThreadId}");
        var rand = new Random();
        double result = 0;
        for (int i = 0; i < n; i++)
        {

            result += 1;
        }
        return result;

}
Console.WriteLine($"前面:{Thread.CurrentThread.ManagedThreadId}");
double r =await doubleAsync(1000000000);
Console.WriteLine($"r:{r}");
Console.WriteLine($"后面:{Thread.CurrentThread.ManagedThreadId}");
//前面:1
//async:1
//r:1000000000
//后面:1

```

##### 为什么有些异步方法没有async关键字

虽然使用了异步任务但是没有用await关键字来等待异步任务返回，自然不需要async关键词。但是如果使用了await关键字那么就一定需要使用async关键字。

```C#
Task<string> ReadAsync_01(int num)
{
	switch (num)
	{
		case 1:
			return File.ReadAllTextAsync(@"e:\a.txt");
        case 2:
            return File.ReadAllTextAsync(@"e:\b.txt");
		default:
			throw new ArgumentException();
	}
}

```

下面是对于异步方法"拆完了再装"，复杂了操作。应该按照上面的代码直接返回Task。

```c#
async Task<string>  ReadAsync_02(int num)
{
    switch (num)
    {
        case 1:
            return await File.ReadAllTextAsync(@"e:\a.txt");
        case 2:
            return await File.ReadAllTextAsync(@"e:\b.txt");
        default:
            throw new ArgumentException();
    }
}

```

如果一个异步的方法只是对别的异步方法调用的转发，并没有太多复杂的逻辑。就去掉async和await关键字。

##### 使用CancellationToken

支持取消的方法会接受一个CancellationToken方法。取消基于协作行为，他不是强制的，长时间运行的任务会检查它是否被取消，并相应返回控制权。

```c#
// 定义模拟使用CancellationToken的一个方法   
public static async Task DownloadAsync(string url,int n,CancellationToken cancellation)
        {
            using (HttpClient client = new HttpClient())
            {
                for (int i = 0; i < n; i++)
                {
                    var res = await client.GetAsync(url, cancellation);
                    string html  = await res.Content.ReadAsStringAsync();
                    Console.WriteLine(html);
                    if (cancellation.IsCancellationRequested)
                    {
                        Console.WriteLine("请求被取消");
                        break;
                    }
                }
            }
        }


//Main函数中
CancellationTokenSource cts = new CancellationTokenSource();
CancellationToken token = cts.Token;
TestCancellation.DownloadAsync("https://www.baidu.com", 300,token);
while (Console.ReadLine() != "q") { }
cts.Cancel();

```

##### Task类

Task类和js中的Promise非常像，并且他们的方法也很像

1. Task.WhenAny()方法等待任何一个Task完成，Task就完成了，允许同时等待多个异步操作的完成，并在其中任何一个操作完成时立即返回。类似于Js中的Promise.race()方法，
2. Task.WhenAll(params Task<TResult>[] tasks)等，所有Task完成Task才完成。用于等待多个任务执行结束，但是不在乎它们的执行序列。等待多个异步操作的完成，并在所有操作完成后返回。Task.WhenAll()方法类似于Promise.all()方法。
3. FromResult() 创建普通数值的Task对象。Task.FromResult()方法类似于Promise.resolve()方法，它们都是将一个已经完成的操作包装成一个Task或者Promise对象。
4. Promise.reject()方法和Task.FromException()方法是类似的方法，它们都是将一个已经失败的操作包装成一个Promise或者Task对象。Promise.reject()方法会返回一个rejected状态的Promise对象，表示操作失败，可以使用.catch()方法来捕获错误。Task.FromException()方法会返回一个faulted状态的Task对象，表示操作失败，可以使用.Wait()方法或者await关键字来等待任务的完成，并使用try-catch语句来捕获错误。

##### 深入立即异步任务

**javaScript中**

​		JavaScript 中没有多线程的概念，因此异步任务只能通过事件循环(event loop)机制来实现。事件循环机制是指 JavaScript 引擎在执行任务时，会先执行同步任务，然后执行微任务队列中的任务，最后才执行宏任务队列中的任务。

**C#中**

异步任务使用任务队列和线程池来管理异步操作的执行，可以更加高效地利用系统资源，并且可以避免多线程带来的线程安全问题。

异步任务的执行过：

1. 当异步方法被调用时，会立即返回一个 Task 对象，表示异步操作的状态和结果。
2. 异步方法内部使用 async/await 关键字来标记异步操作，编译器会将异步操作转换为一个状态机并且加入到一个任务队列中去，然后等待线程池从任务队列中拿取任务。
3. 使用 await 关键字等待异步方法的执行，但是当前的线程不一定会等待异步任务结束(假如异步任务时间很短是会等一下的不会发生线程的切换)，所以在await时当前线程可能干别的事情去了，等到await的异步任务返回时，当前线程可能会发生切换。但是假如不使用await关键字，那么没有等异步任务返回，当前线程就不会发生切换，所以不使用await关键字异步任务前后的线程不会发生切换。
4. 创建一个异步任务交给任务队列执行，然后通过任务调度器把任务分配到线程池中的空闲线程中，任务是不能被直接执行的，只有分配给线程才能被执行，如果任务的数量比线程池中的线程多，线程池的线程数量还没有到达上限，就会创建新线程执行任务。如果线程池的线程已到达上限，没有分配到线程的任务需要等待有线程空闲的时候才执行。
5. await关键字对于当前编辑器代码执行的顺序来讲是同步的效果，但其实await的时候当前线程甚至都没有阻塞而是立即返回去干其他的事情了。只是从效果上看起来当前任务挂起了。

在执行异步任务时，C# 会将异步操作分解为多个任务，并将这些任务加入到一个任务队列中。这个任务队列由线程池中的线程来执行。

线程池是一个包含多个线程的线程集合，这些线程可以重复使用，以执行多个任务。线程池会根据系统的负载情况来动态调整线程的数量，以保证系统的性能和稳定性。

当一个异步任务需要执行时，线程池会从线程池中获取一个可用的线程来执行任务，当任务执行完成后，线程会被释放并返回到线程池中，以供其他任务使用。

```c#
static async Task<string> testAsync()
{
    await Task.Delay(10);
    Console.WriteLine($"异步任务中当前线程:{Thread.CurrentThread.ManagedThreadId}");
    await Task.Delay(10);
    return "ok";
}
Task<string>[] ts = new Task<string>[10];
for( int i = 0; i < 10; i++)
{
    ts[i] = testAsync();
}
Console.WriteLine($"异步任务前的主线程:{Thread.CurrentThread.ManagedThreadId}");
Task.WhenAll(ts);  //如果这里使用了await那么主线程可能会发生切换
Console.WriteLine($"异步任务后的主线程:{Thread.CurrentThread.ManagedThreadId}");\
//卡主主线程防止应用程序结束
Console.ReadLine();
/*
异步任务前的主线程:1
异步任务后的主线程:1
异步任务中当前线程:8目前任务:8
异步任务中当前线程:10目前任务:4
异步任务中当前线程:3目前任务:7
异步任务中当前线程:5目前任务:9
异步任务中当前线程:8目前任务:0
异步任务中当前线程:11目前任务:6
异步任务中当前线程:12目前任务:5
异步任务中当前线程:13目前任务:3
异步任务中当前线程:14目前任务:2
异步任务中当前线程:17目前任务:1
*/

```

### .Net中依赖注入

C#依赖注入(Dependency Injection，简称 DI) 是一种软件设计模式。它的基本概念是，不直接创建或使用对象，而是使用参数、构造函数或属性等来动态地分配责任。

在传统的程序设计中，通常使用构造函数或实例初始化器来创建对象。这样会导致代码的耦合度很高，一旦需要修改对象的属性或构造函数，就需要修改整个代码。而且，构造函数和方法的调用方式可能会造成代码难以理解和维护。

而依赖注入则通过将依赖关系交给容器来管理，容器负责创建对象并将它们连接起来，从而实现代码的松耦合。在依赖注入中，对象不再直接创建或使用其他对象，而是通过参数、属性或构造函数等来获取依赖对象。这种方式使得代码更加灵活、可扩展，并且易于维护。

依赖注入的实现方式有很多种，其中最常见的是 Autofac 和 Unity 等依赖注入容器。这些容器可以使用参数、属性、构造函数等方式来动态地分配依赖关系，并且可以方便地管理对象之间的依赖关系。使用依赖注入容器，可以让代码更加简单、易于维护，并且可以提高代码的可测试性和可维护性。

1. 依赖注入是有“传染性”的，如果一个类的对象是通过DI创建的，那么这个类的构造函数中声明的所有服务类型的参数都会被DI赋值；但是如果一个对象是程序员手动创建的，那么这个对象就和DI没有关系，它的构造函数中声明的服务类型参数就不会被自动赋值。
2. .NET的DI默认是构造函数注入。

##### 使用依赖注入 DI

1. install-Package Microsoft.Extensions.DependencyInjection
2. usgin Microsoft.Extensions.DependencyInjection
3. ServiceCollection用来构造容器对象 IServiceProvider()创建的ServiceProvider,可以用来获取BuildServiceProvider()之前Service

##### 造轮子-日志框架-体现依赖注入

1. 一共三个类库一个控制台。先创建三个.NET Core类库项目，ConfigServices是配置服务的项目，LogServices是日志服务的项目，MailSevices是邮件发送器的项目,然后再建一个.NET Core控制台项目MailServicesConsole来调用MailServices。MailServices项目引用ConfigServices项目和LogServices项目，而MailServicesConsole项目引用MailServices项目。
2. 编写类库项目LogServices，创建lLogProvider接口。编写实现类ConsoleLogProvider。编写一个
   ConsoleLogProviderExtensions定义扩展方法
   AddConsoleLog,namespace和lServiceCollection一致

`LogServices`类库打印日志，通过AddConsoleLog扩展方法将类添加到服务中

```c#
//接口`ILogProvider`

namespace LogServices
{
    public interface ILogProvider
    {
        public void LogError(string msg);

        public void LogInfo(string msg);
    }
}

//实现类 ConsoleLogProvide
namespace LogServices
{
    public class ConsoleLogProvide : ILogProvider
    {
        public void LogInfo(string msg)
        {
            Console.WriteLine($"info:{msg}");
        }

        public void LogError(string msg)
        {
            Console.WriteLine($"Error:{msg}");
        }
    }
}
//扩展方法类 ConsoleLogExtension
namespace Microsoft.Extensions.DependencyInjection
{
    public static class ConsoleLogExtension
    {
        public static void AddConsoleLog(this IServiceCollection services)
        {
            services.AddScoped<ILogProvider,ConsoleLogProvide>();
        }
    }
}

```

`ConfigServices `类库

```c#
//IConfigService 接口
namespace ConfigServices
{
    public interface IConfigService
    {
        public string GetValue(string name);
    }
}
// ConfigService  IConfigService接口实现类
namespace ConfigServices
{
    public class ConfigService : IConfigService
    {
        public string GetValue(string name)
        {
            return Environment.GetEnvironmentVariable(name);
        }
    }
}
//IniFileConfigService IConfigService接口实现类
namespace ConfigServices
{
    public class IniFileConfigService : IConfigService
    {
        public string FilePath { get; set; }
        public string? GetValue(string name)
        {
            var kv = File.ReadAllLines(FilePath).Select(s=>s.Split("=")).Select(str => new { Name = str[0], Value = str[1] }).SingleOrDefault(kv=>kv.Name ==name);
            if (kv != null)
            {
                return kv.Value;
            }
            else
            {
                return null;
            }
        }
    }
}

// ConfigServiceExtension 注册服务
namespace Microsoft.Extensions.DependencyInjection
{
    public static class ConfigServiceExtension
    {
        public static void AddConfigService(this IServiceCollection services)
        {
            services.AddScoped<IConfigService>(s => new IniFileConfigService { FilePath = "E:\\C#10学习\\homeWork\\日志框架\\MailServicesConsole\\mail.ini" });
        }
    }
}


```

`MailSevices`类库

```c#
//IMailService
namespace MailSevices
{
    public interface IMailService
    {
        public void Send(string titile, string to, string body);
    }
}

//MailService  实现类
namespace MailSevices
{
    public class MailService : IMailService
    {
        private readonly ILogProvider log;

        private readonly IConfigService configService;

        public MailService(ILogProvider log, IConfigService configService)
        {
            this.log = log;
            this.configService = configService;
        }

        public void Send(string titile, string to, string body)
        {
            this.log.LogInfo("准备发送邮件");
            string SmtpServer = this.configService.GetValue("SmtpServer");
            string UserName = this.configService.GetValue("UserName");
            string Password = this.configService.GetValue("Password");
            this.log.LogInfo($"邮件服务器地址:{SmtpServer},{UserName},{Password}");
            Console.WriteLine($"真的发送邮件了{titile},{to},{body}");
            this.log.LogInfo("邮件发送了");
        }
    }
}

// MailServiceExtension扩展类
namespace Microsoft.Extensions.DependencyInjection
{
    public static class MailServiceExtension
    {
        public static void AddMailService(this IServiceCollection services)
        {
            services.AddScoped<IMailService, MailService>();
        }
    }
}

```



`MailServicesConsole`控制台类通过依赖注入的方式来注册服务。`ServiceCollection`对象，用来注册和管理依赖入服务。然后，将`IMailService`和它的实现类`MailService`注册为单例服务。这里通过调用`AddScoped`方法，将`IMailService`的生命周期指定为Scoped，也就是在每个请求内部保持唯一的实例。

```c#
using MailSevices;
using Microsoft.Extensions.DependencyInjection;

ServiceCollection services = new ServiceCollection();

services.AddConfigService();
services.AddConsoleLog();
services.AddMailService();

using (var sp = services.BuildServiceProvider())
{
    var mail = sp.GetRequiredService<IMailService>();
    mail.Send("帅哥", "152@qq.com", "小小怪下士");

```

##### `Scoped`、`Transient` 和 `Singleton` 是` ASP.NET Core `中定义服务生命周期的三种方式。

- `Scoped` 意味着在同一请求范围内，每次从容器中获取的实例都是同一个。即针对同一次 HTTP 的web请求，每次请求上下文都会得到同一个服务实例，但不同请求之间会得到不同的实例。对于非ASP.NET core web应用程序，需要自己创建作用域，以获得scoped服务优势。
- `Transient` 每当我们从容器中请求一个服务时，都会创建一个新的服务实例，即每次请求都会得到新的实例。相当于我们每次使用时都会生成一个新的对象，适用于一些轻量级的服务。
- `Singleton` 全局单例模式，在应用程序生命周期内只会创建一个实例，每次请求都会得到同一个实例。即可以在整个应用程序范围内共享一个实例，适用于一些资源密集型或状态全局唯一的服务。

我们需要在注册服务的时候指定服务的生命周期。一般情况下，我们会尽可能地使用Scoped，因为它既可以避免在单个请求内重复创建实例，也不会导致多个请求共享同一实例的问题。Singleton 适用于需要状态全局唯一的服务，Transient 适用于轻量级、无状态的服务。

##### 配置中心，可覆盖的配置读取器。

1. “可覆盖的配置读取器”。配置中心服务器。可以本地的覆盖配置服务器的,或者配置文件覆盖环境变量的。
2. 例如，按照“配置中心服务器”、“本地环境变量”、“本地配置文件”的顺序添加了三个配置提供者，在“配置中心服务器"中提供了“a=1;b=2;C=3”这三个配置项，在“本地环境变量"中配置了“a=10;b=2Q”,在“本地配置文件"中配置了6=20o”，那么最终我们读取的时候读到的就是
   "a=10;b=200;c=3;"

##### 依赖注入总结

编写的依赖注入的代码关注于接口，而不是关注于代码实现，各个服务可以更弱的耦合的鞋套工作，我们甚至可以都不知道具体的服务是干什么。

第三方DI(依赖注入)：Autofac，支持属性注入，名字注入，约定注入，构造函数注入(常用方式)等。

##### 服务定位器生命周期

1、给类构造函数中打印，看看不同生命周期的对象创建，使用serviceProvider.CreateScope()创建Scope。

2、如果一个类实现了IDisposable接口,则离开作用域之后容器会自动调用对象的Dispose方法。

3、不要在长生命周期的对象中引用比它短的生命周期的对象。在ASP.NET Core中，这样做默认会抛异常。

4、生命周期的选择:如果类无状态，建议为Singleton;如果类有状态，且有Scope控制，建议为Scoped，因为通常这种Scope控制下的代码都是运行在同一个线程中的，没有并发修改的问题;在使用Transient的时候要谨慎。

5、.NET注册服务的重载方法很多，看着文档琢磨吧。

### Configure函数和中间件注册

##### Configure函数

Configure函数是ASP.NET Core应用程序中的一个重要方法，用于配置请求的处理管道，其主要职责如下：

1. 配置中间件：Configure函数可以添加所需的中间件组件，以对传入的HTTP请求和HTTP响应进行处理，例如身份验证、缓存、跨域和异常处理等。
2. 配置路由：通过将路由中间件添加到管道中，将请求路由到相应的Action方法或控制器。
3. 启用静态文件：启用静态文件中间件，在需要时将静态文件发送到客户端，例如CSS、JavaScript、图像等。
4. 配置HTTP上下文：可以使用Configure函数访问HTTP请求和响应对象的通用属性，例如Headers、Cookies和Session。
5. 配置应用程序启动时执行的操作：在Configure函数中可以添加需要在应用程序启动时执行的操作，例如数据库连接和数据缓存等。

需要注意的是，Configure方法必须接收一个IApplicationBuilder参数，这个参数是配置HTTP请求管道所必需的，并且可以在其中添加或删除中间件、配置路由和静态文件处理等。而且，Configure方法还可以接收其他服务，例如应用程序配置、日志记录和数据库Context等。

##### 常用中间件

在Configure函数中，我们可以添加各种中间件来处理和响应HTTP请求。以下是ASP.NET Core中一些常用的中间件：

1. 静态文件中间件（UseStaticFiles）：用于向客户端提供静态文件，如图片、CSS、JavaScript等。
2. 路由中间件（UseRouting）：用于根据请求的URL决定调用哪个控制器的哪个方法。
3. 身份验证中间件（UseAuthentication）：用于检查请求的是否已经登录，如果未登录则跳转到登录页面。
4. 授权中间件（UseAuthorization）：用于检查调用API的用户是否具有足够的权限，如果没有则拒绝访问。
5. 异常处理中间件（UseExceptionHandler）：用于捕获异常，记录日志并向用户返回有意义的错误信息。
6. 请求管道记录中间件（UseRequestResponseLogging）：用于记录请求和响应的详细信息，便于出现问题时进行追踪和排查。
7. HTTPS重定向中间件（UseHttpsRedirection）：用于将HTTP请求重定向到HTTPS请求，以增加安全性。

### **Entity Framework概念**

​		Entity Framework是Microsoft提供的一种ORM（Object-Relational Mapping，对象关系映射）工具，它可以将关系型数据库中的数据映射到.NET代码中的数据实体上。它可以让开发者将精力更多地放在业务逻辑上，而不是关注底层数据访问的细节。Entity Framework支持多种数据库，包括SQL Server、MySQL、Oracle等，并且可以使用LINQ语言进行查询和操作数据库。

##### ORM

​		ORM全称Object-Relational Mapping（对象关系映射），是一种编程技术，用于将对象模型与关系型数据库中的数据模型互相映射。ORM技术使得开发人员可以使用类似于面向对象编程语言的语法和方法对数据库进行操作，而无需编写与特定数据库系统相关的代码。ORM负责将对象操作转换为对数据库的操作，同时可以使开发人员以更高的抽象层次来操作数据，避免手写sql语句，提高开发效率。

​		ORM框架旨在解决处理大量数据时的一些常见问题，例如：数据类型转换、维护数据库连接、避免SQL注入等。

##### Entity Framework和hibernate框架异同

Entity Framework 和 Hibernate 都是 ORM 框架，它们的相似之处包括：

1. 都是将对象映射到关系型数据库中的框架。
2. 都提供了面向对象的编程模型，使得开发人员可以更加自然地使用数据库。
3. 都提供了事务管理、缓存机制等高级功能，简化了开发工作。

然而，它们也有不同之处：

1. 编程语言不同：Entity Framework 是 .NET 平台上的 ORM 框架，而 Hibernate 是 Java 平台上的 ORM 框架。
2. 架构不同：Entity Framework 基于 Microsoft 的 [ADO.NET](http://ado.net/) 技术，而 Hibernate 基于 Java 的 JDBC 技术。
3. 映射方式不同：Entity Framework 支持多种映射方式，包括 Code First、Database First 和 Model First 等，而 Hibernate 更加注重 XML 映射文件和注解方式。
4. 性能不同：Entity Framework 从 6.0 版本开始引入了一些性能优化，但是在某些情况下，Hibernate 的性能可能更好。

### **LINQ查询**

LINQ是一种语言集成查询（Language Integrated Query）技术，可以在C#，.NET语言中使用。它提供了一种简单、统一的方式来查询各种数据源，包括集合、数据库和XML文档等。

​	LINQ查询可以使用查询表达式或方法语法来编写。查询表达式使用类似SQL的语法来描述查询，而方法语法使用一系列扩展方法来实现查询。**

下面是一个使用LINQ查询集合的示例：

```csharp
List<int> numbers = new List<int> { 1, 2, 3, 4, 5 };
var query = from num in numbers
            where num % 2 == 0
            select num;

foreach (var num in query)
{
    Console.WriteLine(num);
}

```

上面的代码使用查询表达式查询一个整数集合中的偶数。查询语句中的`from`关键字指定集合中的元素，`where`关键字指定查询条件，`select`关键字指定查询结果。query是一个`IEnumerable<int>`可迭代类型的变量中。注意：在使用foreach循环遍历访问时，才会执行这个查询。定义遍历query时只是一个赋值语句并没有执行这个查询

##### LINQ方法

LINQ方法语法是一种使用方法调用来构建LINQ查询的方式。下面是一些常用的LINQ方法：

1. Where：用于过滤序列中的元素，只返回满足指定条件的元素。
2. Select：用于将序列中的每个元素映射到一个新的形式，并返回一个包含新形式元素的序列。
3. OrderBy/OrderByDescending：用于对序列中的元素进行排序。
4. GroupBy：用于按照指定的键对序列中的元素进行分组。
5. Join：用于将两个序列中的元素根据指定的键进行联接。
6. Any/All：用于检查序列中是否存在满足指定条件的元素。
7. Count：用于计算序列中满足指定条件的元素的数量。
8. First/FirstOrDefault/Last/LastOrDefault：用于返回序列中满足指定条件的第一个或最后一个元素。
9. Sum/Average/Max/Min：用于计算序列中元素的总和、平均值、最大值和最小值。
10. Take/TakeWhile/Skip/SkipWhile：用于从序列中返回指定数量或满足指定条件的元素。

System.Linq命名空间中定义了很多Enumerable的扩展方法，比如上述的Where Select这些。所以所有实现了Enumberable接口的类都可以使用LINQ方法。比如数组，List，还有其他很多的集合只要实现了Enumberable接口都可以使用这些LINQ方法。

迭代查询

在每一次foreach查询时都会调用扩展方法进行过滤，大多数情况这是非常有用的，但在某些场景下我们只希望过滤一次数据，使用数组对象的`ToArrary()`，`Tolist()`方法可以改变这个默认操作。因为在ToArrary时调用了LINQ方法并且返回了一个新的数组，新数组没有这些扩展查询

```c#
void DeferredQuery()
{
    List<string> names = new() { "Nino", "Alberto", "Juan", "Mike", "Phil" };

    var namesWithJ = (from n in names
                     where n.StartsWith("J")
                     orderby n
                     select n).ToArray();

    Console.WriteLine("First iteration");
    foreach (string name in namesWithJ)
    {
        Console.WriteLine(name);
    }
    Console.WriteLine();

    names.Add("John");
    names.Add("Jim");
    names.Add("Jack");
    names.Add("Denny");

    Console.WriteLine("Second iteration");
    foreach (string name in namesWithJ)
    {
        Console.WriteLine(name);
    }
    Console.WriteLine();
}
//First iteration
//Juan

//Second iteration
//Juan

```

