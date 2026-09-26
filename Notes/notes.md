Okay, so the next is constructor injection by using the XML file.

How we will do the constructor injection?

Okay?

We have the `Student` class, and we make the `configuration.xml` file inside the `src/main/resources`.

In that file, for constructor injection, we use the **`bean` tag**, okay?

In both cases, means setter injection and constructor injection, in both cases we use the `bean` tag.

But for constructor injection, instead of the `property` tag, we use the **`constructor-arg` tag**.

Okay?

Because this is constructor injection, we pass the value through the constructor.

For example, suppose our `Student` class has a constructor:

```java
public Student(String name, int age) {
    this.name = name;
    this.age = age;
}
```

Then in the XML file, we can pass these values using `constructor-arg`.

```xml
<bean id="student" class="com.example.Student">

    <constructor-arg value="Rajesh"/>
    <constructor-arg value="23"/>

</bean>
```

Here, because we have not specified any name or index, Spring matches the constructor arguments according to their order.

Means the first `constructor-arg` value goes to the first constructor parameter, and the second `constructor-arg` value goes to the second constructor parameter.

Okay?

And if we want to explicitly specify which constructor parameter we are talking about, we can also use the `name` attribute.

For example:

```xml
<constructor-arg name="name" value="Rajesh"/>
<constructor-arg name="age" value="23"/>
```

Here, `name` represents the constructor parameter name.

We can also use `index` when we want to specify the position of the constructor parameter.

For example:

```xml
<constructor-arg index="0" value="Rajesh"/>
<constructor-arg index="1" value="23"/>
```

Here, `index="0"` means the first parameter, `index="1"` means the second parameter, and so on.

So basically, in setter injection, we use the **`property` tag** to inject the value through the setter method.

And in constructor injection, we use the **`constructor-arg` tag** to pass the value through the constructor.

And that's the whole thing about **constructor injection using the XML configuration file**.
