# Lab Report 3 - 04/30/24
## Part 1 :bug: :beetle: :ant:
### i.
```reverseInPlace``` method original:
```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }

```
JUnit test fails:  :x:
```
@Test 
public void testReverseInPlace() {
    int[] input1 = { 3, 4, 5 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 5, 4, 3 }, input1);
}
```
### ii.
JUnit test passes: :white_check_mark:
```
@Test 
public void testReverseInPlace2() {
    int[] input1 = {1};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 1 }, input1);
}
```
### iii.
Symptom:
![Image](lab3_1.png)
The program is printing the array in order, not reverse order. The first example causes a failure because it contains multiple elements. Instead of printing 3 for the first element, 5 is printed because the text is being overwritten, thus not producing changes in the input. Moreover, the elements are being changed as they are being reversed, which does not produce the expected output. The second example is not failure-inducing output as there is only one input. Therefore, it reverses properly because there is only one element present.
### iv.
The bug: :beetle:
Before: :x:
```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }

```
After: :white_check_mark:
```
static void reverseInPlace(int[] arr) {
    int[] tmp = new int[arr.length];
    for(int i = 0; i<arr.length; i++){
      tmp[i] = arr[i];
    }
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = tmp[arr.length - i-1];
    }
  }
```
### v.
This fix helps address the problem by first creatng a temporary array, and then copying the elements in reverse-order. The original code is not sufficient and produces symptoms because the elements keep getting changed. For example, the first element is assigned to the last element, but then the order is not actually reversed as the elements switch places back again. 

## Part 2: ```Less``` :punch:
### -N 
```$ less -N */*.txt```
![Image](lab3_TWO.png)
Prints all ```.txt``` files and then prints less of the list, with numbered lines. If the command was written without the ```-N``` flag, the lines would not be numbered. \
```$ less -N */bcr***.txt```
![Image](lab3_THREE.png) \
Finds ```.txt``` file that starts with bcr and then prints less of it, with numbered lines. If the command was written without the ```-N``` flag, the lines would not be numbered. 

### -X
```$ less -X */*gb*.txt```
![Image](new1.png)
Finds files containing ```gb``` and prints a reduced version of the contents, and then leaves it on the screen once exiting. If the command was written without the ```-X``` flag, the contents would disappear once the user exited. \
```$ less -X */*research*.txt```
![Image](new2.png) \
Finds files containing ```gb``` and prints a reduced version of the contents, and then leaves it on the screen once exiting. If the command was written without the ```-X``` flag, the contents would disappear once the user exited.

### -F
```$ less -F */hello.txt``` \
![Image](SIX.png) \
Finds file with the name ```hello.txt``` and then prints the entire file. Since the entire file can be displayed on one screen, it exits. If the command was written without the ```-F``` flag, the screen would not immediately exit. \
```$ less -F */*bcr583.txt```
![Image](lab3_SEVEN.png) \
Finds file with the name ```bcr583.txt``` and then prints the beginning of the file. Since the entire file CANNOT be displayed on one screen, it does not exit. If the command was written without the ```-F``` flag, the output would be the same since it is not possible for the entire file to be displayed on one screen.

### -M 
```$ less -M */*bcr583.txt``` \
![Image](lab3_EIGHT.png) \
Finds file with the name ```bcr583.txt``` and then prints the beginning of the file. The highlighted part is changed, and now shows the percentage of the file displayed on the screen, along with the file line numbers of the text shown. If the command was written without the ```-M``` flag, statistics and percentages would not show up.\
```$ less -X */*bcr**.txt```
![Image](lab3_NINE.png) \
Finds the ```.txt``` files containing ```bcr``` and then prints the beginning of one file. It shows the percentage on the screen and the file line numbers of the text shown. If the command was written without the ```-M``` flag, statistics and percentages would not show up. \

## Attribution :clap:
Less Command in Linux https://linuxize.com/post/less-command-in-linux/ \

OpenAI. "ChatGPT - OpenAI's Language Model." ChatGPT, Version 2, OpenAI, 2024 https://openai.com/chatgpt \
Prompt: What are some flag usages with the command less? \
Output: \
![Image](CHAT.png) \
Modification: I took the examples mentioned (```-M, -F```), and created examples of my own with the files in ```docsearch```
