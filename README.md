# KGJSonConverter
This is a library for Android to convert/parse JSON Text into a List/ArrayList of a Generic Class.

#SETUP
1. Download *KGJsonConverter.jar* into your machine > 
   Copy the file and paste into **app>libs**  of your project in Android Studio >
   Right click on it > Choose *Add as Library*
2. Download GSON 2.2.4 library from http://grepcode.com/snapshot/repo1.maven.org/maven2/com.google.code.gson/gson/2.2.4 >
   Add to the same **app>libs** folder of your project > Right click on it > Choose *Add as Library*
   
   Or add **compile 'com.google.code.gson:gson:2.2.4'** into your dependencies

#USAGE
1- Convert to ArrayList:
```java
ArrayList<ModelClass> userList = new JsonConverter<ModelClass>().toArrayList(jsonString, ModelClass.class);
```
2- Convert to List:
```java
List<ModelClass> userList = new JsonConverter<ModelClass>().toList(jsonString, ModelClass.class);
```
Replace *ModelClass* with your model class.
#SAMPLE CODES

This is a model class, e.g. Product. Note that each attribute has *@SerializedName* annotation. This is very important to let the converter knows which attribute uses which name.
```java
import com.google.gson.annotations.SerializedName;

public class Product {
    @SerializedName("id")
    public Integer id;
    @SerializedName("name")
    public String name;
    @SerializedName("qty")
    public Double qty;
    @SerializedName("price")
    public Double price;
}
```
The code below shows how to convert to ArrayList:
```java
String jsonString = "[{\"id\":\"P1\",\"name\":\"Coke\",\"qty\":\"5\",\"price\":\"2.5\"}]";

ArrayList<Product> products = 
            new JsonConverter<Product>().toArrayList(jsonString, Product.class);

//test output result
String output = "";
for(Product p: products){
    output += "id: " + p.id;
    output += ", name: " + p.name;
    output += ", qty: " + p.qty;
    output += ", price: " + p.price;
}
Toast.makeText(this, output, Toast.LENGTH_LONG).show();
```
#FOLLOW ME
Check out my blog about this library and others at http://www.kosalgeek.com 

Also subscribe my YouTube channel at https://youtube.com/c/kosalgeekvideos 

Follow me at https://twitter.comkosalgeek
