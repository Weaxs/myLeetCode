> # 工程模式

> 简单工程模式 (Simple Factory)

    又称为静态工厂方法(Static Factory Method)模式，它属于类创建型模式。
    在简单工厂模式中，可以根据参数的不同返回不同类的实例。简单工厂模式专门定义一个类来负责创建其他类的实例，被创建的实例通常都具有共同的父类。
    
    角色:
        Factory：工厂角色
            工厂角色负责实现创建所有实例的内部逻辑
        Product：抽象产品角色
            抽象产品角色是所创建的所有对象的父类，负责描述所有实例所共有的公共接口
        ConcreteProduct：具体产品角色
            具体产品角色是创建目标，所有创建的对象都充当这个角色的某个具体类的实例。
            
    适用环境
    工厂类负责创建的对象比较少：由于创建的对象较少，不会造成工厂方法中的业务逻辑太过复杂。
    客户端只知道传入工厂类的参数，对于如何创建对象不关心：客户端既不需要关心创建细节，甚至连类名都不需要记住，只需要知道类型所对应的参数。
    
> 工厂方法模式 (Factory Method)

    也叫虚拟构造器(Virtual Constructor)模式或者多态工厂(Polymorphic Factory)模式，它属于类创建型模式。
    在工厂方法模式中，工厂父类负责定义创建产品对象的公共接口，而工厂子类则负责生成具体的产品对象，这样做的目的是将产品类的实例化操作延迟到工厂子类中完成，即通过工厂子类来确定究竟应该实例化哪一个具体产品类。
    
    角色:
        Product             抽象产品
        ConcreteProduct     具体产品
        Factory             抽象工厂
        ConcreteFactory     具体工厂
        
    适用环境:
    一个类不知道它所需要的对象的类：在工厂方法模式中，客户端不需要知道具体产品类的类名，只需要知道所对应的工厂即可，具体的产品对象由具体工厂类创建；客户端需要知道创建具体产品的工厂类。
    一个类通过其子类来指定创建哪个对象：在工厂方法模式中，对于抽象工厂类只需要提供一个创建产品的接口，而由其子类来确定具体要创建的对象，利用面向对象的多态性和里氏代换原则，在程序运行时，子类对象将覆盖父类对象，从而使得系统更容易扩展。
    将创建对象的任务委托给多个工厂子类中的某一个，客户端在使用时可以无须关心是哪一个工厂子类创建产品子类，需要时再动态指定，可将具体工厂类的类名存储在配置文件或数据库中。
    
> 抽象工厂模式 (Abstract Factory)

    提供一个创建一系列相关或相互依赖对象的接口，而无须指定它们具体的类。抽象工厂模式又称为Kit模式，属于对象创建型模式。
    
    角色:
    AbstractFactory：抽象工厂
    ConcreteFactory：具体工厂
    AbstractProduct：抽象产品
    Product：具体产品
    
    适用环境:
    一个系统不应当依赖于产品类实例如何被创建、组合和表达的细节，这对于所有类型的工厂模式都是重要的。
    系统中有多于一个的产品族，而每次只使用其中某一产品族。
    属于同一个产品族的产品将在一起使用，这一约束必须在系统的设计中体现出来。
    系统提供一个产品类的库，所有的产品以同样的接口出现，从而使客户端不依赖于具体实现。
    