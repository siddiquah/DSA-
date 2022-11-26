# DSA-
There are so many different types of DS's, each are good at what they do. For example array is good at some things than linked lists, while linked lists are better at some things than array. Likewise binary tree is better at some things than array or linked lists, while array and linked lists are better than binary tree at some things. So to determine which data structure and algorithm is best suited for which situation, we use Big-O.

Big-O helps find which code between two codes, is better and runs more efficiently.
Time complexity does not measure how much time a code takes to run. Instead we measure it with the number of operations.
Space complexity is the amount of memory something uses.

So we have three notations which we use mainly. Omega, Theta and Omicron(O).
For example lets take an array and try to find a particular element. Arr = [1,2,3,4,5,6,7]. Ok so to find (1), it’ll take 1 iteration, so the time complexity will be the best case. If we try to find (4), it’ll take 4 iterations, so the time complexity will be the average case. If we try to find (7), it’ll take 7 iterations, so the time complexity will be the worst case. 
So the best case is represented with the Greek letter Omega (Ω), average case is represented with the letter Theta(θ), and the worst case is represented with the symbol Omicron(O).
So when we measure Big-O, we are always going to measere the worst case.

Big(O) Notation —> O(n) // n is the number of times the code ran or the number of times the operations ran.
function logItems(n) {
    for(let i = 0; i<n; i++) {
        console.log(i)
    }
}
logItems(10)
//This code ran 10 times, so its time complexity is O(n). but what if we had another for loop that also ran 10 times. Our output will be (01234567890123456789) from both the loops. In this case the notation will be n+n which is O(2n), so to simplify we have this thing called drop constant, and we literally drop the constant 2, so the notation will be O(n), it dosent matter if we have 2 or even 100 n, as long as we have a constant. So to simplify the notation we drop the constant.

Now lets move on to another Big O notation. O(n^2). 
function logItems(n) {
    for(let i = 0; i<n; i++) {
        for(let j = 0; j<n; j++) {
            console.log(i,j)
        }
    }
    
}
logItems(10)
Now in here we have 2 for loops nested. So instead of getting 20 outputs we get 100 outputs  n + n (10+10). we get n * n (10*10) which is n^2.

Now lets try to put another for loop inside the nested loops total 3 nested for loops. We get a 1000 outputs as n*n*n = 10*10*10. In this situation we might think the notation will be n^3. But no, we will simplify this, so that no matter how many n are there we will always get n^2 (as long as its more than one).
Ok so, so far we have O(n) if we have 1 loop O(2n) if we have 2 or more than 1 separate loops.
Next O(n^2) if we have two nested loops, and still O(n^2) even if we have more than 2 loops nested in each other.
O(n) is better than O(n^2).

Now we take this code with two nested for loop and one normal loop.
function logItems(n) {
    for(let i = 0; i<n; i++) {
        for(let j = 0; j<n; j++) {
            console.log(i,j)
        }
    }
    for(let k = 0; k<n; k++) {
            console.log(k)
        }
    
}
logItems(10)
So for nested one we get O(n^2) and for the normal one we simply get O(n). so the notation for this code is O(n^2) + O(n) = O(n^2 + n). so in this situation n^2 is the dominant one and n is the non-dominant one, so we can just drop it. So the final notation will be O(n^2). Thats it. 

Moving on , we see that this code here has only one operation, 
function addItems(n) {
    return n+n
}
which means that whatever is the value if it is 1 or a million, the number of steps to take to solve this code is 1 so the notation is always 1. O(1) = constant time.

Now lets move on to another type of notation O(log n). So lets take an array arr = [1,2,3,4,5,6,7,8].
Here if we have to find a number (1). So we try to divide the array in half. 1,2,3,4 and 5,6,7,8. Now we have eliminated the second half completely as 1 can only be in the first half. Now we divide 1,2,3,4 again and get 1,2 and 3,4. Now we take 1,2. And again divide it. 1,2 and remove 2 . and done. now we found 1 huzzah! So we solved thai problem in 3 steps, we divided the array in 3 steps. So we its 2^3=8. Now in the form of Logarithms, we have log2 8 = 3. So our notation will be O(log n).
In some cases of sorting algorithm, the best case notation is O(nlog n). This notation is closer to O(n^2) in the graph. 

O(1) = best
O(log n) = next best
O(n) = average
O(n^2) = worst

Ok now a trick question, So we know that if we have 2 separate for loops then the notation will be O(n+n) => O(2n) => O(n).
But what if we have different parameters for both the for loops. Like a and b. Then our notation will turn from O(n+n) to O(a+b).  
function logItems(a,b) {
    for(let i = 0; i<a; i++) {
        console.log(i)
    }
    for(let k = 0; k<b; k++) {
        console.log(k)
    }
}
logItems(10,20)

Now in this case the inputs are different so we write O(a+b). Now if we had two for loops nested with different inputs then the notation would be O(a*b).
And thats it, done.

Now lets talk about Array. When we use Push and pop to add or delete an item in the array, the time complexity will be O(1). as  there is only one step required in doing this. But if we use unshift, we remove the first item off of the array. That means 0th index is gone. which also means the other elements in the array needs to be re-indexed. So index no 1 will be 0, index 2 will be 1, and so on. Its the same with unshift method. These requires more than 1 step, so the time complexity will be O(n). even the splice method is O(n). if we have to find a no linearly it is O(n). but if we try to find a no by index then it is O(1).
So to sum it up in array
Push, pop => O(1)
Unshift, shift => O(n)
Splice, slice => O(n)
Find an element linearly => O(n)
Find an element with index => O(1)

Cheatsheet: https://www.bigocheatsheet.com/

Lets move on to the 3rd section, here we talk about classes. Look at this code below.
class Cookie {
    constructor(color) {
        this.color = color
    }
    getColor() {
        return this.color
    }
    setColor() {
        return this.color
    }
}
let CookieOne = new Cookie('green')
let CookieTwo = new Cookie('blue')

All our Data structures need classes, that is why it is so important for us to learn it.
Now Pointers, these are important. If we have 2 var a and b , and a’s value is 3 and b’s value is a. Then when we change values of a to 6 , then also the value of b would be 3.
Let a = 3
Let b = a
// a =3, b = 3
But,
A = 6,
//a = 6, b = 3
. but if we use pointers this wont happen, the value of 2nd variable will point to the same memory where value of a is stored. Look at the code below.
var obj1 = {
    value: 5
}
var obj2 = obj1
console.log(obj1, obj2) // output is 5,5
obj1.value = 8
console.log(obj1, obj2) // output is 8,8

Now when we have something in our memory that cannot be accessed and i just taking up spaces then javascript has something called Garbage Collection, it removes that unnecessary data.

Data like this, which has no name and thus cannot be called.
{
	Value: 7
	Value2: “Anjum”
}
Let’s start with our first DS. LINKED LISTS.
Inked lists are like arrays but without the index numbers. And they are not contiguous, Linked lists are scattered . they have there variables called head and tail. And also each data points to the memory location of the next data. 

(head) Data|next —> Data|next —> Data|next —> Data|next —> Data|next —> Data|null (tail)

When null is at the end of a list then its called null terminated list.

Lets look at the Big(O) of Linked list.
When we are trying to add a node to the end of a linked list, then there will always be 2 steps. Pointing the next of the previous node to this node, and changing the tail from previous node to this. Now this will always remain constant no matter we add 1 node or a million node. 

Pushing new Node at the end => O(1)
Pushing new Node at the start => O(1)

Now if we try to pop a node from the linked list, then the situation changes. Its not short and simple. To do this e start from head and iterate through each node until we reach the tail, then we assign the prev node as tail and delete the last node. So the Big O will be O(n)

Popping a Node at the end => O(n)
Popping a Node at the beginning => O(1)

Adding a node in the middle - we start at the head for this one, and iterate till the node where we will add the new node, its Big O is O(n)

Pushing new Node at the middle => O(n)
Popping a Node at the middle => O(n)

Finding a node is also O(n), as we had to iterate from the head till the node. It dosdent matter if the node we are looking for is by value or index, it always starts from head to find  that node.

Finding a node by value/index => O(n)

Moving on we will see what a NODE is made up of. 
|4|--->null this is a node example. Its made up of a6 value and a pointer.
So basically a node is an object like this.
{
	value: 4,
	next: null
}
{
    head: {
        value: 11,
        next: {
            value: 3,
            next: {
                value: 23,
                next: {
                    value: 7,
                    // tail = node.nextNode
                    next: {
                        value: 4,
                        next: null
                    }  
                }
            }
        }    
    } 
}
This set of nested object is a linked list with multiple nodes.

Everything is clear so far on Linked list. Lets start the code by making a constructor.
Example :-
class LinkedList {
    constructor(value) {
        this.value=value
    }
}
let linkedList = new LinkedList()
Now lets see these methods that we’re gonna do first.
class LinkedList {
    constructor(value) {
        //create new node at the time when we are creating the linked List
    }
    push(value) {
        //create new node
        //adds node to the end
    }
    unshift(value) {
        //create new node
        //adds node to the beginning
    }
    insert(index, value) {
        //create new node
        //insert node in the given index no(middle).
    }
}

In this, we can see the the “Create a new node” has been repeated everytime, so instead of writing the same code again and again. We create a class called node.
class Node{
    constructor(value) {
this.value=value
this.next = null
    }
}
Now here the constructor creates a node, the “value” in parameter means the value we are going to assign the node. Then we see this.value = value. Which means that the value of this new node is equal to the value given in parameter. Same with this.next = null. Which means the value of the next in this node is null.

To use the node, we call the Node class. This calls the constructor & creates a node
Const newNode = new Node(4). This will create a node with a value of 4

This is the FINAL code to create a single node linkedList.
class Node {
    constructor(value) {
        this.value = value
        this.next = null
    }
}
class LinkedList {
    constructor(value) {
        let newNode = new Node(value)
        this.head = newNode //this makes head point towards our new node
        this.tail = this.head //this makes tail point towards our new node
        this.length = 1 // and we will also keep a track of the length of the LL.
    }
}

let linkedList = new LinkedList(4) 
// this LinkedList(4) calls the class LinkedList , and creates a node with the value 4.
//the new keyword is specifically calling the constructor in the class LinkedList.

Now moving on lets try to add a node to our linked list, we will use the push method for this.
class Node {
    constructor(value) {
        this.value = value
        this.next = null
    }
}
class LinkedList {
    constructor(value) {
        let newNode = new Node(value)
        this.head = newNode
        this.tail = this.head
        this.length = 1
    }
    push(value) {
        let newNode = new Node(value)
        //This is when we are trying to add a node to a linked list that is empty.
        if(!this.head) {
            this.head = newNode
            this.tail = this.head
        }
        else {
            this.tail.next = newNode
            this.tail = newNode
        }
        this.length++ // increase the length by one
        return this // return this whole thing
    }
}

let linkedList = new LinkedList(7)
linkedList.push(4)
// This is the Complete code for adding a node to a linked list.

With push we only have to code for 2 scenarios[list with no node, and list with some nodes] but with pop we have to code all three scenarios[list with no node, list with some nodes, and list with only one node].

So pop isnt so simple. We need to iterate through the whole LL to get to the end and then delete that node.
We need to create two new variables, temporary and previous. We move temp to the next node, and the prev stays on the head, then we continue with the loop until temp = tail, and prev = 2nd last node.
Then we simply do prev = tail and then tail.next = null. And the last node gets deleted. Heres the final code.
pop() {
        let temp = this.head
        let pre = this.head
        if(!this.head) {
            return undefined
        }
        while (temp.next) { // thsi means that temp the 1st node is pointing to another node.
            pre = temp
            temp = temp.next // this moves temp to the next node.  
        }
        this.tail = pre
        this.tail.next = null
        this.length--
        if(this.length==0) {
            this.head = null
            this.tail = null
        }
        return temp
    }
Let's move onto unshift.
Now unshift add the node to the beginning of the list. The code is pretty similar to push. 
unshift(value) {
        let node = new Node(value)
        if(!this.head) {
            this.head = node //add node to an empty list
            this.tail = node
        }
        else {
            node.next = this.head // we point the new node towards head
            this.head = node // then we move the head to the new node.
        }
        this.length++
        return this
    }

Lets move onto the shift method.
Now shift removes the node from the beginning of the list. The code is pretty similar to pop. remember we need to create a new var temp, that will store the popped/shifted value, as we need to return it.  Check for all 3 conditions, no node, 1 node, more than 1 node.
    shift() {
        let temp;
        if(!this.head) {
            return undefined
        }
        temp = this.head
        this.head = this.head.next
        temp.next = null
        this.length--
        if(this.length==0) {
            this.tail = null
        }
        temp.next = null
        return temp
    }
Thats it bro~
class Node {
    constructor(value) {
        this.value = value
        this.next = null
    }
}

class LinkedList {
    constructor(value) {
        let node = new Node(value)
        this.head = node
        this.tail = this.head
        this.length = 1
    }
    push(value) {
        let node = new Node(value)
        if (!this.head) {
            this.head = node
            this.tail = node
        } else {
            this.tail.next = node
            this.tail = node
        }
        this.length++
        return this
    }
    pop() {
        let temp = this.head
        let pre = this.head
        if(!this.head) {
            return undefined
        }
        while (temp.next) { // thsi means that temp the 1st node is pointing to another node.
            pre = temp
            temp = temp.next // this moves temp to the next node.  
        }
        this.tail = pre
        this.tail.next = null
        this.length--
        
        if(this.length==0) {
            this.head = null
            this.tail = null
        }
        return temp
    }
    unshift(value) {
        let node = new Node(value)
        if(!this.head) {
            this.head = node
            this.tail = node
        }
        else {
            node.next = this.head
            this.head = node
        }
        this.length++
        return this
    }
    shift() {
        let temp;
        if(!this.head) {
            return undefined
        }
        temp = this.head
        this.head = this.head.next
        temp.next = null
        this.length--

        if(this.length==0) {
            this.tail = null
        }
        temp.next = null
        return temp
    }
}

let linkedList = new LinkedList(6)
linkedList.push(7)
linkedList.push(8)


