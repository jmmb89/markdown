# Exercício de markdown

## História

Aproveito o exercício para compartilhar um pequeno programa em python que criei.  
Criei este programa porque minha namorada nunca consegue decidir entre o que comer ou assistir e este programa resolve o problema de forma rápida.

uso:

>*Note: Usar com python 2.7*

|Input|Valor|
|-----|-----|
|n de escolhas|int de 2 a 10|
|escolhas|str/int/float|


```$ python2.7 coin.py```


```python

from sys import exit
import random

options = []
coinLoop = True

while coinLoop:
	print("\n##################################")
	print("\nI will select an option for you!")
	
	choiceNum = raw_input("\nHow many options?\n\noptions = ")

	if choiceNum.isdigit():
		if int(choiceNum) > 1 and int(choiceNum) < 11:
			for i in range(0, int(choiceNum)):
				pos = i + 1
				newInput = raw_input("\nOption %r: " % pos)
				options.append(newInput)

			maxValue = len(options)

			coin = random.randint(1, maxValue)
			selectedObject = options[coin - 1]
			print("\nOption selected: %r\n" % selectedObject)	
			question = raw_input("Play again? [y, N]\n> ")
			if question == "y":
				del options[:]#python3 uses alist.clear()
			else:
				print("\n##################################\n")
				coinLoop = False
		else:
			print("\nPlease, insert a number from 2 to 10 \n")
	else:
		print("\nNot a valid number!\nTry Again!\n")
exit()
```
 
*To do:*

- Deixar compatível com python3
- Criar a seed a partir do UNIX Epoch time, deixando "mais randomico".
