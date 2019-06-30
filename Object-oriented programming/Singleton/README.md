# Singleton

## Singleton パターンとは何か?

「[オブジェクト指向における再利用のためのデザインパターン](https://www.amazon.co.jp/%E3%82%AA%E3%83%96%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88%E6%8C%87%E5%90%91%E3%81%AB%E3%81%8A%E3%81%91%E3%82%8B%E5%86%8D%E5%88%A9%E7%94%A8%E3%81%AE%E3%81%9F%E3%82%81%E3%81%AE%E3%83%87%E3%82%B6%E3%82%A4%E3%83%B3%E3%83%91%E3%82%BF%E3%83%BC%E3%83%B3-%E3%82%A8%E3%83%AA%E3%83%83%E3%82%AF-%E3%82%AC%E3%83%B3%E3%83%9E/dp/4797311126)」（通称GoF本）に記載されているオブジェクト指向のデザインパターンのうちの1つ。

端的に説明すると、生成するインスタンスの数を1つに制限するデザインパターンのことである。

## どんなときに使われる？

あるクラスのインスタンスが1つしか生成されないように制限するため、インスタンスの状態を保持したかったり、クラス間で共通のメソッド・プロパティにアクセスしたい場合に使われる。

## Singletonクラスの定義

```java
public class Singleton {

    // ①
    private static Singleton singleton = new Singleton();
    // ②
    private Singleton() {
        System.out.println("Cretae Instance");
    }
    // ➂
    public static Singleton getInstance() {
        return singleton;
    }
}
```

①自身の型のインスタンスが privateなクラス変数(static変数)として定義されている  
→static変数はクラスロード時に唯一のインスタンスが生成されるので、どこからでも参照できるグローバル領域で管理される。

②外部から生成されないようにコンストラクタをprivateにしている

③インスタンスを返すためのクラス関数が定義されている

すなわち、Singletonクラスは利用する側からは、
* newできない
* 必ず同一のオブジェクトが返される
クラスであると言える。
