# Lab Report 3 - 04/30/24
## Part 1
### i.
reverseInPlace method original:
```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }

```
JUnit test fails:
```
	@Test 
	public void testReverseInPlace() {
    int[] input1 = { 3, 4, 5 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 5, 4, 3 }, input1);
	}
```
### ii.
JUnit test passes:
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

### iv.
The bug:
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

## Part 2
