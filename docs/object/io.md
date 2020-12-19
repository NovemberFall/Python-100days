## write data into a .txt file


```py
%%writefile myfile.txt
Hello this is a text file
this is the second line
this is the third line          #Writing myfile.txt
                    
 myfile = open('myfile.txt')                   
 pwd                   #'/Users/fish/Desktop/python3workspace/IOfile'

 myfile = open('myfile.txt')
myfile.read()                    #'Hello this is a text file\nthis is the second line\nthis is the third line\n'
myfile.read()    # ''    because every time read a .txt file, the cursor will be at the end.
myfile.seek(0)                    #0      return to the beginning
myfile.read()                    #'Hello this is a text file\nthis is the second line\nthis is the third line\n'
myfile.seek(0)                    #return to beginning

contents = myfile.read()
contents                     #'Hello this is a text file\nthis is the second line\nthis is the third line\n'
myfile.seek(0)
myfile.readlines()                    
#['Hello this is a text file\n',
# 'this is the second line\n',
# 'this is the third line\n']
pwd                    #'/Users/fish/Desktop/python3workspace/IOfile'
myfile.close()
```


---
## Reading, Writing, Appending Modes

- mode='r'  *is read only*
- mode='w'   *is write only(will overwrite files or create new!)*
- mode='a'   *is append only(will add on to files)*
- mode='r+'   *is reading and writing*
- mode='w+'   *is writing and reading(Overwrites existing files or creates a new file!)*


```py
with open('myfile.txt') as my_new_file:
    contents = my_new_file.read()
contents        #'Hello this is a text file\nthis is the second line\nthis is the third line\n'
with open('myfile.txt', mode='r') as myfile:
    contents = myfile.read()
contents        #'Hello this is a text file\nthis is the second line\nthis is the third line\n'

%%writefile my_new_file.txt
ONE ON FIRST
TWO ON SECOND
THREE ON THIRD      #Writing my_new_file.txt

with open('my_new_file.txt', mode='r') as f:
    print(f.read())
#ONE ON FIRST
#TWO ON SECOND
#THREE ON THIRD

# mode append
with open('my_new_file.txt', mode='a') as f:
    f.write('FOUR ON FOURTH')
with open('my_new_file.txt', mode='r') as f:
    print(f.read())
#ONE ON FIRST
#TWO ON SECOND
#THREE ON THIRD
#FOUR ON FOURTH

# mode w,   overwrite
with open('overwrite.txt', mode='w') as f:
    f.write('I create this new file and overwriting.')
with open('overwrite.txt', mode='r') as f:
    print(f.read())     # I create this new file and overwriting.
   
```



