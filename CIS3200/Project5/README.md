I used PySpark on Jupyter Notebook. My logic was to create a list of the middle friends and a list of the actual friends, and to subtract actual friends from middle friends. I initially used a double for loop to create the middle friends list but it took way longer than expected (it worked for smallfriends.txt but not Friends.txt) so I decided to use a data dictionary. Something else I noticed was converting the rdd's to lists made it easier to do the subtraction step. My last step before converting to csv was add back the removed users (they had no friend recommendations) due to them having no friends or being in a closed friend loop. 


Friend Recommendations:

18	['35', '39', '6159', '2435', '15', '2419', '19010', '19079', '2440', '2417']
87	['2823', '15637', '16111', '2242', '8672', '37280', '23266', '37188', '9847', '1148']
480	
512	['490', '33773', '2569', '41393', '38278', '21162', '1083', '17150', '2565', '520']
3971	['1131', '22495', '2455', '44650', '11609', '24088', '11326', '22138', '29891', '40051']
38283	['22662', '19599', '4133', '32535', '12665', '6887', '34278', '1088', '30400', '33379']
49772	

UMID 0908
908	['26921', '41839', '26910', '41835', '41860', '7497', '7425', '7457', '26905', '41853']

The friend recommendations for each user looks to be ranked correctly (by mutual friends), and my code worked to add back users with no recommendations (user 480 and 49772). I wanted to sort the list in ascending user order for readability, but that would have taken too much time in PySpark. I ended up doing that in the generated csv file instead. 
