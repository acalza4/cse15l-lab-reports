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
This code induces a failure because the test case provides an array of length 4 and the code will improperly handle the reversal of this array, leading to the test case failing.

**Input Doesn't Induce Failure**
```
@Test 
public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
}
```
This code does not induce a failure because the reversal of an array of size 1 is the exact same before and after the reversal so the edge case passes with the broken code.

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

Note: For each image, you can see the working directory at the top of the image after the command. All files are out of the `technical` directory and images only display a portion of all returned output in the console.

### 1. `$ grep --color`

The color command is useful because it can help you find words in large chunks of texts easier.

Ex 1.

<img width="495" alt="image" src="https://github.com/acalza4/cse15l-lab-reports/assets/147474371/eb1fa83a-2d5d-49ac-9c70-9420ea9c314c">

In this image, I used the command and searched for the word "September" and the command with the `--color` tag made it easy to see where September appeared in the text.

Ex 2.

![image](https://github.com/acalza4/cse15l-lab-reports/assets/147474371/d2552b7f-5155-48c9-9057-b5afb21de57a)

In this image, I used the command and searched for the word "Data" and the command with the `--color` tag made it visually apparent where the word Data was in the text.

### 2. `$ grep -i`

The `-i` command is useful if you want to not care about the capitalization of the words you are looking for. 

Ex 1.

![image](https://github.com/acalza4/cse15l-lab-reports/assets/147474371/f3f406ff-74d4-4d73-ae57-c1dc62ce776b)

In this image, I searched for the word "intelligence" but with using the `-i` tag, I was able to get returned text where the capitalization of the word didn't matter. Line 2 has the word in lower caps and line 4 has the word with a capitalized "I".

Ex 2.

![image](https://github.com/acalza4/cse15l-lab-reports/assets/147474371/bdefadb0-2f13-40ac-9890-c63e4062e531)

In this image, I searched for the word "Environment" with the `-i` tag where the computer doesn't worry about any capitalization and returns any instance of the word environment. You can see the last line has the lower case version and the rest have a capital E.

### 3. `$ grep ^char`/`$ grep "char"`

The `^` indicates to the program to search to see if the char matches the first letter of every line and returns it. The `" "` searches every line for the char inputted between the quotes and returns every line with it. These commands are useful if you want to search for characters and could be espeically useful for search DNA files.

Ex 1.

![image](https://github.com/acalza4/cse15l-lab-reports/assets/147474371/eeb1e6e4-7e02-4440-b387-271585598255)

In this image, I searched the file for any lines which start with the letter s using `^s`. As you can see, many sentences returned that start with the letter s.

Ex 2.

![image](https://github.com/acalza4/cse15l-lab-reports/assets/147474371/aba9bd7d-2f40-4a0f-b48f-55ff9edceebc)

In this image, I searched the file for the letter 'H' using the `"H"` command. This command returns every single line in the file with the letter 'H' in it.

### 4. `$ grep -v`

The command returns the opposite of whatever we were searching for which is useful when there are a lot of similar things we don't want to be returned so we can use `-v` to search for those things and return every line that doesn't include those things.

Ex 1.

![image](https://github.com/acalza4/cse15l-lab-reports/assets/147474371/39ffbca8-5d59-427a-a558-ae04ef33883c)

In this image, you can see that the command with the `-v` tag returned every line that didn't include the word "the" in it. The gap above between the command and the first real text line are the padded skipped lines with no text. Since they don't contain the word "the", they are also returned.

Ex 2.

![image](https://github.com/acalza4/cse15l-lab-reports/assets/147474371/7e111d0f-53e5-4e68-80e6-95493b94069c)

In this image, you can see that the command with the `-v` tag returned every line that didn't include the word "legal" in it. The gap above between the command and the first real text line are the padded skipped lines with no text. Since they don't contain the word "legal", they are also returned.

**Source for all examples:** https://www.digitalocean.com/community/tutorials/grep-command-in-linux-unix
