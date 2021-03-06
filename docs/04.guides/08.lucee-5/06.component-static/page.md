---
title: Static support for components
id: lucee-5-component-static
---

#Static support for components#
**Lucee 5 supports static variables and functions inside components.**

Example:
```
#!javascript
component {
     // inside the static constructor you can define static variables, this code is executed when the "class" instance is loaded
     static {
            susi=1; // written to the static scope
            static.sorglos=2; // again written to the static scope
     }

     public static function testStatic() {

    }

     public function testInstance() {
          testStatic(); // calling a static function
          return static.sorglos; // returning data from the static scope
     }
}
```
The "static" constructor ```static {...}```  is executed once before the component is loaded for the first time, so every component of the same type shares the same static scope.

You can use static functions and data as follows.
```
#!javascript
component Test {
   static {
      staticValue=1;
   }
   public static function testStatic(){}
}
```
```
#!javascript
Test::testStatic();
x=Test:: staticValue;
```
