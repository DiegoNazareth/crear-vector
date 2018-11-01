#include "Vector.hpp"
#include <cstdlib>
#include <iostream>
using namespace std;

Vector::Vector( int n )
{
   dim = n;
	lista = new int [dim];
	for (int i = 0; i < dim; i++)
	  lista[i] = 0;
}
Vector::Vector(const Vector &A){
	this->dim=A.dim;
	lista=new int[A.dim];
	for(int i=0;i<A.dim;i++){
		lista[i]=A.lista[i];
	}
	
}

Vector Vector::operator +(const Vector &B){
	Vector *temp;
	if(this->dim==B.dim){
		temp=new Vector(B.dim);
		temp->dim=B.dim;
		for(int i=0;i<B.dim;i++){
			temp->lista[i]=lista[i]+B.lista[i];
		}
		return *temp;
	}
}

Vector Vector::operator *(int x){
	Vector *temp;
	temp=new Vector(dim);
	temp->dim=dim;
	for(int i=0;i<dim;i++){
		temp->lista[i]=x*lista[i];
	}
	return *temp;
}

Vector operator *( int x, const Vector &B ){
	Vector *temp;
	temp=new Vector(B.dim);
	temp->dim=B.dim;
	for(int i=0;i<B.dim;i++){
		temp->lista[i]=x*B.lista[i];
	}
	return *temp;
}

//const Vector & operator =( const Vector & );
const Vector &Vector::operator =(const Vector &B){
	if(this != &B){
		dim=B.dim;
		delete []lista;
		lista=new int[B.dim];
		for(int i=0;i<B.dim;i++){
			lista[i]=B.lista[i];
		}
		return *this;
	}
}
//bool operator ==( const Vector & ); // igualdad A == B
bool Vector::operator ==(const Vector &B){
	bool b;
	if(this != &B  && dim==B.dim){
		for(int i=0;i<dim;i++){
			if(lista[i]==B.lista[i])
				b=true;
			else{
				b=false;
				break;
			}
		}
		return b;
	}
}
      
istream& operator >>( istream &in, Vector &A ){
	for(int i=0;i<A.dim;i++){
		cout<<"V["<<i+1<<"] :  ";
		in>>A.lista[i];
		cout<<endl;
	}
	return in;
}

ostream& operator <<( ostream &out, const Vector &A ){
	for(int i=0;i<A.dim;i++)
		out<<A.lista[i]<<"\t";
	out<<endl;
	return out;
}
      
//Vector & renew( int );
Vector& Vector::renew(int x){
	Vector temp(*this);
	Vector *aux;
	aux=new Vector(x);
	for(int i=0;i<temp.dim;i++){
		aux->lista[i]=temp.lista[i];
	}
	return *aux;
}
