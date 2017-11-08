###注意:很多人都习惯了objc中的点语法,点语法用于方便的通过属性的setter,getter去操作成员变量,但是在懒加载的编写过程中应用点语法时一不小心可能会导致程序进入死循环比如: 
```
- (NSMutableArray *)users      // 1部分
{
    if (!_users) {    // 2部分
        _users = [NSMutableArray array];  // 3部分
    }
    return _users;  // 4部分
}
```

第一部分:self.users是一个getter
第二部分:不能写成 !self.users 这也是一个getter,getter中有getter会造成死循环
第三部分:可以使用self.users,这是一个setter
第四部分:不能使用self.users,这也是一个getter,getter中有getter会造成死循环