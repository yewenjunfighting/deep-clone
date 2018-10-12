# js-deep copy 
javaScript
//浅复制
		  var father = {
			name : 'superman',
			adress : 'tower',
			wife : 'hero',
			job : '辛苦',
			son : 'brother',
			son2 : 'didi',
			daughter : 'sister',
			Father : {
		
			},
			shuzu : []
		}
		var son = {
			th : []
		}
		var i = 0; 
		/* for(var prop in father){
			son.th[i] = father[prop];
			i ++;
		}
		father.Father.name = "我是引用值";
		father.shuzu[0] = 1;
    
    
		//深复制A instanceof B 只要A的原型链上有B的原型就返回true,要实现这个就要区分引用值是数组还是对象
		function copyArray(target, shuzu){
			//console.log(shuzu);
			for(var i = 0; i < shuzu.length; i ++){
				if(shuzu[i] instanceof Array){
					target[i] = [];
					copytarget(target[i], shuzu[i]);
				}else if(shuzu[i] instanceof Object){
					target[i] = {};
					copyObject(target[i], shuzu[i]);
				}else {
					target[i] = shuzu[i];
				}
			}
		}
		function copyObject(target, object){
			//console.log(object);	
			for(var prop in object){
				if(object[prop] instanceof Array){
					 target[prop] = [];
					 copyArray(target[prop], object[prop]);
				}else if(object[prop] instanceof Object){
					target[prop] = {};
					copyObject(target[prop], object[prop]);
					}else {
					target[prop] = object[prop]; 
				}
			}
		}
		var origin = {
			name : 'tony',
			school : 'zafu',
			adress : 'quzhou',
			shuzu : [1,2,3,{name : 'sunny'}],
			obj : {love : 'jay', car : '奥迪', th : {name : 'hary'}}
		}
		var target = {};
		function copy(target, origin){
			target = target || {};
			for(var prop in origin){
				if(origin[prop] instanceof Array){
					target[prop] = [];
					copyArray(target[prop], origin[prop]);
					//console.log(target);	
				}else if(origin[prop] instanceof Object){
					target[prop] = {};
					copyObject(target[prop], origin[prop]);
				}else {
					target[prop] = origin[prop];
				}
			}
		}
		copy(target, origin);
		console.log(target);
