###Html书写规范

1. 每个html文件以页面功能命名，如warehouse-integration.html(下面均以此html为例)；

２．每个页面html里面的<body>标签内最近的外层包裹标签的class以html文件名首字母小写命名，如：
```
  <body>
    <div class="wi"></div>
  </body>
```

3.一个html文件里的每个结构块部分用<section>标签(除header footer等特殊功能外)，并且每个<section>之间要有注释，class命名也按照下例规则书写。如warehouse integration页面分为两个section，introduction 和 advantage:
```
  <body>
    <div class="wi">
      <!-- Header -->
      <header>
      </header>
      <!-- end of Header -->

      <!-- Warehouse Integration Introduction -->
      <section class="wi-intro">
        <div class="wi-intro__header"></div>
        <div class="wi-intro__list">
          <div class="wi-intro__list-item"></div>
        </div>
      </section>
      <!-- end of Warehouse Integration Introduction -->

      <!-- Warehouse Integration Advantage -->
      <section class="wi-advantage"></section>
      <!-- end of Warehouse Integration Advantage -->

      <!-- Footer -->
      <footer>
      </footer>
      <!-- end of Footer -->
    </div>
  </body>
```

###CSS书写规范

１．main.scss作为统一样式入口，其他页面每个页面写一个单独的样式文件，以_开头，从main里面引入，如 _warehouse-integration.scss文件，在main.scss最下方引入，引入的时候不用写　_和后缀名；
如：@import './warehouse-integration';

２．有一个_var.scss定义font-size和color变量，在main.scss最上方导入,@import './var'; 在每个页面单独的样式文件里面可直接引入 _var.scss里的变量，不用单独导入 _var.scss；

3.公共样式写在main.scss中间部分；

４．每个页面单独的样式文件里面的命名按照section的class名称分块，不用在最外层嵌套一层,如_warehouse-integration.scss：
.wi-intro {}
.wi-advantage {}