# HTTP - IP restriction bypass

The problem starts with the login page and on the top of the page there is a text telling that my IP doesn't belong to LAN:
<img width="306" height="122" alt="image" src="https://github.com/user-attachments/assets/d0848451-a359-4b0f-af68-d2be1083773d" />

Turned on BurpSuit and intercepted the request to the login page:
<img width="826" height="215" alt="image" src="https://github.com/user-attachments/assets/56fefdec-c16c-4037-86b3-86e3d86d5c02" />

Added "X-Forwarded-For" header with random address from 192.168.0.X network and got the flag:

<img width="307" height="57" alt="Screenshot 2026-08-23 210416" src="https://github.com/user-attachments/assets/16a17c2e-3c91-4c5a-bab0-a3592bfa8540" />
