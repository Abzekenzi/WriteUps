The challenge welcomes with a a page with three buttons:\
<img width="385" height="140" alt="image" src="https://github.com/user-attachments/assets/0cbe04e6-6ac1-4850-ac21-b794d4e2753d" />\
The task hints to changes embedded links to a different one.\
Let's turn on Burp Suit and try to intercept the request for Facebook:\
<img width="1172" height="592" alt="image" src="https://github.com/user-attachments/assets/c6266c17-25c8-470f-ad5e-860a495afb2a" />\
Let's change the URL of redirection to something different:\
<img width="937" height="222" alt="image" src="https://github.com/user-attachments/assets/e4147b45-67cf-4087-aa8f-67f88a6cec92" />\
In the response I got "Invalid hash" message:\
<img width="360" height="111" alt="image" src="https://github.com/user-attachments/assets/1c842ce4-b34b-4d39-99ae-a601e63108f7" />\
There is a second parameter named "h" that seems to contain a MD5 hash. It could be a validation of redirection URL. I tried to make the MD5 hash of "https://facebook.com" and got exact hash that I've got in the request:\
<img width="1010" height="507" alt="image" src="https://github.com/user-attachments/assets/794cc237-8ac2-4730-88ce-acaae0d7ec02" />\
Let's make a new hash for "https://test.com":\
<img width="1010" height="507" alt="image" src="https://github.com/user-attachments/assets/7dfaa707-213c-4d9c-9e86-f61a35e1b10b" />\
Entering these data into corresponding fields revealed the flag 
