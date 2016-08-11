# XamarinFormsListViewXamlCustom

Sample: Using Xamarin.Forms.ListView on XAML, with inline CustomView.

## Pickuped code
### Page1.xaml
```
…
<ListView x:Name="mylist" ItemsSource="{Binding}" VerticalOptions="FillAndExpand">
    <ListView.ItemTemplate>
        <DataTemplate>
            <ViewCell>
                <StackLayout Orientation="Horizontal" Padding="5">
                    <Label Text="{Binding Name}" WidthRequest="200" />
                    <Label Text="{Binding Score}" />
                </StackLayout>
            </ViewCell>
        </DataTemplate>
    </ListView.ItemTemplate>
</ListView>
…
```

### Page1.xaml.cs
```
public partial class Page1 : ContentPage
{
    public Page1()
    {
        InitializeComponent();

        // Make data list
        List<ItemInfo> list = new List<ItemInfo>();
        list.Add(new ItemInfo { Name = "Apple", Score = 100 });
        list.Add(new ItemInfo { Name = "Banana", Score = 150 });
        list.Add(new ItemInfo { Name = "Candy", Score = 80 });
        list.Add(new ItemInfo { Name = "Drop", Score = -10 });

        // Bind
        this.BindingContext = list;
    }
}
```

## Screenshot
![screenshot](https://raw.githubusercontent.com/xamarin-samples/XamarinFormsListViewXamlCustom/master/screenshots/screenshot.png)
