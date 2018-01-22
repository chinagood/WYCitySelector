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
