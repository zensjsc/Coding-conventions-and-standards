##  ZenS -  Coding convention for Flutter project
This template is primarily based on Flutter default lint, known as flutter_lint. Always remember to use a code formatter when coding.

------------


#### Naming convention
- Camel case for public field
- Camel case with underscord prefix for privated field
```dart
int totalCount = 0; // public field
int _currentCount = 0; // private field
```
- Classes, Enums, Typedefs, Extensions use Upper Camel Case
```dart
class Student{...}
enum SortType{...}
typedef Predicate<T> = bool Function(T value);
```
- Interface (abstract class) must start with "i" prefix
```dart
abstract class IRepository {...}
```
- Folder and file name use snake case: Eg: home_screen.dart, home_feat, ...

------------


#### Variable - Method declaration
- Avoid using 'dynamic' or  'object' as much as possible. Use a specific type instead
```dart
// Bad
Future<dynamic> fetchAllData() async {
	dynamic response = await ApiService.fetchData();
	return response;
}
// Good
Future<Response> fetchAllData() async {
	Response response = await ApiService.fetchData();
	return response;
}
```
- Prefer Singletons or static classes instead of global variables
- Variable and method names should be clear, concise, and self-explanatory, avoiding ambiguity

------------

#### Coding style
- Always use commas after each field or widget in the widget tree. This practice enhances code readability and makes code formatting more aesthetically pleasing
```dart
// Bad
Container(
      child: Text("I'm pretty",
          style: TextStyle(color: Colors.black)),
    )
// Good
Container(
      child: Text(
        "I'm pretty",
        style: TextStyle(
          color: Colors.black,
        ),
      ),
    )
```
- Split large widgets into smaller pieces. This practice improves code organization, enhances readability, and promotes reusability
- Prefer using widget classes over helper methods when splitting code
- Use 'const' for widgets, 'final' for fields wherever possible. Follow the immutability concept of Flutter-Dart
- Avoid using the bang operator '!', instead use the nullable operator '?' when accessing fields of nullable field
```dart
// Bad
 var name = student!.name; // may cause null pointer exception
// Good
var name = student?.name; // this can return null
```
- Use case cade operator for faster and shorter
```dart
// Don't
var path = Path();
path.lineTo(0, size.height);
path.lineTo(size.width, size.height);
path.lineTo(size.width, 0);
path.close();
// Do
var path = Path()
..lineTo(0, size.height)
..lineTo(size.width, size.height)
..lineTo(size.width, 0)
..close();
```
- Use spread operator
```dart
// Bad
var list1 = [];
list1.addAll(list2);
list1.addAll(list3);
// Good
var list1 = [...list2, ...list3];
```
- Use callback functions like this if available
```dart
// Bad
GestureDetector(
	onTap: () => controller.onButtonTap(),
),
TextField(
	onChanged: (val) {
	controller.onTextChanged(val),
	},
),
// Good
GestureDetector(
	onTap: controller.onButtonTap,
),
TextField(
	onChanged: controller.onTextChanged,
),
```

------------
#### Formatting
- 1 tab length = 2 space
- Line length = 100 (where code should be wrapped)
- Use relative import instead of absolute import
