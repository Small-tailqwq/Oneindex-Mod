fork一下以后搭建更加方便，会在原有基础上加上个人的修改，原版请[点我](https://github.com/steven52880/Oneindex-Mod)。
- 原重定向链接已经404，安装前请先修改`controller/AdminController.php`中第187行的url为个人下载站的url。  
  - 比如我的下载站是od.hayasa.xyz，那么此处就该填`htps://od.hayasa.xyz`。请务必使用https。  
- 


> 以下为fork前原readme：

---

# OneIndex-MOD  
Onedrive Directory Index  
改动自downwa提供的Oneindex，此为自用改动版本。  

## 改动内容  
### 适用情况  
适用于有较快php空间、小文件长时间展示不修改的情况。  
不需要crontab，缓存自动更新
比如展示多个小文件html，展示markdown等。
### 原版缓存机制  
设置有缓存时间。所有缓存超时则刷新缓存。
### 改后缓存机制  
文件夹手动刷新，文件下载直链过期则自动刷新。
### 其它新增内容
增加文件夹内容更新后手动刷新当前目录功能。  
修改了显示目录时的标题。  
增加了对于指定扩展名无论get/post都展示功能。  
修改了密码保存机制，不直接存储管理密码，而是将密码md5加密后存储。  
新增了切换代理功能。 
新增了重新绑定账户功能，登录管理并访问?reauth或&reauth以重新安装（配置不变）。  
### 配置代理
编辑index.php内的函数，函数参数为OneDrive直链，id为选择的代理序号，返回代理后的链接。
#### 腾讯云cdn
选择TypeA鉴权模式
函数格式：qcloudcdn($url,key)
返回内容：cdn的路径
自己看示例

### 期望增加的功能  
防止加密文件夹子文件夹访问绕过。  

## 安装运行
[或者这个](https://steven53.top/web/251.html)  
请参考downwa的安装教程  
<img width="658" alt="image" src="https://raw.githubusercontent.com/donwa/oneindex/files/images/install.gif">  
  
由于downwa删库跑路了，我就自己搭建了绑定重定向页面，重定向链接为：
https://steven53.top/oneindex  
  
## 必要配置
由于只改了filecache，缓存方式务必选择filecache。  
由于缓存自动更新，请修改缓存过期时间为无穷大，比如233333333。  
还有其它配置写在index.php前面。请用代码编辑器打开并修改。  

## 前端垃圾，凑合着用吧，自行修改
