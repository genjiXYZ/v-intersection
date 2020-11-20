# v-intersection

---

extract some code by vuetify,just for using it lighter


[![npm](https://nodei.co/npm/v-intersection.png)](https://www.npmjs.com/package/v-intersection)

## demo and document

[demo and documment github page](https://genjixyz.github.io/v-intersection/)

[demo and documment coding page](https://coding-pages-bucket-144121-8040028-5553-382057-1259347617.cos-website.ap-hongkong.myqcloud.com/)

## use

install :

```dash
npm install v-intersection --save
```

import:

```js
import intersection from "v-intersection";
Vue.use(intersection);
```

use

```html
<div v-intersection="handler"></div>
```

```js
methods:{
	handler(entries, observer, isIntersecting, ratio){

	}
}
```

what's params mean

[MDN document](https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserver/IntersectionObserver)

options:

```html
<div
  v-intersection="{handler:yourMehtod,
options = {
  root: document.querySelector('#scrollArea'),
  rootMargin: '0px',
  threshold: 1.0   
}
}"
></div>
```

methods:

```js
//disconnect()
el._observe.observe.disconnect();
//unobserve()
el._observe.observe.unobserve(el);
```

