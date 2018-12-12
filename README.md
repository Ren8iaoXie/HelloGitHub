# HelloGitHub
only be a test
package com.Regex;

import java.util.regex.Matcher;
import java.util.regex.Pattern;
//关于正则表达式的各种功能
public class RegexDemo {

	public static void main(String[] args) {
		//匹配功能
//		matchesDemo();
    //切割功能
//		splitDemo();
    //替换功能  
//		replaceDemo();
    //获取功能
		getDemo();
	}

	public static void getDemo() {
		String num="da jia hao ,wo shi xie ren biao";
		//取出由3个字母组成的单词
		String regex="\\b[a-zA-Z]{3}\\b";
		//将规则编译成对象
		Pattern p=Pattern.compile(regex);
		//关联所需要操作的字符串
		Matcher m=p.matcher(num);
		//需要先找
		while(m.find()) {
			//在进行获取
			System.out.println(m.start()+":"+m.group()+":"+m.end());
		}
		
	}

	public static void replaceDemo() {
		String num="13456789086";
		num=num.replaceAll("(\\d{3})\\d{4}(\\d{3})", "$1****$2");
		System.out.println(num);
	}

	public static void splitDemo() {
//		String temp="zhangsan  lisi    wangwu";
//		String regex=" +";
//		String names[]=temp.split(regex);
//		for (String name  : names) {
//			System.out.println(name);
//		}
		
		
			//.代表任意字符，需要用\\将其转义
//		String temp="zhangsan.lisi.wangwu";
//		String regex="\\.";
//		String names[]=temp.split(regex);
//		for (String name  : names) {
//			System.out.println(name);
//		}
//		
		
		String temp="sfvssfekcs***sjinf#####sn!!sdc";
//为了实现规则的复用，用()将需要用的规则封装，就称为正则表达式的组,
//注意：需要先封装完在调用，即编号必须放在组后面
		String regex="(.)\\1+";
		String names[]=temp.split(regex);
		for (String name  : names) {
		System.out.println(name);
	}
	}

	public static void matchesDemo() {
		String num="13456789086";
		String regex="1[358]\\d{9}";
		boolean b=num.matches(regex);
		System.out.println(num+"...is..."+b);
	}

}
