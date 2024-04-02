##  ZenS -  Coding convention for Ruby/Rails project

### Quy ước và Tiêu chuẩn cơ bản

1. **Thụt đầu dòng:** Sử dụng hai dấu cách cho mỗi cấp thụt. Không sử dụng tab.
  ```ruby
  # Bad
  def some_method
      # body
  end

  # Good
  def some_method
    # body
  end
```
2. **Độ dài dòng:**  Giữ cho độ dài dòng ít hơn 80 ký tự. Nếu cần, phân chia dòng dài bằng cách thụt hai dấu cách bên trong khối.

```ruby
# Bad
long_variable_name = some_method_that_has_a_really_long_name_and_it_should_be_broken_up(
  parameter1, parameter2, parameter3, parameter4
)

# Good
long_variable_name = some_method_that_has_a_really_long_name_and_it_should_be_broken_up(
  parameter1,
  parameter2,
  parameter3,
  parameter4
)

```

3. **Quy tắc đặt tên:**
- Biến và tên phương thức: Sử dụng snake_case cho biến và tên phương thức.
- Class và module: Sử dụng CamelCase (hoặc PascalCase) cho tên lớp và module.
- Hằng số: Sử dụng SCREAMING_SNAKE_CASE cho hằng số.

```ruby
# Bad
somevariable = 10

def SomeMethod
end

CONSTANT_VALUE = "Hello"

# Good
some_variable = 10

def some_method
end

CONSTANT_VALUE = "Hello"

```
4. **Định nghĩa phương thức:** Sử dụng dấu ngoặc đơn cho việc định nghĩa phương thức khi có tham số. Bỏ dấu ngoặc đơn khi phương thức không có tham số.

```ruby
# Bad
def some_method ()
  # body
end

# Good
def some_method
  # body
end

```
5. **Khoảng trắng:**
- Sử dụng dấu cách xung quanh các toán tử (+, -, *, /, v.v.) và sau dấu phẩy.
- Sử dụng một dấu cách sau mỗi dấu phẩy, không có dấu cách trước dấu phẩy.
```ruby
# Bad
result = value+10

# Good
result = value + 10

```
6. **Chuỗi ký tự:** Ưu tiên sử dụng dấu nháy đơn (') trừ khi bạn cần nội suy chuỗi hoặc ký tự đặc biệt.

```ruby
# Bad
string = "This is a #{variable} string"

# Good
string = 'This is a #{variable} string'

```
7. **Bình luận:** Viết bình luận để giải thích các đoạn mã phức tạp hoặc lý do quyết định nhất định

```ruby
# Bad
x = x + 1 # increment x by 1

# Good
x = x + 1 # Increment x by 1 to indicate the next element

```
8. **Phân biệt class method và instance method:** Phân biệt phương thức lớp và phương thức thể hiện bằng cách thêm từ khóa self. vào phương thức lớp.

```ruby
class MyClass
  def self.class_method
    # body
  end

  def instance_method
    # body
  end
end

```
9. **Sử dụng self khi cần:** Sử dụng `self` để tham chiếu đến biến hoặc phương thức của lớp từ bên trong phương thức của lớp.

```ruby
class MyClass
  def initialize(value)
    @value = value
  end

  def print_value
    puts self.value
  end

  private

  def value
    @value
  end
end

```
10. **Sử dụng attr_ method hoặc attr_accessor:** Để tạo các getter và setter method, sử dụng `attr_reader`, `attr_writer`, hoặc `attr_accessor`.

```ruby
class MyClass
  attr_reader :value   # Getter method

  def initialize(value)
    @value = value
  end
end

```
11. **Phương thức trả về Boolean phải kết thúc bằng ?:** Các phương thức trả về giá trị Boolean nên kết thúc bằng dấu ?.

```ruby
def valid?
  # body
end

```
12. **Phương thức thay đổi trạng thái hoặc lần lượt nên kết thúc bằng !::** Các phương thức thay đổi trạng thái hoặc thực hiện thao tác lần lượt trên đối tượng nên kết thúc bằng dấu !.

```ruby
array = [1, 2, 3]
array.reverse!   # This modifies the original array
```
13. **Sử dụng do...end cho khối lớn hơn ba dòng:** Sử dụng `do...end` cho khối lớn hơn ba dòng

```ruby
5.times do |i|
  puts "This is iteration number #{i}."
end

```
14. **Sử dụng each thay vì for:** Sử dụng each để lặp qua một mảng hoặc bất kỳ loại dữ liệu nào khác thay vì for.

```ruby
array = [1, 2, 3]
array.each do |item|
  puts item
end

```
15. **Sử dụng && và || thay vì and và or khi có thể: && và || :** có mức độ ưu tiên cao hơn so với and và or, vì vậy nên ưu tiên sử dụng chúng để tránh các hiểu lầm.

```ruby
# Bad
if a > 5 and b < 10
  # body
end

# Good
if a > 5 && b < 10
  # body
end

```
16. **Sử dụng case khi có nhiều lựa chọn:** Sử dụng cấu trúc case khi cần kiểm tra nhiều trường hợp cho một biến.

```ruby
case value
when 'a'
  puts 'Value is a'
when 'b'
  puts 'Value is b'
else
  puts 'Value is neither a nor b'
end

```
17. **Sử dụng ký tự _ cho tham số không sử dụng :** Khi bạn không cần sử dụng tham số trong một khối, hãy sử dụng dấu gạch dưới _ để biểu thị rằng tham số đó không được sử dụng.

```ruby
5.times do |_
  puts "Hello"
end

```
18. **Sử dụng nil? thay vì so sánh với nil:** Sử dụng phương thức nil? để kiểm tra xem một biến có phải là nil hay không.

```ruby
# Bad
if variable == nil
  puts "Variable is nil"
end

# Good
if variable.nil?
  puts "Variable is nil"
end

```
19. **Sử dụng yield với khối tham số:** Khi viết một phương thức có khối, hãy sử dụng yield để gọi khối đó.

```ruby
def my_method
  puts "Start of method"
  yield if block_given?
  puts "End of method"
end

my_method do
  puts "Inside block"
end
```
20. **Sử dụng private và protected để giới hạn phạm vi truy cập:** Sử dụng private để giới hạn truy cập vào các phương thức chỉ được gọi từ bên trong cùng một đối tượng. Sử dụng protected để cho phép truy cập từ bên trong cùng một lớp hoặc từ các lớp con.

```ruby
class MyClass
  def public_method
    # body
  end

  private

  def private_method
    # body
  end

  protected

  def protected_method
    # body
  end
end

```
21. **Sử dụng freeze để bảo vệ đối tượng khỏi thay đổi:** Sử dụng freeze để ngăn chặn đối tượng từ việc thay đổi bên trong chương trình.

```ruby
MY_CONSTANT = "value".freeze

```
22. **Sử dụng super để gọi phương thức cha:** Khi viết một phương thức trong lớp con, sử dụng super để gọi phương thức của lớp cha.

```ruby
class ParentClass
  def some_method
    puts "Parent method"
  end
end

class ChildClass < ParentClass
  def some_method
    super
    puts "Child method"
  end
end

```
23. **Sử dụng next thay vì continue trong vòng lặp:** Sử dụng next thay vì continue trong vòng lặp

```ruby
# Bad
for i in 0..5
  continue if i == 2
  puts i
end

# Good
for i in 0..5
  next if i == 2
  puts i
end

```
24. **Sử dụng retry cẩn thận: :** Sử dụng retry cẩn thận, vì nó có thể dẫn đến vòng lặp vô hạn.

```ruby
def do_something
  attempts = 0
  begin
    # Do something that might fail
  rescue
    attempts += 1
    retry if attempts < 3
  end
end

```
25. ** Sử dụng unless cho điều kiện phủ định:** Sử dụng unless khi bạn muốn kiểm tra một điều kiện phủ định thay vì if not hoặc if !.

```ruby
# Bad
if !condition
  # body
end

# Good
unless condition
  # body
end

```
26. **Tách biệt dòng giữa các phương thức:** Sử dụng một dòng trống để tách biệt giữa các phương thức trong một class.

```ruby
class MyClass
  def method1
    # body
  end

  def method2
    # body
  end
end

```
27. **Sử dụng require_relative cho các tệp cục bộ:** Sử dụng require_relative thay vì require khi yêu cầu các tệp cục bộ trong cùng thư mục hoặc thư mục con.

```ruby
require_relative 'helper'
```
28. **Tránh sử dụng unless...else:** Tránh sử dụng unless...else để tăng tính rõ ràng và dễ đọc của mã.

```ruby
# Bad
unless condition
  # body
else
  # body
end

# Good
if condition
  # body
else
  # body
end

```
29. **Sử dụng return một cách rõ ràng:** Khi một phương thức kết thúc sớm, sử dụng return một cách rõ ràng thay vì dựa vào giá trị cuối cùng của biểu thức.

```ruby
def calculate_something(value)
  return 0 if value.zero?
  # Calculate something based on value
end

```

30. **Sử dụng %() cho chuỗi tạo nhanh với dấu ngoặc đơn:** Thay vì sử dụng dấu ngoặc kép ("") cho chuỗi tạo nhanh có chứa ký tự đặc biệt, bạn có thể sử dụng %() để tránh việc cần escape các ký tự đặc biệt.

```ruby
# Bad
string = "This is a \"quoted\" string"

# Good
string = %q(This is a "quoted" string)
```

31. **Sử dụng defined?:** Sử dụng defined? để kiểm tra xem một biến hoặc phương thức có tồn tại không.

```ruby
if defined?(my_variable)
  puts "my_variable is defined"
end

```
32. **Sử dụng case với multiple when conditions:**  Trong cấu trúc case, bạn có thể sử dụng multiple when conditions bằng cách liệt kê chúng trên cùng một dòng.

```ruby
case value
when 'a', 'b', 'c'
  puts 'Value is a, b, or c'
when 'd'
  puts 'Value is d'
else
  puts 'Value is something else'
end

```
33. **Sử dụng one-line if/unless khi thích hợp:** Đối với điều kiện ngắn, bạn có thể sử dụng one-line if/unless.

```ruby
puts "Valid" if condition

puts "Invalid" unless condition

```
34. **Sử dụng times cho vòng lặp đếm:**  Đối với vòng lặp có số lần lặp xác định, sử dụng phương thức times.

```ruby
5.times do |i|
  puts "Iteration #{i}"
end

```
35. **Sử dụng each_with_index để lặp qua mảng và lấy chỉ số:** Để lặp qua mảng và lấy chỉ số của mỗi phần tử, sử dụng each_with_index.

```ruby
array.each_with_index do |value, index|
  puts "Value at index #{index} is #{value}"
end

```
36. **Sử dụng sort_by cho sắp xếp linh hoạt:** Thay vì sử dụng sort mặc định, hãy sử dụng sort_by khi bạn muốn sắp xếp theo một tiêu chí cụ thể.

```ruby
sorted_array = array.sort_by { |item| item.downcase }

```
37. **Tách biệt phần tạo và gán của biến:** Khi tạo một biến và gán giá trị cho nó, hãy tách biệt phần tạo và gán bằng dấu bằng.

```ruby
variable = nil
variable = calculate_value

```
38. **Sử dụng Ruby's Enumerable methods cho thao tác trên mảng:** Thay vì sử dụng vòng lặp, hãy sử dụng các phương thức Enumerable như map, select, reject, reduce, v.v. để thao tác trên mảng một cách mạch lạc và rõ ràng hơn.

```ruby
doubled_array = array.map { |item| item * 2 }

selected_items = array.select { |item| item > 5 }
```
39. **Sử dụng File.open với block cho mở tệp và tự động đóng:** Khi mở một tệp, sử dụng File.open với block để tự động đóng tệp sau khi hoàn thành công việc.

```ruby
File.open('file.txt', 'r') do |file|
  # Do something with the file
end
```

40. **Sử dụng <<~ cho heredocs đa dòng:** Sử dụng <<~ để tạo heredocs đa dòng mà không cần thụt lề.

```ruby
# Bad
string = <<-EOS
    This is a multiline
    string with indentation.
EOS

# Good
string = <<~EOS
    This is a multiline
    string without indentation.
EOS

```
41. **Sử dụng raise để ném ngoại lệ:** Sử dụng raise để ném ngoại lệ thay vì fail hoặc throw.

```ruby
raise ArgumentError, "Invalid argument" if argument.nil?

```
42. **Sử dụng catch và throw cho luồng điều khiển đặc biệt:** Sử dụng catch và throw khi cần thoát khỏi nhiều cấp độ của luồng điều khiển.

```ruby
catch :done do
  5.times do |i|
    throw :done if i == 2
    puts i
  end
end

```
43. **Sử dụng tap cho các phương thức trả về self:**  Sử dụng tap khi bạn muốn liên tiếp gọi phương thức và vẫn trả về đối tượng gốc.

```ruby
user = User.new.tap do |u|
  u.name = "John"
  u.age = 30
end

```
44. **Sử dụng ! cho phương thức không an toàn:** Khi một phương thức có thể thay đổi trạng thái của đối tượng gọi, hãy thêm dấu ! vào cuối tên phương thức.

```ruby
array.sort!   # Modifies the original array

```
45. **Sử dụng Kernel#sprintf hoặc % để format chuỗi:** Thay vì sử dụng String#% để format chuỗi, hãy sử dụng Kernel#sprintf hoặc %.

```ruby
formatted_string = sprintf("Hello, %s!", name)

```
40. **:**

```ruby
```