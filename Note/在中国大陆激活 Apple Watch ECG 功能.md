# 在中国大陆激活 Apple Watch ECG 功能
- 设备：iPhone 8 , Apple Watch Series 6
- 系统：iOS 14.0, WatchOS 7.0.2

## DFU 模式
进入 DFU 模式的方法：
- 通过数据线将 iPhone 和 PC 连接
- 

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