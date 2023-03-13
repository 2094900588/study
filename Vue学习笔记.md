# Vue 课程笔记                         覃老师        班级：20204122

# 第一章 Vue认识和基础

安装Vue插件到浏览器。

![image-20230311104746986](\img\image-20230311104746986.png)

![image-20230311105024886](\img\image-20230311105024886.png)

## Vue 简介

# 渐进式 JavaScript 框架

易学易用，性能出色，适用场景丰富的 Web 前端框架。

Vue (发音为 /vjuː/，类似 **view**) 是一款用于构建用户界面的 JavaScript 框架。它基于标准 HTML、CSS 和 JavaScript 构建，并提供了一套声明式的、组件化的编程模型，帮助你高效地开发用户界面。无论是简单还是复杂的界面，Vue 都可以胜任。

## 渐进式框架

Vue 是一个框架，也是一个生态。其功能覆盖了大部分前端开发常见的需求。但 Web 世界是十分多样化的，不同的开发者在 Web 上构建的东西可能在形式和规模上会有很大的不同。考虑到这一点，Vue 的设计非常注重灵活性和“可以被逐步集成”这个特点。根据你的需求场景，你可以用不同的方式使用 Vue：

- 无需构建步骤，渐进式增强静态的 HTML
- 在任何页面中作为 Web Components 嵌入
- 单页应用 (SPA)
- 全栈 / 服务端渲染 (SSR)
- Jamstack / 静态站点生成 (SSG)
- 开发桌面端、移动端、WebGL，甚至是命令行终端中的界面

如果你是初学者，可能会觉得这些概念有些复杂。别担心！理解教程和指南的内容只需要具备基础的 HTML 和 JavaScript 知识。即使你不是这些方面的专家，也能够跟得上。

如果你是有经验的开发者，希望了解如何以最合适的方式在项目中引入 Vue，或者是对上述的这些概念感到好奇，我们在[使用 Vue 的多种方式](https://cn.vuejs.org/guide/extras/ways-of-using-vue.html)中讨论了有关它们的更多细节。

无论再怎么灵活，Vue 的核心知识在所有这些用例中都是通用的。即使你现在只是一个初学者，随着你的不断成长，到未来有能力实现更复杂的项目时，这一路上获得的知识依然会适用。如果你已经是一个老手，你可以根据实际场景来选择使用 Vue 的最佳方式，在各种场景下都可以保持同样的开发效率。这就是为什么我们将 Vue 称为“渐进式框架”：它是一个可以与你共同成长、适应你不同需求的框架。

## Vue初次体验

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <!-- 绑定Vue数据的插值语法 -->
    <div id="root">{{username}}</div>

    <!-- 导入Vue的js -->

    <script src="js/vue.js"></script>
    <script>
      // 初始化Vue
      const vm = new Vue({
        el: '#root',
        data: {
          username: '张三',
        },
      })
    </script>
  </body>
</html>

```

## Vue指令语法

### ①插值表达式：

案例一：

```HTML
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <!-- 绑定Vue数据的插值语法 -->
    <div id="root">{{num1+num2}}</div>

    <!-- 导入Vue的js -->

    <script src="js/vue.js"></script>
    <script>
      // 初始化Vue
      const vm = new Vue({
        el: '#root',
        //绑定事件
        data: {
          num1: 6,
          num2: 8,
        },
      })
    </script>
  </body>
</html>

```

案例二：

对象插值表达式使用。

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <!-- 绑定Vue数据的插值语法 -->
    <div id="root">
      <!-- {{num1+num2}} -->
      姓名：{{user.name}} <br />
      年龄：{{user.age}}<br />
      性别：{{user.sex}}
    </div>

    <!-- 导入Vue的js -->

    <script src="js/vue.js"></script>
    <script>
      // 初始化Vue
      const vm = new Vue({
        el: '#root',
        //绑定事件
        data: {
          // num1: 6,
          // num2: 8,
          user: {
            name: '高启强',
            age: 48,
            sex: '男',
          },
        },
      })
    </script>
  </body>
</html>

```

### ②**v-text用法**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <!-- 绑定Vue数据的插值语法 -->
    <div id="root">
      <p v-text="content"></p>
    </div>

    <!-- 导入Vue的js -->

    <script src="js/vue.js"></script>
    <script>
      // 初始化Vue
      const vm = new Vue({
        el: '#root',
        //绑定事件
        data: {
          content: '我是中国人',
        },
      })
    </script>
  </body>
</html>

```

### ③v-html用法

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <!-- 绑定Vue数据的插值语法 -->
    <div id="root">
      <!-- 这样写就直接解析html标签属性 -->
      <div v-html="docontent"></div>
      <!-- 插值是原样输出  -->
      <div>{{docontent}}</div>
    </div>

    <!-- 导入Vue的js -->

    <script src="js/vue.js"></script>
    <script>
      // 初始化Vue
      const vm = new Vue({
        el: '#root',
        //绑定事件
        data: {
          docontent:
            '<h4 style="color: red; font-weight: bold;">欢迎大家来学习前端 vue技术</h4>',
        },
      })
    </script>
  </body>
</html>

```



1. `{{ }}` 插值表达式：在实际开发中用的最多，只是内容的占位符，不会覆盖原有的内容！
2. `v-text` 指令的缺点：会覆盖元素内部原有的内容！
3. `v-html` 指令的作用：可以把带有标签的字符串，渲染成真正的 HTML 内容！

### MVVM架构模型

![image-20230311153617545](\img\image-20230311153617545.png)

## 属性绑定指令

**属性绑定指令分单项属性绑定指令和双向数据绑定指令。**

### ①单项数据绑定指令：v-bind

单项数据绑定指令一般开发用在非表单的标签。

案例一：

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <!-- 绑定Vue数据的插值语法 -->
    <div id="root">
      <!-- v-bind可以简写成英文的: -->
      <p :title="title">{{title}}</p>
    </div>

    <!-- 导入Vue的js -->

    <script src="js/vue.js"></script>
    <script>
      // 初始化Vue
      const vm = new Vue({
        el: '#root',
        //绑定事件
        data: {
          title: '学习Vue开发',
        },
      })
    </script>
  </body>
</html>

```

案例二：

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <!-- 绑定Vue数据的插值语法 -->
    <div id="root">
      <input type="text" :placeholder="tips" /><br />
      <hr />
      <img :src="photo" alt="" style="width: 680" />
    </div>

    <!-- 导入Vue的js -->

    <script src="js/vue.js"></script>
    <script>
      // 初始化Vue
      const vm = new Vue({
        el: '#root',
        //绑定事件
        data: {
          photo:
            'https://syw.ctgu.edu.cn/__local/8/6E/DD/2F507A146723E194C2A7404B0EA_DEE66658_1D0B0.jpg',
          tips: '请您输入',
        },
      })
    </script>
  </body>
</html>

```

### ②事件绑定

`v-on:` 简写是 `@`

案例一

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <!-- 绑定Vue数据的插值语法 -->
    <div id="root">
      你看到的数字是{{num}}
      <hr />
      <button @click="add">点击一下加1</button>
    </div>

    <!-- 导入Vue的js -->

    <script src="js/vue.js"></script>
    <script>
      // 初始化Vue
      const vm = new Vue({
        el: '#root',
        //绑定事件
        data: {
          num: 0,
        },
        methods: {
          add() {
            this.num += 1
            console.log(this)
          },
        },
      })
    </script>
  </body>
</html>

```

案例二：

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <!-- 绑定Vue数据的插值语法 -->
    <div id="root">
      <h2>欢迎来到学习{{name}}技术</h2>
      <!-- <button v-on:click="showInfo">点我提示信息</button> -->
      <button @click="showInfo1">点我提示信息1（不传参）</button>
      <button @click="showInfo2($event,88)">点我提示信息2（传参）</button>
    </div>

    <!-- 导入Vue的js -->

    <script src="js/vue.js"></script>
    <script>
      // 初始化Vue
      const vm = new Vue({
        el: '#root',
        //绑定事件
        data: {
          name: 'vue',
        },
        methods: {
          showInfo1(event) {
            // console.log(event.target.innerText)
            // console.log(this) //此处的this是vm
            alert('同学你好！')
          },
          showInfo2(event, number) {
            console.log(event, number)
            // console.log(event.target.innerText)
            // console.log(this) //此处的this是vm
            alert('同学你好！！')
          },
        },
      })
    </script>
  </body>
</html>

```

**按键修饰符**

案例一：

```HTML
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <!-- 绑定Vue数据的插值语法 -->
    <div id="root">
      按键esc清空输入内容
      <input type="text" @keyup.esc="doesc" />
      <hr />
    </div>

    <!-- 导入Vue的js -->

    <script src="js/vue.js"></script>
    <script>
      // 初始化Vue
      const vm = new Vue({
        el: '#root',
        //绑定事件
        data: {
          username: '',
        },
        methods: {
          doesc(e) {
            //e.targen.value = ''
            e.target.value = ''
            console.log('执行了esc按键操作')
          },
        },
      })
    </script>
  </body>
</html>

```



### ③双向绑定V-model

案例一：

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <!-- 绑定Vue数据的插值语法 -->
    <div id="root">
      双向绑定
      <input type="text" v-model="username" />
      <input type="text" v-model="password" />
      <hr />
      单项绑定
      <input type="text" :value="username" />
      <input type="text" :value="password" />
    </div>

    <!-- 导入Vue的js -->

    <script src="js/vue.js"></script>
    <script>
      // 初始化Vue
      const vm = new Vue({
        el: '#root',
        //绑定事件
        data: {
          username: '张三',
          password: '123456',
        },
      })
    </script>
  </body>
</html>

```

**双向绑定在实际开发中用于表单元素。**

![image-20230311200534596](\img\image-20230311200534596.png)





### 过滤器（了解学习Vue3中已经删除了。）

**filter** 

过滤器（Filters）是 vue 为开发者提供的功能，常用于文本的格式化。过滤器可以用在两个地方：插值表达式 和 v-bind 属性绑定。 过滤器应该被添加在 JavaScript 表达式的尾部，由“管道符”进行调用。

案例一：

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <!-- 绑定Vue数据的插值语法 -->
    <div id="root">
      先输出
      <p>{{massage}}</p>
      <hr />
      通过过滤器输出
      <p>{{massage | cap}}</p>
    </div>

    <!-- 导入Vue的js -->

    <script src="js/vue.js"></script>
    <script>
      // 初始化Vue
      const vm = new Vue({
        el: '#root',
        //绑定事件
        data: {
          massage: 'hello vue.js',
        },
        methods: {},
        //过滤器声明
        filters: {
          //过滤器是函数
          cap(vul) {
            //过滤器必须要求返回值。
            //console.log(vul)
            //return '啊啊啊啊啊啊'
            return vul.charAt(0).toUpperCase() + vul.slice(1)
          },
        },
      })
    </script>
  </body>
</html>

```



### 案例练习

实现效果：

![image-20230312110347213](\img\image-20230312110347213.png)

案例代码如下：

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="./css/brandlist.css" />
    <link rel="stylesheet" href="./tjs/bootstrap.css" />
    <title>案例练习</title>
  </head>

  <body>
    <!-- 绑定Vue数据的插值语法 -->
    <div id="root">
      <div class="card">
        <div class="card-header">添加名称</div>
        <div class="card-body">
          <!-- 添加品牌的表单区域 -->
          <!-- form 表单元素有 submit 事件 -->
          <form @submit.prevent="add">
            <div class="form-row align-items-center">
              <div class="col-auto">
                <div class="input-group mb-2">
                  <div class="input-group-prepend">
                    <div class="input-group-text">用户名称</div>
                  </div>
                  <input
                    type="text"
                    class="form-control"
                    placeholder="请输入用户名称"
                    v-model.trim="brand"
                  />
                </div>
              </div>
              <div class="col-auto">
                <button type="submit" class="btn btn-primary mb-2">添加</button>
              </div>
            </div>
          </form>
        </div>
      </div>

      <table class="table table-bordered table-hover table-striped">
        <thead>
          <tr>
            <th scope="col">#</th>
            <th scope="col">用户名称</th>
            <th scope="col">用户状态</th>
            <th scope="col">创建时间</th>
            <th scope="col">操作</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="item in list" :key="item.id">
            <td>{{ item.id }}</td>
            <td>{{ item.name }}</td>
            <td>
              <div class="custom-control custom-switch">
                <!-- 使用 v-model 实现双向数据绑定 -->
                <input
                  type="checkbox"
                  class="custom-control-input"
                  :id="'cb' + item.id"
                  v-model="item.status"
                />
                <!-- 使用 v-if 结合 v-else 实现按需渲染 -->
                <label
                  class="custom-control-label"
                  :for="'cb' + item.id"
                  v-if="item.status"
                  >健康</label
                >
                <label class="custom-control-label" :for="'cb' + item.id" v-else
                  >生病</label
                >
              </div>
            </td>
            <td>{{ item.time | dateFormat }}</td>
            <td>
              <a href="javascript:;" @click="remove(item.id)">删除</a>
            </td>
          </tr>
        </tbody>
      </table>
    </div>

    <!-- 导入Vue的js -->
    <script src="./tjs/dayjs.min.js"></script>
    <script src="../js/vue.js"></script>
    <script>
      Vue.filter('dateFormat', function (time) {
        // 1. 对 time 进行格式化处理，得到 YYYY-MM-DD HH:mm:ss
        // 2. 把 格式化的结果，return 出去

        // 直接调用 dayjs() 得到的是当前时间
        // dayjs(给定的日期时间) 得到指定的日期
        const dtStr = dayjs(time).format('YYYY-MM-DD HH:mm:ss')
        return dtStr
      })

      // 初始化Vue
      const vm = new Vue({
        el: '#root',
        //绑定事件
        data: {
          brand: '',
          // nextId 是下一个，可用的 id
          nextId: 4,
          // 品牌的列表数据
          list: [
            { id: 1, name: '张三', status: true, time: new Date() },
            { id: 2, name: '李四', status: false, time: new Date() },
            { id: 3, name: '王五', status: true, time: new Date() },
          ],
        },
        methods: {
          // 点击链接，删除对应的品牌信息
          remove(id) {
            this.list = this.list.filter((item) => item.id !== id)
          },
          // 阻止表单的默认提交行为之后，触发 add 方法
          add() {
            // 如果判断到 brand 的值为空字符串，则 return 出去
            if (this.brand === '') return alert('必须用户名称')

            // 如果没有被 return 出去，应该执行添加的逻辑
            // 1. 先把要添加的品牌对象，整理出来
            const obj = {
              id: this.nextId,
              name: this.brand,
              status: true,
              time: new Date(),
            }
            // 2. 往 this.list 数组中 push 步骤 1 中得到的对象
            this.list.push(obj)
            // 3. 清空 this.brand；让 this.nextId 自增 +1
            this.brand = ''
            this.nextId++
          },
        },
      })
    </script>
  </body>
</html>

```

## 第二章Vue

### axios 发送请求后端接口

axios 的基本使用

发送get请求：

```JS
axios({
  // 请求方式
  method: 'GET',
  // 请求的地址
  url: 'http://127.0.0.1:10086/api/get',//请求路径
  // URL 中的查询参数
  params: {
    id: 1
  }
}).then(function (result) {
  console.log(result)
})
```

发送POST请求：

```JS
document.querySelector('#btnPost').addEventListener('click', async function () {
  // 如果调用某个方法的返回值是 Promise 实例，则前面可以添加 await！
  // await 只能用在被 async “修饰”的方法中
  const { data: res } = await axios({
    method: 'POST', 
    url: 'http://127.0.0.1:10086/api/post',
    data: {
      name: 'zs',
      age: 20
    }
  })

  console.log(res)
})
```

案例一：（请求我们之前开发的年级数据）**记得在年级的controller加上跨域注解   @CrossOrigin**

不加注解错误：

![image-20230312201851344](\img\image-20230312201851344.png)

代码如下：

```js
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>

  <body>
    <!-- 绑定Vue数据的插值语法 -->

    <!-- 导入Vue的js -->

    <!-- <script src="js/vue.js"></script> -->
    <script src="js/axios.js"></script>
    <script>
      //调用axios返回结果是Promise 对象
      const result = axios({
        method: 'GET',
        url: 'http://127.0.0.1:10086/sms/gradeController/getGrades',
      })
      // console.log(res)
      result.then(function (list) {
        console.log(list)
      })
    </script>
  </body>
</html>

```

**上述返回结果是：Promise 对象，如果需要后台数据，只需要在返回结果中加上list.data就可以实现。**

Post 请求：

案例

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <script src="js/axios.js"></script>

</head>
<body>
<script>
    //调用axios返回结果是Promise 对象
    const result = axios({
        method: 'post',
        url: 'http://127.0.0.1:10086/sms/gradeController/saveOrUpdateGrade',
        data:{
            name:'大学三年级',
            manager:'赵六',
            email:'111@163.com',
            telephone:'17812345678',
            introducation:'这个班级学生学习JavaEE开发'
        }
    })
    // console.log(res)
    result.then(function (list) {
        console.log(list.data)
    })
</script>
</body>
</html>
```

# Vue CLI(Vue 脚手架及工程化开发)

按照官网安装：

命令：在doc 命令下输入：

```dos
npm install -g @vue/cli
# OR
yarn global add @vue/cli
```

**建议用npm**

![image-20230313103724451](\img\image-20230313103724451.png)

安装好可以查看版本。

用dos 命令：

```
vue --version
```

如果想升级Vue CLI可以用下面命令：

```
npm update -g @vue/cli

# 或者
yarn global upgrade --latest @vue/cli
```

创建项目用下面命令：

```
vue create 项目名称
```

![image-20230313104529551](\img\image-20230313104529551.png)

这里选择自定义选择。

![image-20230313105959638](\img\image-20230313105959638.png)

先选择vue2.0版。后续我们用vue3.0

![image-20230313110426349](\img\image-20230313110426349.png)

下一步：

![image-20230313110726017](\img\image-20230313110726017.png)

下一步：

![image-20230313110934717](\img\image-20230313110934717.png)

下一步：

![image-20230313111212067](\img\image-20230313111212067.png)

下面就可以启动项目了，我就在IDEA中启动了。

启动命令：

```
npm run serve
```

![image-20230313111820221](\img\image-20230313111820221.png)

启动成功后下面显示。

![image-20230313112014407](\img\image-20230313112014407.png)

访问页面就可以看到如下：

![image-20230313112221097](\img\image-20230313112221097.png)

如果想要让项目停止运行：

```
ctrl+c 
```

![image-20230313112543327](\img\image-20230313112543327.png)

### 安装yarn 命令：

①

```js
npm install -g yarn 
```

②查看版本：

```
yarn --version
```

③安装yarn的依赖：

```
yarn install
```

上述是需要的同学安装。

yarn 没有npm稳定建议使用npm命令。



### 介绍一下项目目录：

看下面图就明白：

![image-20230313114543171](\img\image-20230313114543171.png)

src目录重点介绍：

![image-20230313114936993](D:\项目录屏\三峡大学科技学院\javaEE课程体系\Vue课程\笔记\img\image-20230313114936993.png)

**assets 文件夹：存放项目中用到的静态资源文件，例如：css 样式表、图片资源**
**components 文件夹：程序员封装的、可复用的组件，都要放到 components 目录下**
**main.js 是项目的入口文件。整个项目的运行，要先执行 main.js**
**App.vue 是项目的根组件。**

