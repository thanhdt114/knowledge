# Singleton Pattern
## 1. Singleton Pattern là gì?

Singleton là 1 trong 5 design pattern của nhóm Creational Design Pattern.

Singleton đảm bảo chỉ duy nhất một thể hiện (instance) được tạo ra và nó sẽ cung cấp cho bạn một method để có thể truy xuất được thể hiện duy nhất đó mọi lúc mọi nơi trong chương trình.

![Singleton Pattern](/design_pattern/Creational/Images/singleton-pattern.png "San Juan Mountains")

Ví dụ:
```java
package com.gpcoder.patterns.creational.singleton;
  public class EagerInitializedSingleton {
    private static final EagerInitializedSingleton INSTANCE = new EagerInitializedSingleton();
    // Private constructor to avoid client applications to use constructor
    private EagerInitializedSingleton() {  
    }
    public static EagerInitializedSingleton getInstance() {
      return INSTANCE;
    }
}
```

## 2. Tại sao cần sử dụng Singleton Pattern
## 3. Sử dụng Singleton Pattern như thế nào

