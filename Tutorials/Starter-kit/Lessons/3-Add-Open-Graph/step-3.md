---
versionFrom: 8.0.0
---

# Add Open Graph - Step 3

Next step is to get the Open Graph code rendered on the website. This is done in the `head` section of the HTML, so you need to find the template for this. 

In the `Starter Kit` the head is placed in the Master Template, which is responsible for wrapping all the other templates. 

Because you've added the Open Graph feature as a composition you can check if the composition is present on the current page and then render meta tags.

1. Go to the **Settings** section and expand the Template tree.
2. Select the *Master* template
3. Find the `<head>` HTML tags at the top of the Template
4. Write the following before the closing `</head>` tag:

```csharp
@if(Model.Content is IOpenGraph){
    @Html.Partial("openGraph")
}
```

This will render a partial view *if* the composition is present on the current page. Currently that is the case for Home and Blog posts on the site. 

`IOpenGraph` is an interface created by adding the composition. When you know how that works you can see how powerful it can be. If not, enjoy the handy helper to check for the composition.

At the end, the head should look like this:

    <head>
        ...
        
        @if (Model.Content is IOpenGraph) {
            @Html.Partial("openGraph")
        }
    </head>

[Previous](step-2.md) - [Next](step-4.md)
