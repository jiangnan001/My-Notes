JSON 对象


 
   在json 出现之前，一直用xml 来传递数据，xml是一种纯文本格式（即只保存文本，不保存格式，比如大小，颜色，粗体或斜体等格式）
   JSON 文本格式 是当时雅虎的一位叫道格拉斯的架构师发明的一种纯文本格式，属于javascript 的子集；比xml 更快，更小，更好解析；
   json  不支持 变量，函数 和对象实例 ，是一个纯文本；
   
   
  1.要搞清楚 JSON 对象， JSON 字符串和 JS 对象的区别。
    另外js 对象和json 对象的属性可以直接调用 ， 而json 字符串需要先转换成js 对象；
	
  2. JSON 数据类型有： 简单值 ， json 对象 ， json 数组；
      简单值：  "hello json"  ,  100    
      json   对象：  {"name":"jack" ,"age":100}  // 必须有双引号，单引号会引起语法错误；
       json  数组： ["jack",100,"rose" ]

    不同于：
     json  字符串： '{"name":"jack" ,"age":100}  '
     js 对象：  let  ob ={name:"jack",age:100}  //有声明， 属性名不必打双引号，
     js  数组：  let arr = [ "jack",100,"rose" ]  // 有声明；
                 let list = 
			            [
                        {
                        "firstname": "jack"  ， "lastName":"Doe"
                         },

                       {
                     "firstname": "jack"  ， "lastName":"Doe"
                       }
                       ]






 6.不同的语言有不同的JSON 解析器和序列化器。 ECMAscript  提供了一个全局JSON  对象，该对象有两个方法，用来处理js 数据和json 数据；
    JSON 序列化，是将JavaScript对象序列化成 json 字符串，注意不要误以为是一个j'son 对象 ，因为字符串打印出来的时候是不显示引号的；

eg： let  person = {
        name: "xiaoming" ,
        age:  12 ,
        gender: true ,
        grade : null,
        skills: ["css","html","JavaScript"] ，
        school  : {
          name: "光明中学"，
         address：“上海”
}
}

将上面的person 对象 ，序列化成j'son 字符串：
 JSON.stringify(person);
 
只序列化部分：
JSON.stringify(person ,["name","school "]);

还可以传入一个函数：
JSON.stringifty(person,function(){
    console.log("hello json");
});


5. 反序列化：
         JSON.parse()  //  将一个json 字符串转换成js 对象；
注意：  是将一个json 字符串转换成js 对象；

     let  a = {"name":"jack","age": 12}  //  这并非json 字符串，只是json 对象；
    let b = ' {"name":"jack","age": 12} '  // 这才是json 字符串； 必须有引号；
 eg:    JSON.parse(b); // 得到js 对象；
           JSON.parse(a)  // 因为 a 变量中存的是一个json 对象，无法解析 。
   其实到这里根本就不必解析json 对象 ，
   a.name  //  jack  ; 可以直接拿到json 对象中的属性；
        

6. eval（） 函数可以将 json 文本转换成js 对象， 不安全；
    eval("("+b+")") ;
  
  
  


   
2. 把json  数据变成 js  对象叫做json  解析；
 var b=   JSON.parse(a);  把json字符串 a 解析成 js值，存入变量b 中；
   还有一个函数 也可以解析json  ，eval（）；  但是这个函数解析json数据不安全，该函数解析
json 结构的数据时，是把json数据当作代码来执行，如果是恶意代码，就会造成安全问题；
        
2.   json   对象的遍历用  for ...in    循环

         var site=  { “name” :"百度" ，  “url”:"www.baidu.com" };
		 
                     for( var  x in site ){
                                       document.wrte(x);  //   输出某个属性的 key  值；
                             document.write(site[x]+"<br>")            // 输出某个属性的value 值；
                    }

