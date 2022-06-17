# Chapter 2

## Insertion Sort(P18)

```
void insertionSort(int[] A)
{
    for(int i = 1; i<A.length;i++)
    {
        int key = A[i];
        int j = i-1;
        while(j >= 0 && A[j] > key)
        {
            A[j + 1] = A[j];
            j--;
        }
        A[j+1] = key;
    }
}

//test

int[] A = {5,2,4,6,1,3};
insertionSort(A);
for (int i = 0; i < A.length; i++) {
    System.out.println(A[i]);
}
```

## Exercises(P22)

**2.1-1**
> InsertionSort on Array A
```
int[] A = {31,41,59,26,41,58};

// 31 41 59 26 41 58 
// 31 41 59 26 41 58 
// 26 31 41 59 41 58 
// 26 31 41 41 59 58 
// 26 31 41 41 58 59 
// 26 31 41 41 58 59 
```


**2.1-2**
> InsertionSort nonincreasing:
```
void insertionSort(int[] A)
{
    for(int i = 1; i<A.length;i++)
    {
        int key = A[i];
        int j = i-1;
        while(j >= 0 && A[j] < key) //changed line
        {
            A[j + 1] = A[j];
            j--;
        }
        A[j+1] = key;
    }
}
```

**2.1-3**
> Linear search:
>> given A and v, retunr index i if there is such A[i] that is equal to v or null if v does not appear in A
```
int linearSearch(int[] A, int v)
{
    int i = null; // the pseudocode said so
    for(int j = 0; j<A.length;j++)
    {
        if(A[j]==v) i = j;
    }
    return i;
}
```

**2.1.4**
> add 2 n element binary integers in arrays A and B to array C
```
int[] addBinaryInteger(int[] A, int[] B)
{
    int[] C = new int[A.length + 1];
    int carry = 0;
    for(int i = A.length - 1; i>=0; i--
    {
        int sum = A[i] + B[i] + carry;
        C[i+1] = sum % 2;
        if(sum>=2)
        {
            carry = 1;
        }
        else
        {
            carry = 0;
        }
    }
    C[0] = carry;
    return C;
}
```
necessary tests
```
// test
int[] A = {1,0,1,0,1,0,1,0,
        1,0,1,0,1,0,1,0,
        1,0,1,0,1,0,1,0,
        1,0,1,0,1,0,1,0};

System.out.print("  ");
for (int k = 0; k < A.length; k++) {
    System.out.print(A[k] + " ");
}
System.out.print("\n");


int[] B = {1,0,1,0,1,0,1,0,
        1,0,1,0,1,0,1,0,
        1,0,1,0,1,0,1,0,
        1,0,1,0,1,0,1,0};

System.out.print("  ");
for (int k = 0; k < B.length; k++) {
    System.out.print(B[k] + " ");
}

int[] C = addBinaryInteger(A,B);

for (int i = 0; i < C.length; i++) {
    System.out.print(C[i] + " ");
}
System.out.print("\n");

```

## Exercises(P29)

**2.2-2**
> Selection sort algorithm:
```
void selectionSort(int[] A)
{
    for(int i = 0; i<A.length; i++)
    {
        int min = i;
        for(int j = i+1; j < A.length; j++)
        {
            if(A[j] < A[min])
            {
                min = j;
            }
        }
        int temp = A[i];
        A[i] = A[min];
        A[min] = temp;
    }
}
```

## D