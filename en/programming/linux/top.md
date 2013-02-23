# top

## In a nutshell
* upon entering top, press 'zxcb' and use '>' or '<' to change the sort field
z : Toggle: 'z' color/mono;
x : Toggle highlights: 'x' sort field;
c : Toggle: 'c' cmd name/line;
b : bold/reverse (only if 'x' )
R : toggle sorting order

## Controls for the top bar
B     : disable/enable bold
l,t,m : Toggle Summaries: 'l' load avg; 't' task/cpu stats; 'm' mem info
1     : Toggle SMP view: '1' single/separate states
f,F   : Manage Fields: add/remove; change order; select sort field

## Other controls
d,s : Set update interval
k,r : Manipulate tasks: 'k' kill; 'r' renice
u   : Press u then username to get only that user process details

## Other notes
* VIRT is paging mem
* actual memory consumption of a process is somewhere between RES and RES minus SHR, depending on how many shared libraries are loaded by any given process and other processes using those same libraries.