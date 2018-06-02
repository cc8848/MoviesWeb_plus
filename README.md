# MoviesWeb_plus
此项目需要 电脑上 安装有 node+MongoDB数据库。

app.js启动node服务器。
# 该项目是MoviesWeb的升级版，在原有的基础上，进行了优化了项目目录 和代码。
1.加了用户的登录注册

2.以及管理员的权限管理。

3.实现了用户的修改和删除。

4.密码实现了 MD5加盐（加密）

5.用户登录会话 ，做了持久化处理。

6.增加某个电影的访客量。

7。增加了首页 ，电影的增加效果，以及美化

 # 电影首页--localhost:3000/index
 
 电影详情页--localhost:3000/detail
 
 电影后台列表页--localhost:3000/film/list
 
 电影后台录入页--localhost:3000/film/admin
 
 用户 登录--localhost:3000/user/signin
 
 用户 注册--localhost:3000/user/signup
 
 用户 列表--localhost:3000/user/list
 
 用户 详情--localhost:3000/user/detail

因为注册用户的权限默认为0，权限大于10（不包括10）才能访问 后台页面。
所以，大家可以把config目录下的routes.js中的
app.get("/user/list", User.signinRequired, User.adminRequired, User.userlist);//列表 页，
app.post("/admin/update", User.signinRequired, User.adminRequired, User.userUpdate);//更新 数据处理
----改成
app.get("/user/list", User.userlist);//列表 页
app.post("/admin/update", User.adminRequired, User.userUpdate);//更新 数据处理
（去掉中间件），运行，进入localhost:3000/user/list，进行 权限修改（>10）,然后复原代码。

欢迎大家的下载和修改。

升级版 1．用Bootstrap搭建响应式布局页面。运用$.ajax()异步获取Node后台json数据。 使用Vue.js实现页面渲染以及数据的双向绑定和实时计算。 2．通过Node.js+MongoDB实现了电影和用户的增删改查及权限管理。 密码使用MD5加盐处理，用户登录会话做了持久化处理。 收获：解决了IE兼容问题，以及收获了前后端数据的交互和联系。 通过全栈思维引导，拓宽了我对技能的理解，加深了我对整体项目全局观念。
