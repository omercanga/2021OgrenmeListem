# Day-8
javada çok fazla dönen bir foreach için debug koymak için bir sayaç konup bu değere ulaşma noktasına debug konabilir.
örnek uygulama1
```java
int index = 0;
for(Element song : question) {
    System.out.println("Current index is: " + (index++));
}
```
örnek uygulama2
```java
for (Index<String> each: With.index(stringArray)) {
    each.value;
    each.index;
    ...
}
```
