# CaibdeHUD
一个HUD的提示控件
***
# 内容
起因是因为项目中需要这么一个项目提示，之前都是用别人的第三方，最近就索性自己尝试写一个自己的HUD
***
首先我定义了一个枚举，分别表示不同类型的HUD，分为只有小菊花的，小菊花和文字信息的，单纯的文字信息的这三个类
```objc
typedef NS_ENUM(NSInteger, HUDType){
    /**
     *  加载不带有文字信息
     */
    HUDLoadingWithOutMessage = 0,
    /**
     *  加载带有文字信息
     */
    HUDLoadingWithMessage = 1,
    /**
     *  直接弹出一个文字信息
     */
    HUDMessage = 2,
};
```
接下来，定义了一个Show的方法
```objc
+ (instancetype)showInView:(UIView *)view
                  withText:(NSString *)text
                  duration:(NSTimeInterval)duration
                      type:(HUDType)type
                  animated:(BOOL)animated;
```

最后在你要显示的控制器去实现以下就行了，就像这样：
```objc
    self.hudWithMessage = [CaibdeHUD showInView:self.view withText:@"1234" duration:1.5 type:HUDLoadingWithMessage animated:YES];
```
