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
    
        //配置统一资源定位符（个人域名）
        url: https://azurepast.github.io/
    
        //配置部署
        deploy:
           type: git
           repo: https://github.com/AzurePpast/azurepast.github.io.git
           branch: master
      
#### 发表博客文章

* 新建一篇文章

        // 新建一篇文章
        hexo new "文章标题"
    
    我们可以在本地博客文件夹source->_post文件夹下看到我们新建的markdown文件。
        
* 本地发布预览

    保存后，我们进行本地发布：

        $ hexo server
        //本地预览地址 http://localhost:4000/
 
* 发布     

        $ hexo generate
        $ hexo deploy

