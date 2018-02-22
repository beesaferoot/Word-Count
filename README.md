#!/usr/bin/python 

# wordcount.py - counts words from any given file 
# program still on construction 
import sys, os, re

absWorkdir = os.path.abspath('.')

def Count(path):
    path = os.path.abspath(path)
    filename = open(path, 'r')
    reElem = re.compile(r'[a-zA-Z#!.0-9]*')
    file_sort = reElem.findall(''.join(filename))
    count = 0
    for value in file_sort:
        if value != '\n' and value != '':
            print(value + ' -- ' + str(len(value)))
            count = count + len(value)
    print('total num of char in\n %s is %s'%(os.path.basename(sys.argv[2]),str(count)))
    filename.close()



def total(path):
    path = os.path.abspath(path)
    filename = open(path, 'r')
    reElem = re.compile(r'[a-zA-Z]*')
    file_sort = reElem.findall(''.join(filename))
    while True:
        file_sort.remove('')
        if '' not in file_sort:
            break

    print('total num  of words in\n %s is %s '%(os.path.basename(sys.argv[2]), len(file_sort)))
    filename.close()   


def main():
    if len(sys.argv) == 3:
        if sys.argv[1].lower() == '--count' or sys.argv[1].lower() == '-c':
            try:
                Count(sys.argv[2])
            except Exception as inv:
                print('Exception occured : %s'%(str(inv)))
        elif sys.argv[1].lower() == '--total' or sys.argv[1].lower() == '-t':
            total(sys.argv[2])
        else:
            print('Usuage: python wordcount.py --count [filepath]')
    if len(sys.argv) < 3:
        print('Usuage: python wordcount.py --count [filepath]')
 
    
main()

