# 把文件替换成.tsx
自动运行，next会检测项目并且创建ts环境 会给我们自动创建 next-dnv.d.ts 和tsconfig.json 
切记 _app.js这个是next的入口文件不能修改

## 安装typeORM 
使用的时候PostgreSQL数据库 安装对应的数据库驱动和typeORM依赖
~~~shell
yarn add typeorm reflect-metadata pg
~~~

配置tsconfig文件 
```json
"emitDecoratorMetadata": true,
"experimentalDecorators": true,
```

## 初始化typeorm 在父级目录执行
~~~
typeorm init --name blog-test[文件名] --database postgres[使用的数据库名]
~~~

## 当执行yarn dev 时next会修改回原来的tsconfig文件

当运行typeorm时发现 tytpeorm用的时ts-node转义的ts, 而next用的是babel转义
有两种选择， 安装ts-node转义typeorm 或者用babel转义typeorm


# 创建docker 容器
~~~shell
docker run -v blog-dat:/var/lib/postgresql/data -p 5432:5432 -e POSTGRES_USER=blog -e POSTGRES_PASSWORD=blog 
--name postgres 1f1bd4302537
~~~