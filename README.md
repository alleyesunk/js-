# js-
JavaScript基础学习笔记总结

* name: 铭心 
* time: 2021/3/11
* 持续更新

三目运算符
--
    var temperture = 10;
    console.log(temperture > 15 ? '出门' : '在家')
    var temperture = 16;
    console.log(temperture > 15 ? '出门' : '在家')
代码块
--
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
if ... else
---
    var passcode = prompt('请输入暗号')
    if (passcode === '天王盖地虎') {
        alert('登录成功')
    } else {
        alert('登录失败')
    }
if ... else if ... else
--
    var role = prompt("请输入用户权限")；
    if (role === "超级管理员") {
        alert("进入超级管理员界面")；
    } else if (role === "管理员") {
        alert("进入管理员界面");
    } else {
        alert("进入用户界面")
    };
switch case
--
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
while 循环
--
    var password = "";
    while (password !== '123456') {
        password = prompt("请输入密码");
    };
    console.log('登录成功');
do while 循环
--
    var x = 5;
    do {
        console.log(x++)
    } while (x > 5 && x <= 10)
    console.log(x)
for 循环
--
    for (var i = 0; i <= 10; i++) {
        console.log(i);
    };
    
    var j = 0;
    while (j < 10) {
        console.log(j);
        j++;
    };
    
break 和 continue
--
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
函数 —— 声明函数
--
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
    
函数 —— 调用函数
--
    putInRefrigerator();
    putAnythingInRefrigerator("兔子");
    add(1, 2);
    console.log(add(1, 2))

    var result = add(1, 2);
    console.log(result);

    console.log(add(result, 5));

    console.log(testNum(-5));
    console.log(testNum(15));
    

函数 —— 函表达式
--
    add = 5
    var plus = add;

    var multiply = function (a, b) {
        return a * b;
    }
    console.log(multiply(plus, 5));
函数 —— 变量和函数提升(hoisting)
--
    x = 5;
    console.log(x);
    var x = 10;
    console.log(divide(8, 2))
    function (divide(8, 2)) {
        renturn a/b
    }
函数 —— 默认参数
--
    function greetings(name = "铭心") {
    console.log('你好' + name);
    }

    greetings();
    greetings('张三')

    function greetingWithWeather(name = '铭心', weather) {
        console.log("你好," + name + "今天是：" + weather)
    }

    greetingWithWeather(undefined, "晴天");

函数 —— 递归
--
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
    
函数 —— arguments
--
    function log() {
        for (let i = 0; i < arguments.length; i++) {
            console.log(arguments[i]);
        }
    }
    log('abc', 'cba', 'dee')
函数 —— 作用域
--
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
函数 —— var / let 区别
--
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
函数 —— 箭头函数
--

    var greeting = (name, weather) => {
        console.log("hello" + name + "今天是：" + weather)
    };

    greeting("铭心", "晴天");

    var increment = x => x + 1;
    console.log(increment(4));
函数 —— 闭包
--
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
函数 —— 柯里化
--
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
    
函数 —— 自执行函数
--
    var num1 = 10;

    (function () {
        var num1 = 20;
        console.log(num1);
    })();

    console.log(num1)
函数 —— 回调函数
--
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
    
数组
--
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
访问数组
--
    var arr = [1, 2, 3];

    console.log(arr.length);
    console.log(arr[0]);
    console.log(arr[1]);
    console.log(arr[2]);

    console.log(arr[3]); //undefined
    
添加元素
--
    var arr = [1, 2, 3];
    
    arr[0] = 4;
    console.log(arr);
    arr[3] = 5;
    console.log(arr);

    arr[8] = 9;
    console.log(arr);
    console.log(arr[7]);
    
删除元素
--
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
数组遍历
--
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
    
栈模式
--
    var stack = [1, 2, 3];
    stack.push(4);
    console.log(stack);
    
    stack.push(5, 6, 7);
    console.log(stack);

    var last = stack.pop();
    console.log(last);
    console.log(stack);

    console.log(stack[stack.length - 4]);
    
