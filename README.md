# electron-learn

> An electron-vue project


### 使用方法
#### 1.使用git clone到本地或直接下载压缩包解压
#### 2.cd 到此文件夹目录下，你可以修改相关内容并run dev预览一下，修改完成后可直接打包，打包完成你就可以把生成的安装文件或把绿色免安装文件夹压缩一下发给你的小仙女进行体验啦。  
*注：打包会在 build/ 文件夹下生成安装文件和可直接执行程序的文件夹(若想免除安装直接执行，此文件夹内所有东西都需要）
     
```
npm install //安装所需包文件
npm run dev //开发者模式，可以在本地打开此应用预览
npm run build //打包
```

---
### 应用简介
这是一个基于electron-vue的简单应用，我称之为**小仙女验证系统**，可以用它来小小的哄一下女孩子~
  
具体功能就是一个简单的姓名验证：    
  当对方输入的姓名与预设的姓名不同时，就会弹出错误提醒，我这里设置了一个数组来随机提示不同信息。 
  当输入姓名与预设姓名一致时，就会弹出提醒就是你，小仙女。
  
预设姓名你可以自己设置，以上错误提醒与正确提醒你也可以自己修改。以上这些设置均在**src/renderer/components/Hello.vue**文件中进行修改，我在其中均已做了注释。

This project was generated with [electron-vue](https://github.com/SimulatedGREG/electron-vue) using [vue-cli](https://github.com/vuejs/vue-cli). Documentation about the original structure can be found [here](https://simulatedgreg.gitbooks.io/electron-vue/content/index.html).
