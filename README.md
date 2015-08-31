# iToast
提示信息弹窗

~~~ javascript

#import "iToast.h"

NSArray *messages = @"出错了，赶紧找问题吧！", @"正确！", @"因为你的不努力，现在发现了很多存在的隐患，你必须在规定的时间点完成所有的工作。否则后果很严重！"];
NSArray *positons = @[[NSNumber numberWithInteger:PositionBottom], [NSNumber numberWithInteger:PositionCenter], [NSNumber numberWithInteger:PositionTop]];
NSString *message = messages[arc4random() % messages.count];
NSNumber *position = positons[arc4random() % positons.count];
[[iToast shareIToast] showText:message postion:position.integerValue];

~~~