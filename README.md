**一、在实验过程中易出现以下问题：**
    1).Encoded password does not look like BCrypt
    2).id is null

**二、解决方式**
    因为springsecurity在最新版本升级后,默认把之前的明文密码方式给去掉了;
    解决方式:
        1.一般我们客户端账号密码不需要加密,所以在这里实现 
            `.passwordEncoder(NoOpPasswordEncoder.getInstance())` 
             告诉security客户端密码不需要加密
        2.使用BCryptPasswordEncoder将数据库中client密码加密
        
        官方文档说明：https://spring.io/blog/2017/11/01/spring-security-5-0-0-rc1-released#password-storage-updated
        参考文献：https://www.jianshu.com/p/3d87a52048f6