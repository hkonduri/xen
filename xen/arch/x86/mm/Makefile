subdir-y += shadow
subdir-y += hap

obj-y += paging.o
obj-y += p2m.o p2m-pt.o p2m-ept.o p2m-pod.o
obj-y += altp2m.o
obj-y += guest_walk_2.o
obj-y += guest_walk_3.o
obj-y += guest_walk_4.o
obj-y += mem_paging.o
obj-y += mem_sharing.o
obj-y += mem_access.o

guest_walk_%.o: guest_walk.c Makefile
	$(CC) $(CFLAGS) -DGUEST_PAGING_LEVELS=$* -c $< -o $@

guest_walk_%.i: guest_walk.c Makefile
	$(CPP) $(filter-out -Wa$(comma)%,$(CFLAGS)) -DGUEST_PAGING_LEVELS=$* -c $< -o $@

guest_walk_%.s: guest_walk.c Makefile
	$(CC) $(filter-out -Wa$(comma)%,$(CFLAGS)) -DGUEST_PAGING_LEVELS=$* -S $< -o $@
