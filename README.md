#! /usr/bin/python3.6 
# Wordcount program - this basically concatenates words from a file into strings
# and outputs the length of each string
# it also requires commandline arguments = sys.argv to execute
import sys
import os
def Worddict(Textfile):
  abspath = os.path.abspath('.')
  Textfile = os.path.join(abspath, Textfile)
  Text = open(Textfile, 'r')
  Modfile = Text.read()
  for lines in Modfile.splitlines():
  	for words in lines.split(' '):
  		print(words.lower() + ' --- ' + str(len(words)))

  


  

# def Usuage():
# 	if len(sys.argv) ==	 1 :
# 		return Worddict(sys.argv[1])
# 	# elif sys.argv[2] == "--count":
# 	# 	return Worddict(sys.argv[1])
# 	# else:
# 	# 	print('''Usuage: python wordcount.py (--count) filename''')


# defining a main function as a entry point from which other functions are called
def main():
	Worddict(sys.argv[1])
	


if __name__ == '__main__':
	main()

