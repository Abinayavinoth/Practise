#include <stdio.h>
#include <sys/types.h>
#include <unistd.h>

int main() {
   fork();
   printf("Called fork() system call\n");
   return 0;
}

#include<unistd.h>
#include<stdio.h>
#include<sys/types.h>
int main()
{
   printf("Hello\n");
   fork(); 
   printf("World\n");
   return 0;
}

#include <sys/wait.h>
#include <unistd.h>
#include <sys/types.h>
#include <stdio.h>
int main( ){
   pid_t child_pid;
   child_pid = fork (); // Create a new child process;
   if (child_pid < 0) 
   {
      printf("fork failed");
      return 1;
   } 
    else if (child_pid == 0) 
  {
      printf ("child process successfully created!");
      printf ("child_PID = %d,parent_PID = %d",
      getpid(), getppid( ) );
   } 
    else {
      wait(NULL);
  printf ("parent process successfully created!");
      printf ("child_PID = %d, parent_PID = %d", getpid( ), getppid( ) );
   }
   return 0;
}



