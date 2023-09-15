import os  #Library for file and directory paths
import xml.etree.ElementTree as ET  #XML Parsing Library in Python

directory = "C:\\path\\to\\directory"  #Path containing XML files (or r"C:\path\to\directory") - For Windows, example for Linux: '/path/folder'

xml_files = []  #List to store XML file names

for file_name in os.listdir(directory):  #Iterate through all files in the directory
    if file_name.endswith('.xml'):  #Check if the file is XML
        xml_files.append(os.path.join(directory, file_name))  #Add the identified file name to the list

combined_tree = ET.ElementTree(ET.Element('root'))  #Create an empty XML tree/structure for storing elements

for file in xml_files:  #Iterate over identified and listed XML files
    tree = ET.parse(file)  #Parse XML tree for each file
    root = tree.getroot()  #Get the root with specific elements from the file

    for element in root:  #Iterate over elements in the file to combine into the tree
        combined_tree.getroot().append(element)  #Combine elements

combined_tree.write('combined_file.xml', encoding='utf-8', xml_declaration=True)  #Path to save the combined XML file
#Syntax:
#combined_tree.write('\\full\\path\\to\\save\\file\\combined_file.xml' - (\ for Windows) - (/ for Linux)
#If the path is not specified and only the file name, it will be saved in the same folder where the code is being executed
