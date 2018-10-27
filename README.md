# prima tema
import numpy as np
f = open('numbers.txt','r')

def process_line(line):
    return list(map(float,   str.split(line[:-1], ','))    )
nums = [process_line(line) for line in f]       

print("lista de lista", nums)
print("")

n=[]
for i in range(0,len(nums)):
    n+=nums[i]
print("concatenarea listelor:" ,list(n))

print("")
print("suma tuturor numerelor: " , sum(list(n)))

print("")
e=sum(np.array(list(n))>30.1)
print("Sunt",e, "numere mai mari decat 30.1")

print("")
v = np.arange(1, 100, 1)    
z=list(n)
print("z=",z)
print("v=",v)

print("")
n=[]
for i in range(0,len(nums)):
    print("suma pe linia", i,": ", sum(nums[i])) 

print("")
b=0
for i in range(0,len(v)):
    for j in range(0,len(z)):
        if z[j]<v[i]:
            print(z[j],"<",v[i])
            b=b+1
        else:
            print("invalid")
print("sunt",b,"numere din lista mea, mai mici decat numerele din intervalul [1,99]")
           
f.close()
