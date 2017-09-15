
<span data-ttu-id="43c25-101">我们将在下一教程中介绍 [DataAnnotations](http://msdn.microsoft.com/library/system.componentmodel.dataannotations.aspx)。</span><span class="sxs-lookup"><span data-stu-id="43c25-101">We'll cover [DataAnnotations](http://msdn.microsoft.com/library/system.componentmodel.dataannotations.aspx) in the next tutorial.</span></span> <span data-ttu-id="43c25-102">[Display](https://msdn.microsoft.com/library/system.componentmodel.dataannotations.displayattribute.aspx) 特性指定要显示的字段名称的内容（本例中应为“Release Date”，而不是“ReleaseDate”）。</span><span class="sxs-lookup"><span data-stu-id="43c25-102">The [Display](https://msdn.microsoft.com/library/system.componentmodel.dataannotations.displayattribute.aspx) attribute specifies what to display for the name of a field (in this case "Release Date" instead of "ReleaseDate").</span></span> <span data-ttu-id="43c25-103">[DataType](https://msdn.microsoft.com/library/system.componentmodel.dataannotations.datatypeattribute.aspx) 特性指定数据的类型（日期），使字段中存储的时间信息不会显示。</span><span class="sxs-lookup"><span data-stu-id="43c25-103">The [DataType](https://msdn.microsoft.com/library/system.componentmodel.dataannotations.datatypeattribute.aspx) attribute specifies the type of the data (Date), so the time information stored in the field is not displayed.</span></span>

<span data-ttu-id="43c25-104">浏览到 `Movies` 控制器，并将鼠标指针悬停在“编辑”链接上以查看目标 URL。</span><span class="sxs-lookup"><span data-stu-id="43c25-104">Browse to the `Movies` controller and hold the mouse pointer over an **Edit** link to see the target URL.</span></span>

![鼠标悬停在“编辑”链接上的浏览器窗口，显示了 http://localhost:1234/Movies/Edit/5 的链接 URL](../../tutorials/first-mvc-app/controller-methods-views/_static/edit7.png)

<span data-ttu-id="43c25-106">“编辑”、“详细信息”和“删除”链接是在 Views/Movies/Index.cshtml 文件中由 MVC Core 定位标记帮助程序生成的。</span><span class="sxs-lookup"><span data-stu-id="43c25-106">The **Edit**, **Details**, and **Delete** links are generated by the MVC Core Anchor Tag Helper in the *Views/Movies/Index.cshtml* file.</span></span>

<span data-ttu-id="43c25-107">[!code-HTML[Main](../../tutorials/first-mvc-app/start-mvc/sample/MvcMovie/Views/Movies/IndexOriginal.cshtml?highlight=1-3&range=46-50)]</span><span class="sxs-lookup"><span data-stu-id="43c25-107">[!code-HTML[Main](../../tutorials/first-mvc-app/start-mvc/sample/MvcMovie/Views/Movies/IndexOriginal.cshtml?highlight=1-3&range=46-50)]</span></span>

<span data-ttu-id="43c25-108">[标记帮助程序](xref:mvc/views/tag-helpers/intro)使服务器端代码可以在 Razor 文件中参与创建和呈现 HTML 元素。</span><span class="sxs-lookup"><span data-stu-id="43c25-108">[Tag Helpers](xref:mvc/views/tag-helpers/intro) enable server-side code to participate in creating and rendering HTML elements in Razor files.</span></span> <span data-ttu-id="43c25-109">在上面的代码中，`AnchorTagHelper` 从控制器操作方法和路由 ID 动态生成 HTML `href` 特性值。在最喜欢的浏览器中使用“查看源”，或使用开发人员工具来检查生成的标记。</span><span class="sxs-lookup"><span data-stu-id="43c25-109">In the code above, the `AnchorTagHelper` dynamically generates the HTML `href` attribute value from the controller action method and route id. You use **View Source** from your favorite browser or use the developer tools to examine the generated markup.</span></span> <span data-ttu-id="43c25-110">生成的 HTML 的一部分如下所示：</span><span class="sxs-lookup"><span data-stu-id="43c25-110">A portion of the generated HTML is shown below:</span></span>

```html
 <td>
    <a href="/Movies/Edit/4"> Edit </a> |
    <a href="/Movies/Details/4"> Details </a> |
    <a href="/Movies/Delete/4"> Delete </a>
</td>
```

<span data-ttu-id="43c25-111">重新调用在 Startup.cs 文件中设置的[路由](xref:mvc/controllers/routing)的格式：</span><span class="sxs-lookup"><span data-stu-id="43c25-111">Recall the format for [routing](xref:mvc/controllers/routing) set in the *Startup.cs* file:</span></span>

<span data-ttu-id="43c25-112">[!code-csharp[Main](../../tutorials/first-mvc-app/start-mvc/sample/MvcMovie/Startup.cs?name=snippet_1&highlight=5)]</span><span class="sxs-lookup"><span data-stu-id="43c25-112">[!code-csharp[Main](../../tutorials/first-mvc-app/start-mvc/sample/MvcMovie/Startup.cs?name=snippet_1&highlight=5)]</span></span>

<span data-ttu-id="43c25-113">ASP.NET Core 将 `http://localhost:1234/Movies/Edit/4` 转换为对 `Movies` 控制器的 `Edit` 操作方法的请求，参数 `Id` 为 4。</span><span class="sxs-lookup"><span data-stu-id="43c25-113">ASP.NET Core translates `http://localhost:1234/Movies/Edit/4` into a request to the `Edit` action method of the `Movies` controller with the parameter `Id` of 4.</span></span> <span data-ttu-id="43c25-114">（控制器方法也称为操作方法。）</span><span class="sxs-lookup"><span data-stu-id="43c25-114">(Controller methods are also known as action methods.)</span></span>

<span data-ttu-id="43c25-115">[标记帮助程序](xref:mvc/views/tag-helpers/intro)是 ASP.NET Core 中最受欢迎的新功能之一。</span><span class="sxs-lookup"><span data-stu-id="43c25-115">[Tag Helpers](xref:mvc/views/tag-helpers/intro) are one of the most popular new features in ASP.NET Core.</span></span> <span data-ttu-id="43c25-116">有关详细信息，请参阅[其他资源](#additional-resources)。</span><span class="sxs-lookup"><span data-stu-id="43c25-116">See [Additional resources](#additional-resources) for more information.</span></span>

<span data-ttu-id="43c25-117">打开 `Movies` 控制器并检查两个 `Edit` 操作方法。</span><span class="sxs-lookup"><span data-stu-id="43c25-117">Open the `Movies` controller and examine the two `Edit` action methods.</span></span> <span data-ttu-id="43c25-118">以下代码显示了 `HTTP GET Edit` 方法，此方法将提取电影并填充由 Edit.cshtml Razor 文件生成的编辑表单。</span><span class="sxs-lookup"><span data-stu-id="43c25-118">The following code shows the `HTTP GET Edit` method, which fetches the movie and populates the edit form generated by the *Edit.cshtml* Razor file.</span></span>

<span data-ttu-id="43c25-119">[!code-csharp[Main](../../tutorials/first-mvc-app/start-mvc/sample/MvcMovie/Controllers/MC1.cs?name=snippet_edit1)]</span><span class="sxs-lookup"><span data-stu-id="43c25-119">[!code-csharp[Main](../../tutorials/first-mvc-app/start-mvc/sample/MvcMovie/Controllers/MC1.cs?name=snippet_edit1)]</span></span>

<span data-ttu-id="43c25-120">以下代码显示 `HTTP POST Edit` 方法，它会处理已发布的电影值：</span><span class="sxs-lookup"><span data-stu-id="43c25-120">The following code shows the `HTTP POST Edit` method, which processes the posted movie values:</span></span>

<span data-ttu-id="43c25-121">[!code-csharp[Main](../../tutorials/first-mvc-app/start-mvc/sample/MvcMovie/Controllers/MC1.cs?name=snippet_edit2)]</span><span class="sxs-lookup"><span data-stu-id="43c25-121">[!code-csharp[Main](../../tutorials/first-mvc-app/start-mvc/sample/MvcMovie/Controllers/MC1.cs?name=snippet_edit2)]</span></span>

<span data-ttu-id="43c25-122">`[Bind]` 特性是防止[过度发布](https://docs.microsoft.com/aspnet/mvc/overview/getting-started/getting-started-with-ef-using-mvc/implementing-basic-crud-functionality-with-the-entity-framework-in-asp-net-mvc-application#overpost)的一种方法。</span><span class="sxs-lookup"><span data-stu-id="43c25-122">The `[Bind]` attribute is one way to protect against [over-posting](https://docs.microsoft.com/aspnet/mvc/overview/getting-started/getting-started-with-ef-using-mvc/implementing-basic-crud-functionality-with-the-entity-framework-in-asp-net-mvc-application#overpost).</span></span> <span data-ttu-id="43c25-123">只应在 `[Bind]` 特性中包含想要更改的属性。</span><span class="sxs-lookup"><span data-stu-id="43c25-123">You should only include properties in the `[Bind]` attribute that you want to change.</span></span> <span data-ttu-id="43c25-124">有关详细信息，请参阅 [Protect your controller from over-posting](http://www.asp.net/mvc/overview/getting-started/getting-started-with-ef-using-mvc/implementing-basic-crud-functionality-with-the-entity-framework-in-asp-net-mvc-application#overpost)（防止控制器过度发布）。</span><span class="sxs-lookup"><span data-stu-id="43c25-124">See [Protect your controller from over-posting](http://www.asp.net/mvc/overview/getting-started/getting-started-with-ef-using-mvc/implementing-basic-crud-functionality-with-the-entity-framework-in-asp-net-mvc-application#overpost) for more information.</span></span> <span data-ttu-id="43c25-125">[ViewModels](http://rachelappel.com/use-viewmodels-to-manage-data-amp-organize-code-in-asp-net-mvc-applications/) 提供了一种替代方法以防止过度发布。</span><span class="sxs-lookup"><span data-stu-id="43c25-125">[ViewModels](http://rachelappel.com/use-viewmodels-to-manage-data-amp-organize-code-in-asp-net-mvc-applications/) provide an alternative approach to prevent over-posting.</span></span>

<span data-ttu-id="43c25-126">请注意第二个 `Edit` 操作方法的前面是 `[HttpPost]` 特性。</span><span class="sxs-lookup"><span data-stu-id="43c25-126">Notice the second `Edit` action method is preceded by the `[HttpPost]` attribute.</span></span>

<span data-ttu-id="43c25-127">[!code-csharp[Main](../../tutorials/first-mvc-app/start-mvc/sample/MvcMovie/Controllers/MC1.cs?name=snippet_edit2&highlight=4)]</span><span class="sxs-lookup"><span data-stu-id="43c25-127">[!code-csharp[Main](../../tutorials/first-mvc-app/start-mvc/sample/MvcMovie/Controllers/MC1.cs?name=snippet_edit2&highlight=4)]</span></span>

<span data-ttu-id="43c25-128">`HttpPost` 特性指定只能为 `POST` 请求调用此 `Edit` 方法。</span><span class="sxs-lookup"><span data-stu-id="43c25-128">The `HttpPost` attribute specifies that this `Edit` method can be invoked *only* for `POST` requests.</span></span> <span data-ttu-id="43c25-129">可将 `[HttpGet]` 属性应用于第一个编辑方法，但不是必需，因为 `[HttpGet]` 是默认设置。</span><span class="sxs-lookup"><span data-stu-id="43c25-129">You could apply the `[HttpGet]` attribute to the first edit method, but that's not necessary because `[HttpGet]` is the default.</span></span>

<span data-ttu-id="43c25-130">`ValidateAntiForgeryToken` 特性用于[防止请求伪造](xref:security/anti-request-forgery)，并与编辑视图文件 (Views/Movies/Edit.cshtml) 中生成的防伪标记相配对。</span><span class="sxs-lookup"><span data-stu-id="43c25-130">The `ValidateAntiForgeryToken` attribute is used to [prevent forgery of a request](xref:security/anti-request-forgery) and is paired up with an anti-forgery token generated in the edit view file (*Views/Movies/Edit.cshtml*).</span></span> <span data-ttu-id="43c25-131">编辑视图文件使用[表单标记帮助程序](xref:mvc/views/working-with-forms)生成防伪标记。</span><span class="sxs-lookup"><span data-stu-id="43c25-131">The edit view file generates the anti-forgery token with the [Form Tag Helper](xref:mvc/views/working-with-forms).</span></span>

<span data-ttu-id="43c25-132">[!code-HTML[Main](../../tutorials/first-mvc-app/start-mvc/sample/MvcMovie/Views/Movies/Edit.cshtml?range=9)]</span><span class="sxs-lookup"><span data-stu-id="43c25-132">[!code-HTML[Main](../../tutorials/first-mvc-app/start-mvc/sample/MvcMovie/Views/Movies/Edit.cshtml?range=9)]</span></span>

<span data-ttu-id="43c25-133">[表单标记帮助程序](xref:mvc/views/working-with-forms)会生成隐藏的防伪标记，此标记必须与电影控制器的 `Edit` 方法中 `[ValidateAntiForgeryToken]` 生成的防伪标记相匹配。</span><span class="sxs-lookup"><span data-stu-id="43c25-133">The [Form Tag Helper](xref:mvc/views/working-with-forms) generates a hidden anti-forgery token that must match the `[ValidateAntiForgeryToken]` generated anti-forgery token in the `Edit` method of the Movies controller.</span></span> <span data-ttu-id="43c25-134">有关详细信息，请参阅[反请求伪造](xref:security/anti-request-forgery)。</span><span class="sxs-lookup"><span data-stu-id="43c25-134">For more information, see [Anti-Request Forgery](xref:security/anti-request-forgery).</span></span>

<span data-ttu-id="43c25-135">`HttpGet Edit` 方法采用电影 `ID` 参数，使用Entity Framework `SingleOrDefaultAsync` 方法查找电影，并将所选电影返回到“编辑”视图。</span><span class="sxs-lookup"><span data-stu-id="43c25-135">The `HttpGet Edit` method takes the movie `ID` parameter, looks up the movie using the Entity Framework `SingleOrDefaultAsync` method, and returns the selected movie to the Edit view.</span></span> <span data-ttu-id="43c25-136">如果无法找到电影，则返回 `NotFound` (HTTP 404)。</span><span class="sxs-lookup"><span data-stu-id="43c25-136">If a movie cannot be found, `NotFound` (HTTP 404) is returned.</span></span>

<span data-ttu-id="43c25-137">[!code-csharp[Main](../../tutorials/first-mvc-app/start-mvc/sample/MvcMovie/Controllers/MC1.cs?name=snippet_edit1)]</span><span class="sxs-lookup"><span data-stu-id="43c25-137">[!code-csharp[Main](../../tutorials/first-mvc-app/start-mvc/sample/MvcMovie/Controllers/MC1.cs?name=snippet_edit1)]</span></span>

<span data-ttu-id="43c25-138">当基架系统创建“编辑”视图时，它会检查 `Movie` 类并创建代码为类的每个属性呈现 `<label>` 和 `<input>` 元素。</span><span class="sxs-lookup"><span data-stu-id="43c25-138">When the scaffolding system created the Edit view, it examined the `Movie` class and created code to render `<label>` and `<input>` elements for each property of the class.</span></span> <span data-ttu-id="43c25-139">以下示例显示由 Visual Studio 基架系统生成的“编辑”视图：</span><span class="sxs-lookup"><span data-stu-id="43c25-139">The following example shows the Edit view that was generated by the Visual Studio scaffolding system:</span></span>

<span data-ttu-id="43c25-140">[!code-HTML[Main](../../tutorials/first-mvc-app/start-mvc/sample/MvcMovie/Views/Movies/EditCopy.cshtml?highlight=1)]</span><span class="sxs-lookup"><span data-stu-id="43c25-140">[!code-HTML[Main](../../tutorials/first-mvc-app/start-mvc/sample/MvcMovie/Views/Movies/EditCopy.cshtml?highlight=1)]</span></span>

<span data-ttu-id="43c25-141">请注意视图模板在文件顶端有一个 `@model MvcMovie.Models.Movie` 语句。</span><span class="sxs-lookup"><span data-stu-id="43c25-141">Notice how the view template has a `@model MvcMovie.Models.Movie` statement at the top of the file.</span></span> <span data-ttu-id="43c25-142">`@model MvcMovie.Models.Movie` 指定视图期望的视图模板的模型为 `Movie` 类型。</span><span class="sxs-lookup"><span data-stu-id="43c25-142">`@model MvcMovie.Models.Movie` specifies that the view expects the model for the view template to be of type `Movie`.</span></span>

<span data-ttu-id="43c25-143">基架的代码使用几个标记帮助程序方法来简化 HTML 标记。</span><span class="sxs-lookup"><span data-stu-id="43c25-143">The scaffolded code uses several Tag Helper methods to streamline the HTML markup.</span></span> <span data-ttu-id="43c25-144">[标签标记帮助程序](xref:mvc/views/working-with-forms)显示字段的名称（“Title”、“ReleaseDate”、“Genre”或“Price”）。</span><span class="sxs-lookup"><span data-stu-id="43c25-144">The - [Label Tag Helper](xref:mvc/views/working-with-forms) displays the name of the field ("Title", "ReleaseDate", "Genre", or "Price").</span></span> <span data-ttu-id="43c25-145">[输入标记帮助程序](xref:mvc/views/working-with-forms)呈现 HTML `<input>` 元素。</span><span class="sxs-lookup"><span data-stu-id="43c25-145">The [Input Tag Helper](xref:mvc/views/working-with-forms) renders an HTML `<input>` element.</span></span> <span data-ttu-id="43c25-146">[验证标记帮助程序](xref:mvc/views/working-with-forms)显示与该属性相关联的任何验证消息。</span><span class="sxs-lookup"><span data-stu-id="43c25-146">The [Validation Tag Helper](xref:mvc/views/working-with-forms) displays any validation messages associated with that property.</span></span>

<span data-ttu-id="43c25-147">运行应用程序并导航到 `/Movies` URL。</span><span class="sxs-lookup"><span data-stu-id="43c25-147">Run the application and navigate to the `/Movies` URL.</span></span> <span data-ttu-id="43c25-148">点击“编辑”链接。</span><span class="sxs-lookup"><span data-stu-id="43c25-148">Click an **Edit** link.</span></span> <span data-ttu-id="43c25-149">在浏览器中查看页面的源。</span><span class="sxs-lookup"><span data-stu-id="43c25-149">In the browser, view the source for the page.</span></span> <span data-ttu-id="43c25-150">为 `<form>` 元素生成的 HTML 如下所示。</span><span class="sxs-lookup"><span data-stu-id="43c25-150">The generated HTML for the `<form>` element is shown below.</span></span>

<span data-ttu-id="43c25-151">[!code-HTML[Main](../../tutorials/first-mvc-app/start-mvc/sample/MvcMovie/Views/Shared/edit_view_source.html?highlight=1,6,10,17,24,28)]</span><span class="sxs-lookup"><span data-stu-id="43c25-151">[!code-HTML[Main](../../tutorials/first-mvc-app/start-mvc/sample/MvcMovie/Views/Shared/edit_view_source.html?highlight=1,6,10,17,24,28)]</span></span>

<span data-ttu-id="43c25-152">`<input>` 元素位于 `HTML <form>` 元素中，后者的 `action` 特性设置为发布到 `/Movies/Edit/id` URL。</span><span class="sxs-lookup"><span data-stu-id="43c25-152">The `<input>` elements are in an `HTML <form>` element whose `action` attribute is set to post to the `/Movies/Edit/id` URL.</span></span> <span data-ttu-id="43c25-153">当单击 `Save` 按钮时，表单数据将发布到服务器。</span><span class="sxs-lookup"><span data-stu-id="43c25-153">The form data will be posted to the server when the `Save` button is clicked.</span></span> <span data-ttu-id="43c25-154">关闭 `</form>` 元素之前的最后一行显示[表单标记帮助程序](xref:mvc/views/working-with-forms)生成的隐藏的 [XSRF](xref:security/anti-request-forgery) 标记。</span><span class="sxs-lookup"><span data-stu-id="43c25-154">The last line before the closing `</form>` element shows the hidden [XSRF](xref:security/anti-request-forgery) token generated by the [Form Tag Helper](xref:mvc/views/working-with-forms).</span></span>

## <a name="processing-the-post-request"></a><span data-ttu-id="43c25-155">处理 POST 请求</span><span class="sxs-lookup"><span data-stu-id="43c25-155">Processing the POST Request</span></span>

<span data-ttu-id="43c25-156">以下列表显示了 `Edit` 操作方法的 `[HttpPost]` 版本。</span><span class="sxs-lookup"><span data-stu-id="43c25-156">The following listing shows the `[HttpPost]` version of the `Edit` action method.</span></span>

<span data-ttu-id="43c25-157">[!code-csharp[Main](../../tutorials/first-mvc-app/start-mvc/sample/MvcMovie/Controllers/MC1.cs?name=snippet_edit2)]</span><span class="sxs-lookup"><span data-stu-id="43c25-157">[!code-csharp[Main](../../tutorials/first-mvc-app/start-mvc/sample/MvcMovie/Controllers/MC1.cs?name=snippet_edit2)]</span></span>

<span data-ttu-id="43c25-158">`[ValidateAntiForgeryToken]` 特性验证[表单标记帮助程序](xref:mvc/views/working-with-forms)中的防伪标记生成器生成的隐藏的 [XSRF](xref:security/anti-request-forgery) 标记</span><span class="sxs-lookup"><span data-stu-id="43c25-158">The `[ValidateAntiForgeryToken]` attribute validates the hidden [XSRF](xref:security/anti-request-forgery) token generated by the anti-forgery token generator in the [Form Tag Helper](xref:mvc/views/working-with-forms)</span></span>

<span data-ttu-id="43c25-159">[模型绑定](xref:mvc/models/model-binding)系统采用发布的表单值，并创建一个作为 `movie` 参数传递的 `Movie` 对象。</span><span class="sxs-lookup"><span data-stu-id="43c25-159">The [model binding](xref:mvc/models/model-binding) system takes the posted form values and creates a `Movie` object that's passed as the `movie` parameter.</span></span> <span data-ttu-id="43c25-160">`ModelState.IsValid` 方法验证表单中提交的数据是否可以用于修改（编辑或更新）`Movie` 对象。</span><span class="sxs-lookup"><span data-stu-id="43c25-160">The `ModelState.IsValid` method verifies that the data submitted in the form can be used to modify (edit or update) a `Movie` object.</span></span> <span data-ttu-id="43c25-161">如果数据有效，将保存此数据。</span><span class="sxs-lookup"><span data-stu-id="43c25-161">If the data is valid it's saved.</span></span> <span data-ttu-id="43c25-162">通过调用数据库上下文的 `SaveChangesAsync` 方法，将更新（编辑）的电影数据保存到数据库。</span><span class="sxs-lookup"><span data-stu-id="43c25-162">The updated (edited) movie data is saved to the database by calling the `SaveChangesAsync` method of database context.</span></span> <span data-ttu-id="43c25-163">保存数据后，代码将用户重定向到 `MoviesController` 类的 `Index` 操作方法，此方法显示电影集合，包括刚才所做的更改。</span><span class="sxs-lookup"><span data-stu-id="43c25-163">After saving the data, the code redirects the user to the `Index` action method of the `MoviesController` class, which displays the movie collection, including the changes just made.</span></span>

<span data-ttu-id="43c25-164">在表单发布到服务器之前，客户端验证会检查字段上的任何验证规则。</span><span class="sxs-lookup"><span data-stu-id="43c25-164">Before the form is posted to the server, client side validation checks any validation rules on the fields.</span></span> <span data-ttu-id="43c25-165">如果有任何验证错误，则将显示错误消息，并且不会发布表单。</span><span class="sxs-lookup"><span data-stu-id="43c25-165">If there are any validation errors, an error message is displayed and the form is not posted.</span></span> <span data-ttu-id="43c25-166">如果禁用 JavaScript，则不会进行客户端验证，但服务器将检测无效的发布值，并且表单值将与错误消息一起重新显示。</span><span class="sxs-lookup"><span data-stu-id="43c25-166">If JavaScript is disabled, you won't have client side validation but the server will detect the posted values that are not valid, and the form values will be redisplayed with error messages.</span></span> <span data-ttu-id="43c25-167">稍后在本教程中，我们将更详细地研究[模型验证](xref:mvc/models/validation)。</span><span class="sxs-lookup"><span data-stu-id="43c25-167">Later in the tutorial we examine [Model Validation](xref:mvc/models/validation) in more detail.</span></span> <span data-ttu-id="43c25-168">Views/Movies/Edit.cshtml 视图模板中的[验证标记帮助程序](xref:mvc/views/working-with-forms)负责显示相应的错误消息。</span><span class="sxs-lookup"><span data-stu-id="43c25-168">The [Validation Tag Helper](xref:mvc/views/working-with-forms) in the *Views/Movies/Edit.cshtml* view template takes care of displaying appropriate error messages.</span></span>

![“编辑”视图：不正确的“价格”值 abc 的异常，说明“价格”字段必须是一个数字。](../../tutorials/first-mvc-app/controller-methods-views/_static/val.png)

<span data-ttu-id="43c25-171">电影控制器中的所有 `HttpGet` 方法都遵循类似的模式。</span><span class="sxs-lookup"><span data-stu-id="43c25-171">All the `HttpGet` methods in the movie controller follow a similar pattern.</span></span> <span data-ttu-id="43c25-172">它们获取电影对象（对于 `Index`获取的是对象列表）并将对象（模型）传递给视图。</span><span class="sxs-lookup"><span data-stu-id="43c25-172">They get a movie object (or list of objects, in the case of `Index`), and pass the object (model) to the view.</span></span> <span data-ttu-id="43c25-173">`Create` 方法将空的电影对象传递给 `Create` 视图。</span><span class="sxs-lookup"><span data-stu-id="43c25-173">The `Create` method passes an empty movie object to the `Create` view.</span></span> <span data-ttu-id="43c25-174">在方法的 `[HttpPost]` 重载中，创建、编辑、删除或以其他方式修改数据的所有方法都执行此操作。</span><span class="sxs-lookup"><span data-stu-id="43c25-174">All the methods that create, edit, delete, or otherwise modify data do so in the `[HttpPost]` overload of the method.</span></span> <span data-ttu-id="43c25-175">以 `HTTP GET` 方式修改数据是一种安全隐患。</span><span class="sxs-lookup"><span data-stu-id="43c25-175">Modifying data in an `HTTP GET` method is a security risk.</span></span> <span data-ttu-id="43c25-176">以 `HTTP GET` 方法修改数据也违反了 HTTP 最佳做法和架构 [REST](http://rest.elkstein.org/) 模式，后者指定 GET 请求不应更改应用程序的状态。</span><span class="sxs-lookup"><span data-stu-id="43c25-176">Modifying data in an `HTTP GET` method also violates HTTP best practices and the architectural [REST](http://rest.elkstein.org/) pattern, which specifies that GET requests should not change the state of your application.</span></span> <span data-ttu-id="43c25-177">换句话说，执行 GET 操作应是没有任何隐患的安全操作，也不会修改持久数据。</span><span class="sxs-lookup"><span data-stu-id="43c25-177">In other words, performing a GET operation should be a safe operation that has no side effects and doesn't modify your persisted data.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="43c25-178">其他资源</span><span class="sxs-lookup"><span data-stu-id="43c25-178">Additional resources</span></span>

* [<span data-ttu-id="43c25-179">全球化和本地化</span><span class="sxs-lookup"><span data-stu-id="43c25-179">Globalization and localization</span></span>](xref:fundamentals/localization)
* [<span data-ttu-id="43c25-180">标记帮助程序简介</span><span class="sxs-lookup"><span data-stu-id="43c25-180">Introduction to Tag Helpers</span></span>](xref:mvc/views/tag-helpers/intro)
* [<span data-ttu-id="43c25-181">创作标记帮助程序</span><span class="sxs-lookup"><span data-stu-id="43c25-181">Authoring Tag Helpers</span></span>](xref:mvc/views/tag-helpers/authoring)
* [<span data-ttu-id="43c25-182">反请求伪造</span><span class="sxs-lookup"><span data-stu-id="43c25-182">Anti-Request Forgery</span></span>](xref:security/anti-request-forgery)
* <span data-ttu-id="43c25-183">防止控制器[过度发布](http://www.asp.net/mvc/overview/getting-started/getting-started-with-ef-using-mvc/implementing-basic-crud-functionality-with-the-entity-framework-in-asp-net-mvc-application#overpost)</span><span class="sxs-lookup"><span data-stu-id="43c25-183">Protect your controller from [over-posting](http://www.asp.net/mvc/overview/getting-started/getting-started-with-ef-using-mvc/implementing-basic-crud-functionality-with-the-entity-framework-in-asp-net-mvc-application#overpost)</span></span>
* [<span data-ttu-id="43c25-184">ViewModels</span><span class="sxs-lookup"><span data-stu-id="43c25-184">ViewModels</span></span>](http://rachelappel.com/use-viewmodels-to-manage-data-amp-organize-code-in-asp-net-mvc-applications/)
* [<span data-ttu-id="43c25-185">表单标记帮助程序</span><span class="sxs-lookup"><span data-stu-id="43c25-185">Form Tag Helper</span></span>](xref:mvc/views/working-with-forms)
* [<span data-ttu-id="43c25-186">输入标记帮助程序</span><span class="sxs-lookup"><span data-stu-id="43c25-186">Input Tag Helper</span></span>](xref:mvc/views/working-with-forms)
* [<span data-ttu-id="43c25-187">标签标记帮助程序</span><span class="sxs-lookup"><span data-stu-id="43c25-187">Label Tag Helper</span></span>](xref:mvc/views/working-with-forms)
* [<span data-ttu-id="43c25-188">选择标记帮助程序</span><span class="sxs-lookup"><span data-stu-id="43c25-188">Select Tag Helper</span></span>](xref:mvc/views/working-with-forms)
* [<span data-ttu-id="43c25-189">验证标记帮助程序</span><span class="sxs-lookup"><span data-stu-id="43c25-189">Validation Tag Helper</span></span>](xref:mvc/views/working-with-forms)