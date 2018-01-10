# Magisk-op3Tnfc

## **注意事项**

- 本教程在 Oneplus3T 氢公测16版上使用正常
- 对于移动用户，必须先去移动营业厅办理NFC-Sim卡，并下载安装移动和包客户端：http://tsm.cmpay.com/html/commons/?m=getmocam&os=Android
- 若办理的NFC-Sim卡未开卡，可以刷入magisk模块修改当前机型为移动所支持的手机型号(例ZTE-BA602T)后进行开卡

## 使用步骤

1. 关闭支付宝、微信等NFC功能，确保端口不被占用

2. 刷入当前包，重启手机

3. 打开和包，安装相应卡片

4. 如果遇到“Not allowed to bind to service Intent...”之类的错误，需要在终端下赋予该卡片程序SmartcardServicePermission label权限：

``` shell
pm grant com.cmcc.hebao org.simalliance.openmobileapi.SMARTCARD
pm grant com.umpay.bjmobilelife org.simalliance.openmobileapi.SMARTCARD
```

5.修改libnfc-nxp.conf的第474行：33, 04, 00, 00, 00, 00,的后8个数字为门禁卡ID，如12, 34, 56, 78,

6.最终效果可以实现为亮屏下可刷门禁，锁屏/暗屏下可刷地铁/公交。
  ​
