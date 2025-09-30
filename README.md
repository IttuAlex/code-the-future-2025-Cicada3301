# Braccio AI – Robot care vede și sortează culori

Acest proiect a fost realizat la **Code the Futures Hackathon @ Siemens (2025)**.  
Scopul: să învățăm un braț robotic să recunoască obiecte colorate și să le mute în locul potrivit, combinând viziunea computerizată cu controlul robotic.

---

## Ce face proiectul?

1. Camera (Picamera2 pe Raspberry Pi) filmează obiectele de pe masă.  
2. OpenCV detectează culorile (roșu, albastru, verde, galben, portocaliu, mov).  
3. Python trimite prin serial către Arduino ce culoare a fost găsită.  
4. Arduino controlează Braccio: brațul apucă obiectul și îl lasă la locul corespunzător.  

Rezultatul este un sistem simplu de tip Pick & Place cu viziune și mișcare automată.

---

## Demo
[Demo](https://www.youtube.com/watch?v=S1vbpbrqfbk)

### Poze
- ![Poză 1](<img width="543" height="723" alt="image" src="https://github.com/user-attachments/assets/8e117d26-3e5e-44b8-92d6-57c772ca3b3a" />)  
- ![Poză 2](<img width="578" height="743" alt="image" src="https://github.com/user-attachments/assets/4f2020c6-2a13-4674-bc30-23a6ddbf249e" />)  
- ![Poză 3](<img width="847" height="763" alt="image" src="https://github.com/user-attachments/assets/44a0e1a2-6c0a-47cc-b92a-2917104255f6" />)  
- ![Poză 4](<img width="1152" height="767" alt="image" src="https://github.com/user-attachments/assets/cf960ba6-8a7c-420e-8b88-706ec7aa48ad" />)
---

## Tehnologii folosite

- Arduino UNO cu librăria oficială Braccio  
- Braccio robotic arm (6 servomotoare)  
- Raspberry Pi cu Python  
- OpenCV pentru detecția de culori  
- Picamera2 pentru captură video  
- Comunicare serială între Raspberry Pi și Arduino  

---

## Cum rulezi proiectul

### 1. Arduino
- Deschide Arduino IDE  
- Încarcă codul din `arduino/braccio_pick_place.ino`  
- Instalează librăria oficială **Braccio**  

### 2. Raspberry Pi
```bash
sudo apt update
sudo apt install python3-opencv python3-picamera2 -y
python3 vision/color_detect.py
```

### 3. Conexiuni
- Arduino conectat la Raspberry Pi prin USB (`/dev/ttyACM0`)  
- Braccio conectat la Arduino conform manualului oficial  

---

## Culori detectate

| Culoare    | Destinație |
|------------|------------|
| Roșu       | Zona roșie |
| Albastru   | Zona albastră |
| Verde      | Zona verde |
| Galben     | Zona galbenă |
| Portocaliu | Zona portocalie |
| Mov        | Zona mov |

---
