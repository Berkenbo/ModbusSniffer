# RS232 naar RS485

**07/05/2025**

Test schakeling om van rs232 een rs485 signaal te maken.

Voor de input wordt 0 naar 5 volt gebruikt zodat we het PL2303 USB UART Board kunnen gebruiken om met de computer met de software Putty een UART signaal te sturen

Input (rs232): 0V naar +5V

Output (rs485): +2.5V en -2.5V

Het output signaal van +-2.5V valt binnen specificatie van [Sentron-manuaali-englanti.pdf](https://github.com/user-attachments/files/20099430/Sentron-manuaali-englanti.pdf). Het uiteindelijke doel is om met een laptop of ESP32 signalen naar de Siemens SENTRON PAC3100 gestuurd worden.


## Schakeling:

Met LTspice is deze schakeling gemaakt
![image](https://github.com/user-attachments/assets/996f4bac-37c8-4de5-88f3-099f454fcc90 =250x250)


De simulatie van LTspice:



## Opstelling:

![WhatsApp Image 2025-05-08 at 11 05 56_0217f210](https://github.com/user-attachments/assets/813e3f6f-0efc-4f96-ab2c-16a1fa56aeb1)
Zoals zichtbaar hebben we om de juiste weerstand te krijgen veel kleine weerstanden gebruikt om de juiste grotere weerstanden te maken. In de toekomst kan hier een potmeter voor gebruikt worden. 

![TEK0001](https://github.com/user-attachments/assets/14d0f0a6-c88a-45c6-8914-9b8ca9835402)



# Vergelijking onze RS232 naar RS485 schakeling met een Pico-2CH-RS485

**08/05/2025**



