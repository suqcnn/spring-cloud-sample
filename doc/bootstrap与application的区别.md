
bootstrap.yml  和application.yml  都可以用来配置参数
bootstrap.yml可以理解成系统级别的一些参数配置，这些参数一般是不会变动的
application.yml 可以用来定义应用级别的，如果搭配spring-cloud-config使用 application.yml里面定义的文件可以实现动态替换