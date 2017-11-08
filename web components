Web Component(网页组件化开发模板)
http://javascript.ruanyifeng.com/htmlapi/webcomponents.html#toc0
我理解的Web Components开发组件是customElement做外壳，在其中建立shadowDOM,将模板放到shadowDOM中,形成一个html页面，使用时通过HTML Import引入。


A页面
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<script src="bower_components/webcomponentsjs/webcomponents.js"></script>
		<title></title>
        <link rel="import" href="2.html"/>
	</head>
	<body>
		<test-t></test-t>	
	</body>
</html>

B页面
<template>
	<div>welcome to come my test</div>
</template>
<script>
	(function(){
		var currentScript = document._currentScript || document.currentScript,
        doc = currentScript.ownerDocument;
		var prop = Object.create(HTMLElement.prototype);
		prop.createdCallback = function(){
			var template = doc.querySelector('template');
			var clone = document.importNode(template.content,true);
			this.shadowRoot = this.createShadowRoot();
			this.shadowRoot.appendChild(clone);
		}
		
		return document.registerElement('test-t',{
			prototype:prop
		})
	})()
</script>
