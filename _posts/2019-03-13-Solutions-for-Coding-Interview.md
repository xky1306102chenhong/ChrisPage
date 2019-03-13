---
layout: post  
title: 剑指 offer 题解  
---

{{ page.title }}
================

<p class="meta">{{ page.date | date_to_string }} - Changsha</p>  

+ 第一题  
**题目描述**  
在一个二维数组中（每个一维数组的长度相同），每一行都按照从左到右递增的顺序排序，每一列都按照从上到下递增的顺序排序。请完成一个函数，输入这样的一个二维数组和一个整数，判断数组中是否含有该整数。  
**代码**  
```java
import java.util.Scanner;
public class FindTargetInTwoDimensionArray {
    public static boolean Find(int target, int[][] array){
        boolean flag = false;
        for (int i=0;i<array.length;i++){
            for (int j=0;j<array[i].length;j++){
                if (target == array[i][j]){
                    flag = true;
                    break;
                }
            }
            if (flag == true){
                break;
            }
        }
        return flag;
    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        while (sc.hasNext()){
            int target = sc.nextInt();
            int n = sc.nextInt();
            int m = sc.nextInt();
            int[][] array = new int[n][m];
            for(int i=0; i<n; i++){
                for (int j=0; j<m; j++){
                    array[i][j] = sc.nextInt();
                }
            }
            boolean result = Find(target, array);
            System.out.println(result);
        }
    }
}
```  
+ 第二题  
**题目描述**   请实现一个函数，将一个字符串中的每个空格替换成“%20”。例如，当字符串为
We Are Happy.则经过替换之后的字符串为We%20Are%20Happy。  
**代码**  
```java
import java.util.Scanner;
public class ReplaceSpace {
    public static String replaceSpace(StringBuffer str){
        String newStr = "";
        for (int i=0; i<str.length();i++){
            if(str.charAt(i) == ' '){
                newStr += "%20";
            } else {
                newStr += str.charAt(i);
            }
        }
        return newStr;
    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        while (sc.hasNext()){
            String str = sc.nextLine();
            StringBuffer stringBuffer = new StringBuffer(str);
            String newStr = replaceSpace(stringBuffer);
            System.out.println(newStr);
        }
    }
}
```