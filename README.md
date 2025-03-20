1 solve the following

Study and enlist the basuc functionsused for graphics in C/C++/Python language. Give an example for each of them.


#include<iostream.h>

#include<conio.h>

#include<graphics.h>

#include<stdlib.h>


void main()

{


 	clrscr();

 int gdriver = DETECT , gmode;

 	initgraph(&gdriver, &gmode,"c:\\TurboC3\\BGI");

 	setbkcolor(15);

 setcolor(1);


 circle(100,300,50);

 	ellipse(250, 300, 0, 360,30, 70);

 arc(400,300,230,360,60);

 line(250,50,300,250);  

 rectangle(350,100,450,200);

 rectangle(500,100,550,300);


 	 int  a[12];

 	a[0]=150;

   	a[1]=100;

    	a[2]=200;

    	a[3]=150;

    	a[4]=200;

    	a[5]=200;

    	a[6]=100;

    	a[7]=200;

    	a[8]=100;

    	a[9]=150;

    	a[10]=150;

    	a[11]=100;


    	drawpoly(6,a);


    getch();

closegraph();

}


Output:

                      


Dram the coordinate axis at the center of the screen


#include<stdio.h>

#include<conio.h>

#include<graphics.h>

#include<stdlib.h>

void main()

{

int gdriver = DETECT,gmode;

int midx,midy;

initgraph(&gdriver,&gmode,"C:\\Turboc3\\BGI");

midx=getmaxx()/2;

midy=getmaxy()/2;

line(1,midy,640,midy);

line(midx,1,midx,640);

getch();

closegraph();

}



Divide your Screen into four region,draw circle,rectangle,ellipse and half ellipse in each region with appropriate message.

#include<stdio.h>

#include<conio.h>

#include<graphics.h>

#include<stdlib.h>

void main()

{

int gdriver=DETECT,gm;

int xmax,ymax;

initgraph(&gdriver,&gm,"c:\\turboc3\\bgi");

xmax=getmaxx();

ymax=getmaxy();

line(xmax/2,0,xmax/2,ymax);

line(0,ymax/2,xmax,ymax/2);

circle(170,125,100);

outtextxy(170,125,"Circle");

rectangle(58,251,304,392);

outtextxy(160,300,"Rectangle");

arc(500,150,45,135,100);

outtextxy(500,150,"Arc");

ellipse(500,300,0,360,75,25);

outtextxy(500,300,"ellipse");

getch();

}

Output:


Draw a simple hut on a screen

#include<stdio.h>

#include<conio.h>

#include<graphics.h>

#include<stdlib.h>

void main()

{

int gdriver=DETECT,gm;

initgraph(&gdriver,&gm,"c:\\turboc3\\bgi");

setcolor(WHITE);

rectangle(150,180,250,300);

rectangle(250,180,420,300);

rectangle(180,250,220,300);

line(200,100,150,180);

line(200,100,250,180);

line(200,100,370,100);

line(370,100,420,180);

setfillstyle(SOLID_FILL,BROWN);

floodfill(152,182,WHITE);

floodfill(252,182,WHITE);

setfillstyle(SLASH_FILL,BLUE);

floodfill(182,252,WHITE);

setfillstyle(HATCH_FILL,GREEN);

floodfill(200,105,WHITE);

floodfill(210,105,WHITE);

getch();

}

Output:


Draw the basic Shapes in the center of the screen

Circle

Rectangle

Square

Concentric Circles

Ellipse

Line


Code:

#include<stdio.h>

#include<conio.h>

#include<graphics.h>

#include<stdlib.h>

void main()

{

	int gdriver=DETECT,gm;

	int xmax,ymax;

	initgraph(&gdriver,&gm,"C:\\turboC3\\bgi");

	xmax=getmaxx()/2;

	ymax=getmaxy()/2;

	line(xmax,0,xmax,getmaxy());

	line(0,ymax,getmaxx(),ymax);

       	circle(xmax,ymax,100);

      	 circle(xmax,ymax,50);

      	 rectangle(xmax-50,ymax-50,xmax+50,ymax+50);

       	arc(xmax,ymax+100,45,135,100);

       	ellipse(xmax,ymax,0,360,50,75);

        	getch();

}





Output:

Develop the program to draw a line using ‘DDA’ Algorithm.


#include<conio.h>

#include<iostream.h>

#include<graphics.h>

#include<math.h>


void main  ()

{

clrscr();

int gd= DETECT, gmode;

initgraph(&gd,&gmode,"C:\\Turboc3\\BGI");

setbkcolor(15);


int x1,y1,x2,y2,steps,xi,yi,xk,yk,dx,dy;


cout<<"Enter the starting point (x,y) :\t";

cin>>x1>>y1;


cout<<"Enter the ending point (x,y) :\t";

cin>>x2>>y2;


dx=x2-x1;

dy=y2-y1;


xk=x1;

yk=y1;


if(abs(dx)>=abs(dy))

steps=abs(dx);

else

steps=abs(dy);


while(xk!=x2 || yk!=y2)

{

xi=dx/steps;

yi=dy/steps;


putpixel(xk,yk,1);


xk=xk+xi;

yk=yk+yi;


putpixel(xk,yk,1);

}


getch();


}


Output:


Develop program to draw a line using ‘Bresnham’s line drawing Algorithm’.

#include <graphics.h>

#include <stdlib.h>

#include <stdio.h>

#include<iostream.h>

#include <conio.h>

#include<math.h>

void main()

{

int gdriver = DETECT, gmode;

initgraph(&gdriver, &gmode, "C:\\Turboc3\\BGI");

//setbkcolor(15);



int x1,y1,x2,y2,dx,dy,p0,yi,xi,xn,yn,xk,yk;


cout<<"enter the starting points="<<endl;

cin>>x1>>y1;

cout<<"enter the ending points="<<endl;

cin>>x2>>y2;


dx=x2-x1;

dy=y2-y1;


xk=x1;

yk=y1;


while(xk!=x2 || yk!=y2)

{

if(abs(dy)<=abs(dx))

{

p0=2*abs(dy)-abs(dx);

if(p0<0)

{

xi=dx/abs(dx);

yi=0;

p0=p0+2*abs(dy);

}

else if(p0>0)

{

xi=dx/abs(dx);

yi=dy/abs(dy);

p0=p0+2*abs(dy)-2*abs(dx);

}

}


if(abs(dy)>abs(dx))

{

p0=2*abs(dx)-abs(dy);

if (p0<0)

{

xi=0;

yi=dy/abs(dy);

p0=p0+2*abs(dx);

}

else if(p0>0)

{

xi=dx/abs(dx);

yi=dy/abs(dy);

p0=p0+2*abs(dx)-2*abs(dy);

}

}

xk=xk+xi;

yk=yk+yi;

putpixel(xk,yk,1);

}

getch();

}


Output:




Solve ethe following

Write a Program to draw a circle using ‘Bresnham’s Circle Algorithm’.

Write a program to draw a circle using ‘Mid point Circle drawing Algorithm’.


a. Write a Program to draw a circle using ‘Bresnham’s Circle Algorithm’.


#include<iostream.h>

#include<conio.h>

#include<graphics.h>

#include<stdio.h>

void main()

{

	clrscr();

	int gdriver=DETECT,gmode;

	initgraph(&gdriver,&gmode,"c:\\Turboc3\\BGI");


	setbkcolor(15);



	int x0,y0,r,d0,x,xc,yc,y;


	cout<<"ENTER THE CENTRE AND RADIUS";

	cin>>xc>>yc>>r;


	x=0;

	y=r;

	d0=3-2*r;


    while(x<=y)

    {

     if(d0<0)

     {     x=x+1;

	   y=y;

	  d0=d0+4*x+6;

     }

     else if(d0>0)

     {

	x=x+1;

	y=y-1;

	d0=d0+4*(x-y)+10;

     }


     putpixel(xc+x,yc+y,1);

     putpixel(xc+x,yc-y,1);

     putpixel(xc-x,yc+y,1);

     putpixel(xc-x,yc-y,1);

     putpixel(xc+y,yc+x,1);

     putpixel(xc+y,yc-x,1);

     putpixel(xc-y,yc+x,1);

     putpixel(xc-y,yc-x,1);


    }

	getch();

}


Output:



b. Write a program to draw a circle using ‘Mid point Circle drawing Algorithm’.

#include<iostream.h>

#include<conio.h>

#include<graphics.h>

#include<stdio.h>

void main()

{

clrscr();

int gdriver=DETECT,gmode;

initgraph(&gdriver,&gmode,"c:\\Turboc3\\BGI");

setbkcolor(15);


int r,xc,yc,x0,y0;

float pk;


cout<<"ENTER THE CENTRE AND RADIUS";

cin>>xc>>yc>>r;


x0=0;

y0=r;



pk=1-r;

while(x0<=y0)

{

if(pk<0)

{

x0=x0+1;

y0=y0;

pk=pk+2*x0+1;

}

else

{

x0=x0+1;

y0=y0-1;

pk=pk+2*(x0-y0)+1;

}

putpixel(xc+x0,yc+y0,1);

putpixel(xc+x0,yc-y0,1);

putpixel(xc-x0,yc+y0,1);

putpixel(xc-x0,yc-y0,1);

putpixel(xc+y0,yc+x0,1);

putpixel(xc+y0,yc-x0,1);

putpixel(xc-y0,yc+x0,1);

putpixel(xc-y0,yc-x0,1);

}

getch();

}


Output:




Practical no. 6A

AIM: Write a program to implement 2D scaling

#include<graphics.h>

#include<stdlib.h>

#include<stdio.h>

#include<math.h>

#include<conio.h>

void main()

{

int gd=DETECT,gm;

initgraph(&gd,&gm,"c:\\turboc3\\bgi");

//int i;

int x2,y2,x1,y1,x,y;

printf("Enter the line end points:");

printf("x1,y1,x2,y2");

scanf("%d%d%d%d",&x1,&y1,&x2,&y2);

line(x1,y1,x2,y2);

printf("Enter scaling coordinate");

printf("x,y");

scanf("%d%d",&x,&y);

x1=(x1*x);

y1=(y1*y);

x2=(x2*x);

y2=(y2*y);

printf("line after scaling");

line(x1,y1,x2,y2);

getch();

}


Output:






Practical no. 6B

AIM: Write a program to implement 2D translation

#include<graphics.h>

#include<stdlib.h>

#include<stdio.h>

#include<math.h>

#include<conio.h>

void main()

{

int gd=DETECT,gm;

initgraph(&gd,&gm,"c:\\turboc3\\bgi");

//int i;

int x2,y2,x1,y1,x,y;

printf("Enter the line end points:");

printf("x1,y1,x2,y2");

scanf("%d%d%d%d",&x1,&y1,&x2,&y2);

line(x1,y1,x2,y2);

printf("Enter scaling coordinate");

printf("x,y");

scanf("%d%d",&x,&y);

x1=(x1*x);

y1=(y1*y);

x2=(x2*x);

y2=(y2*y);

printf("line after scaling");

line(x1,y1,x2,y2);

getch();

}


Output:


Practical no. 7A

AIM: Perform 2D rotation on a given object


#include<stdio.h>

#include<conio.h>

#include<graphics.h>

#include<stdlib.h>

#include<math.h>

void main()

{

int gd=DETECT,gm,errorcode;

int i;

int x2,y2,x1,y1,x,y,xn,yn;

double r11,r12,th;

float r21,r22;

clrscr();

printf("Enter the 2 line end points:");

printf("x,y1,x2,y2");

scanf("%d%d%d%d",&x1,&y1,&x2,&y2);

initgraph(&gd,&gm,"c:\\turboc3\\bgi");

line(x1,y1,x2,y2);

printf("\n\n\n Enter the angle");

scanf("%1f",&th);

r11=cos((th*3.1428)/180);

r12=sin((th*3.1428)/180);

r21=(-sin((th*3.1428)/180);

r22=cos((th*3.1428)/180);

xn=((x2*r11)-(y2*r12));

yn=((x2*r12)+(y2*r11));

line(x1,y1,xn.yn);

getch();

closegraph();

}


Output :

AIM: program to create a house like figure and perform the following operations.

Scaling about the origin followed by translation 

Scaling with reference to an arbitrary point

Reflect about the line y=mx + c


#include<stdio.h>

#include<graphics.h>

#include<stdlib.h>

#include<math.h>

#include<conio.h>

void reset(int h[][2])

{

int val[9][2]={

{50,50},{75,50},{75,75},{100,75},{100,50},{125,50},{125,100},{87,125},{50,100}

};

int i;

for(i=0;i<9;i++)

{

h[i][0]=val[i][0]-50;

h[i][1]=val[i][1]-50;

}

}

void draw(int h[][2])

{

int i;

setlinestyle(DOTTED_LINE,0,1);

line(320,0,320,480);

line(0,240,640,240);

setlinestyle(SOLID_LINE,0,1);

for(i=0;i<8;i++)

line(320+h[i][0],240-h[i][1],320+h[i+1][0],240-h[i+1][1]);

line(320+h[0][0],240-h[0][1],320+h[8][0],240-h[8][1]);

}

void rotate(int h[][2],float angle)

{

int i;

for(i=0;i<9;i++)

{

int xnew,ynew;

xnew=h[i][0]*cos(angle)-h[i][1]*sin(angle);

ynew=h[i][0]*sin(angle)-h[i][1]*cos(angle);

h[i][0]=xnew;h[i][1]=ynew;

}

}

void scale(int h[][2],int sx,int sy)

{

int i;

for(i=0;i<9;i++)

{

h[i][0]*=sx;

h[i][1]*=sy;

}

}

void translate(int h[][2],int dx,int dy)

{

int i;

for(i=0;i<9;i++)

{

h[i][0]+=dx;

h[i][1]+=dy;

}

}

void reflect(int h[][2],int m,int c)

{

int i;

float angle;

for(i=0;i<9;i++)

h[i][1]-=c;

angle=M_PI/2-atan(m);

rotate(h,angle);

for(i=0;i<9;i++)

h[i][1]+=c;

}

void ini()

{

int gd=DETECT,gm;

initgraph(&gd,&gm,"c:\\turboc3\\bgi");

}

void dini()

{

getch();

closegraph();

}

void main()

{

int h[9][2],sx,sy,x,y,m,c,choice;

do

{

clrscr();

printf("1.Scaling about the origin.\n");

printf("2.Scaling about an arbitrary point.\n");

printf("3.Reflection about the line y=mx+c.\n");

printf("4.Exit\n");

printf("Enter the choice:");

scanf("%d",&choice);

switch(choice)

{

case 1:printf("Enter the x- and y-scaling factors:");

scanf("%d%d",&sx,&sy);

ini();

reset(h);

draw(h);

getch();

scale(h,sx,sy);

cleardevice();

draw(h);

dini();

break;

case 2:printf("Enter the x- and y-scaling factors:");

scanf("%d%d",&sx,&sy);

printf("Enter the x- and y-coordinates of the point:");

scanf("%d%d",&sx,&sy);

ini();

reset(h);

translate(h,x,y);

draw(h);

getch();

translate(h,x,y);

cleardevice();

draw(h);

putpixel(320+x,240-y,WHITE);

dini();

break;

case 3:printf("Enter the values of m and c:");

scanf("%d%d",&m,&c);

ini();

reset(h);

draw(h);

getch();

reflect(h,m,c);

cleardevice();

draw(h);

dini();

break;

case 4:exit(0);

}

}while(choice!=4);

}


OUTPUT:

Practical no 8

Aim: Write a program to implement liang-barsky line clippling algorithm

#include<iostream.h>
#include<conio.h>
#include<graphics.h>
void main()
{
int gd=DETECT,gm;
initgraph(&gd,&gd,"C:\\Turboc3\\BGI");
int
x1,y1,x2,y2,xmax,xmin,ymax,ymin,xx1,yy1,xx2,yy2,dx,dy,i;
int p[4],q[4];
float t1,t2,t[4];
cout<<"Enter the lower co-ordinates of window";
cin>>xmin>>ymin;
cout<<"Enter the upper co-ordinates of window";
cin>>xmax>>ymax;
setcolor(RED);
rectangle(xmin,ymin,xmax,ymax);
cout<<"Enter x1:";
cin>>x1;
cout<<"Enter y1:";
cin>>y1;
cout<<"Enter x2:";
cin>>x2;
cout<<"Enter y2:";
cin>>y2;
line(x1,y1,x2,y2);
dx=x2-x1;
dy=y2-y1;
p[0]=-dx;
p[1]=dx;
p[2]=-dy;
p[3]=dy;
q[0]=x1-xmin;
q[1]=xmax-x1;
q[2]=y1-ymin;
q[3]=ymax-y1;
for(i=0;i<4;i++){
if(p[i]!=0){
t[i]=(float)q[i]/p[i];
}
else
if(p[i]==0&&q[i]<0)
cout<<"line completely outside the window";
else
if(p[i]==0&&q[i]>=0)
cout<<"line completely inside the window";

}
if(t[0]>t[2]){
t1=t[0];
}
else{
t1=t[2];
}
if(t[1]<t[3]){
t2=t[1];
}
else{
t2=t[3];
}
if(t1<t2){
xx1=x1+t1*dx;
xx2=x1+t2*dx;
yy1=y1+t1*dy;
yy2=y1+t2*dy;
cout<<"line after clipping:";
setcolor(WHITE);
line(xx1,yy1,xx2,yy2);
}
else{
cout<<"line lies out of the window";
}
getch();
}

Output: (refer text book page no. L -14)


Write a program to fill circle using floodfill algorithm


#include<stdio.h>

#include<graphics.h>

#include<dos.h>

void floodFill(int x,int y,int oldcolor,int newcolor)

{

if(getpixel(x,y)==oldcolor)

{

putpixel(x,y,newcolor);

floodFill(x+1,y,oldcolor,newcolor);

floodFill(x,y+1,oldcolor,newcolor);

floodFill(x-1,y,oldcolor,newcolor);

floodFill(x,y-1,oldcolor,newcolor);

}

}

//getpixel(x,y)given the color of specified pixel

int main()

{

int gm,gd=DETECT,radius;

int x,y;

printf("Enter x and y position for circle\n");

scanf("%d%d",&x,&y);

printf("Enter radius of circle\n");

scanf("%d",&radius);

initgraph(&gd,&gm,"c:\\turbo3\\bgi");

circle(x,y,radius);

floodFill(x,y,0,14);

delay(5000);

closegraph();

return 0;

}










Output
























Pratical no 9 B


Write a program to fill a circle using boundary fill algorithm


Program 


#include<iostream.h>

#include<graphics.h>

#include<dos.h>

void boundaryfill(int x,int y,int f_color,int b_color)

{

if(getpixel(x,y)!=b_color&& getpixel(x,y)!=f_color)

{

putpixel(x,y,f_color);

boundaryfill(x+1,y,f_color,b_color);

boundaryfill(x,y+1,f_color,b_color);

boundaryfill(x-1,y,f_color,b_color);

boundaryfill(x,y-1,f_color,b_color);

}

}

int main()

{

int gm,gd=DETECT,radius;

int x,y;

cout<<"Enter x & y positions for circle\n";

cin>>x>>y;

cout<<"Enter radius of circle \n";

cin>>radius;

initgraph(&gd,&gm,"C:\\TURBOC3\\BGI");

circle(x,y,radius);

boundaryfill(x,y,4,15);

delay(5000);

closegraph();

return 0;

}
Output

g

Perform Smiling face animation using graphic function

#include <conio.h>

#include <dos.h>

#include <graphics.h>

#include <stdio.h>


// Driver Code

int main()

{

    // Initialize graphic driver

    int gd = DETECT, gm;

    initgraph(&gd, &gm, "C:\\Turboc3\\BGI");

    setcolor(YELLOW);


    // creating circle and fill it with

    // yellow color using floodfill.

    circle(300, 100, 40);

    setfillstyle(SOLID_FILL, YELLOW);

    floodfill(300, 100, YELLOW);


    // Set color of background to black

    setcolor(BLACK);

    setfillstyle(SOLID_FILL, BLACK);


    // Use fill ellipse for creating eyes

    fillellipse(310, 85, 2, 6);

    fillellipse(290, 85, 2, 6);


    // Use ellipse for creating mouth

    ellipse(300, 100, 205, 335, 20, 9);

    ellipse(300, 100, 205, 335, 20, 10);

    ellipse(300, 100, 205, 335, 20, 11);


    getch();

    closegraph();

    return 0;

}


Output:


c. Draw the moving car on the screen


#include <conio.h>

#include <dos.h>

#include <graphics.h>

#include <stdio.h>

void draw_moving_car(void)

 {

   int i, gd = DETECT, gm;

  initgraph(&gd, &gm, "c:\\turboc3\\bgi");

    for (i = 0; i <= 420; i = i + 10) {


	// Set color of car as red

	setcolor(RED);


	// These lines for bonnet and

	// body of car

	line(0 + i, 300, 210 + i, 300);

	line(50 + i, 300, 75 + i, 270);

	line(75 + i, 270, 150 + i, 270);

	line(150 + i, 270, 165 + i, 300);

	line(0 + i, 300, 0 + i, 330);

	line(210 + i, 300, 210 + i, 330);


	// For left wheel of car

	circle(65 + i, 330, 15);

	circle(65 + i, 330, 2);


	// For right wheel of car

	circle(145 + i, 330, 15);

	circle(145 + i, 330, 2);


	// Line left of left wheel

	line(0 + i, 330, 50 + i, 330);


	// Line middle of both wheel

	line(80 + i, 330, 130 + i, 330);


	// Line right of right wheel

	line(210 + i, 330, 160 + i, 330);


	delay(100);


	// To erase previous drawn car, draw

	// the whole car at same position

	// but color using black

	setcolor(BLACK);


	// Lines for bonnet and body of car

	line(0 + i, 300, 210 + i, 300);

	line(50 + i, 300, 75 + i, 270);

	line(75 + i, 270, 150 + i, 270);

	line(150 + i, 270, 165 + i, 300);

	line(0 + i, 300, 0 + i, 330);

	line(210 + i, 300, 210 + i, 330);


	// For left wheel of car

	circle(65 + i, 330, 15);

	circle(65 + i, 330, 2);


	// For right wheel of car

	circle(145 + i, 330, 15);

	circle(145 + i, 330, 2);


	// Line left of left wheel

	line(0 + i, 330, 50 + i, 330);


	// Line middle of both wheel

	line(80 + i, 330, 130 + i, 330);


	// Line right of right wheel

	line(210 + i, 330, 160 + i, 330);

    }

    getch();

    closegraph();

}

int main()

{

    draw_moving_car();

    return 0;

}


Output



