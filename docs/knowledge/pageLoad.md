# 页面加载

页面优化的文章在网上已经是数不胜数了，这里主要是想说说其中的图片的优化

图片加载优化大概要注意以下几点

- 1.图片在线压缩网站   
    世界上有许多免费的在线压缩图片网站，这里我比较喜欢的是 https://tinypng.com/。
- 2.图片格式   
    随着技术发展，现在的图片尽可能用webp格式，网上有很多的在线转换的网站，可以自己试一试，体积的确很小。
- 3.image-webpack-loader  
    使用这个webpack的plugin在打包时候压缩图片，这个里面有一个需要注意的问题   
    一张10k图片经过网站A压缩后剩5k，经过图片插件压缩后可能剩4k。同样经过网站B压缩后剩4k，经过插件压缩后很有可能剩4.5k。
    我们很难知道一个图片可以被极限压缩到多少k，很难知道怎么压缩是最小的。
- 4.页面上的img标签要手动设定图片宽高，避免浏览器自己计算     
- 5.让图片的size 100% 的展示出来，不要在一个小窗体内展示大的图片  
    利用srcset 和 size 设定图集，优化显示，让浏览器自己去选择加载最合适的图片   
    使用picture 与 source 标签也可以实现相同的效果  
    具体怎么做可以百度，网上有很多资料

     
