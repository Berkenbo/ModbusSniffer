# Modbus berichten uitlezen met oscilloscoop

**Datum: 23/04/2025**

Met behulp van software van “modbus tools” hebben we een ASCII modbus RS232 signaal verstuurd met computer1(Client) en ontvangen met computer2 (Server). Hiervoor worden twee PL2303 usb uart borden gebruikt die de twee computer verbinden.

Dit beeld is genomen met de Siglent SDS 1202X-E oscilloscoop:

<img src="https://github.com/user-attachments/assets/45bd326b-ee0c-4ab3-b436-e611f03695e5" alt="Alt Text" width="800" height="500">

Hier is automatic polling zichtbaar, we gebruiken de software modbus poll, het idee is dat er elke seconde registers van de slave geupdate worden. Daarom gaat er eerst een signaal vanaf te TX lijn en een antwoord vie de RX lijn.


# RS232 naar RS485

**Datum: 07/05/2025**

Test schakeling om van rs232 een rs485 signaal te maken.

Voor de input wordt 0 naar 5 volt gebruikt zodat we het PL2303 USB UART Board kunnen gebruiken om met de computer met de software Putty een UART signaal te sturen

Input (rs232): 0V naar +5V

Output (rs485): +2.5V en -2.5V

Het output signaal van +-2.5V valt binnen specificatie van [Sentron-manuaali-englanti.pdf](https://github.com/user-attachments/files/20099430/Sentron-manuaali-englanti.pdf). Het uiteindelijke doel is om met een laptop of ESP32 signalen naar de Siemens SENTRON PAC3100 te sturen.


## Schakeling:

Met LTspice is deze schakeling gemaakt
<img src="https://github.com/user-attachments/assets/996f4bac-37c8-4de5-88f3-099f454fcc90" alt="Alt Text" width="800" height="500">

De simulatie van LTspice:


## Berekening:

<img src="https://github.com/user-attachments/assets/0ed6c466-29dc-419e-89e1-f9875c57d170" alt="Alt Text" width="333" height="500">

## Opstelling:

<img src="https://github.com/user-attachments/assets/813e3f6f-0efc-4f96-ab2c-16a1fa56aeb1" alt="Alt Text" width="600" height="400">

Zoals zichtbaar hebben we om de juiste weerstand te krijgen veel kleine weerstanden gebruikt om de juiste grotere weerstanden te maken. In de toekomst kan hier een potmeter voor gebruikt worden. 

## Resultaat:


<img src="https://github.com/user-attachments/assets/14d0f0a6-c88a-45c6-8914-9b8ca9835402" width="600" height="400">
De schakeling werkt effectief, de signalen zijn niet 100 procent exact gespiegeld, maar deze zijn voldoende helder 


# Vergelijking onze RS232 naar RS485 schakeling met een Pico-2CH-RS485

**Datum: 08/05/2025**

Na gesprek met Bart Snijder, heeft hij aangeraad om onze bevindingen met onze rs232 naar rs485 schakeling nog naast een "of the shelf" adapter te houden.
Hiervoor hebben we de Pico-2CH-RS485 gebruikt. Dit bord is bedoeld voor de Raspberry Pi Pico maar bij hebben hiervoor het PL2303 USB UART Board gebruikt samen met de opensource software [PuTTY](https://www.putty.org/). 

## Opstelling:

<img src="https://github.com/user-attachments/assets/62d8e469-b8b4-4405-9028-a335943edaca" width="600" height="400">

## Resultaat: 

<img src="https://github.com/user-attachments/assets/7d224bac-cbcc-464c-9805-14f940556831" width="600" height="400">

Het lijkt er op dat de output van de Pico-2CH-RS485 een minder strak signaal geeft dan deze van onze [schakeling](https://github.com/Berkenbo/ModbusSniffer/blob/main/Logboek.md#rs232-naar-rs485) 

# Met de ESP32 een RS485 modbus signaal naar de Siemens Sentron PAC3100 multimeter sturen.

**Datum 09/05/2025**





