1)javascriptin  bir construktoru :obyekler variydi. Her obyektin gizli propertysi var hansi ki bawqa obyetin linkini dawiyir
budaprototype adlanir.javasript obyekleri properitler ucun dimanim "canta" rolu oynayir.Prototypal miras modeliu klassik model
daha guclu edir.misal ucun kicik bir prototypal model ust birklassik model qurmagi mumkun edir.
var o = {
  a: 2,
  m: function() {
    return this.a + 1;
  }
};

console.log(o.m()); // 3
// When calling o.m in this case, 'this' refers to o

var p = Object.create(o);
// p is an object that inherits from o

p.a = 4; // creates an own property 'a' on p
console.log(p.m()); // 5
// when p.m is called, 'this' refers to p.
// So when p inherits the function m of o, 
// 'this.a' means p.a, the own property 'a' of p
-----------------------------------------------------
function Rectangle( width, height ) {
 this.width = width;
 this.height = height;
}
rectangle constructoru yardaq.indi ise uzunluq ver hundurluk verilir ve arqumentler verilir.
var rect = new Rectangle( 3, 4 );
rect.width; // 3
rect.height; // 4
Indi ise rectangle methodunu verek.
Rectangle.prototype.area = function() {
 return this.width * this.height;
};
var rect = new Rectangle( 3, 4 );
rect.area(); // 12
----------------------------------------------------------------------------------------------------------------------------
//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
-----------------------------------------------------------------------------------------------------------------------------
2)What are closures and how are they used?
Ilk novbede closure functiondir ki bawqa funckssiyada teyin olunur. dacxili funksiya onan usteki fumksiyanin deyiwenlerini 
ce parametlerini access edir.
function init() {
  var name = 'Mozilla'; // name is a local variable created by init
  function displayName() { // displayName() is the inner function, a closure
    alert(name); // use variable declared in the parent function    
  }
  displayName();    
}
init();
init() local deyiwen teyin edir ve funksiya displayName() cagirir.displayName() funksiyasi daxili funksiyadir ki, init()de cagirilir.
init() daxilinde activedir.Ancaq displayName() ozunun lokal deyiwenleri yoxdur. belelikle initden goturur.
---------------------------------------------------------------------------------------------------------------------------
/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
--------------------------------------------------------------------------------------------------------------------------
3)Can you use x === “object” to test if x is an object?
bele bir misala baxaq
var car = {type:"Fiat", model:"500", color:"white"};

if(typeof(car) === "object"){
	console.log("duzgundur")
}
else{
	console.log("duzgundur deyil")
}
burada cavab olaraq duzgundur cixardacaq,cunki typeof(car) object verecek ve == olar.
var car = {type:"Fiat", model:"500", color:"white"};

if(car === "object"){
	console.log("duzgundur")
}
else{
	console.log("duzgundur deyil")
}
bele yaziliwda ise duzgun deyil cixacaq cunki burada obyekti icinde olanlari caxrdacaq.
--------------------------------------------------------------------------------------------------------------------------
//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
----------------------------------------------------------------------------------------------------------------------------
4)What happens when you don’t declare a variable in Javascript?
var foo = 1; // declared properly
bar = 2; // implied global
window.baz = 3; // global via window object
delete foo; // false
delete bar; // true
delete baz; // true

foo; // 1
bar; // ReferenceError
baz; // ReferenceError
burad gorunur ki,foo declare olunub ancaq bar olunmuyub ve onalroi silende foo  false verecek.Elave olaraq eger var nan her hani deyiwen teyin
olunub ver onan sora ki hemin adda feyiewn varla teyi n olmayibsa axirnci evelikini deyiwecek.
var foo = "I'm global";
var bar = "So am I";

function () {
    var foo = "I'm local, the previous 'foo' didn't notice a thing";
    var baz = "I'm local, too";

    function () {
        var foo = "I'm even more local, all three 'foos' have different values";
        baz = "I just changed 'baz' one scope higher, but it's still not global";
        bar = "I just changed the global 'bar' variable";
        xyz = "I just created a new global variable";
    }
}
-------------------------------------------------------------------------------------------------------------------------
//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
--------------------------------------------------------------------------------------------------------------------------
5)What is the difference between == and === ?
bunlar arasinda bawlicaq ferq == bu icindekiler oxuyur meslen 6=="6" bu dogrudur. Ancaq === bu ise tip olaraq yoxluyur
6==="6" false olar;
--------------------------------------------------------------------------------------------------------------------------
//////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
---------------------------------------------------------------------------------------------------------------------------
6)What datatypes are supported in Javascript?
javascriptde Boolean
Null
Undefined
Number
String
Symbol
Object 
data tipleri var.
1)boolean true false deyerler qaytarir.
2)var num = 1;
typeof num; // number
3)"hello world"; stringdir
4)var cat = { sound: "meow" };

var fluffy = new Cat();

var whiskers = new function() {
   
--------------------------------------------------------------------------------------------------------------------------
/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
-----------------------------------------------------------------------------------------------------------------------
7)What would “1”+2+3 and 1+2+“3” evaluate to, respectively?
bunar = olar cunki string icindekileri reqem kimi gorecek ver 6=6 olar.
---------------------------------------------------------------------------------------------------------------
////////////////////////////////////////////////////////////////////////////////////////////////////////////////
------------------------------------------------------------------------------------------------------------------
9)What is the difference between a null value and an undefined value?
undefibed-eger varda delere edib value vermesek bu undifinned olar.
null- variable devclare edib onu null kimi teyin etsek null gosterer
var a = [ 'a', 'b', 'c' ];
delete a[1];
for (var i = 0; i < a.length; i++)
WScript.Echo((i+".) "+a[i]);
burada a[1]massivi undefined olar.
bawqa misal
var a = ''; 
console.log(typeof a); // string 
console.log(a == null); //false 
console.log(a == undefined); // false 
===============
var a; 
console.log(a == null); //false 
console.log(a == undefined); // true
-------------------------------------------------------------------------------------------------------------------------
////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
------------------------------------------------------------------------------------------------------------------

10)Which conditional statements will JavaScript support?

if else wert opratorlaridir. if(cond){wert}else{wert2}
ternar opratoruda var ki if else qisaldilmiwidir.
condition ? expr1 : expr2 
bu wekilde yazilir.
swir=tch case wert opratoru
switch (expression) {
  case value1:
    //Statements executed when the result of expression matches value1
    [break;]
  case value2:
    //Statements executed when the result of expression matches value2
    [break;]
  ...
  case valueN:
    //Statements executed when the result of expression matches valueN
    [break;]
  default:
    //Statements executed when none of the values match the value of the expression
    [break;]
} b
bu wekilde yzailir.
-------------------------------------------------------------------------------------------------------------
///////////////////////////////////////////////////////////////////////////////////////////////////////////////
--------------------------------------------------------------------------------------------------------------
11)What is NaN?
Nan "Not-a-Number" deyrini teyin edir.Bununn legal eded olmadigini gosterir.
 isNaN()  istifade ederek Nan in deyeri Nan olub olmadiginin yoxlamaq olar.
 ---------------------------------------------------------------------------------------------------------------------
 //////////////////////////////////////////////////////////////////////////////////////////////////////////////////////
 ---------------------------------------------------------------------------------------------------------------------
 12)Explain the meaning of the keyword ‘this’ in JavaScript functions





11)


