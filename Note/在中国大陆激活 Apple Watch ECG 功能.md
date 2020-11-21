# 在中国大陆激活 Apple Watch ECG 功能
由于 ECG 心电图属于医疗功能，所以在该功能上线之前，必须通过所在地区的监管部门认证，而 Apple Watch 目前仅通过了美国 FDA 认证，在中国大陆未能获得认证，因此苹果公司就没有在国内广而告之地宣传 ECG 功能，自然也就导致了比较少的人不知道 ECG 为何物。

Apple Watch 作为一款具备医疗功能的**消费级**可穿戴设备，近年来也逐步下沉到医疗领域，不论其专业性如何，总是能给普罗大众提供一定程度地参考意见。现在就来介绍，即使身处限制区域，如何自己动手激活 Apple Watch ECG 功能？[查看支持 ECG 功能的国家/地区列表。](https://www.apple.com/hk/watchos/feature-availability/#branded-ecg)

## 准备工作
Google 了一波看到全网解锁 ECG 功能，用得最多的办法就是在淘宝花个二三十块，要么买个别人已经预先开通 ECG 功能的 Apple ID，要么就是将自己的 Apple ID 及密码提供给商家做些小手段。私以为，这种办法具有非常高的风险，很可能会导致个人信息和 iCloud 数据泄露。贪图便宜一时爽，可这也为隐私安全埋下了后患。

所以本文主要介绍了一种完全可控地、不需要借助第三方 ID 来开通 ECG 功能的手段。另外本方法，更适用于动手能力强和拥有较高搜商的同学们。

## 设备与系统
- Device: iPhone 8 , Apple Watch Series 6
- OS: iOS 14.0, WatchOS 7.0.2

## 警告
- 本教程仅提供学习使用，请勿用于商业研究目的，在未经许可的国家或地区开启 ECG 功能或贩卖开通的方法可能会触犯当地的法律。
- 本教程仅适用于支持 ECG 功能的 Apple Watch。
- 请务必要对 iPhone 做好完整的备份，这起到了关键的作用。
- 存在被 Apple 官方封禁的风险。

## DFU 恢复
假如刷机失败/恢复失败导致白苹果，即 iPhone 卡在 logo 页面无限重启，可以通过 DFU 模式进入 itunes 恢复出厂设置，但是会清空所有数据，所以务必做好备份。 
- 通过数据线将 iPhone 和 PC 连接
- 按下调高音量按钮再快速松开，按下调低音量按钮再快速松开。然后按住侧边按钮，直到看到 Apple 标志。
- 在 PD 端打开 itunes ，自动识别手机并更新 iOS


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

## 参考连接
- [Apple 支持：白苹果解决方案](https://discussionschinese.apple.com/thread/251717050)