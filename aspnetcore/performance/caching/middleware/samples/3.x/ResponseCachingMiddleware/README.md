# <a name="aspnet-core-response-caching-sample"></a><span data-ttu-id="62add-101">ASP.NET Core 响应缓存示例</span><span class="sxs-lookup"><span data-stu-id="62add-101">ASP.NET Core Response Caching Sample</span></span>

<span data-ttu-id="62add-102">本示例演示使用 ASP.NET Core [响应缓存中间件](https://docs.microsoft.com/aspnet/core/performance/caching/middleware)。</span><span class="sxs-lookup"><span data-stu-id="62add-102">This sample illustrates the usage of ASP.NET Core [Response Caching Middleware](https://docs.microsoft.com/aspnet/core/performance/caching/middleware).</span></span>

<span data-ttu-id="62add-103">应用使用其索引页进行响应, 包括配置`Cache-Control`缓存行为的标头。</span><span class="sxs-lookup"><span data-stu-id="62add-103">The app responds with its Index page, including a `Cache-Control` header to configure caching behavior.</span></span> <span data-ttu-id="62add-104">应用程序还会将`Vary`标头设置为将缓存配置为仅`Accept-Encoding`当后续请求的标头与原始请求中的标头匹配时才为响应提供服务。</span><span class="sxs-lookup"><span data-stu-id="62add-104">The app also sets the `Vary` header to configure the cache to serve the response only if the `Accept-Encoding` header of subsequent requests matches that from the original request.</span></span>

<span data-ttu-id="62add-105">运行示例时, 将在存储和缓存索引页时从缓存中为长达10秒提供服务。</span><span class="sxs-lookup"><span data-stu-id="62add-105">When running the sample, the Index page is served from cache when stored and cached for up to 10 seconds.</span></span>

<span data-ttu-id="62add-106">测试缓存行为:</span><span class="sxs-lookup"><span data-stu-id="62add-106">To test caching behavior:</span></span>

* <span data-ttu-id="62add-107">不要使用浏览器测试缓存行为。</span><span class="sxs-lookup"><span data-stu-id="62add-107">Don't use a browser to test caching behavior.</span></span> <span data-ttu-id="62add-108">浏览器通常会在重新加载时添加一个缓存控制标头, 以阻止中间件提供缓存页面。</span><span class="sxs-lookup"><span data-stu-id="62add-108">Browsers often add a cache control header on reload that prevent the middleware from serving a cached page.</span></span> <span data-ttu-id="62add-109">例如, `Cache-Control`浏览器可能会添加值为`max-age=0`的标头。</span><span class="sxs-lookup"><span data-stu-id="62add-109">For example, a `Cache-Control` header with a value of `max-age=0`) might be added by the browser.</span></span>
* <span data-ttu-id="62add-110">使用允许显式设置请求标头的开发人员工具, 如<a href="https://www.telerik.com/fiddler">Fiddler</a>或<a href="https://www.getpostman.com/">Postman</a>。</span><span class="sxs-lookup"><span data-stu-id="62add-110">Use a developer tool that permits setting the request headers explicitly, such as <a href="https://www.telerik.com/fiddler">Fiddler</a> or <a href="https://www.getpostman.com/">Postman</a>.</span></span>