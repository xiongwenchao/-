实验目的
掌握字符串String及其方法的使用
掌握异常处理结构
业务要求
内容：利用已学的字符串处理知识编程完成《长恨歌》古诗的整理对齐工作，写出功能函数，并运行。达到如下功能：

1.每7个汉字加入一个标点符号，奇数时加“，”，偶数时加“。”
2.允许提供输入参数，统计古诗中某个字或词出现的次数
3.考虑操作中可能出现的异常，在程序中设计异常处理程序
核心代码
1定义字符串输入要处理的古诗：
String gs ="汉皇重色思倾国御宇多年求不得杨家有女初长成养在深闺人未识"
+ "天生丽质难自弃一朝选在君王侧回眸一笑百媚生六宫粉黛无颜色"
+ "春寒赐浴华清池温泉水滑洗凝脂侍儿扶起娇无力始是新承恩泽时"
+ "云鬓花颜金步摇芙蓉帐暖度春宵春宵苦短日高起从此君王不早朝";
StringBuffer s = new StringBuffer(gs);
2利用for循环来处理古诗，使其加入标点符号，并对其输出：
for (int i = 7; i < s.length(); i = i + 15) {
					s.insert(i, ",");
				}
				for (int i = 15; i < s.length() + 1; i = i + 16) {
					s.insert(i, "。");
				}
				for (int i = 16; i < s.length(); i = i + 17) {
					s.insert(i, "\n");
				}
				System.out.println(s);
3 异常处理语句：
try {……
 } catch (Exception e) {……
}
4查询字或词出现次数语句：
Scanner in = new Scanner(System.in);// 定义scanner，等待输入
            System.out.println("输入所要查询的字或词:");
		    String wz = in.nextLine();
			String a = s.toString();
			int indexStart = 0;
			int count = 0;
			while (true) {
					int tm = a.indexOf(wz, indexStart);
					if (tm >= 0) {
						count++;
						indexStart = tm + wz.length();
					} else {
						break;
					}
				}
				if (count == 0) {
					System.out.println("这个字或词在古诗中没有出现");
				} else {
					System.out.println("这个字或词共出现了" + count + "次");
				}
			}
实验输出
汉皇重色思倾国,御宇多年求不得。
杨家有女初长成,养在深闺人未识。
天生丽质难自弃,一朝选在君王侧。
回眸一笑百媚生,六宫粉黛无颜色。
春寒赐浴华清池,温泉水滑洗凝脂。
侍儿扶起娇无力,始是新承恩泽时。
云鬓花颜金步摇,芙蓉帐暖度春宵。
春宵苦短日高起,从此君王不早朝。
输入所要查询的字或词:
时
这个字或词共出现了1次
实验感想
通过此次实验，掌握了字符串String及其方法的使用，并掌握了异常处理结构的方法编写，对于字符串的处理更加熟悉。
