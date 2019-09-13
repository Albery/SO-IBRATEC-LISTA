

};

typedef struct complex Complex;

Complex soma (Complex c1, Complex c2)
{
Complex c3;
c3.real = c1.real + c2.real;
c3.imag = c1.imag + c2.imag;
return c3;

}

Complex sub (Complex c1, Complex c2)
{
Complex c4;
c4.real = c1.real - c2.real;
c4.imag = c1.imag - c2.imag;
return c4;

}

Complex mult (Complex c1, Complex c2)
{ 
Complex c5;
c5.real = ( (c1.real*c2.imag)- (c1.imag*c2.imag));
c5.imag = ((c1.imag*c2.real) + (c1.real*c2.imag));

return c5;

}

Complex mult_Escalar (Complex c1, float escalar)
{ 
Complex c6;
c6.real =  escalar * c1.real;
c6.imag = escalar * c1.imag;
return c6;
}

float norma (Complex c1)
{ 
float c7;
c7=sqrt(c1.real*c1.real)+(c1.imag*c1.imag);
c1.z =c7;
return c7;
}

Complex conjugado (Complex c1)
{ 
Complex c8;
c1.real = c1.real;
c1.imag = -c1.imag;
return c8;
}

Complex divisao (Complex c1, Complex c2)
{ 
float denom = norma(c2)*norma(c2);
Complex c9;
c9.real=(c1.real*c2.real+c1.imag*c2.imag) / denom;
c9.imag=(c2.real*c1.imag+c1.real*c2.imag) / denom;
return c9;
}

double angulo (Complex c1)
{
double angle=tan(c1.imag/c1.real);
return angle;

}


int main() 

{

Complex c1 = {4,5};
Complex c2 = {3,4};
Complex c3 = soma(c1,c2);
Complex c4 = sub(c1,c2);
Complex c5 = mult(c1,c2);
Complex c6 = mult_Escalar(c1,c2);
Complex c7 =norma (c1, c2);
Complex c8 = conjugado (c1, c2);
Complex c9 = Divisao(c1, c2);

printf("C1: real=%f imag=%f\n", c1.real,c1.imag);
printf("C2: real=%f imag=%f\n", c2.real,c2.imag);
printf("C3 (Soma): real=%f imag=%f\n", c3.real,c3.imag); //resultado da soma
printf("C4 (Subtracao): real=%f imag=%f\n", c4.real,c4.imag); //resultado da subtração
printf("C5 (Multiplicacao): real=%f imag=%f\n", c5.real,c5.imag); //resultado da multiplicação
printf("C6 (Multiplicacao por escalar): real=%f imag=%f\n", c6.real, c6.imag); //resultado da multiplicação por escalar
printf("C7 (norma): real=%f imag=%f\n", c7.real,c7.imag); //resultado norma
printf("C8 (conjugado): real=%f imag=%f\n", c8.real,c8.imag); // resultado da Norma
printf("C9 Divisao): real=%f imag=%f\n", c9.real,c9.imag); //Divisao dos Num Complexos

return 0;
}
