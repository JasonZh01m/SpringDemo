# SpringDemo
Spring in Action Tutoriol


```java
    /**
     * Supports FileUploads.
     */
    @Bean
    public MultipartResolver multipartResolver() {
        CommonsMultipartResolver multipartResolver = new CommonsMultipartResolver();
        multipartResolver.setMaxUploadSize(5000000);
        return multipartResolver;
    }
```
**示例code如下:**

	import java.io.FileInputStream;
	import java.io.FileNotFoundException;
	import java.io.FileOutputStream;
	import java.io.IOException;
	import java.io.ObjectInputStream;
	import java.io.ObjectOutputStream;
	import java.io.Serializable;
	
	/**
	 * @description 使用transient关键字不序列化某个变量
	 *        注意读取的时候，读取数据的顺序一定要和存放数据的顺序保持一致
	 */
	public class TransientTest {
	    
	    public static void main(String[] args) {
	        
	        User user = new User();
	        user.setUsername("Alexia");
	        user.setPasswd("123456");
	        
	        System.out.println("read before Serializable: ");
	        System.out.println("username: " + user.getUsername());
	        System.err.println("password: " + user.getPasswd());
	        
	        try {
	            ObjectOutputStream os = new ObjectOutputStream(
	                    new FileOutputStream("C:/user.txt"));
	            os.writeObject(user); // 将User对象写进文件
	            os.flush();
	            os.close();

