������.class�ļ��еĳ����أ��������ڼ䱻jvmװ�أ����ҿ������䡣String��intern()�����������䳣���ص�һ����������һ��Stringʵ��str����intern()����ʱ��java���ҳ��������Ƿ�����ͬunicode���ַ�������������У��򷵻������ã����û�У����ڳ�����������һ��unicode����str���ַ����������������á�  
��3��  
```
String s0=��kvill��;
String s1=new String(��kvill��);
String s2=new String(��kvill��);
System.out.println(s0==s1);
S1.intern();
S2=s2.intern();
System.out.println(s0==s1);
System.out.prntln(s0==s1.intern());
System.out.println(s0==s2);
```
���Ϊ��  
```
False
False //��Ȼִ����s1.intern()�������ķ���ֵû�и���s1
True
True
```
������Ƴ�һ���������⣺  
����˵����ʹ��String.intern()�������Խ�һ��String�ౣ�浽һ��ȫ�ֵ�String���У����������ֵͬ��unicode�ַ����Ѿ���������У���ô�÷������ر��������ַ����ĵ�ַ������ڱ���û����ֵͬ���ַ��������Լ��ĵ�ַע�ᵽ���С���������ȫ�ֵ�String�����Ϊ�����ԵĻ������һ�仰������ڱ���û����ֵͬ���ַ��������Լ��ĵ�ַע�ᵽ���С��Ǵ�ġ�  
��4��  
```
String s1=new String(��kvill��);
String s2=s1.intern();
System.out.println(s1==s1.intern());
System.out.println(s1+�� ��+s2);
System.out.println(s2==s1.intern());
```
����ǣ�  
```
False
Kvill kvill
True
```
����û������һ����kvill�����������Գ�������һ��ʼû�С�kvill���ģ������ǵ���s1.intern()����ڳ��������������һ����kvill��������ԭ���Ĳ��ڳ������еġ�kvill����Ȼ���ڣ�Ҳ�Ͳ��ǡ����Լ��ĵ�ַע�ᵽ�������С��ˡ�  
��5��  
```
String str1=��java��;
String str2=��blog��;
String s=str1+str2;
System.out.println(s==��javablog��);
```
�����false��Jvmȷʵ������String str1=��java��;��String������ڳ���������������ڱ���ʱ��ô���ģ���String s=str1+str2;��������ʱ�̲���֪����Ҳ����˵str1+str2���ڶ��ﴴ���ģ����Խ��Ϊfalse�ˡ�   