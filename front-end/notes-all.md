# input��ǩ  
### ��ѡ��  
Ĭ��ѡ�� <input type="radio" checked="checked" >  
���鼴�������ѡ�򣬶���һ�������ͬһʱ�䣬ֻ��ѡ��һ����ѡ������name������ͬ���� 
```  
dota<input type="radio" name="activity" value="dota" > <br/>  
LOL<input type="radio" name="activity"  value="lol"> <br/>  
```
### ��ѡ��
```
<p>����������ʲô��</p>
ѧϰjava<input type="checkbox" value="ѧϰjava" > <br/>
������<input type="checkbox" checked="checked"  name="activity" value="tokyohot" > <br/>
dota<input type="checkbox" value="dota" > <br/>
LOL<input type="checkbox" value="lol"> <br/>
```
### �����б�  
```
<select >
 <option >����ʦ</option>
 <option >����������</option>
 <option >ң��</option>
</select>
//---size��ʾ���У�multiple�Ƿ��ѡ��selectedĬ��ѡ��---
<select size="3" multiple="multiple">
 <option >����ʦ</option>
 <option selected="selected">����������</option>
 <option selected="selected">ң��</option>
</select>
```
### �ı���
```
<textarea>abc
def
</textarea>
``` 
### ���ð�ť  
`<input type="reset" value="����">`

# ѡ����  
## css������ѡ����  
```
1��ѡ������p��ǩ
<style>
p{ <!-- ѡ������p��ǩ -->
  color:red;
}
#p1{ <!-- ѡ������idΪp1�ı�ǩ -->
  color:blue;
}
.class1{ <!-- ѡ������classΪclass1�ı�ǩ -->
  color:blue;
}
</style>
p.blue{ <!-- classΪ"blue"�ı�ǩ -->
  color:blue;
}
```
## jqueryѡ����  
```
$("p")  $("#p1")  $(".class1")  

$("selector1 selector2")  :ѡ�� selector1�µ�selector2Ԫ�� �� 

$("selector:first") ����ѡ���������ĵ�һ��Ԫ��  
$("p:first")
$("selector:last") ����ѡ�������������һ��Ԫ��   

$("selector:odd") ����ѡ��������������Ԫ��
$("selector:even") ����ѡ����������ż��Ԫ��
��Ϊ�ǻ���ģ����Ե�һ�ŵ��±���ʵ��0(��ż��) 


```

# λ��
```
HTML DOM position ����   
static 	           Ĭ�ϡ�λ������Ϊ static ��Ԫ�أ���ʼ�ջᴦ��ҳ���������λ��
                   ��static Ԫ�ػ�����κ� top��bottom��left �� right ��������
relative 	λ�ñ�����Ϊ relative ��Ԫ�أ��ɽ������������������λ�õĵط���
                 ��� "left:20" �ὫԪ������Ԫ������λ����� 20 ��           ���ص�λ�á�
absolute 	λ������Ϊ absolute ��Ԫ�أ��ɶ�λ������ڰ�������Ԫ�ص�ָ�����ꡣ
                 ��Ԫ�ص�λ�ÿ�ͨ�� "left"��"top"��"right" �Լ�                     "bottom" �������涨��
fixed 	          λ�ñ�����Ϊ fixed ��Ԫ�أ��ɶ�λ���������������ڵ�ָ�����ꡣ
                  ��Ԫ�ص�λ�ÿ�ͨ�� "left"��"top"��"right" �Լ�"bottom" �������涨�����۴��ڹ������Ԫ�ض��������Ǹ�λ�á�
                 ������ IE7��strict ģʽ����

```
# �ĵ���
���ϵ���   
�����ⲿ�ļ�(js��css)���൱����ջ   
$(function(){...})������ɺ�   
js�ȶ�var������function����Ԥ���룬var������Ϊundefined   
document.write()�Ƚϸ��ӣ��ӳټ��أ�����������ջ�������걾ҳ������ջ   
