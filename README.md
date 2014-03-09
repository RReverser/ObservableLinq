# ObservableLinq


ObservableLinq is an open source, portable class library that can be easily deployed from [nuget] and used in .NET 4.5, Windows Phone 8 and Windows Store applications. ObservableLinq proposes to implement a subset of the [LINQ] operators on ObservableCollection, where source collection changes are automatically reflected in the result collection.

![a](https://raw.github.com/TheFabFab/ObservableLinq/master/img/basic_projection.gif)

## How would you use ObservableLinq?

### Project data between different domains

Larger applications are often architectured in a layered manner (3-tier application, MVVM, etc.) The different domains can add new attributes, filters and sort criteria to your data.

Consider an editable data grid that contains personal data in an MVVM application. The model class will contain records with first name, last name, etc. Your view model might wrap the model object and have additional attributes, like 'IsEditing' and 'IsChanged'. Your UI layer will transform the view model into rows in the datagrid.

Using ObservableLinq not only allows you to project your model into view models, but when your original collection changes, it will keep the view model collection up to date, without loosing the added data on the view model level.

### Change between different views of the same collection

ObservableLinq provides a special collection, called ObserverCollection. This collection can be instructed to follow an observable collection. However, ObserverCollection can change from one observed collection to another at any time. All items present in both collections will be retained and moved to their new position.

Let's consider our personal data view models from before. We can project that collection into one where we sort by first name and another one where we sort by last name. Maybe another one, where we filter out unchanged items. Then, we bind our datagrid to an observer collection that switches between these collections according to user input...

## Current state

 - ObservableCollection
 - Select, Distinct, Where, OrderBy operators *mostly* ready

## License

[Apache License Version 2.0]

## Contributions

They're welcome - more to come

[nuget]: https://www.nuget.org/
[LINQ]: http://msdn.microsoft.com/en-us/library/bb397926.aspx
[Apache License Version 2.0]:https://github.com/TheFabFab/ObservableLinq/blob/master/License.txt
