java.util.concurrent
# �̳߳�
```java
public interface Executor
```
```java
public interface ExecutorService extends Executor
```
```java
public abstract class AbstractExecutorService implements ExecutorService
```

```java
public class ThreadPoolExecutor extends AbstractExecutorService 
```

```java
    public ThreadPoolExecutor(int corePoolSize,//�̳߳��������߳���
                              int maximumPoolSize,//����߳���
                              long keepAliveTime,//���������߳������̴߳��ʱ��
                              TimeUnit unit,//keepAliveTime�ĵ�λ
                              BlockingQueue<Runnable> workQueue,//�������
                              ThreadFactory threadFactory,//�̹߳���
                              RejectedExecutionHandler handler)//�ܾ�����
```
������->  
ʵ���߳��� < corePoolSize:�����߳�  
ʵ���߳��� > corePoolSize:��  
����û��:�������  
��������:��  
���߳��� < maximumPoolSize:�������߳�ִ��  
���߳��� > maximumPoolSize:�ܾ�����  
����  
  
���У�  
ֱ���ύ�Ķ���(����Ϊ0����Զ���ǣ���������)��SynchronousQueue  
�н���������(����Ϊ����)��ArrayBlockingQueue  
�޽���������(����Ϊ������)��LinkedBlockingQueue  
�����������(PriorityBlockingQueue,�����Ķ���Ϊ�Ƚ��ȳ�,����������Լ�������˳��)  
```java
BlockingQueue ������������ʽ���֣����ڲ����������㵫�����ڽ���ĳһʱ�̿�������Ĳ�����
��������ʽ�Ĵ���ʽ��ͬ��
��һ�����׳�һ���쳣��
�ڶ����Ƿ���һ������ֵ��null �� false������ȡ���ڲ�������
���������ڲ������Գɹ�ǰ�������ڵ�������ǰ�̣߳�
���������ڷ���ǰֻ�ڸ��������ʱ��������������
 	�׳��쳣        	����ֵ 	���� 	��ʱ
���� 	add(e) 	       offer(e) put(e) 	offer(e, time, unit)
�Ƴ� 	remove() 	poll() 	take() 	poll(time, unit)
��� 	element() 	peek() 	������ 	������
```
```java
Executors ����
//�̶��������̳߳�
public class Executors {
    public static ExecutorService newFixedThreadPool(int nThreads) {
        return new ThreadPoolExecutor(nThreads, nThreads,
                                      0L, TimeUnit.MILLISECONDS,
                                      new LinkedBlockingQueue<Runnable>());
    }
//ֻ��һ���̵߳��̳߳�
    public static ExecutorService newSingleThreadExecutor() {
        return new FinalizableDelegatedExecutorService
            (new ThreadPoolExecutor(1, 1,
                                    0L, TimeUnit.MILLISECONDS,
                                    new LinkedBlockingQueue<Runnable>()));
    }
//���̸߳��þ��ã�û�оʹ���������Ϊ0���߳����������
    public static ExecutorService newCachedThreadPool() {
        return new ThreadPoolExecutor(0, Integer.MAX_VALUE,
                                      60L, TimeUnit.SECONDS,
                                      new SynchronousQueue<Runnable>());
    }
//
    public static ScheduledExecutorService newSingleThreadScheduledExecutor() {
        return new DelegatedScheduledExecutorService
            (new ScheduledThreadPoolExecutor(1));
    }
}
```

���Դ���:
```java
public class ThreadPoolExecutorTest {
	public static void main(String[] args) {
		ExecutorService es = new ThreadPoolExecutor(5, 
				5, 
				0L, 
				TimeUnit.MILLISECONDS, 
				new SynchronousQueue<Runnable>(),
				new ThreadFactory() {
					@Override
					public Thread newThread(Runnable r) {
						Thread th =new Thread(r);
						System.out.println("create"+th);
						return th;
					}
				}
				);
		for (int i = 0; i < 5; i++) {
			es.submit(new Runnable() {
				@Override
				public void run() {
					System.out.println("Runnable");
				}});
		}
	}
}
```


# ������ ���Է������롢���ж�