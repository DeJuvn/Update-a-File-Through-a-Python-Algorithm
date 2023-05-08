# Update-a-File-Through-a-Python-Algorithm

<b>Project description</b>

To control access to restricted content at my organization, we maintain an allow list of IP addresses in a file named "allow_list.txt". Additionally, we maintain a remove list that identifies IP addresses that should no longer have access to the content. To automate the process of updating the "allow_list.txt" file and removing these IP addresses, I created an algorithm.

<b>Open the file that contains the allow list</b>

To begin the algorithm, I stored the name of the "allow_list.txt" file in a string variable called "import_file".

![image](https://user-images.githubusercontent.com/131769679/236790023-8f803e47-fabd-4cd7-8abd-ae3e6686eefd.png)

Then, I used a with statement to open the file.

![image](https://user-images.githubusercontent.com/131769679/236790124-b2dca5f6-8956-4027-b50a-398cd98f4e29.png)

To access the IP addresses stored in the allow list file, my algorithm utilizes the with statement in conjunction with the open() function in read mode. The purpose of opening the file is to read it, and the with keyword is used to manage the resources by automatically closing the file after exiting the with statement. The open() function takes two parameters: the first identifies the file to import, and the second specifies the intended operation on the file. In this case, "r" indicates that the file should be read. The as keyword is also used to assign the output of the open() function to a variable named file, which is used to manipulate the contents of the file within the with statement.

<b>Read the file contents</b>

 I used the .read() method to convert it into the string.
 
 ![image](https://user-images.githubusercontent.com/131769679/236790521-4a7a54a0-5e39-432a-9d1a-3a1dad7bf1c9.png)

<b>Convert the string into a list</b>

To enable the removal of individual IP addresses from the allow list, I converted the ip_addresses string into a list using the .split() method.

![image](https://user-images.githubusercontent.com/131769679/236790775-132eee9a-dbb6-4b21-a50a-1c56c3679109.png)

<b>Iterate through the remove list</b>

I included a for loop in my algorithm to iterate through the IP addresses in the remove_list, which is a list of IP addresses that should no longer have access to the restricted content.

![image](https://user-images.githubusercontent.com/131769679/236790929-2d9a1413-d0e5-4113-bf00-218e8424419d.png)

<b>Remove IP addresses that are on the remove list</b>

To ensure that the IP addresses listed in the remove_list are removed from the ip_addresses list, I used the .remove() method within a for loop. Since all the elements of remove_list are also present in ip_addresses, and there are no duplicates in ip_addresses, I could use .remove() to eliminate any matching IP address. Here's how I implemented it:

![image](https://user-images.githubusercontent.com/131769679/236791218-001d186d-9190-4537-8bf5-c6e39081aa13.png)

<b>Update the file with the revised list of IP addresses</b>

To update the allow list file with the revised list of IP addresses, I first converted the list of IP addresses back into a string using the .join() method. This method takes the elements of a list and concatenates them into a string with a specified delimiter. In this case, I used the newline character (\n) as the delimiter, which creates a new line for each IP address in the file.

![image](https://user-images.githubusercontent.com/131769679/236791567-673ed289-930a-4faf-8dc4-01503bcc8fd4.png)

I used another with statement and the .write() method to update the file:

![image](https://user-images.githubusercontent.com/131769679/236791636-4f4b3f23-41b1-403d-b033-277be2a23e94.png)

<b>Summary</b>

I developed an algorithm to update the "allow_list.txt" file by removing the IP addresses present in the remove_list. The algorithm involved opening the file, reading its contents as a string, and then converting it into a list of IP addresses stored in the variable ip_addresses. I then used a for loop to iterate through each IP address in the remove_list and removed it from the ip_addresses list using the .remove() method. Finally, I used the .join() method to convert the ip_addresses list back into a string, allowing me to overwrite the contents of the "allow_list.txt" file with the updated list of IP addresses.
