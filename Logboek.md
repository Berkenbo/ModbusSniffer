# RS232 naar RS485

07/05/2025

Test schakeling om van rs232 een rs485 signaal te maken.

Voor de input wordt 0 naar 5 volt gebruikt zodat we het PL2303 USB UART Board kunnen gebruiken om met de computer met de software Putty een UART signaal te sturen

Input (rs232): 0V naar +5V

Output (rs485): +2.5V en -2.5V

## Schakeling:

Met LTspice is deze schakeling gemaakt
![image](https://github.com/user-attachments/assets/996f4bac-37c8-4de5-88f3-099f454fcc90)


De simulatie van LTspice:


Het output signaal van +-2.5V valt binnen specificatie van [Sentron-manuaali-englanti.pdf](https://github.com/user-attachments/files/20099430/Sentron-manuaali-englanti.pdf)





# Vergelijking onze RS232 naar RS485 schakeling met een Pico-2CH-RS485

08/05/2025



