# SARDINAS
import random
import math
class Sardinas (object):
    def __init__(self):
        self.x=random.randint(0,999)
        self.y=random.randint(0,999)
        self.z=random.randint(0,999)
    def sensor1(self):
        self.a= 0
        self.b= 0
        self.c= 0
        self.ausuario=0
        self.busuario= 0
        while True:
            self.ausuario= int(input("Inserte valor para sensor 'a': "))
            if self.ausuario< 0 or self.ausuario > 1000:
                print ("Error. El número no es válido.")
                continue
            else:
                self.a=self.ausuario
                break
        while True:
            self.busuario=int(input("Inserte valor para sensor 'b': "))
            if self.busuario<0 or self.busuario>1000:
                print ("Error. El número no es válido.")
                continue
            else:
                self.b=self.busuario
                break       
    def sensor2(self):
        self.p= 0
        self.q= 0
        self.r= 0
        self.pusuario=0
        self.qusuario=0
        while True:
            self.pusuario=int(input("Inserte valor para sensor 'p': "))
            if self.pusuario<0 or self.pusuario>1000:
                print ("Error. El número no es válido.")
                continue
            else:
                self.p=self.pusuario
                break
        while True:
            self.qusuario=int(input("Inserte valor para sensor 'q': "))
            if self.qusuario<0 or self.qusuario>1000:
                print ("Error. El número no es válido.")
                continue
            else:
                self.q=self.qusuario
                break       
    def sensor3(self):
        self.w= 0
        self.e= 0
        self.t= 0
        self.wusuario=0
        self.eusuario=0
        while True:
            self.wusuario=int(input("Inserte valor para sensor 'w': "))
            if self.wusuario<0 or self.wusuario>1000:
                print ("Error. El número no es válido.")
                continue
            else:
                self.w=self.wusuario
                break
        while True:
            self.eusuario=int(input("Inserte valor para sensor 'e': "))
            if self.eusuario<0 or self.eusuario>1000:
                print ("Error. El número no es válido.")
                continue
            else:
                self.e=self.eusuario
                break  
    def impacto(self, x, y, z):
        if x==self.x and y==self.y and z==self.z:
            return True
        else:
            return False

    def desplazamiento(self):
        self.x=random.randint(-1,1)
        self.y= random.randint(-1,1)
        self.z=random.randint(-1,1)
        #if random.random() > 0.1:
            #if random.random()>0.5:
                #self.x += 1
                #self.y +=1
                #self.z +=1
            #else:
                #self.x -=1
                #self.y -=1
                #self.z -=1

    def distanciaSensor1(self):
        return int(math.sqrt(((self.x-self.a)**2)+((self.y-self.b)**2)+((self.z-self.c)**2)))
    def distanciaSensor2(self):
        return int(math.sqrt(((self.x-self.p)**2)+((self.y-self.q)**2)+((self.z-self.r)**2)))
    def distanciaSensor3(self):
        return int(math.sqrt(((self.x-self.w)**2)+((self.y-self.e)**2)+((self.z-self.t)**2)))


print("Bienvenido al juego de las sardinas asesinas") 
input("Presione enter para comenzar ")                             
banco=Sardinas()
x=0 
y=0 
z=0 
       
while True:
    banco.sensor1()
    banco.sensor2()
    banco.sensor3()
    print("Distancia sensor 1: ", banco.distanciaSensor1())
    print("Distancia sensor 2: ",banco.distanciaSensor2())
    print("Distancia sensor 3: ",banco.distanciaSensor3())
    banco.desplazamiento()
    
    x= int(input("Ingrese coordenadas en X: "))
    y= int(input("Ingrese coordenadas en Y: "))
    z= int(input("Ingrese coordenadas en Z: "))
    if banco.impacto(x,y,z):
           print("¡¡¡¡¡¡¡¡FELICIDADES, LOGRASTE DARLE A LA SARDINA!!!!!!")
           break
    else:
           print('''GAME OVER.
Intenta otra vez''')
           continue

