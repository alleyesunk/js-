# js-
JavaScript基础学习笔记总结

* name: 铭心 
* time: 2021/3/11
* 该内容所有代码均可在控制台进行输出查看结果:wink:
* 该内容将持续更新
* 如果对您有帮助的话！还请给个star鼓励一下♥


<p href="#while-循环">循环</p>




三目运算符
--
```javascript
    var temperture = 10;
    console.log(temperture > 15 ? '出门' : '在家')
    var temperture = 16;
    console.log(temperture > 15 ? '出门' : '在家')
```
代码块
--
```javascript
    {
        var name = '铭心';
        console.log(name);

        let age = 15;
        console.log(age)

        const YEAR = 2020;
        console.log(YEAR);
    }
    console.log(name);
    //不可调用
    console.log(age);
    console.log(YEAR);
```
if ... else
---
```javascript
    var passcode = prompt('请输入暗号')
    if (passcode === '天王盖地虎') {
        alert('登录成功')
    } else {
        alert('登录失败')
    }
```
if ... else if ... else
--
```javascript
    var role = prompt("请输入用户权限")；
    if (role === "超级管理员") {
        alert("进入超级管理员界面")；
    } else if (role === "管理员") {
        alert("进入管理员界面");
    } else {
        alert("进入用户界面")
    };
```
switch case
--
```javascript
    var role = prompt("请输入用户权限")；
    switch (role) {
        case "超级管理":
            alert('超级管理员页面')
            break;
        case "管理员":
            alert('管理员');
            break;
        case "特殊用户":
            alert('特殊用户页面');
            break;
        case "一般用户":
            alert('一般用户页面');
            break;
        default:
            alert("跳转到其他页面")
    };
```
while 循环
--
```javascript
    var password = "";
    while (password !== '123456') {
        password = prompt("请输入密码");
    };
    console.log('登录成功');
```
do while 循环
--
```javascript
    var x = 5;
    do {
        console.log(x++)
    } while (x > 5 && x <= 10)
    console.log(x)
```
for 循环
--
```javascript
    for (var i = 0; i <= 10; i++) {
        console.log(i);
    };
    
    var j = 0;
    while (j < 10) {
        console.log(j);
        j++;
    };
    
```
break 和 continue
--
```javascript
    for (let i = 0; i < 10; i++) {
        if (i === 5) {
            continue; // 跳过5
        }
        console.log(i);
    }
    
    for (let i = 0; i < 10; i++) {
        if (i === 5) {
            break; // i = 5 停止循环
        }
        console.log(i);
    }

    function putInRefrigerator() {
        console.log("打开冰箱们");
        console.log('把大象放进去');
        console.log('关上冰箱们');
    }
```
函数 —— 声明函数
--
```javascript
    function putAnythingInRefrigerator(something) {
        console.log('打开冰箱们');
        console.log('把' + something + '放进去');
        console.log('关上冰箱们');
    }

    function add(a, b) {
        return a + b;
    }

    function testNum(num) {
        if (num < 0) return;
        return num > 10;
    }
```    
函数 —— 调用函数
--
```javascript
    putInRefrigerator();
    putAnythingInRefrigerator("兔子");
    add(1, 2);
    console.log(add(1, 2))

    var result = add(1, 2);
    console.log(result);

    console.log(add(result, 5));

    console.log(testNum(-5));
    console.log(testNum(15));
 ```   

函数 —— 函表达式
--
```javascript
    add = 5
    var plus = add;

    var multiply = function (a, b) {
        return a * b;
    }
    console.log(multiply(plus, 5));
```
函数 —— 变量和函数提升(hoisting)
--
```javascript
    x = 5;
    console.log(x);
    var x = 10;
    console.log(divide(8, 2))
    function (divide(8, 2)) {
        renturn a/b
    }
```
函数 —— 默认参数
--
```javascript
    function greetings(name = "铭心") {
    console.log('你好' + name);
    }

    greetings();
    greetings('张三')

    function greetingWithWeather(name = '铭心', weather) {
        console.log("你好," + name + "今天是：" + weather)
    }

    greetingWithWeather(undefined, "晴天");
```
函数 —— 递归
--
```javascript
    function sum(n) {
    if (n === 1) {
        return 1;
    }
    return n + sum(n - 1)
    }
    console.log(sum(5));
   
    //1 1 2 3 5 8 13 ...
    function fib(num) {
        if (num <= 1) {
            return 1;
        }
        return fib(num - 1) + fib(num - 2);
    }

    console.log(fib(7))
    
```
函数 —— arguments
--
```javascript
    function log() {
        for (let i = 0; i < arguments.length; i++) {
            console.log(arguments[i]);
        }
    }
    log('abc', 'cba', 'dee')
```
函数 —— 作用域
--
```javascript
    var x = 5;
    function add(a) {
        var y = 10;
        console.log("y=" + y)
        return a + x;
    };
    console.log(add(10))

    var num = 100;

    function multiply(num) {
        return num * 10;
    }

    console.log(multiply(23))

    console.log(add(20))
```
函数 —— var / let 区别
--
```javascript
    var z = 6;
    if (z > 2) {
        console.log(z);
        var innerZ = 17;
    }
    
    console.log(innerZ);
    
    for (let i = 0; i < 10; i++) {
        console.log(i)
    }
    // 不可调用
    console.log(i);
```
函数 —— 箭头函数
--
```javascript

    var greeting = (name, weather) => {
        console.log("hello" + name + "今天是：" + weather)
    };

    greeting("铭心", "晴天");

    var increment = x => x + 1;
    console.log(increment(4));
```
函数 —— 闭包
--
```javascript
    function squareSum(a, b) {
        function square(x) {
            return x * x;
        }
        return square(a) + square(b);
    }
    
    console.log(squareSum(5,6));
    
    function person() {
        let name = "铭心";
        function getName() {
            return name;
        }
        return getName;
    }
    
    var getName = person();
    console.log(getName);
    console.log(getName());
    console.log(person);
    console.log(person());
```
函数 —— 柯里化
--
```javascript
    function addThreeNums(a, b, c) {
        return a + b + c;
    }

    console.log(addThreeNums(1, 2, 3));

    function addThreeNumsCurry(a) {
        return function (b) {
            return function (c) {
                return a + b + c;
            }
        }
    }

    console.log(addThreeNumsCurry(1)(2)(3));

    var fixedTwo = addThreeNumsCurry(1)(2);
    console.log(fixedTwo(4));
    console.log(fixedTwo(5));
    console.log(fixedTwo(6));
```    
函数 —— 自执行函数
--
```javascript
    var num1 = 10;

    (function () {
        var num1 = 20;
        console.log(num1);
    })();

    console.log(num1)
```
函数 —— 回调函数
--
```javascript
    function request(cb) {
        console.log("请求数据");
        cb();
        console.log("请求结束");
    }

    function callback() {
        console.log("执行回调")
        console.log("执行结果：" + result);
    }

    request(results => {
        console.log("执行回调")
        console.log("回调结果：铭心")
    })
```    
数组
--
```javascript
    var arr1 = [1, 2, 3];
    console.log(arr1);
    var arr2 = new Array(4, 5, 6);
    console.log(arr2);
    var arr3 = Array(7, 8, 9);
    console.log(arr3);
    var arr4 = Array.of(10, 11, 12);
    console.log(arr4);

    var arrSingle = Array(6);
    console.log(arrSingle);
    var arrSingle2 = new Array(7);
    console.log(arrSingle2);
    var arrSingle3 = Array.of(4);
    console.log(arrSingle3);
    var arrSingle4 = [0];
    console.log(arrSingle4);
```
访问数组
--
```javascript
    var arr = [1, 2, 3];

    console.log(arr.length);
    console.log(arr[0]);
    console.log(arr[1]);
    console.log(arr[2]);

    console.log(arr[3]); //undefined
```    
添加元素
--
```javascript
    var arr = [1, 2, 3];
    
    arr[0] = 4;
    console.log(arr);
    arr[3] = 5;
    console.log(arr);

    arr[8] = 9;
    console.log(arr);
    console.log(arr[7]);
```    
删除元素
--
```javascript
    var arr = [3, 4, 5];
    arr.length = 2;
    console.log(arr); // [3， 4]
    arr.length = 0;
    console.log(arr); // 空数组
    
    var arr = [1, 2, 3, 4, 5, 6];

    arr.splice(2, 1);
    console.log(arr);

    arr.splice(1, 2, 3, 7, 8);
    console.log(arr);

    arr.splice(1, 0, 9, 10);
    console.log(arr);
```
数组遍历
--
```javascript
    var arr = [1, 3, 5, 7, 9];
    for (let i = 0; i < arr.length; i++) {
        console.log(arr[i]);
    }

    console.log('for....of');
    for (let ele of arr) {
        console.log(ele);
    }

    arr.forEach((ele, index, self) => {
        console.log(ele, index, self);
    })
    
```
栈模式
--
```javascript
    var stack = [1, 2, 3];
    stack.push(4);
    console.log(stack);
    
    stack.push(5, 6, 7);
    console.log(stack);

    var last = stack.pop();
    console.log(last);
    console.log(stack);

    console.log(stack[stack.length - 4]);
```
队列模式
--
```javascript
    var queue = [1, 2, 3];
    queue.push(4, 5, 6);
    console.log(queue);
    
    var first = queue.shift();
    console.log(first);
    console.log(queue);
    
    queue.unshift(10, 11, 12);
    console.log(queue);
```

反转数组
--
```javascript
    var arr = [1, 2, 3];
    console.log(arr.reverse());
    console.log(arr);
    
    console.log(
    "hello"
        .split('')
        .reverse()
        .join('')
    )
    
```
数组排序
--
```javascript
    // 正序
    var arr = [1, 5, 3, 2, 4, 8, 6];
    arr.sort();
    console.log(arr);
    // 倒序
    arr.sort((a, b) => {
        if (a > b) {
            return -1;
        } else if (a < b) {
            return 1;
        } else {
            return;
        }
    })

    arr.sort((a, b) => b - a)

    console.log(arr)
```
数组链接
--
```javascript
    var arr1 = [1, 2, 3];
    var arr2 = [4, 5, 6];
    console.log(arr1.concat(arr2))
```
数组裁切
--
```javascript
    var arr = [1, 2, 3, 4, 5, 6];
    console.log(arr.slice(1, 2))
```

数组map
--
```javascript
    var arr = [1, 2, 3, 4, 5];
    var mappedArr = arr.map(ele => ele * 2);
    console.log(mappedArr);
    console.log(arr);
```

数组 reduce
--
```javascript
    var arr = [1, 2, 3, 4, 5];
    var result = arr.reduce((previous, current) => previous + current);
    console.log(result);
    
    var result2 = arr.reduce((first, second) => first + second);
    console.log(result2);
```

数组过滤
--
```javascript
    var arr = [1, 2, 3, 4, 5, 6];
    var filteredArr = arr.filter(item => item > 4);

    console.log(filteredArr);

```
数组测试
--
```javascript
    var arr = [1, 2, 3, 4, 5, 6]
    var result = arr.every(item => item > 2);
    console.log(result);

    var resultSum = arr.some(item => item > 5);
    console.log(resultSum)
```
destructuring 操作符
--
```javascript
    var arr = [1, 2, 3];
    var [a, b, c] = arr;
    console.log(a, b, c);

    var [d, e] = arr;
    console.log(d, e);

    var [, f] = arr;
    console.log(f);

    function multipleReturns() {
        let name = '铭心';
        let position = '前端工程师';

        return [name, position];
    }

    var [myName, myPosition] = multipleReturns();
    console.log(myName, myPosition);
```
rest 操作符
--
```javascript
    var arr = [1, 2, 3, 4, 5, 6, 7, 8];
    var [a, b, ...rest] = arr;
    console.log(a, b, rest);

    var [a, , b, ...rest] = arr;
    console.log(a, b, rest);

    function variousArgs(...args) {
        console.log(args);
    }

    variousArgs(1, 2, 3);
```
多维数组
--
```javascript
    var arr = [];
    for (let i = 0; i < 5; i++) {
        arr[i] = [];
        for (let j = 0; j < 4; j++) {
            arr[i][j] = i + j;
        }
    }

    console.log(arr);
```

创建对象
--
```javascript
    var employee = {
        name: '铭心',
        age: 21,
        position: '前端工程师',
        signIn: function () {
            console.log("铭心打卡成功");
        }
    };

    var employee2 = new Object();
    employee2.name = '张三';
    employee2.signIn = function () {
        console.log('张三打卡成功');
    };
```
对象属性
--
```javascript
    // 该段代码结合创建对象一同使用
    console.log(employee.name);
    console.log(employee["name"]);

    employee.name = '老板';
    console.log(employee.name);
    employee['name'] = '大王';
    console.log(employee['name']);

    console.log(employee2.age);
    employee2.age = 22;
    console.log(employee2.age);

    var employee3 = {
        name: '王五',
        birthDate: '2000-01-10',
    };

    console.log(employee3.name + '的生日是：' + employee3.birthDate);
```
省略key
--
```javascript
    var name = '铭心';
    var employee4 = {
        name,
        signIn() {
            console.log('铭心打卡成功')
        }
    };

    console.log(employee4.name);
    console.log(employee4.signIn());
```
遍历对象所有属性
--
```javascript
    console.log(Object.keys(employee));

    for (key in employee) {
        console.log(key);
    }
```
删除对象属性
--
```javascript
    delete employee.name;
    console.log(employee);
    console.log(Object.keys(employee));
```

构造函数
--
```javascript
    function Employee (name, position) {
         this.name = name;
         this.position = position;
     }

    var emp1 = new Employee("铭心", "前端工程师");
    console.log(emp1);

    var emp2 = new Employee("李四", "后端工程师");
    console.log(emp2);
```
this
--
```javascript
    var emp3 = {
        name: "李四",
        position: "后端工程师",
        SignIn() {
            console.log(this.name + "上班打卡")
        }
    };
    
    emp3.SignIn();
    
    emp3.goToWork = () => {
        console.log(this.name + "去上班");
    };
    emp3.goToWork();
    
    function Employee(name, position) {
        this.name = name;
        this.position = position;
        this.signIn = () => {
            console.log(this.name + "去上班");
        };
    }

    var emp4 = new Employee("铭心", "前端工程师");
    emp4.signIn();
```
getters 和 setters
--
```javascript
    var person = {
        firstName: '三',
        lastName: '张',
        get fullName() {
            return this.lastName + this.firstName;
        },
        set fullName(fullName) {
            let [lastName, firstName] = fullName.split(",");
            this.lastName = lastName;
            this.firstName = firstName;
        }
    };

    console.log(person.fullName);
    person.fullName = "李,四";
    console.log(person.fullName);
    console.log(person.lastName, person.firstName);
    
    function Employee2 (name, position) {
        this.name = name;
        this.position = position;
    }
    
    var emp5 = new Employee2("赵六", "前端工程师");
    Object.defineProperty(emp5, "info", {
        get: function() {
            return this.name + " " + this.position;
        },
        set: function(info) {
            let [name, position] = info.split(" ");
            this.name = name;
            this.position = position;
        }
    });
    
    console.log(emp5.info);
    emp5.info = "赵七 后端工程师";
    console.log(emp5.name);
    console.log(emp5.info);
```
原型
--
```javascript
    function Employee(name, position) {
        this.name = name;
        this.position = position;
        this.signIn = function () {
            console.log(this.name + "打卡");
        }
    };
    
    var emp1 = new Employee ('张三', '前端工程师');
    var emp2 = new Employee ('李四', "后端工程师");
    
    console.log(emp1);
    console.log(emp2);
    
    console.log(Employee.prototype);
    Employee.prototype.age = 20;
    
    console.log(emp1.age);
    console.log(emp2.age);
    
    Employee.prototype.printInfo = function () {
        console.log(this.name, this.age, this.position);
    }
    
    emp1.printInfo();
    emp2.printInfo();
    
    console.log(emp1.__proto__);
    console.log(Employee.prototype);
    console.log(emp1.__proto__ === Employee.prototype);
    console.log(Object.getPrototypeOf(emp1));
```
Object.create
--
```javascript
    //结合上段代码
    console.log(emp1);
    for (key in emp1) {
        console.log(key);
    }

    var manager = Object.create(emp1);
    console.log(manager);
    for (key in manager) {
        console.log(key);
    }

    console.log(manager, name);
    manager.name = "李四";
    manager.position = "经理";
    console.log(manager);
    manager.signIn();
    console.log(Object.getOwnPropertyNames(manager));
```
原型链
--
```javascript
    // 结合上段代码
    var protoOfManager = Object.getPrototypeOf(manager);
    console.log(protoOfManager);
    var protoOfEmp1 = Object.getPrototypeOf(protoOfManager);
    console.log(protoOfEmp1);
    var protoOfEmp = Object.getPrototypeOf(protoOfEmp1);
    console.log(protoOfEmp);
    var protoOfobj = Object.getPrototypeOf(protoOfEmp);
    console.log(protoOfobj);

    console.log(Object.getPrototypeOf(Object.prototype));

    console.log(manager.toString);
    console.log(manager.toString());
```
修改原型指向
--
```javascript
    // 结合上段代码

    function Manager() { };

    Manager.prototype.department = "技术部";

    Object.setPrototypeOf(manager, Manager.prototype);

    console.log(manager.department);
    console.log(Object.getPrototypeOf(manager));
    // console.log(manager.signIn())
    for (key in manager) {
        console.log(key);
    }
```
Spread 操作符
--
```javascript
    var post = {
        id: 1,
        title: "标题1",
        content: '这是内容'
    };
    
    console.log(post);
    
    var postClone = { ...post };
    console.log(postClone);
    console.log(post === postClone);
    
    var post2 = {
        ...post,
        author: "铭心"
    };
    console.log(post);
    
    var arr = [1, 2, 3];
    var arrClone = [ ...arr ];
    console.log(arrClone);
    
    var arr2 = [...arr, 4, 5, 6];
    console.log(arr2)
    function savePost(id, title, content) {
        console.log("保存了文章：" + id, title, content);
    }
    
    savePost(...[2, "标题", "内容"]);
```
destructuring & rest
--
```javascript
    var post = {
        id: 1,
        title: "标题",
        content: "内容",
        comments: null
    };
    
    var {id, title} = post;
    console.log(id, title);
    
    var { id, title: headline } = post;
    console.log(id, headline);
    
    var { id, title, comments = "没有评论" } = post;
    console.log(comments);

    var [a, b = 2] = [1];
    console.log(a, b);

    var post2 = {
        id: 2,
        title: "标题2",
        content: "这是内容",
        comments: [
            {
                userId: 1,
                comment: "评论1"
            },
            {
                userId: 2,
                comment: "评论2"
            },
            {
                userId: 3,
                comment: "评论3"
            }
        ]
    };

    var {
        comments: [, { comment }]
    } = post2;
    console.log(comment);

    function getId(idKey, obj) {
        let { [idKey]: id } = obj;
        return id;
    }
    console.log(getId("userId", { userId: 3 }));

    var { comments, ...rest } = post2;
    console.log(rest);

    function savePustObj({ id, title, content, ...rest }) {
        console.log("保存了文章：", id, title, content);
        console.log(rest);
    }

    savePustObj({ id: 4, title: "标题4", content: "内容4", author: "铭心" });

```

值传递与引用传递
--
```javascript
    function byReference(arr) {
        arr[0] = 5;
    }
    var array = [1, 2, 3];
    byReference(array);
    console.log(array);

    function byReferenceObj(obj) {
        obj.title = "标题标题";
    }

    var post = { id: 1, title: "标题" };
    byReferenceObj(post);
    console.log(post);

    function byReferenceStr(str) {
        str = "abc"
    }
    var testStr = "test";
    byReferenceStr(testStr);
    console.log(testStr);

    function byValue(num) {
        num = 10;
        console.log(num);
    }

    var testNum = 1;
    byValue(testNum);
    console.log(testNum);

```
call, apply 与 bind
--
```javascript
    var emp = {
        id: 1,
        name: "铭心"
    };

    function printInfo(dep1, dep2, dep3) {
        console.log("员工姓名：" + this.name, dep1, dep2, dep3);
    }

    printInfo.call(emp, "技术部", "IT事件部", "总裁办公室");
    printInfo.apply(emp, ["技术部", "IT事件部", "总裁办公室"]);

    var empPrintInfo = printInfo.bind(emp, "技术部", "IT事件部", "总裁办公室");
    empPrintInfo();
```
定义class
--
```javascript
    class Emplayee{
        constructor(name, position) {
            this.name = name;
            this.position = position;
        }
        
        signIn() {
            console.log(this.name + "打卡上班");
        }
        
        get info() {
            return this.name + " " + this.position;
        }
        
        set info(info) {
            let [name, position] = info.split(" ");
            this.name = name;
            this.position = position;
        }
    }
    
    var emp = new Emplayee("铭心", "前端工程师");
    console.log(emp)
    emp.signIn();
    console.log("职位：" + emp.position);

    console.log(emp.info);
    emp.info = "李四 后端";
    console.log(emp.info);
    console.log(emp.name, emp.position);

    class Manager extends Emplayee {
        constructor(name, position, dept) {
            super(name, position);
            this.dept = dept;
        }

        signIn() {
            super.signIn();
            console.log("额外信息： 经理打卡")
        }
    }

    var manager = new Manager("王五", "经理");
    console.log(manager);
    manager.signIn();

    manager.dept = "技术部";
    console.log(manager);

```

字符串-字符串定义与转义
--
```javascript
    var str = "hello!";
    console.log(str);
    
    var str2 = new String("你好");
    console.log(str2)
```
转义字符
--
```javascript
    str = '他说：\"我们出去玩吧!"';
    console.log(str)
    for (let i = 0; i < str.length; i++) {
        console.log(str.charAt(i))
    }

    for (let c of str) {
        console.log(c)
    }

```
裁切
--
```javascript
    var str = "This is a long string.....";

    console.log(str.slice(0, 4));
    console.log(str.slice(4));
    console.log(str.slice(0, -1));
    console.log(str.slice(-6, -1));
    console.log(str.slice(4, 1));

    console.log(str.substring(0, 4))
    console.log(str.substring(4));
    console.log(str.substring(0, -1));
    console.log(str.substring(-6, -1));
    console.log(str.substring(4, 1));
    
```
拼接
--
```javascript
    var str1 = "hello";
    var str2 = "word";

    console.log(str1 + str2);
    console.log(str1.concat(str2));
```
大小写
--
```javascript
    console.log(str.toUpperCase());
    console.log("WORD".toLocaleLowerCase());
```
去除空格
--
```javasscript
    var str = "  Hello  word";
    console.log(str.trim());
```
模板字符串
--
```javascript
    var longStr = `Lorem ipsun dolor sir amer 
    consoctetur adipisicing elit
    .Ques aliquam 
         laboriosam nist
                 cuoiditare eaque ratione labore,
      padit     iusto facere squi qued aliquid. 
      Expedita quas odio enim a consequunter.`;
    console.log(longStr);

    var name = "铭心";
    var str = `你好 ${name}`;
    console.log(str)

    function greeting(strings, gender) {
        let genderStr = "";
        if (gender === "M") {
            genderStr = "先生";
        } else if (gender === "F") {
            genderStr = "女士";
        }
        return `${strings[0]}${genderStr}`;
    }

    var gender = "M";
    var result = greeting`你好，铭心${gender}`;
    console.log(result);

```
创建正则表达式
--
```javascript
    var str = "where when what";
    var re = /wh/;
    var re2 = new RegExp('wh');
    
    // console.log(re.exec(str));
    // console.log(re.test(str));

    // console.log(re2.exec(str));
    // console.log(re2.test(str));

    console.log(re.exec(str));
    console.log(re.exec(str));
    console.log(re.exec(str));
```
字符匹配
--
```javascript
    var str = `This str contains 123
     CAPITALIZED letters and _-&^% symbols`;

    console.log(/T/.test(str));
    console.log(/This/.test(str));
    console.log(/Thiss/.test(str));
    console.log(/12/.test(str));
    console.log(/1234/.test(str));
    console.log(/_-&/.test(str));
```
特殊字符匹配
--
```javascript
    console.log(str.match(/Th.s/g));
    console.log(str.match(/1.3/g));
    console.log(str.match(/\d/g));
    console.log(str.match(/\w/g));
    console.log(str.match(/\s/g));
    console.log(str.match(/Th.s/g))
    console.log("你好".match(/\u4f60/g));
```
匹配次数
--
```javascript
    var str = `This str contains 123
     CAPITALIZED letters and _-&^% symbols`;

    console.log(str.match(/This.*/g));
    console.log(str.match(/T*/g));
    console.log(str.match(/t?/g));

    console.log(str.match(/t{2}/g));
    console.log(str.match(/\d{1,2}/g));
```
区间、逻辑和界定符
--
```javascript
    console.log(str.match(/[abc]/g));
    console.log(str.match(/[0-9]/g));
    console.log(str.match(/[\-_&\^]/g));

    console.log(str.match(/This|contains/g))
```
分组
--
```javascript
    var str = `this that this and that`;
    console.log(/(th).*(th)/.exec(str));

    var str = `aaaab abb cbbaa`;
    console.log(str.match(/(aa){2}/g));
```
常规正则表达式
--
```javascript
    var mobliLeRe = /^1[3-9]\d[9]/g;
    console.log(mobliLeRe.test("13123407839"));

    var emailRe = /^([a-zA-Z0-9_\-\.]+@([a_zA-Z0-9_\-\.]))/g;
    console.log(emailRe.test("admin@163.com"));
    console.log(emailRe.test("admin@163.coom"));
```
字符串替换
--
```javascript
    var str = "This 1is 2an 3apple";
    console.log(str.replace(/\d+/g, ""));

    var html = `<span>hello</span><div> world</div>`;
    console.log(html.replace(/<[^>]*>([^<>]*)<\/[^>]*>/g, "$1"));
```
正则-字符串分隔
--
```javascript
    var tags = "html, css, javascript";
    console.log(tags.split(", "));

    var str = "This | is , an & apple";
    console.log(str.split(/\W+/g));
```
内置对象 —— number
--
```javascript
    var strNum = "15";
    var num = Number.parseInt(strNum);

    console.log(strNum);
    console.log(num);
    console.log(typeof num);

    var strNum = "12.34";
    var num = parseInt(strNum);

    console.log(typeof num);

    var strNum = "abc";
    var num = parseInt(strNum);

    console.log(num);
    console.log(isNaN(num));

    var num = 12.33645;
    var numStr = num.toFixed(2);
    console.log(numStr);

    console.log(Number.MAX_SAFE_INTEGER);
    console.log(Number.POSITIVE_INFINITY);
    console.log(Number.NEGATIVE_INFINITY);
```
Math
--
```javascript
    console.log(Math.PI);
    console.log(Math.abs(-1));
    console.log(Math.sin(Math.PI / 2));
    console.log(Math.floor(3.98));
    console.log(Math.ceil(3.1));
    console.log(Math.pow(10, 3));
    console.log(Math.trunc(2.645));
    console.log(Math.random());
```
Date
--
```javascript
    console.clear();
    var date = new Date();
    console.log(date);
    console.log(date.getFullYear());
    console.log(date.getMonth());
    console.log(date.getDay());
    console.log(date.getDate());
    console.log(date.getHours());
    console.log(date.getMinutes());
    console.log(date.getSeconds());
    console.log(date.getTime());
    console.log(date.toDateString());
    console.log(date.toLocaleDateString())

    date.setFullYear(2022);
    console.log(date.toLocaleDateString());
    date.setTime(15881231419);
    console.log(date.toLocaleDateString()); 
```
JSON
--
```javascript
    var postJSON = `{
        "id": 1,
        "title": "标题",
        "comments": [
            {
                "userId": 1,
                "comment": "评论1"
            },{
                "userId": 2,
                "comment": "评论2"
            }
        ],
        "published": true,
        "author": null
    }`;

    console.log(JSON.parse(postJSON));

    var person = {
        id: 1,
        name: "铭心",
        skills: ["React", "Java"]
    };

    console.log(person);
    console.log(JSON.stringify(person, null, 2));

    var comments = `[
            {
                "userId": 1,
                "comment": "评论1"
            },{
                "userId": 2,
                "comment": "评论2"
            }
        ]`

    console.log(JSON.parse(comments));
```
set
--
```javascript
    var set = new Set();
    set.add(1);
    set.add(3);
    set.add(6);

    console.log(set);

    set.add(3);
    console.log(set);

    console.log(set.has(4));

    set.forEach(value => {
        console.log(value)
    });

    set.delete(3);
    console.log(set);

    set.clear();
    console.log(set);

    var obj1 = { id: 1 };
    var obj2 = { id: 1 };
    set.add(obj1);
    set.add(obj2);
    console.log(set);

    set.add(obj1);
    console.log(set);
```
