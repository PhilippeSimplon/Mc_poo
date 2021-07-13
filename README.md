# **MasterClass**
## :gift: The return of POO RPG :gift:
![](https://media.giphy.com/media/dtLZo270HKH15vA4jx/giphy.gif)

### **Structure**
Créez le dossier et les fichiers suivants:
- :file_folder: **src**
  - :file_folder: **characters**
    - :page_facing_up: character.js
    - :page_facing_up: player.js
    - :page_facing_up: ork.js
    - :page_facing_up: goblin.js
  - :page_facing_up: battle.js
  - :page_facing_up: main.js
  - :page_facing_up: index.html

### **Propriétés**
- health
- hitStrength
- level  
Les proprietes et methodes commune a player, ork et goblin vont dans character.js
### **Méthodes**
- Getter et Setter pour chaque propriete publique
- attack qui retourne hitStrength * level

### **character.js**
```javascript
export default class Character {
    level = 1;
    constructor(health, hitStrength) {
        this.health = health;
        this.hitstrength = hitStrength;
    }
    getHealth() {
        return this.health;
    }
    setHealth(damage) {
        this.health -= damage;
    }
    attack() {
        return this.hitStrength * this.level;
    }
}
```

### **player.js** (player a 25% de bonus en defense)
```javascript
export default class Player extends Character {
    super(health, hitStrength);
    setHealth(damage) {
        this.health -= damage * 0.75;
    }
}
```

### **index.html**
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>The return of POO RPG</title>
    
</head>
<body>
    <!-- !!! Pour utiliser les imports il faut ajouter type="module" !!! -->
    <script type="module" src="./main.js"></script>
</body>
</html>
```

### **A vous de jouer pour l'ork et le goblin**
- Ork a 25% d'attaque en plus.
- Goblin a un hitStrength fixe à 1 mais son level augmente de 1 a chaque attaque.

### **battle.js**
```javascript
export default class Battle {
    fight(a, b){
        // on check que les 2 combattants sonts presents
        if (!a || !b){
            console.log('il manque un ou plusieurs combattants');
            // on quitte la methode fight avec return
            return;
        }
        // et on commence la battle
        while (a.getHealth() > 0 && b.getHealth() > 0) {
            // Compléter cette partie
            // Les combattants s'attaquent chacun leur tour
            // Afficher dans la console
            // les dégâts de l'attaquant 
            // et la vie restante du défenseur
            // à chaque tour.
        }
        //Ensuite affichez le vainqueur dans la console
        // ainsi que ses points de vie restants
    }
}
```

### **main.js**
```javascript
import Player from '/characters/player.js';
let player = new Player(10, 10)
console.log(player, player.getHealth(), player.attack());
// Faire les import manquants
// Creer un ork, un goblin
// Faites combattre player contre ork, puis contre goblin
```

### **Pensez a créer une classe**, 
#### chaque fois que vous devez reproduire plein de fois un même objet (User, Book, Cd, Produits, ...)

# **THE END**
