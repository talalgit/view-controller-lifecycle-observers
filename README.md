# UIViewController Lifecycle Observers

Useful UIViewController extension for composing/creating reusable view controllers – no swizzling or subclassing needed!

```
controller.onViewWillAppear {
    print("viewWillAppear was called!")
}
```

This extension is very useful when composing view controllers with other modules. For example:

```
let analytics = ItemsAnalytics()
itemsListController.onViewDidAppear(run: analytics.reportListPageView)
```

You can also stop receiving messages by removing observers:

```
let service = ItemsService()
let observer = controller.onViewWillAppear(run: service.reloadItems)
observer.remove()
```