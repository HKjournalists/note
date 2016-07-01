##读《Effective java》
####1.多参数对象可以尝试使用Builder来创建。
最近写代码时，多参数的model创建设值时会有大量的set（）语句，表示使代码十分难看。。不能忍。而换用长长的构造器的话，参数多起来，一是不易理解，二是容易出错（参数一个对一个啊，眼睛花了！！）！！下面上代码：
	
	/**
	 * Created by wangjia on 16/3/24 22:15
	 * desc:builder!!
	 */
	public class User {
	    private final String name;
	    private final int age;
	    private final Timestamp createTime;
	    private final Date birthday;
	    private final Timestamp updateTime;
	
	    private User(Builder builder) {
	        this.name = builder.name;
	        this.age = builder.age;
	        this.createTime = builder.createTime;
	        this.birthday = builder.birthday;
	        this.updateTime = builder.updateTime;
	    }
	
	    public static class Builder {
	        private String name;
	
	        private int age;
	        private Timestamp createTime;
	        private Date birthday;
	        private Timestamp updateTime;
	
	        public Builder(String name) {
	            this.name = name;
	        }
	
	        public Builder age(int age) {
	            this.age = age;
	            return this;
	        }
	
	        public Builder createTime(Timestamp createTime) {
	            this.createTime = createTime;
	            return this;
	        }
	
	        public Builder birthday(Date birthday) {
	            this.birthday = birthday;
	            return this;
	        }
	
	        public Builder age(Timestamp updateTime) {
	            this.updateTime = updateTime;
	            return this;
	        }
	
	        public User build() {
	            return new User(this);
	        }
	    }
	}

构造方式

    User wj = new User.Builder("WJ")
                .age(12)
                .birthday(birthday)
                .createTime(createTime)
                .build();

使用场景：类构造器或者静态工厂有大量参数时。。。。。            
 好处：
> 1.保证代码简洁的同时，保证易于阅读和理解。  
> 2.可变参数的形式，十分灵活。  
> 3.避免了使用大量set()时的不安全问题（每次set（）都会使对象的状态不一致！）  

缺点:  
> 1.需要先建builder类，会增加一些工作量，和一些开销。（十分注重性能的情况下，需要注意）.