# Website Performance Optimization portfolio project

Your challenge, if you wish to accept it (and we sure hope you will), is to optimize this online portfolio for speed! In particular, optimize the critical rendering path and make this page render as quickly as possible by applying the techniques you've picked up in the [Critical Rendering Path course](https://www.udacity.com/course/ud884).

To get started, check out the repository and inspect the code.

## Getting started

### Part 1: Optimize PageSpeed Insights score for index.html

Some useful tips to help you get started:

1. Check out the repository
1. To inspect the site on your phone, you can run a local server

```bash
$> cd /path/to/your-project-folder
$> python -m SimpleHTTPServer 8080
```

1. Open a browser and visit localhost:8080
1. Download and install [ngrok](https://ngrok.com/) to the top-level of your project directory to make your local server accessible remotely.

```bash
$> cd /path/to/your-project-folder
$> ./ngrok http 8080
```

1. Copy the public URL ngrok gives you and try running it through PageSpeed Insights! Optional: [More on integrating ngrok, Grunt and PageSpeed.](http://www.jamescryer.com/2014/06/12/grunt-pagespeed-and-ngrok-locally-testing/)

Profile, optimize, measure... and then lather, rinse, and repeat. Good luck!

#### 字体优化

- 使用 `font-display:swap` 在字体加载完成前回退到默认字体
- 使用 `rel="preload" as="style"` 预加载谷歌字体
- 使用 `media="print" onload="this.media='all'"` 使字体不阻塞初次渲染

#### CSS 优化

- 使用 `media="print"` 使打印样式不阻塞初次渲染
- 内联 CSS 个人认为应该只有骨架屏之类的场景可以用到

#### 图片优化

- 将原始图片压缩为 `webp` 格式
- github pages 不支持手动设置缓存时间

### Part 2: Optimize Frames per Second in pizza.html

To optimize views/pizza.html, you will need to modify views/js/main.js until your frames per second rate is 60 fps or higher. You will find instructive comments in main.js.

You might find the FPS Counter/HUD Display useful in Chrome developer tools described here: [Chrome Dev Tools tips-and-tricks](https://developer.chrome.com/devtools/docs/tips-and-tricks).

#### JS 优化

- `offsetWidth` 和 `scrollTop` 属性会强制浏览器清空当前的更新队列，从而无法合并多次更新来优化，因此除非必要都应该只读取一次缓存下来之后使用

## Optimization Tips and Tricks

- [Optimizing Performance](https://developers.google.com/web/fundamentals/performance/)
- [Analyzing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/analyzing-crp.html)
- [Optimizing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/optimizing-critical-rendering-path.html)
- [Avoiding Rendering Blocking CSS](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-blocking-css.html)
- [Optimizing JavaScript](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/adding-interactivity-with-javascript.html)
- [Measuring with Navigation Timing](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/measure-crp.html) We didn't cover the Navigation Timing API in the first two lessons but it's an incredibly useful tool for automated page profiling. I highly recommend reading.
- [The fewer the downloads, the better](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/eliminate-downloads.html)
- [Reduce the size of text](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer.html)
- [Optimize images](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization.html)
- [HTTP caching](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/http-caching.html)

## Customization with Bootstrap

The portfolio was built on Twitter's [Bootstrap](http://getbootstrap.com) framework. All custom styles are in `dist/css/portfolio.css` in the portfolio repo.

- [Bootstrap's CSS Classes](http://getbootstrap.com/css/)
- [Bootstrap's Components](http://getbootstrap.com/components/)
