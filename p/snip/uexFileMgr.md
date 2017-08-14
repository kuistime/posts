

* wgt://对应widget的沙盒根路径,可读可写；
* res://对应widget目录下的wgtRes路径,只可读不可写。

安卓
```
wgt://  =>  /storage/sdcard0/widgetone/apps/<appId>/
wgts:// => /storage/sdcard0/widgetone/widgets/
res://  =>  /data/data/com.simcere.dev/files/widget/wgtRes/
box:// =>  /data/data/com.simcere.dev/files/
files:/// => /
```

iOS

主应用，测试源/Documents/widget/start.html

```
wgt://  =>  /Documents/apps/aaaio10008/
wgts:// => /Documents/widgets/
res://  =>  /Documents/widget/wgtRes/
box:// =>  /Documents/box/
files:/// => /Documents/widget/files:///
```

iOS子应用

子应用，测试源/Documents/widgets/aaaio10061/html/index.html

```
wgt://  =>  /Documents/widgets/aaaio10061/
wgts:// => /Documents/widgets/
res://  =>  /Documents/widgets/aaaio10061/wgtRes/
box:// =>  /Documents/box/
files:/// => /Documents/widgets/aaaio10061/html/files:///
```
