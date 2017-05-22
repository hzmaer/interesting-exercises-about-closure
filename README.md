# interesting-exercises-about-closure
关于闭包的有趣习题

1.function fun(n,o) {

 console.log(o)
 
 return {
 
  fun:function(m){
  
   return fun(m,n);
   
  }
  
 };
 
}

var a = fun(0); a.fun(1); a.fun(2); a.fun(3);

var b = fun(0).fun(1).fun(2).fun(3);

var c = fun(0).fun(1); c.fun(2); c.fun(3)

2.var name = 'global';

var obj = {

	name : 'obj',
 
	dose : function(){
 
		this.name = 'dose';
  
		return function(){
  
			return this.name;
   
		}
  
	}
 
}

alert(obj.dose().call(this))

3.var name = 'global';

var obj = {

	name : 'obj',
	
	dose : function(){
	
		this.name = 'dose';
		
		return function(){
		
			return this.name;
			
		}.bind(this)
	}
}

alert(obj.dose().call(this))
