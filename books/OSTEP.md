# Operating Systems: Three Easy Pieces

> Operating Systems: Three Easy Pieces 
> Remzi H. Arpaci-Dusseau and Andrea C. Arpaci-Dusseau 
> Arpaci-Dusseau Books 
> March, 2015 (Version 0.90) 

Read online: http://pages.cs.wisc.edu/~remzi/OSTEP/

## Preface
The three easy pieces refer to virtualization, concurrency, and persistence.

## Chapter 2 - Introduction to Operating Systems
### Virtualizing the CPU
### Virtualizing Memory
This example was particularly interesting. We create a program that performs the following:
1. Dynamically allocate memory for an integer
1. Print the address of the newly allocated memory
1. Initialize the memory to 0
1. while(true) {
1. Print the process ID and contents of the memory
1. Increment the contents of the memory
1. }

``` c
int main(int argc, char* argv[]) {
	int* p = malloc(sizeof(int));
	printf("[%d] memory address of p: %08\n");
	
	*p = 0;
	
	while(1) {
		Spin(1);
		*p = *p + 1;
		
		printf("[%d] p: %d\n", getpid(), *p);
	}
	
	return 0;
}
```

Running the program once prints `0x00200000` and then 1, 2, 3, ... as expected.

We then run multiple instances of the same program simultaneously and each one prints `0x00200000` while maintaining a independent count. How can all of the programs be pointing to the same address, but maintaining independent counts?

```
[1234] memory address of p: 00200000
[1235] memory address of p: 00200000
[1234] p: 1
[1235] p: 1
[1234] p: 2
[1235] p: 2
[1234] p: 3
[1235] p: 3
...
```

The explanation is that the memory is virtualized. The address printed isn't in the global address space. Instead, the address is in the virtual address space, which is specific to the process and mapped into the global address space by the operating system. So process 1234's address `0x00200000` could map to the global address `0xCAFEBABE` and process 1235's address `0x00200000` could map to the global address `0xCAFED00D`.

