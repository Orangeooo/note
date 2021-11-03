# mysql相关

AndroidManifest中添加权限

```
<uses-permission android:name="android.permission.INTERNET"/>
```

Demo代码

```java
package com.example.mysqlcon;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.widget.TextView;

import java.sql.*;

public class MainActivity extends AppCompatActivity {
    


    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        new Thread(runnable).start();

    }

    Runnable runnable = new Runnable() {

            private Connection con = null;

            @Override

            public void run() {

                // TODO Auto-generated method stub

                try {

                    Class.forName("com.mysql.jdbc.Driver");

                    //引用代码此处需要修改，address为数据IP，Port为端口号，DBName为数据名称，UserName为数据库登录账户，Password为数据库登录密码

                    con = DriverManager.getConnection("jdbc:mysql://1.117.54.58:3306/DB?useSSL=false&useUnicode=true&characterEncoding=UTF-8", "root","1qazxsw2");

                } catch (SQLException e) {

                    // TODO Auto-generated catch block

                    System.out.println(e.getMessage());

                } catch (ClassNotFoundException e) {

                    // TODO Auto-generated catch block

                    System.out.println(e.getMessage());

                }
                try {
                    System.out.println("aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa");
                    insert("测试", "小戴", con);



                } catch (Exception e) {

                }


            }


        };



    private static void insert(String name, String age, Connection con) throws SQLException {

        PreparedStatement pstmt;

        System.out.println("bbbbbbbbbbbbbbbbbbbb");

        String sql = "insert into user(type,type_name,isd) values(?,?,?)";
        pstmt=con.prepareStatement(sql);
        System.out.println("cccccccccccccccccccc");
        pstmt.setString(1,"测试");
        System.out.println("ffffffffffffffffffffff");
        pstmt.setString(2,"小戴");
        pstmt.setString(3,"2");

        System.out.println("ggggggggggggggggggggggggg");
//            ResultSet res = st.executeQuery(sql);
        pstmt.executeUpdate();
        System.out.println("ddddddddddddddddddddd");


        System.out.println("插入成功！");
        System.out.println("eeeeeeeeeeeeeeeeeeeee");
        System.out.println("插入失败！");

//            if (res == null) {
//
//            } else {
//               while (res.next()){
//                    System.out.println(res.getString("type")+res.getString("type_name"));
//                }
//                res.close();
        pstmt.close();
        con.close();


    }
}
```

