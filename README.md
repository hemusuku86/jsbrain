# JSBrain
A JSFuck Decoder with no evaluating the code, with python. (still under development?)<br><br>
I know that JSFuck isn`t for safe obfuscation, but i made this for fun.<br><br>
If you have a bug, a request or more nice code than mine, you can write anything on Issues. I need your help!
## Usage
No modules are required.<br><br>
You can use file path for input code:
```
python3 jsbrain.py -p input.js
```
or, you can enter code directly:
```
python3 jsbrain.py -c "(!![]+[][(![]+[])[+!+[]]+(!![]+[])[+[]]])[+!+[]+[+[]]]+((+[])[([]..."
```
## Example
Original Code:
```javascript
alert("JSFuck!")
```
JSFucked Code:
```javascript
[][(![]+[])[+!+[]]+(!![]+[])[+[]]][([][(![]+[])[+!+[]]+(!![]+[])[+[]]]+[])[!+[]+!+[]+!+[]]+(!![]+[][(![]+[])[+!+[]]+(!![]+[])[+[]]])[+!+[]+[+[]]]+([][[]]+[])[+!+[]]+(![]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+[]]+(!![]+[])[+!+[]]+([][[]]+[])[+[]]+([][(![]+[])[+!+[]]+(!![]+[])[+[]]]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+[]]+(!![]+[][(![]+[])[+!+[]]+(!![]+[])[+[]]])[+!+[]+[+[]]]+(!![]+[])[+!+[]]]((!![]+[])[+!+[]]+(!![]+[])[!+[]+!+[]+!+[]]+(!![]+[])[+[]]+([][[]]+[])[+[]]+(!![]+[])[+!+[]]+([][[]]+[])[+!+[]]+(+[![]]+[][(![]+[])[+!+[]]+(!![]+[])[+[]]])[+!+[]+[+!+[]]]+(!![]+[])[!+[]...
```
Decoded with JSBrain:
```javascript
eval(Function("return"+'"'+("alert"+[1]+[6]+[4]+"t"+[5]+[0]+"t"+[4]+[2]+"t"+[1]+[1]+[2]+"t"+[1]+[2]+[3]+"t"+[1]+[0]+[6]+"ut"+[1]+[4]+[3]+"t"+[1]+[5]+[3]+"t"+[4]+[1]+"t"+[4]+[2]+"t"+[5]+[1])["split"]("t")["join"]("\\")+'"')())
```
It's almost readable, the `("alert"+[1]+[6]+[4]+"t"+[5]+[0]+"t"+[4]+[2]+"t"+[1]+[1]+[2]+"t"+[1]+[2]+[3]+"t"+[1]+[0]+[6]+"ut"+[1]+[4]+[3]+"t"+[1]+[5]+[3]+"t"+[4]+[1]+"t"+[4]+[2]+"t"+[5]+[1])` part is making the string `'alert164t50t42t112t123t106ut143t153t41t42t51'`, and replacing 't' with '\\' in `["split"]("t")["join"]("\\")`.<br><br>
Replaced string is `'aler\\164\\50\\42\\112\\123\\106u\\143\\153\\41\\42\\51'` and evaluating this string in `Function("return"+'"'+The String+'"')()`. the string is escaped with charCode ("\99" -> "c"). so, the evaluation returns `'alert("JSFuck!")'`.<br><br>
So, this code is completly same with:
```javascript
eval('alert("JSFuck!")')
```
(maybe I will automate this part too in future...(so maybe im tired))
