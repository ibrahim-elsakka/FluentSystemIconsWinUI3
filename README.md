# FluentSystemIconsWinUI3
 A WinUI 3 library that provides easy access to Microsoft's [Fluent System Icons](https://github.com/microsoft/fluentui-system-icons)

Fluent UI System Icons are a collection of familiar, friendly and modern icons from Microsoft.

![fluent system icons](https://raw.githubusercontent.com/microsoft/fluentui-system-icons/master/art/readme-banner.png)

# Installation
## From NuGet
In your app project, install the [`WinUI3.Fluent.Icons` NuGet package](https://nuget.org/packages/WinUI3.Fluent.Icons). 

You can install the latest version using the following command in the NuGet Package Manager:
```ps
Install-Package WinUI3.Fluent.Icons
```

# Examples
The following examples assume that you have imported the `WinUI3.Fluent.Icons` namespace as follows.
```xml
xmlns:fluent="using:WinUI3.Fluent.Icons"
```
```cs
using Fluent.Icons;
```

## Example A
Use a Fluent Icon as a button's content.
```xml
<Button>
    <fluent:FluentSymbolIcon Symbol="AddCircle24"/>
</Button>
```
```cs
myButton.Content = new FluentSymbolIcon(FluentSymbol.AddCircle24);
```

## Example B
Use Fluent Icons in a NavigationView's MenuItems.
```xml
<NavigationView.MenuItems>
    <NavigationViewItem Content="Navigate">
        <NavigationViewItem.Icon>
            <FluentIconElement Symbol="Directions24" />
        </NavigationViewItem.Icon>
    </NavigationViewItem>
</NavigationView.MenuItems>
```
```cs
myNavView.MenuItems.Add(new NavigationViewItem()
{
    Icon = new FluentIconElement(FluentSymbol.Directions24);
});
```

## Example C
Use a Fluent Icon in an AppBarButton.
```xml
<AppBarButton>
    <AppBarButton.Icon>
        <FluentIconElement Symbol="Star24" />
    </AppBarButton.Icon>
</AppBarButton>
```
```cs
myAppBarButton.Icon = new FluentIconElement(FluentSymbol.Star24);
```

## Example D
Show a list of all available Fluent Icons.
```xml
<ListView ItemsSource="{x:Bind fluent:FluentSymbolIcon.AllFluentIcons.Keys}">
    <ListView.ItemTemplate>
        <DataTemplate x:DataType="fluent:FluentSymbol">
            <ListViewItem>
                <StackPanel Spacing="10" Orientation="Horizontal">
                    <fluent:FluentSymbolIcon Symbol="{x:Bind}"/>
                    <TextBlock Text="{x:Bind}"/>
                </StackPanel>
            </ListViewItem>
        </DataTemplate>
    </ListView.ItemTemplate>
</ListView>
```

## Example E
Get the `Windows.UI.Xaml.Media.Geometry` object that represents an icon
```cs
FluentSymbolIcon.GetPathData(FluentSymbol.Home);
```

## Example F
Get a PathIcon object that represents an icon
```cs
FluentSymbolIcon.GetPathIcon(FluentSymbol.Home);
```

## Example G
Get the raw SVG path data for a given icon
```cs
FluentSymbolIcon.AllFluentIcons[FluentSymbol.Home];
```
