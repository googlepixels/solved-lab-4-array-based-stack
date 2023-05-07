Download Link: https://assignmentchef.com/product/solved-lab-4-array-based-stack
<br>
<h1>Overview</h1>

In this assignment, you will be implementing your own <em>Array-Based Stack</em> (ABS). A <strong>stack</strong> is a linear data structure which follows the last in, first out (LIFO) property. LIFO means that the data most recently added is the first data to be removed. (Imagine a stack of books, or a stack of papers on a desk—the first one to be removed is the last one placed on top.)




The typical operations of a stack are:

<strong>Push</strong> – Add something to the top of the stack

<strong>Pop</strong> – Remove something from the top of the stack and return it

<img decoding="async" data-recalc-dims="1" data-src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2018/09/965.png?w=980&amp;ssl=1" class="aligncenter lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

 <noscript>

  <img decoding="async" class="aligncenter" src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2018/09/965.png?w=980&amp;ssl=1" data-recalc-dims="1">

 </noscript>

<strong>Example of a LIFO-the data most recently added is the first to be removed</strong>

<h1>Description</h1>

Your ABS will be a template class, and thus will be able to hold any data type. (Many data structures follow this convention—reuse code whenever you can!) As with previous classes that use dynamic memory, you must be sure to define The Big Three: The Copy Constructor, the Assignment Operator, and the Destructor.

Data will be stored using an array (hence the <em>array-based </em>stack)<em>.</em> You may use any other variables/function in your class to make implementation easier.

By default, your ABS will have a scale factor 2.0f.

<ol>

 <li>Attempting to push() an item onto an ABS that is full will scale its capacity by the scale factor.</li>

 <li>When calling pop(), if the “percent full” (e.g. current size / max capacity) becomes less than</li>

</ol>

1/scale_factor, decrease the capacity of the ABS by 1-1/scale_factor




<strong>Why increase (or decrease) the size by any amount other than one? </strong>

Short answer: performance!

If you are increasing or decreasing the size of a container, it’s reasonable to assume that you will want to increase or decrease the size again at some point, requiring another round of allocate, copy, delete, etc.

Increasing the capacity by more than you might need (right now) or waiting to reduce the total capacity allows you to avoid costly dynamic allocations, which can improve performance—especially in situations in which this resizing happens frequently. This tradeoff to this approach is that it will use more memory, but this speed-versus-memory conflict is something that programmers have been dealing with for a long time.

<strong><img decoding="async" data-recalc-dims="1" data-src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2018/09/698.png?w=980&amp;ssl=1" class="aligncenter lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

  <noscript>

   <img decoding="async" class="aligncenter" src="https://i0.wp.com/www.ankitcodinghub.com/wp-content/uploads/2018/09/698.png?w=980&amp;ssl=1" data-recalc-dims="1">

  </noscript></strong>

<strong>                                                  The images above assume a 2.0f scale factor</strong>

Your ABS will support the following methods:

<ul>

 <li>ABS(): Default constructor. Capacity should be initialized to 1, and size should be initialized to 0.</li>

 <li>ABS(int capacity): Constructor for an ABS with the specified starting capacity.</li>

 <li>ABS(const ABS &amp;d): Copy constructor.</li>

 <li>ABS &amp;operator=(const ABS &amp;d): Assignment operator.</li>

 <li>~ABS(): Destructor for an ABS.</li>

 <li>void push(T data): Add a new item to the top of the stack.</li>

 <li>T pop(): Remove the item at the top of the stack, and return its value. Throws -1 if the stack is empty.</li>

 <li>T peek(): Return the value of the item at the top of the stack, without removing it. Throws -1 if the stack is empty.</li>

 <li>unsigned int getSize(): Returns the current number of items in the ABS.</li>

 <li>unsigned int getMaxCapacity(): Returns the current max capacity of the ABS.</li>

 <li>T* getData(): Returns the array representing the stack. This should only be used in order to implement the copy constructor or assignment operator.</li>

</ul>