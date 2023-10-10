# OS-EX.6-IMPLEMENTATION-OF-INTER-PROCESS-COMMUNICATION-USING-PIPE

## AIM:
Write C programs to illustrate IPC using pipes mechanisms

## ALGORITHM:

Create a child process usingfork()

Create a simple pipe with C, we make use of the pipe() systemcall.

Create two file descriptor fd[0] is set up for reading, fd[1] isset up forwriting

Close the read end of parent process using close() and perform writeoperation

Close the write end of child process and performreading

Display the text.
## PROGRAM:
```
#include <stdio.h>

int main()

{

int fd[2],child; char a[20];

printf("\n Enter the string:");

scanf("%s",a);

pipe(fd);

child=fork();

if(!child)

{

close(fd[0]);

write(fd[1],a,5); wait(0);

}

else

{

close(fd[1]);

read(fd[0],a,5); printf("The string received from pipe is: %s",a);

}

return 0;

}
```


## OUTPUT:

![image](https://github.com/KumaravelIT/OS-EX.6-IMPLEMENTATION-OF-INTER-PROCESS-COMMUNICATION-USING-PIPE/assets/117756569/19db49c6-d1a8-4469-9953-5b3ade7eeaf6)



## RESULT:
Thus, IPC using pipes mechanisms is illustrated using c program successfully
