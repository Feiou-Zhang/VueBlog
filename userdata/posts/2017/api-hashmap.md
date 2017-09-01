title: Post
------------------------------------
<!-- en-US:+ -->

> The **differences** between put(K,V), replace(K,V),replace(K,V,V)

`put` will add new K,V or overwrite the old V if the K is already existing. 

##### Does not have to match anything to add or update.
 

`replace` will only update the V if the K is existing, otherwise, just do nothing.

##### The K has to match to update.

`replace(K,V,V)` will only update the V if the K is existing and you provide the right old V.

##### Both K and V have to match to update.

> It will be the same thing for the remove(K) and remove(K,V)

`remove(K,V)` only remove the pair when the K,V matches the existing pair, while the remove(K) will remove the pair only if the K is existing.
