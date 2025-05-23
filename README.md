For_reddit  
 Let's start with functions first because they are essential.

●Instead of writing normal functions, lambda functions that take up less space can be written. for example,

```dart
// Normal function

int collect(int a, int b) {
return a + b;
}
```

```dart
// Lambda function

int collect(int a, int b) => a + b;
```

So what if my function is more complicated than that? Example,

```dart
// Normal version

List evenNumbers(List numbers) {
  var results= [];
  for (var number in numbers) {
    if (number% 2 == 0) {
      result.add(number);
    }
  }
  return result;
}
```

```dart
// lambda version

List evenNumbers(List numbers) => [for (var number in numbers if (number % 2 == 0) number];
```

●Yes,now I am explaining the second most common problem in dart code class structures

With Widget used to The extension method can be used because it is useful when adding helper methods to an existing Class. Use with widgets

```dart
//No-extension version

class WidgetUtils {
  static Widget withPadding(Widget child, EdgeInsets padding) {
    return Padding(
      padding: padding,
      child: child,
    );
  }

  static Widget withMargin(Widget child, EdgeInsets margin) {
    return Container(
      margin: margin,
      child: child,
    );
  }
}
```

```dart
//usage

final widget = WidgetUtils.withPadding(
  WidgetUtils.withMargin(
    Text('Hello'),
    EdgeInsets.all(8),
  ),
  EdgeInsets.all(16),
);
```

```dart
//with extansion version

extension WidgetExtensions on Widget {
  Widget padding(EdgeInsets padding) => Padding(
    padding: padding,
    child: this,
  );

  Widget margin(EdgeInsets margin) => Container(
    margin: margin,
    child: this,
  );
}
```

```dart
// usage

final widget = Text('Hello')
  .margin(EdgeInsets.all(8))
  .padding(EdgeInsets.all(16));
```

```dart
//Creating widgets with methods

class HomePage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: _buildAppBar(),
      body: _buildBody(),
      bottomNavigationBar: _buildBottomNav(),
    );
  }

  AppBar _buildAppBar() {
    return AppBar(
      title: Text('Home Page'),
      actions: [
        IconButton(icon: Icon(Icons.search), onPressed: () {}),
      ],
    );
  }

  Widget _buildBody() {
    return Column(
      children: [
        _buildHeader(),
        _buildContent(),
      ],
    );
  }
}
```

I hope it will be useful for you
