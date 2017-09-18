## 启动mysql服务
- 通过控制servers.msc,在服务中查看mysql服务的名字使用命令可以开关mysql服务,以管理员身份运行cmd
    ```
    net start mysql57
    net stop mysql57
    ```

## mysql创建数据库
```
create DATABASE tb2;
SHOW DATABASES;
```

## 使用数据库
```
use tb2;
select database();
```

## 创建数据表
```
create table user(
	id TINYINT not null PRIMARY key auto_increment,
	username varchar(20) not null
);
show create TABLE user; 显示创建的表代码
show COLUMNS from user; 显示当前表的列
```

## 查找表
```
select * from user;
```

## 像表中插入内容
```
insert user(username) value ('jw');
```


## 添加主键约束
```
alter table student change id id int not null primary key ;
alter table student add CONSTRAINT student_id PRIMARY KEY (id);
```

## 添加外键约束
```
create table student(
	id int not null PRIMARY KEY auto_increment,
	name varchar(20),
	pid int,
	FOREIGN KEY (pid) REFERENCES province(id) 
);
alter table student add FOREIGN key (pid) REFERENCES province(id);
```
## 添加唯一约束
```
alter table student add CONSTRAINT UNIQUE (username);
```

## 添加默认约束
```
alter table student alter number set DEFAULT 30;
```

## 修改列的顺序
```
alter table student MODIFY id int not null AFTER username;
```

## 修改列名
```
alter table province change COLUMN city province varchar(20)
```

## 删除列
```
alter table student drop COLUMN id;
```

## 删除主键
```
alter table student drop primary key;
```

## 删除外键
```
alter table student drop FOREIGN key student_ibfk_1
```

## 删除默认约束
```
alter table student alter number drop default ;
```
