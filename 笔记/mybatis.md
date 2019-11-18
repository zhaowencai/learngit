## mybatis

1. 实体对象属性和数据库表列名不对应时，两种解决方案：

- 使用 resultMap 元素进行映射关系描述
    <resultMap id="userResultMap" type="User">
        <id property="id" column="user_id" />
        <result property="username" column="user_name"/>
        <result property="password" column="hashed_password"/>
    </resultMap>
- SELECT 语句中对列使用别名
    <select id="selectUsers" resultType="User">
        select
        user_id             as "id",
        user_name           as "userName",
        hashed_password     as "hashedPassword"
        from some_table
        where id = #{id}
    </select>
    
2. 高级结果映射

- <association property="author" javaType="Author"><association/> 复杂类型（某个引用类型）的关联
- <resultMap id="blogResult" type="Blog">
  <id property="id" column="blog_id" />
  <result property="title" column="blog_title"/>
  <association property="author" javaType="Author">
    <id property="id" column="author_id"/>
    <result property="username" column="author_username"/>
    <result property="password" column="author_password"/>
    <result property="email" column="author_email"/>
    <result property="bio" column="author_bio"/>
  </association>
  </resultMap>
- <collection property="comments" ofType="Comment"><collection/> 某个引用类型的集合
- <id><id/> 一个 ID 结果，标记出作为 ID 的结果可以帮助提高整体性能，会在比较对象实例时用到
- <discriminator><discriminator/> 根据结果值来判断使用哪个 resultMap 
  
3. 动态SQL
  
- choose, when, otherwise; choose 元素，它有点像 Java 中的 switch 语句,例如：

4. 本地缓存
   
- Mybatis 使用到了两种缓存：本地缓存（local cache）和二级缓存（second level cache）
- 每当一个新 session 被创建，MyBatis 就会创建一个与之相关联的本地缓存。任何在 session 执行过的查询语句本身都会被保存在本地缓存中，那么，相同的查询语句和相同的参数所产生的更改就不会二度影响数据库了。本地缓存会被增删改、提交事务、关闭事务以及关闭 session 所清空
- 默认情况下，本地缓存数据可在整个 session 的周期内使用，这一缓存需要被用来解决循环引用错误和加快重复嵌套查询的速度，所以它可以不被禁用掉，但是你可以设置 localCacheScope=STATEMENT 表示缓存仅在语句执行时有效