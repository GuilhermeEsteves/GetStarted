# Get Started with ASP.NET Core

Below you will find the steps to build your first ASP.NET Core app. See [Get Started with ASP.NET](http://www.asp.net/get-started/framework) if you are looking to get started with ASP.NET and the .NET Framework on Windows. [Learn more](http://www.asp.net/learn) about the difference between ASP.NET and ASP.NET Core.

Let's start by building a simple "Hello, world!" app.

1. Install .NET Core. See installation steps for Windows, macOS and Linux [here](https://dot.net/core).

2. Download the [sample](https://github.com/aspnet/GetStarted/archive/master.zip) and unzip it.

3. Restore the packages

  `dotnet restore`
   
4. Update the code in Startup.cs to return a message of your choice

  ```c#
  public class Startup
  {
      public void Configure(IApplicationBuilder app)
      {
          app.Run(context =>
          {
              return context.Response.WriteAsync("Hello from ASP.NET Core!");
          });
      }
  }
  ```

5. Run the app (the dotnet run command will build the app when it's out of date)

  `dotnet run`
  
6. Browse to http://localhost:5000

  ![Hello world output](https://www-asp.azureedge.net/v-2016-07-25-003/images/ui/get-started-1.png)

7. Press Ctrl+C to stop the app

Now let's enable support for static files.

1. Add the static file middleware in Startup.cs

  ```c#
  public class Startup
  {
      public void Configure(IApplicationBuilder app)
      {
          app.UseStaticFiles();
          
          app.Run(context =>
          {
              return context.Response.WriteAsync("Hello from ASP.NET Core!");
          });
      }
  }
  ```
  
2. Add a wwwroot folder with an index.html file

  ```html
  <!DOCTYPE html>
  <html>
  <body>
      <h1>Static file from ASP.NET Core!</h1>
  </body>
  </html>
  ```

3. Build and run the app

  `dotnet run`

4. Browse to http://localhost:5000/index.html

  ![Static file output](https://www-asp.azureedge.net/v-2016-07-25-003/images/ui/get-started-2.png)
  
That's it! 

Next up, try building your first ASP.NET Core MVC app with [Visual Studio](https://docs.asp.net/en/latest/tutorials/first-mvc-app/start-mvc.html) or [Visual Studio Code](https://docs.asp.net/en/latest/tutorials/your-first-mac-aspnet.html).

Also checkout out the [docs](https://docs.asp.net) and [tutorials](https://docs.asp.net/en/latest/tutorials/index.html).
