Repository with examples for openFga used by my blog https://ericksegaar.com

```cli
//create a store with the name hospital and the model model.fga
fga store create --name hospital --model model.fga

//write the tuples
fga tuple write --store-id=$FGA_STORE --file tuples.yaml

//query a check 
fga query check --store-id=$FGA_STORE user:joe view_in_detail health_record:treatment1
```

```
//add any assigned users to emergency_shift:now#shift as applicable to be approved_emergency_shift
 
fga tuple write emergency_shift:now#shift approved_emergency_shift hospital:VU --store-id=$FGA_STORE

fga query check user:joe approved_emergency_shift hospital:VU --contextual-tuple "user:joe shift emergency_shift:now" --store-id=$FGA_STORE
```