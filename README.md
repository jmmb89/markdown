# Exercício de markdown

## História

Aproveito o exercício para compartilhar um pequeno programa em python que criei.  
Criei este programa porque minha namorada nunca consegue decidir entre o que comer, assistir e este programa resolve o problema.

uso:

|Input|Valor|
|-----|-----|
|n de escolhas|int de 1 a 10|
|escolhas|str/int/float|


´´´$ python2.7 coin.py´´´

__*Só roda com python 2.7*__

´´´python

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
´´´
 
*To do*

*[x] polimento do código.
*[] fazer o programa compativel com python3 e python2.7
*[] Criar a seed para o random a partir do tempo do UNIX, deixando "mais randomico".
