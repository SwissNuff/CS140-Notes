## 1. Cloning a repo
For each CS 140 laboratory session, you are expected to clone the private xv6 repository that is set up for you on Github Classroom.

**Go to shared folder terminal**
1. ssh-keygen -t ed25519 -C "githubemail@up.edu.ph"
2. ssh-add ~/.ssh/id_ed25519
3. cat ~/.ssh/id_ed25519.pub
4. Open https://github.com/settings/ssh/new and paste your SSH key in the
Key field; the Title field can be set to any string

After setting your SSH key up, do the following to clone your private repository for this lab into your Ubuntu VM:
1. Open up a terminal on the Ubuntu VM
2. Change its working directory to your shared folder (e.g., /media/sf cs140 or
/vagrant)
3. Run git clone git@github.com:<copy_the_ssh_git_clone>
4. Verify from outside the Ubuntu VM (i.e., your host machine) that there is a
cs140221lab00-yourusername folder inside the shared folder

Compiling and running user programs
To compile a user program in xv6, the following must be done:
1. Place C source file in xv6 directory
2. Modify `UPROGS` in `Makefile`
3. Recompile the xv6 kernel via make `qemu-nox`

## 2. Compiling Programs in XV6

**Boot up xv6**
- `make qemu-nox` 
**Boot up using GDB GUI**
- `make qemu-nox-gdb`
- `gdbgui -r kernell`

### CREATING A NEW SYSTEM CALL
**User Side** (Wrapper function)
- [ ] 1. In `user.h` (C function prototype) add the system name under system calls
	- A function prototype (in C) is needed so other C programs are allowed to execute the assembly code via a regular function call
- [ ] 2. `usys.S` (x86 assembly implementation)
**User Program or Test File** (Note when making a user program you only need to do steps 3 and 4)
- [ ] 3. User Program for testing by creating new test sourcefile 
- [ ] 4. In `Makefile` add the user program name under UPROGS

**Kernel Side**
- [ ] 1. syscall.h (syscall number)
- [ ] 2. sysproc.c (syscall handler;)
- [ ] 3. syscall.c (syscall table to link syscall.h and sysproc.c; make sure na kasama extern and syscalls)
- Note only use *cprintf* in kernel


# 3. Extra Notes
#### Figure 1: Important parts of the gdbgui interface
	![[Pasted image 20240901211137.png]]
### New Learnings
1. Look up `git reset --soft`
	1. 