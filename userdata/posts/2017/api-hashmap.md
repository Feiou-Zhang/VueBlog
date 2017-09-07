title: Post
------------------------------------
<!-- en-US:+ -->

### Java 8 new furtures
---


> The **differences** between put(K,V), replace(K,V),replace(K,V,V) 

`put` will add new K,V or overwrite the old V if the K is already existing. 

##### Does not have to match anything to add or update.
 

`replace(K, V)` will only update the V if the K is existing, otherwise, just do nothing.

##### The K has to match to update.

`replace(K,V,V)` will only update the V if the K is existing and you provide the right old V.

##### Both K and V have to match to update.

> It will be the same thing for the remove(K) and remove(K,V)

`remove(K,V)` only remove the pair when the K,V matches the existing pair, while the remove(K) will remove the pair only if the K is existing.

> getOrDefault(K, V) and putIfAbsent(K, V)

`getOrDefault(K, V)` will do the following code

```java
if(hashmap.containsKey(K))
    return hashmap.get(K);
else
    return V;
```
`putIfAbsent(K, V)` will only put the (K, V) when there is no such a `K` or the `K` is mapping to null, it is very similar with the `replace(K, V)` but in the opposite way,

> the way to return all the Keys or Values *Just need to be aware the names of the methods*

`keySet()` returns all the keys as the keys are all unique

`valuse()` returns all the values as the values can be duplicated
