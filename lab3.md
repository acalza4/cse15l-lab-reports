# Lab Report 3
## Part 1 - Bugs:

**Failure Inducing Input**
```
@Test 
public void testReverseInPlaceList() {
    int[] input1 = {1, 2, 3, 4};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{4, 3, 2, 1}, input1);
}
```
**Input Doesn't Induce Failure**
```
@Test 
public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
}
```
**In JUnit**

<img width="900" alt="image" src="https://github.com/acalza4/cse15l-lab-reports/assets/147474371/35b8a452-8e9d-44fb-a997-3ff4b1350163">

**Method Bug**
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
        arr[i] = arr[arr.length - i - 1]; 
    }  
}
```
The Fix:
```
static void reverseInPlace(int[] arr) {
    int[] newArray = new int[arr.length];
    for (int i = 0; i < arr.length; i++) {
        newArray[i] = arr[i];
    }
    for(int i = 0; i < arr.length; i += 1) {
        arr[i] = newArray[arr.length - i - 1];
    }
}
```
This fix addresses the issue as previously, the method was not able to properly reverse the list as the backhalf of the array's data was lost during the loop. The fix creates a new array which allows the array to be properly copied over without the loss of the backhalf of the array.

## Part 2 - Researching Commands
Exploring `Grep`!

1. `$ grep --color`

Ex 1.

<img width="495" alt="image" src="https://github.com/acalza4/cse15l-lab-reports/assets/147474371/eb1fa83a-2d5d-49ac-9c70-9420ea9c314c">

Ex 2.

![image](https://github.com/acalza4/cse15l-lab-reports/assets/147474371/d2552b7f-5155-48c9-9057-b5afb21de57a)

The color command is useful because it can help you find words in large chunks of texts easier.


2. `$ grep -i`

Ex 1.

![image](https://github.com/acalza4/cse15l-lab-reports/assets/147474371/f3f406ff-74d4-4d73-ae57-c1dc62ce776b)

Ex 2.

![image](https://github.com/acalza4/cse15l-lab-reports/assets/147474371/bdefadb0-2f13-40ac-9890-c63e4062e531)

The `-i` command is useful if you want to not care about the capitalization of the words you are looking for. 

3. `$ grep ^char`/`$ grep "char"`

Ex 1.

![image](https://github.com/acalza4/cse15l-lab-reports/assets/147474371/eeb1e6e4-7e02-4440-b387-271585598255)

Ex 2.

![image](https://github.com/acalza4/cse15l-lab-reports/assets/147474371/aba9bd7d-2f40-4a0f-b48f-55ff9edceebc)

The `^` indicates to the program to search to see if the char matches the first letter of every line and returns it. The `" "` searches every line for the char inputted between the quotes and returns every line with it. These commands are useful if you want to search for characters and could be espeically useful for search DNA files.

4. `$ grep -v`

Ex 1.

![image](https://github.com/acalza4/cse15l-lab-reports/assets/147474371/39ffbca8-5d59-427a-a558-ae04ef33883c)

Ex 2.

![image](https://github.com/acalza4/cse15l-lab-reports/assets/147474371/7e111d0f-53e5-4e68-80e6-95493b94069c)

The command returns the opposite of whatever we were searching for which is useful when there are a lot of similar things we don't want to be returned so we can use `-v` to search for those things and return every line that doesn't include those things.

**Source for all examples:** https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix
