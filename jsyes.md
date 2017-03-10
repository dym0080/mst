###第一次看到就做出来的，但是感觉有必要记录下来。
####  1.console.log('hello'.repeatify(3))期望打印出hellohellohello
```js
        function repeatify(str,n) {
            var newStr="";
            for(var i=0;i<n;i++){
                newStr+=str;
            }
            return newStr;
        }
        console.log(repeatify('hello',3));
```
#### 2.下面代码如何改可以让person()打印出Colin Ihrig
```js
    var fullname = 'John Doe'
    var obj = {
        fullname: 'Colin Ihrig',
        getFullname: function() {
        return this.fullname
        }
    }

    var person = obj.getFullname
    console.log(obj.getFullname()) // Colin Ihrig
    console.log(person()) // John Doe
```
改变执行上下文即可。我的答案：
```js
        var fullname = 'John Doe'
        var obj = {
            fullname: 'Colin Ihrig',
            getFullname: function() {
                return this.fullname
            }
        }

        var person = obj.getFullname
        console.log(obj.getFullname()) // Colin Ihrig
        console.log(person.call(obj,'')) // John Doe
```
