The start of the problem begins with a form that accepts an IP address and makes a ping request to the specified server:\n
<img width="450" height="175" alt="image" src="https://github.com/user-attachments/assets/3fdf3de9-7b70-4b58-b3ab-e4a6d84c5789" />\n
It seems like the command goes directly to the shell to the *ping* command with the user input as the argument of the command. I we put "127.0.0.1; ls -lah", then we will execute *ping -c 3 127.0.0.1; ls -lah*:\n
<img width="582" height="311" alt="image" src="https://github.com/user-attachments/assets/e6c7c24f-0095-49d4-833e-4ea5b091debf" />\n
Reading ".passwd" file will reveal the flag
