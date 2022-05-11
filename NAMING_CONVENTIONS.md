# 10 JavaScript Naming Conventions Every Developer Should Know

Following standard naming conventions increases readability and makes it easier to understand your code. However, many developers are not aware of how to use naming conventions correctly, and sometimes they make things complicated.

In this article, I will discuss 10  [JavaScript](https://en.wikipedia.org/wiki/JavaScript)  naming convention best practices you should follow.

# 1. Naming Convention for Variables

JavaScript variable names are case-sensitive. Lowercase and uppercase letters are distinct. For example, you can define three unique variables to store a dog name, as follows.

var DogName = 'Scooby-Doo';  
var dogName = 'Droopy';  
var DOGNAME = 'Odie';  
console.log(DogName); // "Scooby-Doo"  
console.log(dogName); // "Droopy"  
console.log(DOGNAME); // "Odie"

However, the most recommended way to declare JavaScript variables is with  **camel case**  variable names. You can use the camel case naming convention for all types of variables in JavaScript, and it will ensure that there aren’t multiple variables with the same name.

// bad  
var dogname = 'Droopy';   
// bad  
var dog_name = 'Droopy';   
// bad  
var DOGNAME = ‘Droopy’;   
// bad  
var DOG_NAME = 'Droopy';   
// good  
var dogName = 'Droopy';

The names of variables should be self-explanatory and describe the stored value. For example, if you need a variable to store a dog’s name, you should use dogName instead of just Name since it is more meaningful.

// bad  
var d = 'Scooby-Doo';  
// bad  
var name = 'Scooby-Doo';  
// good  
var dogName = 'Scooby-Doo';

# 2. Naming Convention for Booleans

When it comes to Boolean variables, we should use  **is**  or  **has** as prefixes. For example, if you need a Boolean variable to check if a dog has an owner, you should use hasOwner as the variable name.

// bad  
var bark = false;  
// good  
var isBark = false;  
// bad  
var ideal = true;  
// good  
var areIdeal = true;  
// bad  
var owner = true;  
// good  
var hasOwner = true;

# 3. Naming Convention for Functions

JavaScript function names are also case-sensitive. So, similar to variables, the  **camel case**  approach is the recommended way to declare function names.

In addition to that, you should use descriptive nouns and verbs as prefixes. For example, if we declare a function to retrieve a name, the function name should be getName.

// bad  
function name(dogName, ownerName) {   
  return '${dogName} ${ownerName}';  
}  
  
// good  
function getName(dogName, ownerName) {   
  return '${dogName} ${ownerName}';  
}

# 4. Naming Convention for Constants

JavaScript constants are also case-sensitive. However, these constants should be written in  **uppercase** because they are nonchanging variables.

var LEG = 4;  
var TAIL = 1;  
var MOVABLE = LEG + TAIL;

If the variable declaration name contains more than one word, you should use  **UPPER_SNAKE_CASE.**

var DAYS_UNTIL_TOMORROW = 1;

All the constants should be defined at the start of your file, method, or class.

# 5. Naming Convention for Classes

Naming convention rules for JavaScript classes are pretty similar to functions. We have to use descriptive titles that explain the class’s capabilities.

The major difference between function and class names is that we have to use  **Pascal case**  for class names.

class DogCartoon {   
  constructor(dogName, ownerName) {   
    this.dogName = dogName;   
    this.ownerName = ownerName;   
  }  
}  
  
var cartoon = new DogCartoon('Scooby-Doo', 'Shaggy');

# 6. Naming Convention for Components

JavaScript components are widely used in front-end frameworks like React. Although components are used in the DOM, treating them similarly to classes and using  **Pascal case** to define names is recommended.

// bad  
function dogCartoon(roles) {   
  return (   
    < div >   
      < span > Dog Name: { roles.dogName } < /span>   
      < span > Owner Name: { roles.ownerName } < /span>   
    < /div>   
  );  
}   
  
// good  
function DogCartoon(roles) {   
  return (   
    < div >   
      < span > Dog Name: { roles.dogName } < /span>   
      < span > Owner Name: { roles.ownerName } < /span>   
    < /div>   
  );  
}

Since the initial letter is always written in uppercase, a component stands out from native HTML and web components when utilized.

<div>   
  <DogCartoon   
    roles={{ dogName: 'Scooby-Doo', ownerName: 'Shaggy' }}   
  />  
</div>

# 7. Naming Convention for Methods

Although there are some differences, the structure of a JavaScript function and a method are pretty similar. So, naming convention rules are the same.

We must use  **camel case** to declare JavaScript methods and use verbs as prefixes to make names more meaningful.

class DogCartoon {  
  constructor(dogName, ownerName) {   
    this.dogName = dogName;   
    this.ownerName = ownerName;   
  }  
  
  getName() {   
    return '${this.dogName} ${this.ownerName}';   
  }  
}  
  
var cartoon= new DogCartoon('Scooby-Doo', 'Shaggy');  
  
console.log(cartoon.getName());  
// "Scooby-Doo Shaggy"

# 8. Naming Convention for Denoting Private Functions

Underscores ( _ ) are widely used in languages like MySQL and PHP to define variables, functions, and methods. But in JavaScript, an underscore is used to denote private variables or functions.

For example, if you have a private function name like toonName, you can denote it as a private function by adding an underscore as a prefix (_toonName).

class DogCartoon {   
  constructor(dogName, ownerName) {   
    this.dogName = dogName;   
    this.ownerName = ownerName;   
    this.name = _toonName(dogName, ownerName);   
  }   
  _toonName(dogName, ownerName) {   
    return `${dogName} ${ownerName}`;   
  }   
}  
  

    var cartoon = new DodCartoon('Scooby-Doo', 'Shaggy');   
      
    // good  
    var name = cartoon.name;  
    console.log(name);  
    // "Scooby-Doo Shaggy"   
      
    // bad  
    name =cartoon._toonName(cartoon.dogName, cartoon.ownerName);  
    console.log(name);  
    // "Scooby-Doo Shaggy"
    
    # 9. Naming Convention for Global Variables
    
    For global JavaScript variables, there are no specific naming standards.

It is recommended to use  **camel case**  for  **mutable**  global variables and  **uppercase** for **immutable** global variables.

# 10. Naming Convention for File Names

Most web servers (Apache, Unix) are case-sensitive when it comes to handling files. For example,  **_flower.jpg_** isn’t  **_Flower.jpg_**.

On the other hand, web servers, such as Microsoft’s IIS, do not care about the case. In such servers, you can use  **_Flower.jpg_** or  **_flower.jpg_** _to_  access  **_Flower.jpg_**.

However, if you switch from a case-insensitive server to a case-sensitive server, even a tiny mistake can cause your website to crash.

So, it is recommended to use  **lowercase**  file names in all servers despite their case-sensitive support.

# Conclusion

In this article, I discussed 10 JavaScript naming conventions that can be used to improve our coding skills. As developers, we should always adhere to best practices, since that will increase readability and make it easier for you and your team to understand your code.

I hope those suggestions will help you improve your coding skills. Thank you for reading.

The Syncfusion  [JavaScript suite](https://www.syncfusion.com/javascript-ui-controls) will be the only suite you will ever need to build an application. It contains over 65 high-performance, lightweight, modular, and responsive UI components in a single package. Download the  [FREE trial](https://www.syncfusion.com/downloads/essential-js2)  and evaluate the controls today.

If you have any questions or comments, you can contact us through our  [support forums](https://www.syncfusion.com/forums),  [support portal](https://support.syncfusion.com/), or  [feedback portal](https://www.syncfusion.com/feedback/). We are always happy to assist you!
