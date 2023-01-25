# Traitement_Tp2

#Objectifs
Comprendre comment manipuler un signal audio avec Matlab, en effectuant
certaines opérations classiques sur un fichier audio d’une phrase enregistrée via
un smartphone.
 Comprendre la notion des sons purs à travers la synthèse et l’analyse spectrale
d’une gamme de musique.

#Jeux de mots

### 1)Sauvegardez ce fichier sur votre répertoire de travail, puis charger-le dans MATLAB à l’aide de la commande « audioread ».
```
    [y,Fs]=audioread('phrase.wav');
    dt = 1/Fs;
    t = 0:dt:(length(y)-1)*dt;
```
### 2)- Tracez le signal enregistré en fonction du temps, puis écoutez-le en utilisant la commande « sound ».

<img width="484" alt="Screenshot 2023-01-25 at 00 38 24" src="https://user-images.githubusercontent.com/87026851/214445692-4cf51a69-ff4b-4c2b-9261-e110871d4ff0.png">

```
  [x,fs]=audioread("phrase.au");

    Taille = length(x);
    ts=1/fs;
    T = (0:Taille-1)*ts;

    sound(x,fs);
    plot(T,x);
    legend("Representation du signal du son");
    xlabel("t");
    ylabel("x(t)");
```
### 3)
```
  sound(y,2*Fs); %Donald Duck
  sound(y,Fs/2); %Terminator
```
### 4)Tracez le signal en fonction des indices du vecteur x, puis essayez de repérer les indices de début et de fin de la phrase « Rien ne sert de ».

<img width="477" alt="Screenshot 2023-01-25 at 00 53 17" src="https://user-images.githubusercontent.com/87026851/214447186-5fbb8588-d4c9-4dc1-8932-219262f7a7a9.png">


```
        seg1 = x(36500:130106);
        plot(seg1);
        title('Rien ne sert de');
```

### 5)Créez ce vecteur, puis écoutez le mot segmenté.

```
    sound(seg1,fs);
```

### 6)Segmentez cette fois-ci toute la phrase en créant les variables suivantes : riennesertde, courir, ilfaut, partirapoint.

```
%first segmentation 'rien ne sert de'
        seg1 = x(36500:130106);
        plot(seg1);
        title('Rien ne sert de');

       %second segmentation 'courir'
        seg2=x(130107:190006);
        
       %third segmentation 'il faut'
        seg3=x(190007:250006);
        
       %4th segmentation 'partir a point'
        seg4=x(250007:394240);
```

### 7)la phrase synthétisée « Rien ne sert de partir à point, il faut courir ».

```
  sound([seg1;seg4;seg3;seg2],fs);
```
