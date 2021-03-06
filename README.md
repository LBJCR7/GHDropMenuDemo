![](https://img.shields.io/badge/platform-iOS-red.svg) ![](https://img.shields.io/badge/language-Objective--C-orange.svg) 
![](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg) 
![](https://img.shields.io/appveyor/ci/gruntjs/grunt.svg)
![](https://img.shields.io/vscode-marketplace/d/repo.svg)
![](https://img.shields.io/cocoapods/l/packageName.svg)
# GHDropMenuDemo

`筛选菜单` `京东筛选菜单` `美团筛选菜单` `电商通用筛选菜单`

---

![Untitled.gif](https://upload-images.jianshu.io/upload_images/1419035-0da7858245c4693a.gif?imageMogr2/auto-orient/strip)

---
### 2019.1.1更新

```diff
+ 增加代理方法创建菜单
+ 增加数据源

```
#### 使用方法:

```Objective-C
GHDropMenu *dropMenu = [GHDropMenu creatDropMenuWithConfiguration:nil frame:CGRectMake(0, kGHSafeAreaTopHeight,kGHScreenWidth, 44) dropMenuTitleBlock:^(GHDropMenuModel * _Nonnull dropMenuModel) {
        weakSelf.navigationItem.title = [NSString stringWithFormat:@"筛选结果: %@",dropMenuModel.title];
    } dropMenuTagArrayBlock:^(NSArray * _Nonnull tagArray) {
        [weakSelf getStrWith:tagArray];
    }];
    dropMenu.durationTime = 0.5;
    dropMenu.delegate = self;
    dropMenu.dataSource = self;
    [self.view addSubview:dropMenu];
```
#### 实现数据源方法:
```Objective-C
// 返回筛选菜单标题的个数
- (NSArray *)columnTitlesInMeun:(GHDropMenu *)menu {
}

// 返回每列筛选菜单的选项
- (NSArray *)menu:(GHDropMenu *)menu numberOfColumns:(NSInteger)columns {
}
```
--- 

### 2018.12.30更新

```diff
+ 增加吸附效果的筛选菜单
+ 分别可选tableView悬浮菜单和collectionView悬浮菜单
+ 增加单独侧滑菜单筛选
+ dropMenu的title自适应宽度
+ 适配x,xs,xr,xsmax
+ 去掉刚开始创建的动画
+ 自定义筛选标题,自定义筛选内容,自定义筛选标签,自定义筛选头部内容
+ 数组越界处理
+ 价格输入筛选
+ 实现tag标签,单选,多选,取消选中效果
+ 保留上次选中选项
+ 动画展开,移除
+ 可以重新传入模型,重新刷新数据源
+ 选中内容通过代理的方式回调
+ 对原有项目无污染,直接拖进项目即可使用

- 去掉titleView初始化动画
- 修复无法点击bug
```


### 使用方法
* GHDropMenu文件夹 拖入项目中
* 导入 `GHDropMenu.h `

```Objective-C
    /** 配置筛选菜单模型 */
    GHDropMenuModel *configuration = [[GHDropMenuModel alloc]init];
    /** 配置筛选菜单是否记录用户选中 默认NO */
    configuration.recordSeleted = NO;
    /** 设置数据源 */
    configuration.titles = [configuration creaDropMenuData];
    
    /** 创建dropMenu 配置模型 &&frame */
    GHDropMenu *dropMenu = [[GHDropMenu alloc]creatDropMenuWithConfiguration:configuration frame:CGRectMake(0, 0, [UIScreen mainScreen].bounds.size.width, 44)];
    dropMenu.delegate = self;
    
    [self.view addSubview:dropMenu];
    
```

* 需要构造json数据
```
详见demo
```

### 在使用中如有任何问题欢迎骚扰我,如果对你有帮助请点帮我一个✨,小弟感激不尽:blush:

### qq群 `621286914 `

[关注我的博客 没事写点小东西](https://www.jianshu.com/u/884a67907187)

---
