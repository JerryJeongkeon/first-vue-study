🚩 Vue 개념잡기               start _ 2020-03-31



##### Vue.js 웹 프로그래밍[스마트러닝]

기본 Vue 개념 강의를 들으며 Vue.js에 대해 개념을 잡고 실습을 통해 코딩 능력을 키우는 것을 목표로 합니다.





## :white_check_mark: Vue

	- **MVVM**( **Model-View-ViewModel** ) 패턴을 기반으로 디자인 되어 있다.

- MVC 의 Model - View - Controller에서 **Controller**가 **ViewModel**로 변경된 개념이다.

- AngularJS, Backbone, React 에 비해 매우 **작고 가볍다**
- View에 초점을 맞춰 만들어진 프레임워크
- 가상 DOM을 사용한다.





#### **Vue 개발환경 설치**

##### 이 강의에서는 Java언어를 기반으로 Eclipse, Apache Tomcat, Oracle 11g, Chrome을 사용할 예정입니다.

##### 



**Vue 개발 방식**

1. Vue Devtools

2. **CDN : 서버에 올려두고 불러오는 방식이어서 항상 최신 버전의 Vue를 이용할 수 있다.**

3. 직접 <script>에 추가

4. NPM으로 추가





### :pushpin:  기본 Vue 프로젝트 Template

```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
</head>
<body>

</body>
</html>
```



Eclipse에서  [ **Window -> Preference -> Web -> Template -> New** 버튼 클릭 ] 

​		Name : VueJS 설정, Context : New HTML로 설정해준 뒤

​			위에 적힌 코드를 붙혀주면 기본 HTML을 생성할 때 Vue CDN이 추가된 채로 진행할 수 있다.





## :heavy_check_mark: Vue 객체



##### el : 웹 애플리케이션 내의 html 요소 중 Vue 객체가 관리할 태그를 설정한다.



##### data: **웹 애플리케이션에서 사용하는 데이터를 설정한다.** 



##### method : Html을 랜더링할 때 호출할 함수를 등록한다.

##### 					이 함수가 호출하는 HTML코드를 랜더링 데이터로 사용한다.







## :heavy_check_mark: Vue 라이프사이클 다이어그램



![img](./lifecycle.png)







```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<script>

window.onload = function(){	
	var vm1 = new Vue({
		// el : '#test1',
		data : {
			a1 : 100
		},
		// Vue 객체가 관리할 요소들이 만들어지기 전에 호출되는 함수
		beforeCreate : function(){
			console.log('Vue 객체가 관리할 요소들이 만들어지기 전 입니다.')
			console.log('a1 : ' + this.a1 )
		},
		// Vue 객체가 관리할 요소들이 만들어지고 난 이후
		created : function(){
			console.log('Vue 객체가 관리할 요소들이 만들어진 후 입니다.')
			console.log('a1 : ' + this.a1)
		},
		// Vue 객체가 관리할 HTML 태그 객체가 할당 되기 전
		beforeMount : function(){
			console.log('Vue 객체가 관리할 태그가 할당 되기 전입니다.')
		},
		// Vue 객체가 관리할 HTML 태그 객체가 할당 된 후
		mounted : function(){
			console.log('Vue 객체가 관리할 태그가 할당 된 이후입니다.')
		},
		beforeUpdate : function(){
			console.log('관리하고 있는 HTML 요소 내부가 변경되기 전입니다.')
		},
		updated : function(){
			console.log('관리하고 있는 HTML 요소 내부가 변경된 후입니다.')
		},
		beforeDestroy : function(){
			console.log('Vue 객체의 기능이 소멸되기 전입니다')
		},
		destroyed : function(){
			console.log('Vue 객체의 기능이 소멸된 후입니다.')
		},
		
		methods: {
			setValue : function(){
				this.a1 = 200
			}
		}
	})
	
	// Vue 객체에 마운트 된 태그를 관리하는 요소를 소멸시킨다.
	vm1.$destroy()
	
	// Vue 객체에 태그를 할당한다.
	vm1.$mount('#test1')
}
</script>
</head>
<body>
	<div id="test1">
		<h3>{{a1}}</h3>
		<button type="button" v-on:click="setValue">값 변경</button>
	</div>
</body>
</html>
```









## :heavy_check_mark: Template



#### v-html : 지정된 데이터를 html 코드로 인식하여 바인딩한다.



#### v-bind : 속성명 :  지정된 데이터를 지정된 속성 값으로 설정한다.





```html
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<script>
	window.onload = function(){
		var test1 = new Vue({
			el : '#test1',
			data : {
				a1 : '문자열1',
				a2 : '문자열2',
				a3 : '<h2>문자열3</h2>',
				a4 : 'image/기존 IP주소.png',
				a5 : 300,
				a6 : 200
			}
		})
	}
</script>
</head>
<body>
	<div id="test1">
		<h3>{{a1}}</h3>
		<h3>{{a2}}</h3>
		<h3>{{a3}}</h3>
		<div v-html='a3'></div>
		
		<img src='{{a4}}'>
		
		<img v-bind:src='a4' v-bind:width='a5' v-bind:height='a6'>
	</div>
</body>
</html>
```





























