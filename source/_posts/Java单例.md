---
title: Java单例
date: 2019-10-16 23:43:14
type: "java_singleton"
---

### 双重校验锁实现
````
/**
 * @author :jiang
 * @time :2019-10-17
 */
public class DoubleLock {

    private volatile static DoubleLock doubleLock;

    private DoubleLock() {
    }

    public DoubleLock getDoubleLock() {
        if (null == doubleLock) {
            synchronized (DoubleLock.class) {
                if (null == doubleLock) {
                    doubleLock = new DoubleLock();
                }
            }
        }
        return doubleLock;
    }

}
````

### 枚举实现
````
/**
 * @author :jiang
 * @time :2019-10-17
 */
public enum EnumSingleton {

    INSTANCE;

    private SingletonClass singleton;

    EnumSingleton() {
        this.singleton = new SingletonClass();
    }

    public SingletonClass getSingleton() {
        return this.singleton;
    }
}

class SingletonClass {
    int i = 0;

    public SingletonClass() {
        System.out.println(++i);
    }
}

class test {
    public static void main(String[] args) {
        EnumSingleton.INSTANCE.getSingleton();
    }
}

````
