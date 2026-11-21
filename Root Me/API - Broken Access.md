The problem starts with a Swagger page listing API endpoints with descriptions:\n
<img width="1491" height="690" alt="image" src="https://github.com/user-attachments/assets/44c121c9-1a87-472f-a104-79374daf613d" />\n
Let's create a user "tester":\n
<img width="1397" height="707" alt="image" src="https://github.com/user-attachments/assets/971959dd-3d48-414b-9f31-bc559c7b466c" />\n
Now let's login as a newly created user:\n
<img width="1422" height="720" alt="image" src="https://github.com/user-attachments/assets/81a1eff5-7f76-4fca-a668-d32b6aebd347" />\n
Now let's open BurpSuite and send to Reapeter the request going to "/api/user":\n
<img width="1097" height="282" alt="image" src="https://github.com/user-attachments/assets/c5ee1654-2682-4c06-8724-ac6c907884cb" />\n
Let's try to add numbers to the end of api endpoint:\n
<img width="1052" height="252" alt="image" src="https://github.com/user-attachments/assets/4d953421-6120-49b9-8a96-573dbe44d6c9" />\n
Adding 0 to the end showed an error telling that the user haven't been found:\n
<img width="1052" height="252" alt="image" src="https://github.com/user-attachments/assets/c5cd77fa-1143-4a5a-90e3-a0759b150259" />\n
Adding 1 revealed the flag
