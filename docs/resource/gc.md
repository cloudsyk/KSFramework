
在KEngine的资源模块中，需要手工的对资源进行释放，减少引用。
但是当引用为0后，会有一个延迟时间，才进行真正的资源释放。

这是因为，实际项目开发中，清理掉所有的现有资源，可能同时重新初始化这样的一个资源，即引用为0的同一帧内，可能引用立刻又会改变。

因此，引用为0，释放资源，显然不符合项目真实情况。

事实上，Unity的GameObject.Destroy也有类似的机制，Destroy并非立刻触发的。