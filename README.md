# v-intersection

---

a vue component for IntersectionObserver

一个 vue 的 IntersectionObserver 组件

support vue3.0

[![npm](https://nodei.co/npm/v-intersection.png)](https://www.npmjs.com/package/v-intersection)

## demo and document


[demo and documment github page](https://genjixyz.github.io/v-intersection/)

[demo and documment 国内](https://coding-pages-bucket-144121-8040028-5553-382057-1259347617.cos-website.ap-hongkong.myqcloud.com/)  


## use

### install :

```dash
npm install v-intersection --save
```

### import:

vue 2.6.11
```js
import Vue from 'vue'
import intersection from "v-intersection";
Vue.use(intersection);
```

vue 3.0

```js
import intersection from "v-intersection";
createApp(App).use(intersection ).mount('#app')
```

### use

```html
vue directive

<div v-intersection="handler"></div>



<script>
export default {
  methods:{
	  handler(entries, observer, isIntersecting, ratio){

	  }
  }
};
</script>
```



### options:

```html
<div
  v-intersection="{handler:yourMehtod,
      options = {
        root: document.querySelector('#scrollArea'),
        rootMargin: '0px',
        threshold: [0,1]  
      }
  }"
>

</div>
```





more options info  in   [MDN document](https://developer.mozilla.org/zh-CN/docs/Web/API/IntersectionObserver)

更多配置参数请见 [MDN document](https://developer.mozilla.org/zh-CN/docs/Web/API/IntersectionObserver)



### modifier

```html

once
just run once ,and  IntersectionObserver.unobserve( target) 
只执行一次, 执行结束后 , IntersectionObserver.unobserve(target)
<div v-intersection.once="handler"></div>


quiet
when init don't run 
初始化设置的时候不执行, 
<div v-intersection.quiet="handler"></div>

```





## disconect( )  

```html
<div v-intersection="handler" ref="mydom"></div>


<button @click="disconect">  disconect( )  </button>


<script>
export default {
  methods:{
	  handler(entries, observer, isIntersecting, ratio){
	  },
    disconect(){
      this.$refs.mydom._observe.observer.disconnect() 
    }
  }
};
</script>

```



## unobserved ( ) 

```html
<div v-intersection="handler" ref="mydom"></div>



<button @click="unobserved">  unobserved( )  </button>


<script>
export default {
  methods:{
    
	  handler(entries, observer, isIntersecting, ratio){
	  },
    
    unobserved(){
      var observer = new IntersectionObserver(callback);
			observer.observe(this.$ref.mydom)
    }
  }
};
</script>


```

