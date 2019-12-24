<!-- ---
layout: post
title: Blogging Like a Hacker
--- -->


1.对数组中是 `Model``NSDictionary` 过滤 

定义模型 - `CXPersion`
```
@interface CXPerson : NSObject

@property (nonatomic, strong) NSString *name;
@property (nonatomic, assign) NSInteger age;

@end

@implementation CXPerson

@end
```

`tmp`数组创建
```
NSMutableArray *tmp = [NSMutableArray array];
for (int i = 0; i < 20; i ++) {
    CXPersion *p = [CXPerson new];
    p.name = [NSString stringWithFormat:@"value%d", i];
    p.age = arc4random_uniform(210);
    [tmp addObject:p];
}
```

过滤`Model`中指定`String`
```
// name 是 key, value2 是 value
NSPredicate *predicate = [NSPredicate predicateWithFormat:@"name = 'value2'"];
// array 是 tmp 所有 name = value2 的集合
NSArray *array = [tmp filteredArrayUsingPredicate:predicate];
```
过滤`Model`中指定条件
逻辑运算符号 `>` `<` `=` `>=` `<=` 都可以使用
```
NSPredicate *predicate = [NSPredicate predicateWithFormat:@"age < 100"];
NSArray *array = [tmp filteredArrayUsingPredicate:predicate];
```

`&&` `||` `AND` `OR`同理, 同时谓词不区分大小写
```
NSPredicate *predicate = [NSPredicate predicateWithFormat:@"name > 'abc' && age > 10"];
```

`IN``BEGINSWITH` `ENDSWITH` `CONTAINS` `LIKE` 的使用
```
NSPredicate *predicate = [NSPredicate predicateWithFormat:@"name IN {'abc' , 'def' , '123'}"];
NSPredicate *predicate = [NSPredicate predicateWithFormat:@"name BEGINSWITH 'A'"]; //name以A打头的person
NSPredicate *predicate = [NSPredicate predicateWithFormat:@"name ENDSWITH 'A'"]; //name以A结尾的person
NSPredicate *predicate = [NSPredicate predicateWithFormat:@"name CONTAINS 'A'"];
NSPredicate *predicate = [NSPredicate predicateWithFormat:@"name LIKE '*A*'"];
```

2.对数组中是 `String` 过滤 
使用 `SELF`
```
NSArray *array = [NSArray arrayWithObjects:@"abc", @"def", @"ghi", @"jkl", nil];
NSPredicate *pre = [NSPredicate predicateWithFormat:@"SELF == 'abc'"];
NSArray *array2 = [array filteredArrayUsingPredicate:pre];
```

3.对正则表达式的使用就不具体说明了
```
NSString *regex = @"";
NSPredicate *predicate = [NSPredicate predicateWithFormat:@"SELF MATCHES %@", regex];
[predicate evaluateWithObject:@""];
```

更多用法就以后慢慢补充了...







