# METADATOS-CON-PYTHON

# Daniel Acevedo Mejia TAREA 2 
# extraccion de metadatos de archivos pdf, xlsx, docxs
#principalmente se establece la instalacion de librerias 
#instalacion(pip install pypdf2, pip install openpyxl, pip install, 
 #pip install python-docx

import PyPDF2
from openpyxl import load_workbook
from docx import Document
#en esta parte decidi hacer el tipo de separacion de los documentos para que el usuario pueda elegir de que tipo, tambien #es necesario que esten en la misma carpeta del ejecutable de python
tipo= int
tipo=1
print("tipo de archivo a analizar\n")
print("1.........................PDF\n")
print("2.........................DOCX\n")
print("3.........................XLSX\n")
tipo=int(input("ingrese el numero: \n"))	



if tipo == 1:
#se puede observar que se pide el nombre del archivo para poder leerlo , despues analizarlo con meta, es interesante como funciona y se puede establecer distitos tipos de datos que se quiera establcer
		print("ingrese el nombre del archivo con la terminacion\n")
		nombre = input()
		pdf = open(nombre,"rb")

		reader = PyPDF2.PdfReader(pdf)

		meta = reader.metadata

		print(meta)
elif tipo == 2:
	print("ingrese el nombre del archivo con la terminacion\n")
	nombre = input()
	doc= Document(nombre)
	metadata= doc.core_properties
	print(metadata)
	
	

		
elif tipo == 3:
	#como tal tambien se pide el nombre del documento a analizar
	print("ingrese el nombre del archivo con la terminacion\n")
	nombre = input()
	#se abre y se lee el archivo adjuntado el nombre al input #posteriormente se imprime
	wb= 	load_workbook(nombre)
	reader = wb
	meta= reader.properties
	print(meta)
