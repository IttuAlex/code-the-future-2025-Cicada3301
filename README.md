# Braccio AI – Robot care vede si sorteaza culori

Acest proiect a fost realizat la **Code the Futures Hackathon @ Siemens (2025)**.  
Scopul: sa invatam un braț robotic sa recunoasca obiecte colorate si sa le mute in locul potrivit, combinand vederea artificiala cu bratul robotic.

---

## Ce face proiectul?

1. Camera (Picamera2 pe Raspberry Pi) filmeaza obiectele de pe masa.  
2. OpenCV detecteaza culorile (rosu, albastru, verde, galben, portocaliu, mov).  
3. Python trimite prin serial catre Arduino ce culoare a fost gasita.  
4. Arduino controlează Braccio: bratul apuca obiectul si il lasa la locul prestabilit.  

Rezultatul este un sistem simplu de tip Pick & Place cu viziune si miacare automata.

---

## Demo
[Video](https://www.youtube.com/watch?v=S1vbpbrqfbk)

### Poze
- ![Poza 1](https://github.com/user-attachments/assets/8e117d26-3e5e-44b8-92d6-57c772ca3b3a)  
- ![Poza 2](https://github.com/user-attachments/assets/4f2020c6-2a13-4674-bc30-23a6ddbf249e)  
- ![Poza 3](https://github.com/user-attachments/assets/44a0e1a2-6c0a-47cc-b92a-2917104255f6)  
- ![Poza 4](https://github.com/user-attachments/assets/cf960ba6-8a7c-420e-8b88-706ec7aa48ad)
---

## Tehnologii folosite

- Arduino UNO cu libraria oficiala Braccio  
- Braccio robotic arm (6 servomotoare)  
- Raspberry Pi cu Python  
- OpenCV pentru detectia de culori  
- Picamera2 pentru captura video  
- Comunicare seriala intre Raspberry Pi si Arduino  

---

## Cum rulezi proiectul

### 1. Arduino
- Deschide Arduino IDE  
- Incarca codul din `robot/braccio.ino`  
- Instaleaza libraria oficiala **Braccio**  

### 2. Raspberry Pi
```bash
sudo apt update
sudo apt install python3-opencv python3-picamera2 -y
python3 ai/color_detect.py
```

### 3. Conexiuni
- Arduino conectat la Raspberry Pi prin USB (`/dev/ttyACM0`)  
- Braccio conectat la Arduino conform manualului oficial  

---

## Culori detectate

| Culoare    | Destinatie |
|------------|------------|
| Rosu       | Zona rosie |
| Albastru   | Zona albastra |
| Verde      | Zona verde |
| Galben     | Zona galbena |
| Portocaliu | Zona portocalie |
| Mov        | Zona mov |

---
