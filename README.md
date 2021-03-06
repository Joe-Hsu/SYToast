# SYToast
提示信息弹窗


使用介绍 
  * 自动导入：使用命令`pod 'SYIToast'`导入到项目中
  * 手动导入：或下载源码后，将源码添加到项目中
  

使用示例

* SYIToast的使用示例

导入头文件
```
#import "SYIToast"
// 或
#import "SYIToast+SYCategory.h"
```

```
NSArray *messages = @[@"出错了，赶紧找问题吧！", @"正确！", @"因为你的不努力，现在发现了很多存在的隐患，你必须在规定的时间点完成所有的工作。否则后果很严重！"];
NSArray *positons = @[[NSNumber numberWithInteger:iToastPositionBottom], [NSNumber numberWithInteger:iToastPositionCenter], [NSNumber numberWithInteger:iToastPositionTop]];
NSString *message = messages[arc4random() % messages.count];
NSNumber *position = positons[arc4random() % positons.count];
```

属性设置
```
// 背景颜色
[[SYIToast shareIToast] setBgroundColor:[UIColor greenColor]];

// 字体颜色 
[[SYIToast shareIToast] setTextColor:[UIColor orangeColor]];

// 字体大小
[[SYIToast shareIToast] setTextFont:[UIFont systemFontOfSize:20.0]];

// 菊花转颜色
[[SYIToast shareIToast] setIndicatoColor:[UIColor redColor]];
```

方法1
```
// 文本提示
[[SYIToast shareIToast] showToastInView:self.view text:message type:SYIToastTypeDefault position:position.integerValue hide:NO enable:YES];

// 菊花转提示
[[SYIToast shareIToast] showToastInView:self.view text:message type:SYIToastTypeIndicato position:position.integerValue hide:NO enable:YES];

// 自定义视图提示
UIImageView *imageView = [[UIImageView alloc] initWithImage:[UIImage imageNamed:@"withNetwork"]];
imageView.frame = CGRectMake(0.0, 0.0, 50, 50.0);
[[SYIToast shareIToast] setCustomView:imageView];
[[SYIToast shareIToast] showToastInView:self.view text:message type:SYIToastTypeCustom position:position.integerValue hide:NO enable:YES];
```

方法2 扩展类方法
```
if (iToastPositionTop == position.integerValue) {
    [SYIToast alertWithTitle:message];
} else if (iToastPositionCenter == position.integerValue) {
    [SYIToast alertWithTitleCenter:message];
} else if (iToastPositionBottom == position.integerValue) {
    [SYIToast alertWithTitleBottom:message];
}
```


* SYToastView的使用示例

导入头文件
```
#import "SYToastView.h"
```

属性设置
```
// 背景颜色
ToastView.bgroundColor = [UIColor yellowColor];

// 字体大小
ToastView.textFont = [UIFont systemFontOfSize:12.0f];

// 字体颜色
ToastView.textColor = [UIColor redColor];
```

提示信息
```
[ToastView showInView:view position:PositionTop message:@"没有网络..没有网络..没有网络..没有网络..没有网络..没有网络" image:[UIImage imageNamed:@"withoutNetwork"] animation:YES];
```

效果图

* 随机位置显示：顶端提示效果，或中间提示效果，或底端提示效果

![SYToast](./images/SYToast.gif) 


#### 修改说明
* 20181115
  * 版本号：1.1.7
  * 修改显示重影的异常
  
* 20181114
  * 版本号：1.1.6
  * 修改完善
    * 自定义父视图
    * 自定义显示类型：文本、菊花转、自定义视图

* 20181019
  * 版本号：1.1.4
  * 删除HUD
  
* 20180816
  * 版本号：1.1.2
  
  * 版本号：1.1.1
  * 功能完善：修改异常

* 20180815
  * 版本号：1.1.0
  * 功能完善
    * 添加属性设置
      * 延迟隐藏时间
      * 背景颜色设置
      * 字体颜色设置
      * 字体大小设置
    * 修改隐藏方法
    * 添加`MBProgressHUD`封装类库`SYHUDProgress`
    * 添加`SYNetworkStatusView`顶部弹窗提示封装类（常用于网络状态提示）

* 20180802
  * 版本号：1.0.0
  * 修改完善
  
* 20170607
  * 方法名称修改，避免其他库文件方法同名。

