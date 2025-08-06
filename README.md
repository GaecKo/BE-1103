# BE-1103: Ressources

> Accessible jusqu'au 31/08/2025

## Séance 1

> Powerpoint: [BE1-1103](https://uclouvain-my.sharepoint.com/:p:/g/personal/arthur_deneyer_student_uclouvain_be/ESafe8ZlXQJHtZtkMkx3y-EBY6sRSQkUoAn52nzFMDox3A?e=drF6OJ)

## Séance 2

> Powerpoint: [BE2-1103](https://uclouvain-my.sharepoint.com/:p:/g/personal/arthur_deneyer_student_uclouvain_be/EYn9acZKGLNLoAkbzZ5QrMQBPl0C3VwXCYz1PQmgc6j0Og?e=PquMPY)

## Séance 3

> Powerpoint: [BE3-1103](https://uclouvain-my.sharepoint.com/:p:/g/personal/arthur_deneyer_student_uclouvain_be/ET3-366scJpLmz02s9Rw95oBsmLDgwO1G6TAPK4TKDTfkw?e=uVd20w)

## Séance 4

> Powerpoint: [BE4-1103](https://uclouvain-my.sharepoint.com/:p:/g/personal/arthur_deneyer_student_uclouvain_be/EUB1m03RYlBDlJ0-HOXNZOUB461BH-uh3VFnNpveExTSrg?e=JbyEnj)



# Exo sur les classes abstraires, interfaces, polymorphisme, héritage et délégation 

# Objectif
En partant du code suivant: 
```java
public class exercices {
    public static void main(String[] args) {
        Voiture mercedesAMG = new Mercedes("AMG", 240);
        Voiture audiA4 = new Audi("A4", 210);
        Voiture touktouk = new ToukTouk("vMax", 300);

        Voiture[] mesVoitures = new Voiture[] {mercedesAMG, audiA4, touktouk};

        Arrays.sort(mesVoitures);
        System.out.println("Tri par rapport au critère par défaut (la vitesses)");
        System.out.println(Arrays.deepToString(mesVoitures));
        System.out.println("\n\nTri par rapport au critère personnalisé (nbr roues)");
        Arrays.sort(mesVoitures, new RouesVoitureComparator());
        System.out.println(Arrays.deepToString(mesVoitures));

    }
}
```
Ton but est d'avoir la sortie suivante:
```
Tri par rapport au critère par défaut (la vitesses)
[Mercedes AMG, Audi A4, ToukTouk vMax]

Tri par rapport au critère personnalisé (nbr roues)
[ToukTouk vMax, Mercedes AMG, Audi A4]
```

Pour cela, tu dois:
1. Création de la classe abstraite `Voiture`:
    * Elle implémente la classe `Comparable`
    * Elle a trois attributs (`marque`, `maxSpeed` et `nombreDeRoues`)
    * Elle a deux constructeurs, un reliant ces 2 attributs et mettant une valeur par défaut à `nbreDeRoues` et l'autre reliant directement les 3 attributs)
    * Elle définit une méthode abstraite getInfo()
2. 3 classes `Mercedes`, `Audi` et `ToukTouk` qui étende `Voiture`
   * Il faut y ajouter un attribut `model`, a assigné dans un constructeur
   * Il faut aussi forcément appeler `super()` quelque part 
   * Il faut ajouter toutes les méthodes nécessaires de l'héritage
   * Il faut Override la méthode `toString` qui indique la marque et le modèle
   * La comparaison se fait par rapport à la vitesse de la voiture
3. 1 classe `RouesVoitureComparator` qui implémente `Comparator`
   * La comparaison se fait par rapport au nombre de roues
