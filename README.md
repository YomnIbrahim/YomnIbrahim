-#include <GL/gl.h>
#include <GL/glu.h>
#include <GL/glut.h>
#include<math.h>


#include <stdlib.h>
#include <windows.h>
void display();
void reshape(int w,int h);
void timer(int);



void init(){
    glClearColor(73.0/255.0,146.0/255.0 ,255.0/255.0,0.0);
}
int main(int argc,char**argv)
{
    glutInit(&argc,argv);
    glutInitDisplayMode(GLUT_RGB);

    glutInitWindowPosition(200,0);
    glutInitWindowSize(1200,800);

    glutCreateWindow("20100797");

    glutDisplayFunc(display);
    glutReshapeFunc(reshape);
    glutTimerFunc(0,timer,0);

     init();

    glutMainLoop();
}
float step=0;
void display()
{
    glClear(GL_COLOR_BUFFER_BIT);
    glLoadIdentity();
    double radius;


 //sea
glPushMatrix();
glBegin(GL_QUADS);
glColor3ub(0, 255 ,255);
glVertex2f(-15,-4);
glVertex2f(-15,-10);
glVertex2f(15,-10);
glVertex2f(15,-4);
glEnd();
glPopMatrix();

//wave1

glPushMatrix();
    glLineWidth(10.0);
    glBegin(GL_POLYGON);
    glColor3ub(245 ,245 ,245);
    glVertex2f(-15,-4);
    glVertex2f(-9,-4);
    glVertex2f(-12,-1);

    glEnd();
glPopMatrix();


//wave 2

glPushMatrix();
    glLineWidth(10.0);
    glBegin(GL_POLYGON);
    glColor3ub(245 ,245 ,245);
    glVertex2f(-9,-4);
    glVertex2f(-3,-4);
    glVertex2f(-6,-1);

    glEnd();
glPopMatrix();

//wave 3

glPushMatrix();
    glLineWidth(10.0);
    glBegin(GL_POLYGON);
    glColor3ub(245 ,245 ,245);
    glVertex2f(-3,-4);
    glVertex2f(3,-4);
    glVertex2f(0,-1);

    glEnd();
glPopMatrix();


//wave 4

glPushMatrix();
    glLineWidth(10.0);
    glBegin(GL_POLYGON);
    glColor3ub(245 ,245 ,245);
    glVertex2f(3,-4);
    glVertex2f(9,-4);
    glVertex2f(6,-1);

    glEnd();
glPopMatrix();

//wave 5

glPushMatrix();
    glLineWidth(10.0);
    glBegin(GL_POLYGON);
    glColor3ub(245 ,245 ,245);
    glVertex2f(9,-4);
    glVertex2f(15,-4);
    glVertex2f(12,-1);

    glEnd();
glPopMatrix();

//boat1
glPushMatrix();
    glLineWidth(10.0);
    glBegin(GL_POLYGON);
    glColor3ub(205 ,133 ,63);
    glVertex2f(-8+step,2);
    glVertex2f(-6+step,-1);
    glVertex2f(6+step,-1);
    glVertex2f(8+step,2);


    glEnd();
glPopMatrix();

//flag pole1
glPushMatrix();
glBegin(GL_QUADS);
glColor3ub(245, 222 ,179);
glVertex2f(-0.5+step,8);
glVertex2f(-0.5+step,2);
glVertex2f(0.5+step,2);
glVertex2f(0.5+step,8);
glEnd();
glPopMatrix();


//flag1
glPushMatrix();
    glLineWidth(10.0);
    glBegin(GL_POLYGON);
    glColor3ub(25 ,25 ,112);
    glVertex2f(-3+step,2.5);
    glVertex2f(-0.5+step,2.5);
    glVertex2f(-0.5+step,7);

    glEnd();
glPopMatrix();


//flag2
glPushMatrix();
    glLineWidth(10.0);
    glBegin(GL_POLYGON);
    glColor3ub(255 ,255 ,0);
    glVertex2f(3+step,2.5);
    glVertex2f(0.5+step,2.5);
    glVertex2f(0.5+step,6);

    glEnd();
glPopMatrix();

//flag3
glPushMatrix();
    glLineWidth(10.0);
    glBegin(GL_POLYGON);
    glColor3ub(255 ,0 ,0);
    glVertex2f(0.5+step,6);
    glVertex2f(3+step,7.5);
    glVertex2f(0.5+step,8);

    glEnd();
glPopMatrix();


//boat2
glPushMatrix();
    glLineWidth(10.0);
    glBegin(GL_POLYGON);
    glColor3ub(205 ,133 ,63);
    glVertex2f(-15+step,-1);
    glVertex2f(-13+step,-2);
    glVertex2f(-11+step,-2);
    glVertex2f(-9+step,-1);


    glEnd();
glPopMatrix();

//flag pole2
glPushMatrix();
glBegin(GL_QUADS);
glColor3ub(245, 222 ,179);
glVertex2f(-12.25+step,2.5);
glVertex2f(-12.25+step,-1);
glVertex2f(-11.5+step,-1);
glVertex2f(-11.5+step,2.5);
glEnd();
glPopMatrix();


//flag1
glPushMatrix();
    glLineWidth(10.0);
    glBegin(GL_POLYGON);
    glColor3ub(25 ,25 ,112);
    glVertex2f(-14+step,-0.5);
    glVertex2f(-12.25+step,-0.5);
    glVertex2f(-12.25+step,1);

    glEnd();
glPopMatrix();


//flag2
glPushMatrix();
    glLineWidth(10.0);
    glBegin(GL_POLYGON);
    glColor3ub(255 ,255 ,0);
    glVertex2f(-10+step,-0.5);
    glVertex2f(-11.5+step,-0.5);
    glVertex2f(-11.5+step,0.75);

    glEnd();
glPopMatrix();

//flag3
glPushMatrix();
    glLineWidth(10.0);
    glBegin(GL_POLYGON);
    glColor3ub(255 ,0 ,0);
    glVertex2f(-10+step,0.5);
    glVertex2f(-11.5+step,0.5);
    glVertex2f(-11.5+step,1);

    glRotated(180,-12.5,1,2);

    glEnd();
glPopMatrix();

//sun
glPushMatrix();
glTranslated(-12,8,0);
glBegin(GL_POLYGON);
glColor3ub(255,255,0);
radius=1.8;
for(int i=0;i<360;i++){
    double angle=i*3.14/180;
    glVertex2d(cos(angle)*radius,radius*sin(angle));
}


glEnd();
glPopMatrix();

//sun's face
glPushMatrix();
    glLineWidth(10.0);
    glBegin(GL_POLYGON);
    glColor3ub(245 ,245 ,245);
    glVertex2f(-13.5,8.5);
    glVertex2f(-12.5,8.5);
    glVertex2f(-13,9);

    glEnd();
glPopMatrix();

glPushMatrix();
    glLineWidth(10.0);
    glBegin(GL_POLYGON);
    glColor3ub(245 ,245 ,245);
    glVertex2f(-11.5,8.5);
    glVertex2f(-10.5,8.5);
    glVertex2f(-11,9);

    glEnd();
glPopMatrix();

glPushMatrix();
    glLineWidth(10.0);
    glBegin(GL_POLYGON);
    glColor3ub(255 ,0 ,0);
    glVertex2f(-13.5,8.5);
    glVertex2f(-12.5,8.5);
    glVertex2f(-13,8);

    glEnd();
glPopMatrix();


glPopMatrix();

glPushMatrix();
    glLineWidth(10.0);
    glBegin(GL_POLYGON);
    glColor3ub(255 ,0 ,0);
    glVertex2f(-11.5,8.5);
    glVertex2f(-10.5,8.5);
    glVertex2f(-11,8);

    glEnd();
glPopMatrix();

glPushMatrix();
glTranslated(-12,7,0);
glBegin(GL_POLYGON);
glColor3ub(0,0,0);
radius=0.5;
for(int i=0;i<360;i++){
    double angle=i*3.14/180;
    glVertex2d(cos(angle)*radius,radius*sin(angle));
}


glEnd();
glPopMatrix();
    glFlush();
}

void reshape(int w,int h)
{
    glViewport(0,0,(GLsizei)w,(GLsizei)h);
    glMatrixMode(GL_PROJECTION);
    glLoadIdentity();
    gluOrtho2D(-15,15,-10,10);
    glMatrixMode(GL_MODELVIEW);
}


void timer(int){
glutPostRedisplay();
glutTimerFunc(1000/25,timer,0);
step+=0.1;


}
