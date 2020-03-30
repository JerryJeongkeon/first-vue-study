## 🚩 Vue 개념잡기               start _ 2020-03-31



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







### 1. 기본 프로젝트 생성

​	1-1 기본 Maven 프로젝트 생성 ( new -> Maven Project )



​	1-2 pom.xml 작성



```java
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <groupId>spring4</groupId>
  <artifactId>testPjt</artifactId>
  <version>0.0.1-SNAPSHOT</version>
  
  	<dependencies>
		<dependency>
			<groupId>org.springframework</groupId>
			<artifactId>spring-context</artifactId>
			<version>4.1.0.RELEASE</version>
		</dependency>
	</dependencies>

	<build>
		<plugins>
			<plugin>
				<artifactId>maven-compiler-plugin</artifactId>
				<version>3.1</version>
				<configuration>
					<source>1.8</source>
					<target>1.8</target>
					<encoding>utf-8</encoding>
				</configuration>
			</plugin>
		</plugins>
	</build>
  
</project>
```



이곳에서 기본 pom.xml파일에 

두 가지,  org.springframework와 maven-compiler-plugin을 추가해주었다.



:soon:   plugin을 추가해준 뒤 [ Maven -> Update Project ] 를 진행해준다.

:soon:  ​ 가장 기본의 Maven 프로젝트 src/main/ java와 resources 생성되며

:soon:   이후 테스트에 사용할 src/test/ java와 resources 생성된다.



java 폴더는 JAVA 파일들이 위치하는 곳이고 

​	resources 는 자원을 관리하는 폴더로 스프링 설정 파일(XML) 또는 프로퍼티 파일 등을 관리











