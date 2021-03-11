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
函数 ——— 声明函数
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
    
调用函数
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
    

函表达式
--
    add = 5
    var plus = add;

    var multiply = function (a, b) {
        return a * b;
    }
    console.log(multiply(plus, 5));
函数和变量提升
--
    x = 5;
    console.log(x);
    var x = 10;
    console.log(divide(8, 2))
    function (divide(8, 2)) {
        renturn a/b
    }
默认参数
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

递归
--
    function sum(n) {
    if (n === 1) {
        return 1;
    }
    return n + sum(n - 1)
    }
    console.log(sum(5));
    
1 1 2 3 5 8 13 ...
--
    function fib(num) {
        if (num <= 1) {
            return 1;
        }
        return fib(num - 1) + fib(num - 2);
    }

    console.log(fib(7))
    
arguments
--
    function log() {
        for (let i = 0; i < arguments.length; i++) {
            console.log(arguments[i]);
        }
    }
    log('abc', 'cba', 'dee')

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
var / let
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
