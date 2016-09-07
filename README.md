# KGJSonConverter
This is a library for Android to convert/parse JSON Text into a List/ArrayList of a Generic Class.

### Now you can watch video tutorials of using this lib on YouTube at:
* https://www.youtube.com/watch?v=PRQvn__YkCM and 
* https://www.youtube.com/watch?v=T05kFxvPmk8

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
# Follow Me
 * Get more free source code at https://github.com/kosalgeek
 * Watch my video tutorials at my YouTube channel https://youtube.com/user/oumsaokosal
 * Like my Facebook Page at https://facebook.com/kosalgeek
 * Follow me on Twitter https://twitter.com/okosal
 * Get more tutorials at http://www.kosalgeek.com and http://www.top12review.com

# Donation
#### If you think this library have saved your life, please support me by donating a few bucks, just for my coffee :)
[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](
https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=oumsaokosal01%40gmail%2ecom&lc=US&currency_code=USD&bn=PP%2dDonationsBF%3abtn_donateCC_LG%2egif%3aNonHosted)

<input type="image" src="https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif" border="0" name="submit" alt="PayPal - The safer, easier way to pay online!">
<img alt="" border="0" src="https://www.paypalobjects.com/en_US/i/scr/pixel.gif" width="1" height="1">
</form>
 
# LICENSE

(The MIT License)
Copyright (c) 2016 KosalGeek. (kosalgeek at gmail dot com)

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the 'Software'), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
