# django-custom-parser-class
uploading image in nested serializer to django restframework is problem so its a simple solution. there to file one for client side, other server side.
client side class take a object and on run call it return a FormData instance which includes json key and all files with in object with keys file_id_{xx}.
on server side the parser decode the sended data and recreate the object as it was on client side

## Object obtain from React-final-form
```
obj=
{
    "attribute":[],
    "category":"Car",
    "name":"WagonR",
    "description":"Maruti Wagon R is a 5 seater hatchback car",
    "productimg":[<Object ListData>]
}
```
```
aFormDataInstance=new toMultipart().run()

instance have following keys:
json=
{
    "attribute":[],
    "category":"Car",
    "name":"WagonR",
    "description":"Maruti Wagon R is a 5 seater hatchback car",
    "productimg":[file_id_0,file_id_1]
}
file_id_0:{**file object}
file_id_1:{**file object}
```
once its pass through custom parser its recover back to origional form as 
```
{
    "attribute":[],
    "category":"Car",
    "name":"WagonR",
    "description":"Maruti Wagon R is a 5 seater hatchback car",
    "productimg":[<File>,<File>]
}
```
