# java-Experiment-4
# 计G201 2020322058    刘芸杉
## 阅读程序
+ 设计学生的个人信息

+ 创建student对象并构造Scanner类的对象scan，接收从控制台输入的信息。    

+ 封装学生信息，按要求统计关键字的个数并添加合适的标点符号。

+ 将学生信息、作业统一存储到一个文件夹中，。

## 实验目的
+ 掌握字符串String及其方法的使用
+ 掌握文件的读取/写入方法
+ 掌握异常处理结构

## 实验过程
1. 构造Scanner类的对象，sc.hasNext()要求输入一个值，String name = sc.next()中,会从sc中取出我们输入的那个值返回到name中并赋值给name
2. 统计关键字出现的次数通过while循环语句实现；
3. 根据要求填写标点符号，使用if---else语句按要求奇数时加“，”，偶数时加“。”
4. 使用FileInputStream来实现文件的读取，使用try--catch--finally来实现，为防止乱码使用gbk编码格式
5. 使用FileOutputStream来实现文件的写入
   
 ## 3.核心方法
 + 读取文件
 ```
 FileInputStream fis = null;
		File file = new File("C:\\Users\\Lenovo\\Desktop\\1.txt");
		try {
			fis = new FileInputStream(file);
			int len = 0;
			byte[] buff = new byte[1024];
			while((len = fis.read(buff)) != -1){
				fileStr=new String(buff, 0, len,"gbk");//gbk编码格式 出现乱码的话修改此处
			}
		} catch (Exception e) {
			e.printStackTrace();
		}finally{
			try {
				fis.close();
			} catch (IOException e) {
				e.printStackTrace();
			} 
    ```
```

 + 写入文件
      ```
    FileOutputStream fos=new FileOutputStream("C:\\Users\\Lenovo\\Desktop\\2.txt"); 
		fos.write(stuStr.getBytes());
		fos.write(newStr.getBytes());
		fos.write(countStr.getBytes());
		fos.close();//关闭资源
       ```
  
  ## 4.实验结果
```
请输入学生姓名:刘芸杉
请输入学生年龄:23
请输入学生班级:计G202
请输入学生性别:女
请输入需要统计的字或者词:汉
开始读取文件.....
读取文件结束.....
开始统计关键字.....
关键字：汉,出现：1次
关键字统计结束.....
开始处理文件信息.....
处理文件信息结束.....
开始组装学生信息.....
组装学生信息结束.....
开始写入信息.....
写入信息结束.....
```
  ## 5.实验感想
  1. 通过这次实验更加熟悉了如何使用异常处理结构
  2. 练习了对文件的写入和读取
  
  
