# js-
JavaScript基础学习笔记总结



 * name: 铭心
 * time: 2021/3/11



console.log("true && true", true && true)
console.log("true && false", true && false)

console.log("true || false", true || false)

console.log("!true", !true)

var a = null;
b = a || 5;
console.log(b);

console.log("false && 'not printed'", false && 'not printer')
console.log("true || 'not printed'", 4 + 2 || 'not printed')

console.log(!!4);

console.log("5 & 3", 5 & 3);
console.log("5 | 3", 5 | 3);
console.log("5 ^ 3", 5 ^ 3);
console.log("~5", ~5)
console.log("~3", ~3)

console.log("5 << 1", 5 << 1)
console.log("5 >> 1", 5 >> 1)
console.log("~5 >>> 1", ~5 >>> 1)

三目运算符
var temperture = 10;
console.log(temperture > 15 ? '出门' : '在家');
var temperture = 16;
console.log(temperture > 15 ? '出门' : '在家');

代码块
console.clear()
{
    var name = '铭心';
    console.log(name);
    let age = 15;
    console.log(age)
    const YEAR = 2020;
    console.log(YEAR);
}
console.log(name);
