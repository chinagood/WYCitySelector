# WYCitySelector
快速搭建一个城市选择器
***
# 1. WYCitySelector 效果展示

![普通选择.gif](https://github.com/yiyi0202/WYCitySelector/blob/master/普通选择.gif)

![搜索.gif](https://github.com/yiyi0202/WYCitySelector/blob/master/搜索.gif)
***
# 2. 使用方法
（1）下载 [WYCitySelector](https://github.com/yiyi0202/WYCitySelector)，直接将 Demo 里的 **WYCitySelectorCodes** 文件夹拖入项目中；

（2）在需要跳转到城市选择界面的控制器里导入头文件：
```
#import "WYCitySelectViewController.h"
```
（3）在需要跳转到城市选择界面的触发事件里实例化  **WYCitySelectViewController**：
```
- (void)citySelectButtonAction:(UIButton *)button {
    
    WYCitySelectViewController *citySelecteVC = [[WYCitySelectViewController alloc] init];
    
    citySelecteVC.tintColor = [UIColor orangeColor];// 分区索引及搜索关键字的颜色
    
    // 选择城市之后的回调, cityName 为选择的城市
    citySelecteVC.block = ^(NSString *cityName) {
        
        // 根据自己的需求实现效果即可
        [self.citySelectButton setTitle:cityName forState:(UIControlStateNormal)];
    };
    
    [self presentViewController:[[UINavigationController alloc] initWithRootViewController:citySelecteVC] animated:YES completion:nil];
}
```
***
# 3. 一些配置
（1）AppDelegate.m 全局设置一些样式：
```
#pragma mark - 导航栏
    
    [UINavigationBar appearance].barTintColor = [UIColor orangeColor];// 导航栏的颜色
    [UINavigationBar appearance].titleTextAttributes = @{NSFontAttributeName : [UIFont systemFontOfSize:17.0], NSForegroundColorAttributeName : [UIColor whiteColor]};// 导航栏中间字体的大小和颜色
    [UINavigationBar appearance].tintColor = [UIColor whiteColor];// 导航栏 barButtonItem 的颜色
    
    
#pragma mark - searchBar
    
    [UISearchBar appearance].tintColor = [UIColor orangeColor];// 光标的颜色
    [[UIBarButtonItem appearanceWhenContainedIn:[UISearchBar class], nil] setTitleTextAttributes:@{NSForegroundColorAttributeName : [UIColor colorWithRed:195 / 255.0 green:195 / 255.0 blue:195 / 255.0 alpha:1]} forState:UIControlStateNormal];// 取消按钮的颜色
```
（2）Info.plist 
```
    <!-- 隐私权限申请 -->
    <key>NSLocationWhenInUseUsageDescription</key>
    <string>App需要您的同意，才能访问位置</string>
```
```
    <!-- 本地化 -->
	<key>CFBundleDevelopmentRegion</key>
	<string>zh_CN</string>
```
***
# 4. 完成
做了以上工作，就可以完成一个城市选择器。
***
