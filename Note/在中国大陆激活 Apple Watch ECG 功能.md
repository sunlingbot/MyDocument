# 在中国大陆激活 Apple Watch ECG 功能
- 设备：iPhone 8 , Apple Watch Series 6
- 系统：iOS 14.0, WatchOS 7.0.2

## DFU 恢复
假如刷机失败/恢复失败导致白苹果，即 iPhone 卡在 logo 页面无限重启，可以通过 DFU 模式进入 itunes 恢复出厂设置，但是会清空所有数据，所以务必做好备份。 
- 通过数据线将 iPhone 和 PC 连接
- 按下调高音量按钮再快速松开，按下调低音量按钮再快速松开。然后按住侧边按钮，直到看到 Apple 标志。
- 在 PD 端打开 itunes ，自动识别手机并更新 iOS

## 警告

[Apple 支持：白苹果解决方案](https://discussionschinese.apple.com/thread/251717050)

```JavaScript
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
	<key>HKAtrialFibrillationDetectionOnboardingCompleted</key>
	<integer>1</integer>
	<key>HKElectrocardiogramOnboardingCompleted</key>
	<integer>3</integer>
</dict>
</plist>
```

```JavaScript
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
	<key>HKElectrocardiogramOnboardingCompleted</key>
	<integer>3</integer>
	<key>HKAtrialFibrillationDetectionOnboardingCompleted</key>
	<integer>1</integer>
</dict>
</plist>
```