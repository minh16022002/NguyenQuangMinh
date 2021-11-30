# BÁO CÁO VỀ MẪU THIẾT KẾ

## 1. GIỚI THIỆU:

### 1.1 Yêu cầu:

- Tìm các mẫu thiết kế trong mã nguồn của các dự án có trên 1000 sao trên github. 

- So sánh các mẫu tìm được với mẫu chuẩn của 23 mẫu thiết kế. 

- Viết báo cáo ở dạng file .md và nộp bằng pull request đến repo của giáo viên.

### 1.2 Các repo đã them khảo:
- [REPO_PATTERNLOCKVIEW](https://github.com/aritraroy/PatternLockView?fbclid=IwAR2Pg4eIPS8W2NUxNkU0bnueW8uWCbMEjOYuYU90euGqcMmc1WsAi7St5bU)
	*Repo của tác giả aritraroy với 2700 sao trên github*

- [REPO_CPPDESIGNPATTERN](https://github.com/liu-jianhao/Cpp-Design-Patterns?fbclid=IwAR1GkSRQBmd5q7f4AAvW8veAEl3oz39jhyf_BwHeiGKWkr1CVzy5Manv1Z8)
	*Repo của tác giả liu-jianhao với với 1000 sao trên github*

### 1.3 Thành viên nhóm (MSV - Họ và tên):

- 20021395 Nguyễn Quang Minh

- 20021387 Nguyễn Phúc Long

- 20021334 Đào Văn Đức

### 1.4 Repo của nhóm: 

https://github.com/minh16022002/NguyenQuangMinh

*Các thành viên nộp vào repo của nhóm, sau đó nhóm trưởng tổng hợp lại và gửi lên repo của giáo viên.*


## 2. BÁO CÁO:
*Sau khi tham khảo 2 repo trên, nhóm em tiến hành so sánh với các mẫu thiết kế:*

### 2.1 Nhóm các mẫu thiết kế Creational:
*Những Design pattern loại này cung cấp một giải pháp để tạo ra các object và che giấu được logic của việc tạo ra nó, thay vì tạo ra object một cách*

 *trực tiếp bằng cách sử dụng method new.* 
*Điều này giúp cho chương trình trở nên mềm dẻo hơn trong việc quyết định object nào cần được tạo ra trong những tình huống được đưa ra.*


#### 2.1.1 Abstract Factory: 

**Trong package ``com.andrognito.rxpatternlockview.events`` của repo số 1:**

*Đường dẫn: https://github.com/aritraroy/PatternLockView/tree/master/patternlockview-reactive/src/main/java/com/andrognito/rxpatternlockview/events*
	
Abstract class ``BasePatternLockEvent`` được kế thừa bởi các class sau:

```Java
class PatternLockCompleteEvent

class PatternLockCompoundEvent

class PatternLockProgressEvent 
```
**Trong package ``com.andrognito.rxpatternlockview.observables`` của repo số 1:**

*Đường dẫn: https://github.com/aritraroy/PatternLockView/tree/master/patternlockview-reactive/src/main/java/com/andrognito/rxpatternlockview/observables*

Abstract class ``BasePatternLockViewObservable`` được kế thừa bởi các class sau:

```Java
class PatternLockViewCompleteObservable

class PatternLockViewCompoundObservable

class PatternLockViewProgressObservable
```

Việc tạo ra những Super-factory này dùng để tạo ra các Factory tiếp theo rất giống với mẫu thiết kế Abstract Factory.

Trong Abstract Factory pattern, một interface có nhiệm vụ tạo ra một Factory của các object có liên quan tới nhau mà không cần phải chỉ ra trực tiếp các class của object. Mỗi Factory được tạo ra có thể tạo ra các object bằng phương pháp giống như Factory pattern.


#### 2.1.2 Singleton:

**Trong package ``com.andrognito.patternlockview.utils`` của repo số 1:**

*Đường dẫn: https://github.com/aritraroy/PatternLockView/tree/master/patternlockview/src/main/java/com/andrognito/patternlockview/utils*

*Mô tả: đảm bảo chỉ duy nhất một thể hiện (instance) được tạo ra và nó sẽ cung cấp cho bạn một method để có thể truy xuất được thể hiện duy nhất đó mọi lúc mọi nơi trong chương trình.*

Các lớp dưới đây đều chỉ có một thể hiện và chỉ cung cấp một method có thể truy xuất được thể hiện duy nhất đó

```Java
class PatternLockUtils
private PatternLockUtils() {
        throw new AssertionError("You can not instantiate this class. Use its static utility " +
                "methods instead");
    }
```

```Java
class RandomUtils
private RandomUtils() {
        throw new AssertionError("You can not instantiate this class. Use its static utility " +
                "methods instead");
    }
```

```Java
class ResourceUtils
private ResourceUtils() {
        throw new AssertionError("You can not instantiate this class. Use its static utility " +
                "methods instead");
    }
```
*Khác so với Singleton: Các class vẫn tồn tại những hàm ngoài luồng, dùng để xử lý ngoại lệ, đôi khi khó nhận biết*

#### 2.1.3 Builder:

#### 2.1.4 Factory Method:

#### 2.1.5 Prototype:

### 2.2 Nhóm các mẫu thiết kế Structural:

*Những Design pattern loại này liên quan tới class và các thành phần của object. Nó dùng để thiết lập, định nghĩa quan hệ giữa các đối tượng.*

#### 2.2.1 Adapter:

*Mô tả: Các interface không liên quan tới nhau có thể làm việc cùng nhau.*

**Adapter được thể hiện trong repo số 1:**

*Đường dẫn:https://github.com/aritraroy/PatternLockView/tree/master/patternlockview-reactive/src/main/java/com/andrognito/rxpatternlockview/observables*

Nhóm các class dưới đây tuy mang những chức năng khác nhau nhưng vẫn làm việc cùng nhau, kế thừa từ class ``io.reactivex.Observable``

```Java
class PatternLockViewCompleteObservable
```

```Java
class PatternLockViewCompoundObservable
```

```Java
class PatternLockViewProgressObservable
```

*Sau khi so sánh với mẫu thiết kế Adapter, nhóm mình thấy việc sử dụng mẫu thiết kế này khá phổ biến và có nhiều biến thể của chúng, chẳng hạn như việc các lớp có thể tuy cùng kế thừa từ một class, có mục đích sử dụng khác nhau, nhưng vẫn hoạt động và làm việc cùng nhau bình thường.* 

#### 2.2.2 Bridge Pattern:

#### 2.2.3 Composite Pattern:

#### 2.2.4 Decorator Pattern:

#### 2.2.5 Facade Pattern:

#### 2.2.6 Flyweight:

#### 2.2.7 Proxy:

### 2.3 Nhóm các mẫu thiết kế Behavioral: 

#### 2.3.1 Chain of responsibility:

#### 2.3.2 Command Pattern:

#### 2.3.3 Iterator Pattern:

#### 2.3.4 Mediator Pattern:

#### 2.3.5 Mementor:

#### 2.3.6 Observer Pattern:

#### 2.3.7 State Pattern:

#### 2.3.8 Strategy Pattern:

#### 2.3.9 Template Method Pattern:

#### 2.3.10 Visitor: 

## 3. KẾT LUẬN:

Sau khi tìm hiểu các mẫu thiết kế trong hai repo trên, nhóm chúng mình xin đưa ra những kết luận chung của bài báo cáo:

- Đa phần các mẫu thiết kế được sử dụng khá giống các mẫu thiết kế chuẩn, có sửa đổi linh hoạt để phù hợp với dự án.

- Lợi ích của việc vận dụng được các mẫu thiết kế vào dự án: 
	- Đơn giản hoá mã nguồn.
	- Giảm thời gian và công sức suy nghĩ các cách phân bố và cấu trúc chương trình.
	- Dễ dàng kiểm tra, nâng cấp mã nguồn.

Cảm ơn thầy và các bạn đã đọc và nhận xét. Phần báo cáo của nhóm mình còn nhiều thiếu sót, mong thầy và các bạn thông cảm.
