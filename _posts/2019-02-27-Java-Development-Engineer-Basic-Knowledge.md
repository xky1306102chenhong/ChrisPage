---
layout: post
title: Java开发工程师的基本素养
---

{{ page.title }}
================

<p class="meta">{{ page.date | date_to_string }} - Changsha</p>

+ **自我介绍**
+ **介绍一下™、®、©、sm四个标识的含义?**
  + ™(Trademark)：商标，但没有法律含义和法律效力。
  + ®：指的是注册商标，表示商标已经注册成功。
  + ©：表示受版权保护的标识。
  + SM：服务标识(Service Mark)  
  
  ![avatar](/images/posts/2019-03-05/tm.png)
+ **Java规范(Java Specification)制定过程?**
  + [JCP](https://zh.wikipedia.org/wiki/JCP)(Java Community Process):是一个由Oracle(以前是Sun)领导的机构(mechanism)，通过[JSRs](https://zh.wikipedia.org/wiki/JCP)(Java Specification Requests，Java规范请求)的方式<span style="border-bottom:2px solid red;">制定Java技术的标准技术规范。</span>
  + JSR变为final状态前需要正式的公开审查，并由JCP Executive Committee投票决定。最终的JSR会提供一个参考实现，它是免费而且公开源代码的；还有一个验证是否符合API规范的Technology Compatibility Kit。
  + JCP设有执行委员会(EXECUTIVE COMMITTEE,EC)，阿里巴巴是执行委员会里唯一的中国公司。
+ **说说Java SE、Java EE和Java ME的关系？**(三种标准或规范)
   + Java SE(Java Platform, Standard Edition): <span style="border-bottom:2px solid red;">Java平台</span>，标准版可以在桌面(desktops)和服务器(servers)上开发和部署Java应用。JDK(Java SE Development Kit)实现了Java SE规范，例如有Oracle JDK，OpenJDK和AJDK等。
   + Java EE(Java Platform, Enterprise Edition): <span style="border-bottom:2px solid red;">Java平台</span>，企业版是社区驱动的企业软件的<span style="border-bottom:2px solid red;">标准</span>(例如Servlet、JAX-RS、JMS等)。2018年3月更名为Jakarta EE。Oracle提供的Java EE 8 Platform SDK是Java EE标准的参考实现。
   + Java ME(Java Platform, Micro Edition): <span style="border-bottom:2px solid red;">Java平台</span>，微型版为在嵌入式和物联网中的移动设备上运行的应用提供一个强健的、灵活的环境。
+ **为什么会存在J2SE与Java SE、J2EE与Java EE和J2ME与Java ME？**
  + 因为在Sun公司在1998年发表JDK1.2版本的时候，使用了新名称Java 2 Platform，所以就出现了J2XX。
  + 因为在2005年6月，JavaOne大会召开，SUN公司公开Java SE 6。此时，Java的各种版本已经更名以取消其中的数字“2”：J2EE更名为Java EE, J2SE更名为Java SE，J2ME更名为Java ME。
+ **谈谈Java EE和Spring之间的关系？**
  + 首先，Java EE指的是Java平台，企业版，它是社区驱动的企业软件标准。常见的标准有：
    + Servlet：定义了如何处理Web请求
    + JAX-RS：定义了如何编写RESTful的接口
    + JAX-WS：定义了如何编写基于XML的网络服务，即SOAP
    + JPA：定义了如何编写ORM和数据存取
    + JMS：定义了如何编写消息队列程序
    + CDI: 定义了如何编写依赖注入
    + JAX：定义了如何编写XML程序
    + JTA: 定义了如何编写事务相关代码
    + EJB：定义了如何编写”企业级Java Bean“
    + Java Server Faces：定义了如何使编写Web界面
    + ...
    
    <span style="border-bottom:2px solid red;">JDBC不是Java EE标准，因为只需按照JDK就可以引包。</span>
  + 在使用实现Java EE的API太难用了，在2002~2004年间，Rod Johnson总结了一套框架叫Spring，该框架是轻量级的，其中最重要的是IoC(控制反转)。
  经过多年发展，Spring发布了很多组件：
    + spring-core：Spring的Bean的管理，控制反转和程序上下文
    + spring-mvc: web开发中的model-view-controller
    + spring-data: 数据层访问和封装
    + spring-boot: spring全家桶自助配置和部署管理工具
    + spring-batch：一个简单的批处理框架
    + spring-cloud：支持与许多云服务接口的整合
    + spring-security：认证和权限管理
    + ...
    
   spring中其实大量使用或者实现了JavaEE标准。比如spring-mvc是在servlet基础之上的封装。spring本身并不提供容器，而是支持使用任何支持servlet标准的容器（如tomcat，jetty等）。spring-data也实现了JPA，通过标准接口对进行CRUD等。
   归根到底Spring只是想更好的解决实际问题。JavaEE的实现做得好的就用，做得不好的用比较恰当的方式独立实现或者封装。俗称“接地气”。  
+ **说说JDK、JRE和JVM的区别？**
  + 首先，JDK指定是Java SE开发工具包，是使用Java编程语言构建应用和组件的开发环境，它有Oracle JDK、OpenJDK和AJDK等不同的实现，它包括了Java运行环境JRE（Java Runtime Envirnment）、一堆Java工具（javac/java/jdb等）和Java基础的类库（即Java API 包括>rt.jar）。
  + JRE(Java Runtime Environment)是指Java运行时环境，它包含JVM，运行时类库(runtime class libraries)和Java application launcher等，
  是运行Java程序的必要环境。
  + JVM是指Java虚拟机，它是实现跨平台的最核心的部分，所有的java程序会首先被编译为.class的类文件，这种类文件可以在虚拟机上执行。

-------------------------------------------------------------------------------
### Spring ###
+ **介绍下Spring IoC？**
  + IoC是整个Spring框架的核心，它解决了在Java中只能import类，却import不了组件的问题。这个问题在js，python之类的环境中都是小菜一碟。但是Java中，如果没有IoC，程序员就要花大量的时间写new和set，组装整个服务的引用关系（你不觉得这很不人道吗？）。

-------------------------------------------------------------------------------
### 数据结构 ###
+ TCP(三次握手四次挥手，与UDP的区别，流量控制原理)
+ 排序算法
+ 5亿的数据如何排序
+ 进程间通信方式，那种效率高
+ 讲一下进程和线程的区别
+ 如何找数组内第二大元素
+ 两个非空链表相加
+ 剑指Offer
+ String和StringBuffer的区别
-------------------------------------------------------------------------------
### 算法 ###
+ 动态规划
  + [最小路径和](https://leetcode-cn.com/problems/minimum-path-sum/)  
    + 思路：  
    ![avatar](/images/posts/2019-03-14/minimum-path-sum.jpeg)
    + 代码：  
    ```
    import java.util.ArrayDeque;
    import java.util.Arrays;
    import java.util.Scanner;
    public class MinPathSum {
    
        public static int getMin(int a, int b){
            return a<b?a:b;
        }
        public static int minPathSum(int[][] grid){
            int m = grid.length;
            int n = grid[0].length;
            int k = m + n - 1;
            class Point{
                int x;
                int y;
    
                public Point(int x, int y) {
                    this.x = x;
                    this.y = y;
                }
    
                public void setX(int x) {
                    this.x = x;
                }
    
                public void setY(int y) {
                    this.y = y;
                }
            }
    
            int[][] dir = {{-1, 0}, {0, -1}};
    
            int[][] f= new int[m+5][n+5];
            for(int i=0;i<m+5;i++){
                Arrays.fill(f[i],9999999);
            }
            boolean[][] flag = new boolean[m][n];
            for(int i=0;i<m;i++){
    
                Arrays.fill(flag[i], false);
            }
            f[m-1][n-1] = grid[m-1][n-1];
            flag[m-1][n-1] = true;
            ArrayDeque queue = new ArrayDeque();
            Point point = new Point(m-1, n-1);
            queue.offer(point);
            while (!queue.isEmpty()){
                point = (Point) queue.poll();
                for (int i=0; i<2; i++){
                    int tmpX = point.x + dir[i][0];
                    int tmpY = point.y + dir[i][1];
                    if(tmpX>=0 && tmpX<m && tmpY>=0 && tmpY<n && flag[tmpX][tmpY]==false){
                        Point tmpPoint = new Point(tmpX,tmpY);
                        int a= grid[tmpPoint.x][tmpPoint.y]+f[tmpPoint.x+1][tmpPoint.y];
                        int b= grid[tmpPoint.x][tmpPoint.y]+f[tmpPoint.x][tmpPoint.y+1];
                        f[tmpPoint.x][tmpPoint.y] = getMin(a, b);
                        flag[tmpPoint.x][tmpPoint.y] = true;
                        queue.offer(tmpPoint);
                    }
                }
            }
            return f[0][0];
        }
        public static void main(String[] args) {
            Scanner sc = new Scanner(System.in);
            while(sc.hasNext()){
    
                int m = sc.nextInt();
                int n= sc.nextInt();
                int[][] grid = new int[m][n];
                for (int i =0; i< m;i++){
                    for (int j=0;j<n;j++){
                        grid[i][j]=sc.nextInt();
                    }
                }
                int ans=minPathSum(grid);
                System.out.println(ans);
            }
        }
    }

    ```
  + [最长回文子串](https://leetcode-cn.com/problems/longest-palindromic-substring/)
    + 思路：  
    ![avatar](/images/posts/2019-03-14/LPS.jpeg)
    + 代码：  
    ```java
    /**
     * @author Chris Chen
     * @date 2019/4/21 下午1:01
     */
    public class LongestPalindromicSubstring {
    
        public static int max(int a, int b){
            return a > b?a:b;
        }
    
        public static String longestPalindrome(String s) {
            String ans =null;
            int len = s.length();
            if(len == 0){
                return "";
            }
            int[][] f = new int[len][len];
            for(int i=0;i<len;i++){
                for(int j=0;j<len;j++){
                    if(i==j){
                        f[i][j]=1;
                    }else {
                        f[i][j]=0;
                    }
                }
            }
            class Point {
                int x;
                int y;
    
                public Point(int x, int y) {
                    this.x = x;
                    this.y = y;
                }
                public void setXY(int x,int y){
                    this.x =x;
                    this.y = y;
                }
            }
            Point point = new Point(0,0);
            for(int k=1;k<len;k++){
                for(int i=0;i<len-k;i++){
                    int j= i+k;
                            if(s.charAt(i)==s.charAt(j) && f[i+1][j-1]==j-i-1){
                                f[i][j]=2+f[i+1][j-1];
                            }else{
                                f[i][j]=max(f[i][j-1],f[i+1][j]);
                            }
                            if(f[i][j]>f[point.x][point.y]){
                                point.setXY(i,j);
                            }
                }
            }
            ans = s.substring(point.x,point.y+1);
            return ans;
        }
        public static void main(String[] args) {
            String s = "abcda";
            System.out.println(longestPalindrome(s));
        }
    }

    ```