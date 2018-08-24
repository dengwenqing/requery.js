# requery.js
RequiresJS_2.0_API中文

1.引入js文件
<script  data-main=”js /main”  scr=” js/require.js”></script>
2.文件目录结构
	● index.html
	●script/
  js/
			● app/
				● AppCommon.js
			● libs/
				● jquery.min.js
				●swiper.min.js
			●main.js
●require.js

	(1).index.html
	<script  data-main=”script/js /main”  scr=” script/js /require.js”></script>


	
	(2). main.js

require.config({
    baseUrl:"script/js",
    paths: {
        jquery: 'libs/jquery.min',
        appCom: 'app/AppCommon'
    },
    shim: {
    		appCom: { 
exports: 'appCom' 
}
    }
});
require(['jquery','appCom'], function($,appCom) {
    appCom.hello();
});

 (3). AppCommon.js

define(["jquery"],function(require){
    return{
        hello: function(){
            alert('Say Hello!');
        }
    }
})

 	(4).shim是什么？
		①、exports值（输出的变量名），表明这个模块外部调用时的名称；
		②、deps数组，表明该模块的依赖性。

		shim{
		    'jquery.scroll': {
		      exports: 'jQuery.fn.scroll',

		      deps: ['jquery']
		    }
		}
