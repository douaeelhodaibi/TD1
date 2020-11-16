# TD1#pragma once
//main
#ifndef CERCLE _H
#define CERCLE _H


class Cercle
{
    public:

        Cercle (double , Point );
        Cercle(const Cercle &c);
        void m_print();
        double get_rayon() const ;//permet d acceder a rayon qui est prive
        void set_rayon(double r);//pour changer le rayon
        Cercle translate(double d);
        double surface()const;
        double perimetre()const;
        ~Cercle () {}

    private:
        double rayon;
        Point centre;
};

#endif // CERCLE _H

#ifndef POINT_H
#define POINT_H
#include <string.h>
#include "Cercle.h"

class Point
{
    //public:
       // Point();
       // Point(double,double);
      //  Point (const Point &P);//this modifiable
     //   void m_printPoint() const ;//l objet courant non modifiable
      //  string tostring();
       // Point translate(double d);
         private:
    Point();
    Point(double; double);
    Point (const Point &p);
    public:
    void m_print() const;
    Point translate(double d);
    static Point m_creator (double x, double y);//methode de classe
    private:
        double x;
        double y;
        }
        //Cercle.cpp
 #include "Cercle.h"
#include <iostream>

using namespace std;
Cercle:: Cercle()
{
double x,y;
Point :: m_creator(x,y);
//Point p;//c est un objet
this->rayon=0;
}
Cercle::Cercle(double r, const Point & P)
{
    this->centre= P;
    this->rayon = r;
}

Cercle::Cercle( const Cercle & c)
{
    this->centre = Point (c.centre);
    this->rayon =c.rayon;
}
void Cercle :: m_print()
{
    cout <<" le rayon " << this->rayon ;
    this->centre.m_print() ;
}
double Cercle :: get_rayon () const
{
    return this->rayon;
}
void Cercle :: set_rayon(double r)//tjr void pour modifier
{
    this->rayon = r;
}
Cercle Cercle  ::translate (double d)
{
    Cercle res;
    res.centre=this->centre.translate (d);//translation du cercle = translation du centre
    res.rayon=this->rayon;//tjr le meme rayon
return res();
}
double Cercle :: surface() const
{
  double res;
  res=3.14*this->rayon * this->rayon;
  return res;
}
double Cercle :: perimetre()const{
double res ;
res=2*3.14 *this->rayon;
return res;
}
bool Point::operator == (const Point & a , const Point & b){//tester appartenance au cercle
   if (pow(a-(this->center),2)+pow(b-(this->center),2)< pow(this->rayon,2))
    return true;
else
    return false;}
bool Cercle :: operator==(double rr){//egalite des cercle
if (this->rayon == rr)
    return true ;
else
return false;
}
//Point.cpp

#include "Point.h"
#include <iostream>
#include <string>
using namespace std;

Point :: Point()
{
    this->x=0;
    this->y=0;
}
Point::Point(double x ,double y)
{
    this->x=x;
    this->y=y;

}

point::Point (const Point & P){
this->x=P.x;
this->y=P.y;
}
 void Point ::m_print () const
 {
    cout <<"(" << this->x << "," << this->y<<  ")"<< endl;// << operateur decalage a droite
 }
string Point ::tostring(){
    string s;
    s="("+ this->x +","+ this->y +")";
return s;

}
Point Point :: translate (double d)
{
    Point P;
    P.x=this->x + d;
    P.y=this->y + d;
    return P;
}
Point Point :: m_creator(double x, double y)//creer un point--impo de travailler avc this
{
    Point P1(x,y);//x et y sont des valeures
    return P1;
}

#endif // POINT_H

//main.cpp
#include <iostream>
#include "Point.h"

using namespace std;

int main()
{
  // Point p;
   //Cercle c;
 POint :: m_creator//passer via une classe __doit etre statique
}
