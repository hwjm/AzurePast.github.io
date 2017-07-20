# AzurePast.github.io

### 本博客创建步骤

#### 创建仓库
#### 安装node.js
#### 安装git
#### 安装hexo
* 下载安装hexo

        $ npm install -g hexo-cli
    
* 初始化博客

        // 建立一个博客文件夹，名为<folder_name> (名字可以随便起)
        $ cd <folder_name>
         // 初始化
        $ hexo init
        // node.js的命令，根据博客既定的dependencies配置安装所有的依赖包
        $ npm install
        // 安装部署相关的配置
        npm install hexo-deployer-git
    
* 配置博客

    前往<folder_name>文件夹, 打开_config.yml文件, 修改如下配置信息

        // 修改网站相关信息
        title: <your_title>
        subtitle: <your_subtitle>
        description: <your_description>
        author: <author>
        language: zh-CN
        timezone: Asia/Shanghai
    
        // 配置统一资源定位符（个人域名）
        url: <your_url>
    
        // 配置部署
        deploy:
           type: git
           repo: https://github.com/用户名/仓库名.git
           branch: master
      
#### 发表博客文章

* 新建一篇文章

        // 新建一篇文章
        hexo new "文章标题"
    
    我们可以在本地博客文件夹source->_post文件夹下看到我们新建的markdown文件。
        
* 本地发布预览

    保存后，我们进行本地发布：

        $ hexo server
        // 本地预览地址 http://localhost:4000/
 
* 发布     

        $ hexo generate
        $ hexo deploy

#### 多端同步

* hexo工程代码上传

    前往github创建新的分支, 并设置该分支为默认分支
    
    ![Github上新建分支](http://upload-images.jianshu.io/upload_images/291600-fd8d2be4578c9aa4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
    
    在本地博客根目录下使用git指令上传项目到Github

        // git初始化
        git init
        // 添加仓库地址
        git remote add origin https://github.com/用户名/仓库名.git
        // 新建分支并切换到新建分支(hexo为分支名)
        git checkout -b hexo
        // 添加所有本地文件到git
        git add .
        git commit -m "<your_description>"
        // 推送到hexo分支
        git push origin hexo
        
* 其它设备同步
    
    在其它设备上clone下Github上hexo分支下的hexo工程到本地, 就可以写文章了
    
        // 克隆文件到本地
        git clone -b hexo https://github.com/用户名/仓库名.git
        
    文章写好后, 重新部署到Github
    
        // 安装hexo
        npm install hexo
        // 注意这里不需要hexo初始化：hexo init；否则之前的hexo配置参数会重置
        // 安装依赖库
        npm install
        // 安装部署相关配置
        npm install hexo-deployer-git
        
    同步项目源文件到Github

        // 添加源文件
        git add .
        // git提交
        git commit -m ""
        // 先拉原来Github分支上的源文件到本地，进行合并
        git pull origin 分支名
        // 比较解决前后版本冲突后，push源文件到Github的分支
        git push origin 分支名
        至此多设备同步到此为止。

* 打完收工

#### 参考

    [20分钟教你使用hexo搭建github博客](http://www.jianshu.com/p/e99ed60390a8)
    [多设备同步hexo搭建的Github博客](http://www.jianshu.com/p/6fb0b287f950)
