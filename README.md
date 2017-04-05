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


	        } catch (FileNotFoundException e) {
	            e.printStackTrace();
	        } catch (IOException e) {
	            e.printStackTrace();
	        }
	        try {
	            ObjectInputStream is = new ObjectInputStream(new FileInputStream(
	                    "C:/user.txt"));
	            user = (User) is.readObject(); // 从流中读取User的数据
	            is.close();
	            
	            System.out.println("\nread after Serializable: ");
	            System.out.println("username: " + user.getUsername());
	            System.err.println("password: " + user.getPasswd());
	            
	        } catch (FileNotFoundException e) {
	            e.printStackTrace();
	        } catch (IOException e) {
	            e.printStackTrace();
	        } catch (ClassNotFoundException e) {
	            e.printStackTrace();
	        }
	    }
	}
	
	class User implements Serializable {
	    private static final long serialVersionUID = 8294180014912103005L;  
	    
	    private String username;
	    private transient String passwd;
	    
	    public String getUsername() {
	        return username;
	    }
	    
	    public void setUsername(String username) {
	        this.username = username;
	    }
	    
	    public String getPasswd() {
	        return passwd;
	    }
	    
	    public void setPasswd(String passwd) {
	        this.passwd = passwd;
	    }
	
	}
