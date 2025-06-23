# File Management
----
## Write a C program to create a new text file and write "Hello, World!" to it? 
```c
#include<stdio.h>
#include<sys/types.h>
#include<unistd.h>
#include<fcntl.h>
#include<string.h>
void main()
{
        int fd,ret;
        char buf[]="hello,world,";
        fd=open("createfile.txt",O_WRONLY|O_CREAT,0660);
        if(fd<0)
        {
                printf("failed to open the file \n");
                return;
        }
        printf("file opened successfully\n");
        ret=write(fd,buf,strlen(buf));
        if(ret<0)
        {
                printf("failed to write\n");
                return;
        }
        printf("written %d bytes to file \n",ret);
        close(fd);
}
```
