MJRefresh-1
===========

比EGOtableviewpullrefresh好用的下拉刷新，下拉加载更多


###Step 1，导入

```obj-c
#import "MJRefresh.h"
```

###Step 2,添加方法

```obj-c
- (void)addHeader
{
    // 添加下拉刷新头部控件
    [self.tableView addHeaderWithCallback:^{
        // 进入刷新状态就会回调这个Block
        [pushModel firstPage];
    }];
    
    [self.tableView headerBeginRefreshing];
}

- (void)addFooter
{
    // 添加上拉刷新尾部控件
    [self.tableView addFooterWithCallback:^{
        // 进入刷新状态就会回调这个Block
        [pushModel nextPage];
    }];
}
```

###Step3 ，在数据完成调用的地方添加代码：
```ojb-c
    [self.tableView headerEndRefreshing];
    [self.tableView footerEndRefreshing];

```

###Good Luck!





