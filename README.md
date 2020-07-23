# Pacman-Game-coding in C
#include<graphics.h>
#include<conio.h> 
#include<stdlib.h>
#include<dos.h>
void m_right(int,int,int,int); 
void m_up(int,int,int,int);
void m_left(int,int,int,int);
void m_down(int,int,int,int); 
void grid(); 
int main(void)
{
int gd=DETECT,gm; 
int xmax,ymax; 
initgraph(&gd,&gm,"C:\\tc\\bgi");
grid(); //MAIN FUNCTION
m_right(80,360,560,360); 
m_up(560,360,560,80); 
m_left(560,80,80,80);
m_down(80,80,80,360);.
getch(); clrscr(); 
settextstyle(0,0,2); 
getch(); 
return 0;
}

void grid() //FUNCTION FOR GRID FORMATION
{ 
setcolor(8);
outtextxy(400,460,"Paceman"); 
setcolor(9);
for(int i=40;i<640;i++)
{ 
for(int j=40;j<480;j++)
{ 
if(i%40==0 && j%40==0)
{ 
outtextxy(i,j,"%"); } 
}
} 
}
voiod m_right(int a,int b,int c, int d) //FUNCTION FOR MOVING RIGHT
{ 
int s,e; s=30,e=330; 
for(int k=a;k<c;k++) 
{ 
if(s==0) 
{
s=30; e=330; }
setfillstyle(SOLID_FILL,14); 
pieslice(k,b,s,e,25);
settextstyle(SOLID_FILL,0);
pieslice(k,b-15,0,360,5);
setcolor(0);
sound(k);
delay(15); 
nosound(); 
circle(k,b,25);
s=s-1; e=e+1; }

}
void m_up(int a,int b,int c, int d) //FUNCTION FOR MOVING UP
{ 
int s,e; s=60,e=120;
for(int l=b;l>d;l--) 
{ if(s==90) 
{ s=60; e=120; }
setfillstyle(SOLID_FILL,14); 
pieslice(a,1,0,360,25);
setfillstyle(SOLID_FILL,0);
pieslice(a-15,1,0,360,5);
pieslice(a,l,s,e,25); 
setcolor(0); 
sound(l); 
delay(15); 
nosound(); 
circle(a,l,25); 
s=s+1; e=e-1; } }
void m_left(int a,int b,int c, int d) //FUNCTION FOR MOVING LEFT
{ int s,e; s=150,e=210;
for(int k=b;k>c;k--)
{ if(s==180)
{ s=150; e=210; }
setfillstyle(SOLID_FILL,14);
pieslice(k,b,0,360,25); 
setfillstyle(SOLID_FILL,0);
pieslice(k,b-15,0,360,5);
pieslice(k,b,s,e,25);
setcolor(0); 
sound(k); 
delay(15); 
nosound();
circle(k,b,25);
s=s+1;
e=e-1; } }
void m_down(int a,int b,int c, int d) //FUNCTION FOR MOVING DOWN 
{ int s,e; 
s=250,e=300;
for(int l=b;l<d;l++)
{
if(s==270)
{ s=250; e=300; }
setfillstyle(SOLID_FILL,14);
pieslice(a,l,0,360,25);
setfillstyle(SOLID_FILL,0); 
pieslice(a-15,l,0,360,5);
pieslice(a,l,s,e,25);
setcolor(0); 
sound(l);
delay(15);
nosound();
circle(a,l,25);
s=s+1; 
e=e-1; } }
