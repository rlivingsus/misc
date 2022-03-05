
### Python Notes  
----
-A return statement is used to end the execution of the function call and "returns" the result.  Note that a return statement can not be used outside the function.  Every function returns something although some may return "None".
-Functions that return values are sometimes called fruitful functions.  In many other languages, a function that doesn't return a value is called a procedure.
----
REF: https://pythonbasics.org/what-is-flask-python/
----
python exception example using file opening:

#!/usr/bin/python

try:
   fh = open("testfile", "r")
   fh.write("This is my test file for exception handling!!")
except IOError:
   print "Error: can\'t find file or read data"
else:
   print "Written content in the file successfully"
   
REF: https://www.tutorialspoint.com/python/python_exceptions.htm
----
One way to open files in Python:
with open("passwords.txt", "r") as f:
	for line in f:
		print (line)
	f.close() 
----
Python usually snake case (pothole case) rather than camelcase.  Also all CAPS for construct class or program class
---
Python zip method takes two arrays/lists and combines them into key/value pair (tuple?) but need some sort of collection by using tuple or maybe a dict
----
-Python great but slow; Rust is fast
-Lambda is AWS functions basically: JS, python, rust, etc..
----
-Create python web app where you can enter a date and it'll show last appt (for medical or car)
-Shiftleft.io https://www.shiftleft.io/login is the modern code security platform loved by developers
----
basic setup is below:
import argparse
parser = arg.parse.ArgumentParser()
parser.parse_args()

If you run the script normally nothing is displayed but when you follow with a '-h' or '-help' more details.  This options is the only one you get for 'free'

you can use the "add_argument()" method to specify which command-line options the program can accept so now the program will require this option which can be seen if you run the program without the option or if you use the help flag.  

parse_args() method returns data from options specified.

REF: https://docs.python.org/3/howto/argparse.html
----
#!/usr/bin/python3

import argparse

parser = argparse.ArgumentParser(description="Convert a Numeral to another Numeric type")
parser.add_argument("cvrtFrom", help="Convert Numeric type FROM...BIN, HEX, OCT, or DEC")
parser.add_argument("numericValue", type=str, help="Numeral")   //type=str not needed cuz by default? type=int need to state it
args = parser.parse_args()
args.cvrtFrom    //a variable option from above
args.numericValue  //a variable option from above

if __name__ == '__main__':     //common code to guard/protect users from invoking the script when didn't mean to such as when importing the script  REF: https://stackoverflow.com/questions/419163/what-does-if-name-main-do
	print ("executed when invoked directly")	

else:
	print ("executed when imported")

Determining if a number is a prime
-if number is divisible by (2-9) & has no mod (whole number answers only) then NOT prime
-else if number is divisible by 1 then prime (or all in this category is prime so no check needed)
----

-pwnedpass.py DONE used to check if your password has been compromised
-crypto.py DONE to convert a numeric type to another numeric type
