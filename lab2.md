# Lab 2
### Exercise 1
Implement: in kern/pmap.c
	boot_alloc()
	mem_init() (only up to the call to check_page_free_list(1))
	page_init()
	page_alloc()
	page_free()

	-- done -- 

### Exercise 2: 
read https://pdos.csail.mit.edu/6.828/2017/readings/i386/s06_04.htm and https://pdos.csail.mit.edu/6.828/2017/readings/i386/s05_02.htm


### Exercise 3
In lab folder, type into command line make qemu. The jos terminal/monitor should pop up. Run make gdb in another terminal but also within the lab folder. My virtual box tends to freeze when I make qemu, but make qemu-nox or make qemu-nox-gdb tends to work okay.   


On __x__ command, at address 0x00100000 for the physical address and address 0xf0000000 for the virtual address. Thus, our commands to gdb will be x/16x 0x00100000 and x/16x 0xf0000000.

At info mem, qemu says that PG is disabled. Info pg should work for the patched version of qemu, so I guess I don't have the patched version since that line does not seem to be a valid command. 

#### Question 1
JOS kernel has / inside code.

	uintptr_t represents virtual addresses
	physaddr_t represents physical addresses 
	T* represents virtual address type

For the following JOS kernel code, variable x should be uintptr_t type because this is an application/code. Also, according to the information given by the lab, the kernel can not sensibly dereference a physical address, since the MMU translates all memory references. (The MMU is x86 hardware's memory management unit that performs the mapping when instructions use memory, consulting a set of page tables.) So under the given assumption that this code is correct, the value of char* value from return_a_pointer() is assigned the value of 10. The MMU translates the memory references here to a virtual address. 

	mystery_t x;
	char* value = return_a_pointer();
	*value = 10;
	x = (mystery_t) value;

### Exercise 4
Implement these functions in kern/pmap.c.

	pgdir_walk()
    boot_map_region()
    page_lookup()
    page_remove()
    page_insert()
	


## Part 3




## Notes: 
The Memory Management Unit is a computer hardware unit having all memory references passed through itself, primarily performing the translation of virtual memory addresses to physical addresses.  