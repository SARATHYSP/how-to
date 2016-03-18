 JS Syntax

         In html JS must be written within the script
         JS statements must be terminated with semicolons
         <!DOCTYPE html>
         <html>
         <body>
         <h1>JavaScript is Case Sensitive</h1>
         <p id="demo"></p>
         <script>
         var lastName = "Doe";
         var lastname = "Peterson"; -- strings must be written in quotes whereas numbers can be declared directly
         document.getElementById("demo").innerHTML = lastname; --o/p will be Peterson
         <script>
         </body>
         </html>
         <p id="demo1"></p>
         <script>
         document.getElementById("demo2").innerHTML = "John" + " "  + "Doe"; --o/p will be John Doe
         </script>  

JS Comments

          // --used to wirte single line Comment which will not be displayed in the o/p

JS Variables

          <p id="demo"></p>
          <script>
          var price1 = 5;
          var price2 = 6;
          var total = price1 + price2;
          document.getElementById("demo").innerHTML = "The total is: " + total;
          </script>
          One statement can declare multiple variables like
          var person = "John Doe", carName = "Volvo", price = 200;
          var x = 5 + 2 + 3;  --we can also perform arithmetic operation in variables
          var x = "5" + 2 + 3;  --o/p will be 523

JS Datatypes

          JavaScript variables can hold many data types: numbers, strings, arrays, objects and more:
            var length = 16;                               // Number
            var lastName = "Johnson";                      // String
            var cars = ["Saab", "Volvo", "BMW"];           // Array
            var x = {firstName:"John", lastName:"Doe"};    // Object
          "type of" operator gives the type of the variable
             typeof "john"   --it is a String

JS Functions

          A JavaScript function is a block of code designed to perform a particular task.
          A JavaScript function is executed when "something" invokes it (calls it).
          <script>
          function toCelsius(f) {
                    return (5/9) * (f-32);
                  }
          document.getElementById("demo").innerHTML = toCelsius(77);
          </script>
          Functions can also be declared as variables like
          document.getElementById("demo").innerHTML = "The temperature is " + toCelsius(77) + " Celsius";
          the o/p will be like this - The temperature is 25 Celsius

JS Objects

        Creating a JS object:
          <p id="demo"></p>
          <script>
          var person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};
          document.getElementById("demo").innerHTML = person.firstName + " is " + person.age + " years old.";
          </script>
          The o/p will be like - John is 50 years old.
       You access an object method with the following syntax:
          <script>
          var person = { firstName: "John",lastName : "Doe",id: 5566,fullName : function() {
                                                                                     return this.firstName + " " + this.lastName;
                                                                                         }
          document.getElementById("demo").innerHTML = person.fullName();

JS Events

       HTML events are "things" that happen to HTML elements.When JavaScript is used in HTML pages, JavaScript can "react" on these events
          <some-HTML-element some-event='some JavaScript'>
          eg:<button onclick="getElementById('demo').innerHTML=Date()">The time is?</button> --it will create a button with text "The time is"
       Common HTML Events
          Here is a list of some common HTML events:
            Event 	   Description
          onchange 	    An HTML element has been changed
          onclick     	The user clicks an HTML element
          onmouseover 	The user moves the mouse over an HTML element
          onmouseout 	  The user moves the mouse away from an HTML element
          onkeydown 	  The user pushes a keyboard key
          onload 	      The browser has finished loading the page  

JS Strings Methods

       The indexOf() method returns the index of (the position of) the first occurrence of a specified text in a string:
           <p id="p1">Please locate where 'locate' occurs!.</p>
           <button onclick="myFunction()">Try it</button>
           <p id="demo"></p>
           <script>
            function myFunction() {
                        var str = document.getElementById("p1").innerHTML;
                        var pos = str.indexOf("locate");   --The o/p will be 7
                        document.getElementById("demo").innerHTML = pos;
                           }
           </script>
       The lastIndexOf() method returns the index of the last occurrence of a specified text in a string:
          var pos = str.lastIndexOf("locate");
       The search() method searches a string for a specified value and returns the position of the match:
          var pos = str.search("locate");  

       The slice() extracts a part of a string and returns the extracted part in a new string.The method takes 2 parameters: the starting index (position), and the ending index (position).
       This example slices out a portion of a string from position 7 to position 13  
          <p id="demo"></p>
          <script>
          var str = "Apple, Banana, Kiwi";
          document.getElementById("demo").innerHTML = str.slice(7,13); --The o/p will be Banana.
           </script>
      If a parameter is negative, the position is counted from the end of the string.
          str.slice(-12,-6); --The o/p is Banana
      If you omit the second parameter, the method will slice out the rest of the string:
          str.slice(7); --The o/p will be Banana, Kiwi.
      The substring() is similar to slice().The difference is that substring() cannot accept negative indexes.
          str.substring(7,13);  --The o/p is Banana.
      The substr() is similar to slice().The difference is that the second parameter specifies the length of the extracted part.    
          str.substr(7,6);  --The o/p is Banana.
      The replace() method replaces a specified value with another value in a string:
          <p id="demo">Please visit Microsoft!</p>
          <script>
          function myFunction() {
                 var str = document.getElementById("demo").innerHTML;
                 var txt = str.replace("Microsoft","W3Schools");
                 document.getElementById("demo").innerHTML = txt;
                   }
           The o/p for above will be --Please visit W3Schools
      The replace() method can also take a regular expression as the search value.By default, the replace() function replaces only the first match. To replace all matches, use a regular expression with a g flag (for global match):
           var txt = str.replace(/Microsoft/g,"W3Schools");
      A string is converted to upper case with toUpperCase():      
           document.getElementById("demo").innerHTML = text.toUpperCase();
      A string is converted to lower case with toLowerCase():
           document.getElementById("demo").innerHTML = text.toLowerCase();
      The concat() method joins two or more strings:
           var text1 = "Hello";
           var text2 = "World!";
           document.getElementById("demo").innerHTML = text1.concat(" ",text2);
          The o/p will be Hello World!
      The charAt() method returns the character at a given position in a string:
           var str = "HELLO WORLD";
           document.getElementById("demo").innerHTML = str.charAt(0);  
          The o/p will be H
      The charCodeAt() method returns the unicode of the character at a given position in a string:
           str.charCodeAt(0);
          The o/p will be 72
      A string can be converted to an array with the split() method:
           var str = "HELLO WORLD";
           var arr = str.split(" "); --split based on spaces
           document.getElementById("demo").innerHTML = arr[0];
          The o/p will be Hello
            txt.split(",");          -- Split on commas
            txt.split("|");          -- Split on pipe

JS Number Methods

      JavaScript number methods are methods that can be used on numbers:
         Method 	  Description
      toString() 	   Returns a number as a string
 toExponential() 	   Returns a string, with a number rounded and written using exponential notation.
       toFixed() 	   Returns a string, with a number rounded and written with a specified number of decimals.
   toPrecision() 	   Returns a string, with a number written with a specified length
       valueOf() 	   Returns a number as a number

JS Global Methods

      JavaScript global functions can be used on all JavaScript data types.These are the most relevant methods, when working with numbers:
         Method     Description
        Number() 	    Returns a number, converted from its argument.
    parseFloat() 	    Parses its argument and returns a floating point number
      parseInt() 	    Parses its argument and returns an integer

    [For more details refer w3tutorials-Javascript-Number Methods]

JS Math

      The Math object allows you to perform mathematical tasks.The Math object includes several mathematical methods.
      One common use of the Math object is to create a random number:
             document.getElementById("demo").innerHTML = Math.random();   --returns a random number
      Math.min() and Math.max() can be used to find the lowest or highest value in a list of arguments:
             Math.min(0, 150, 30, 20, -8, -200);      -- returns -200
             Math.max(0, 150, 30, 20, -8, -200);      -- returns 150
      Math.round() rounds a number to the nearest integer:
             Math.round(4.7);            -- returns 5
             Math.round(4.4);            -- returns 4
      Math.ceil() rounds a number up to the nearest integer:
             Math.ceil(4.4);             -- returns 5
      Math.floor() rounds a number down to the nearest integer:
             Math.floor(4.7);            -- returns 4         
      Math.floor() and Math.random() can be used together to return a random number between 0 and 10:
              Math.floor(Math.random() * 11);    returns a random number between 0 and 10
      JavaScript provides 8 mathematical constants that can be accessed with the Math object:
              Math.E          -- returns Euler's number
              Math.PI         -- returns PI
              Math.SQRT2      -- returns the square root of 2
              Math.SQRT1_2    -- returns the square root of 1/2
              Math.LN2        -- returns the natural logarithm of 2
              Math.LN10       -- returns the natural logarithm of 10
              Math.LOG2E      -- returns base 2 logarithm of E
              Math.LOG10E     -- returns base 10 logarithm of E

JS Dates

      The date can be obtained by the command
              <p id="demo"></p>
              <script>
                 var d = new Date();
                 document.getElementById("demo").innerHTML = d;
              </script>
      Dates can be created.Date objects are created with the new Date() constructor.There are 4 ways of initiating a date:
              new Date()             
              new Date(milliseconds)  eg: var d = new Date(86400000);
              new Date(dateString)    eg: var d = new Date("October 13, 2014 11:13:00");
              new Date(year, month, day, hours, minutes, seconds, milliseconds)  eg: var d = new Date(99,5,24,11,33,30,0);
      When you display a date object in HTML, it is automatically converted to a string, with the toString() method.
              document.getElementById("demo").innerHTML = d.toString();;
      The toUTCString() method converts a date to a UTC string (a date display standard).
              document.getElementById("demo").innerHTML = d.toUTCString();
      The toDateString() method converts a date to a more readable format:
              document.getElementById("demo").innerHTML = d.toDateString();
      Date Get methods are used for getting a part of a date. Here are the most common (alphabetically):
              Method 	    Description
           getDate() 	      Get the day as a number (1-31)
            getDay() 	      Get the weekday as a number (0-6)
       getFullYear() 	      Get the four digit year (yyyy)
          getHours() 	      Get the hour (0-23)
   getMilliseconds() 	      Get the milliseconds (0-999)
        getMinutes() 	      Get the minutes (0-59)
          getMonth() 	      Get the month (0-11)
        getSeconds() 	      Get the seconds (0-59)
           getTime() 	      Get the time (milliseconds since January 1, 1970)

      eg: document.getElementById("demo").innerHTML gives the output of  -- 1458209646783  

      Date Set methods are used for setting a part of a date. Here are the most common (alphabetically):
             Method 	    Description
           setDate() 	       Set the day as a number (1-31)
       setFullYear() 	       Set the year (optionally month and day)
          setHours() 	       Set the hour (0-23)
   setMilliseconds() 	       Set the milliseconds (0-999)
        setMinutes() 	       Set the minutes (0-59)
          setMonth() 	       Set the month (0-11)
        setSeconds() 	       Set the seconds (0-59)
           setTime() 	       Set the time (milliseconds since January 1, 1970)

      eg: var d = new Date();
          d.setFullYear(2020, 0, 14);
          document.getElementById("demo").innerHTML = d;   -- gives the o/p Tue Jan 14 2020 15:47:43 GMT+0530 (IST)

JS Array Methods

    The join() method joins array elements into a string.
          <p id="demo"></p>
          <script>
           var fruits = ["Banana", "Orange", "Apple", "Mango"];
           document.getElementById("demo").innerHTML = fruits.join(" * ");
          </script>     
        The o/p will be Banana * Orange * Apple * Mango
    The pop method removes the last element from an array.
          fruits.pop();
          document.getElementById("demo").innerHTML = fruits;       
        The o/p will be Banana,Orange,Apple
          document.getElementById("demo").innerHTML = fruits.pop();       
        The o/p will be Mango
    The push method appends a new element to an array.
           fruits.push("Kiwi");
           document.getElementById("demo").innerHTML = fruits;
        The o/p will be Banana,Orange,Apple,Mango,Kiwi
    The push method returns the new array length.</p>
           document.getElementById("demo").innerHTML = fruits.push("Kiwi")
        The o/p will be 5
    The shift method removes the first element of an array, and "shifts" all other elements one place up.</p>
           fruits.shift();
           document.getElementById("demo").innerHTML = fruits;
         The o/p will be Orange,Apple,Mango
    The unshift method adds new elements to the beginning of an array.</p>
           fruits.unshift("Lemon");
           document.getElementById("demo").innerHTML = fruits;
         The  o/p  will be Lemon,Banana,Orange,Apple,Mango
    Array elements are accessed using their index number.
           fruits[0] = "Kiwi";
           document.getElementById("demo").innerHTML = fruits;
          The o/p  will be  Kiwi,Orange,Apple,Mango      
    The splice() method adds new elements to an array.The first parameter (2) defines the position where new elements should be added (spliced in).The second parameter (0) defines how many elements should be removed.The rest of the parameters ("Lemon" , "Kiwi") define the new elements to be added.
           fruits.splice(2, 0, "Lemon", "Kiwi");
           document.getElementById("demo").innerHTML = fruits;          
          The o/p  will be  Banana,Orange,Lemon,Kiwi,Apple,Mango
    With clever parameter setting, you can use splice() to remove elements without leaving "holes" in the array.The first parameter (0) defines the position where new elements should be added (spliced in).The second parameter (1) defines how many elements should be removed.The rest of the parameters are omitted. No new elements will be added.      
           fruits.splice(0, 1);        -- Removes the first element of fruits
    The sort() method sorts an array alphabetically.</p>
           fruits.sort();
           document.getElementById("demo").innerHTML = fruits;
          The o/p  will be Apple,Banana,Mango,Orange
           fruits.reverse();
           document.getElementById("demo").innerHTML = fruits
          The  o/p  will be  Orange,Mango,Banana,Apple
    The slice() method slices out a piece of an array into a new array.
           fruits.slice(3);
           document.getElementById("demo").innerHTML = fruits
          The  o/p will be Mango  
    For Sortting the numbers in ascending order
           var points = [40, 100, 1, 5, 25, 10];
           points.sort(function(a, b){return a>b});
           document.getElementById("demo").innerHTML = points;        
          The  o/p will  be  1,5,10,25,40,100
           points.sort(function(a, b){return b>a});  --for Sortting in descending order
    To find out the highest number
           points.sort(function(a, b){return b-a});
           document.getElementById("demo").innerHTML = points[0];       
          The o/p will be 100
           points.sort(function(a, b){return a-b});   --to find lowest number
          The o/p will be 1

        For more details refer w3 tutorials-JavaScript 
