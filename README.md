# linux-bash
linux-bash

### ECHO, COMMAND / myscript1.sh:
```bash
#!/bin/bash

echo "Hello this is Message from Script"
echo "Let's show files in this folder...."

ls
xterm &
ls -l

echo "Done"
```


### Variables, COMMAND / myscript1.sh:
```bash
#!/bin/bash

mycomp="Lenovo"
myOS=`uname -a`

echo "This script name is $0"
echo "Privet $1"
echo "Hello $2"

num1=50
num2=45
summa=$((num1+num2))

echo "$num1 + $num2 = $summa"

myhost=`hostname`
mygtw="8.8.8.8"

ping -c 4 $myhost
ping -c 4 $mygtw

echo -n  "This is done..."
echo "Really done"
```


### IF-ELIF-ELSE-IF / myscript3.sh:
```bash
#!/bin/bash
if [ "$name" == "Vasya" ]; then    
    echo "Privet $name"
elif [ "$name" == "John" ]; then    
    echo "Hello $name"
else echo "Hi $name"
fi

read -p "Enter something:" x

echo "Starting  CASE selection..."
case $x in
    1) echo "This is one";;
    [2-9]) echo "Two-Nine";;
    "Petya") echo "Privet $x";;
    *) echo "Parameter Unknown, sorry!"
esac
```


### FOR / myscript4.sh:
```bash
#!/bin/bash
COUNTER=0
while [ $COUNTER -lt 10 ]; do
  echo "Current counter is $COUNTER"
  COUNTER=$(($COUNTER+1))
  #LET COUNTER+=1
done

for myfile in `ls *.txt`; do
        cat $myfile
done

for x in {1..10}; do
        echo "X = $x"
done

for (( i=1; i<=10; i++ )); do
        echo "Number I = $i"
done
```


### Function / myscript5.sh:
```bash
#!/bin/bash

summa = 0

myFunction()
{
        echo "This is text from Function"
        echo "Num1= $1"
        echo "Num2= $2"
        summa=$(($1+$2))
}

myFunction 50 10
echo "Summa = $summa"
```

### check file + check port
```bash
#!/bin/bash

my_index=`test -f /var/www/html/index.html`

my_port=`bash -c "</dev/tcp/localhost/80"`

if [ $my_index -eq 0 ] && [ $port -eq 0 ]; then
        exit 0
else
        exit 1
fi
```
