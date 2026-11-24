# TP : Application Web JEE de gestion des produits avec Spring Boot et Spring Security

## 1. Introduction

Ce projet consiste à développer une application Web JEE de gestion des produits en utilisant Spring Boot, Spring MVC, Spring Data JPA, Hibernate, Thymeleaf et Spring Security.

L'application permet de gérer les produits à travers une interface Web, tout en assurant la sécurité et la validation des données.

**Vidéo de démonstration :**  
https://www.youtube.com/watch?v=FHy7raIldgg

## 2. Objectifs du TP

Les principaux objectifs de ce travail pratique sont :

- Développer une application Web avec Spring Boot.
- Utiliser Spring Data JPA et Hibernate pour gérer la persistance des données.
- Créer une interface utilisateur avec Thymeleaf et Bootstrap.
- Implémenter les opérations CRUD.
- Valider les formulaires de saisie.
- Sécuriser l'application avec Spring Security.
- Ajouter des fonctionnalités de recherche et de mise à jour des produits.

## 3. Technologies et outils utilisés

| Technologie | Rôle |
|---|---|
| Java | Langage de programmation |
| IntelliJ IDEA | Environnement de développement |
| Spring Boot | Création de l'application |
| Spring Web / Spring MVC | Gestion des requêtes Web |
| Spring Data JPA | Accès aux données |
| Hibernate | Mapping objet-relationnel |
| H2 Database | Base de données en mémoire |
| MySQL | Base de données relationnelle |
| Thymeleaf | Génération des pages HTML |
| Bootstrap | Mise en forme de l'interface |
| Lombok | Réduction du code répétitif |
| Spring Security | Sécurisation de l'application |
| Spring Validation | Validation des formulaires |
| Maven | Gestion des dépendances |

## 4. Création du projet Spring Boot

Le projet est créé avec Spring Initializr en utilisant Maven et Java.

### Dépendances ajoutées

- Spring Web
- Spring Data JPA
- H2 Database
- MySQL Driver
- Thymeleaf
- Lombok
- Spring Security
- Spring Validation

## 5. Création de l'entité JPA Product

L'entité `Product` représente les produits enregistrés dans la base de données.

Elle contient les attributs suivants :

| Attribut | Type | Description |
|---|---|---|
| id | Long | Identifiant unique |
| name | String | Nom du produit |
| price | double | Prix du produit |
| quantity | int | Quantité disponible |

Exemple de code :

```java
@Entity
@Data
@NoArgsConstructor
@AllArgsConstructor
public class Product {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private String name;
    private double price;
    private int quantity;
}
```

## 6. Création de ProductRepository

L'interface `ProductRepository` permet d'effectuer les opérations d'accès aux données grâce à Spring Data JPA.

```java
public interface ProductRepository extends JpaRepository<Product, Long> {
}
```

Elle permet notamment de :

- Ajouter un produit.
- Consulter tous les produits.
- Rechercher un produit par son identifiant.
- Modifier un produit.
- Supprimer un produit.

## 7. Test de la couche DAO

La couche DAO est testée afin de vérifier le bon fonctionnement de l'accès à la base de données.

Les opérations testées sont :

- L'enregistrement d'un produit.
- La récupération de tous les produits.
- La recherche d'un produit par son identifiant.
- La modification d'un produit.
- La suppression d'un produit.

## 8. Configuration de Spring Security

Dans un premier temps, la protection par défaut de Spring Security est désactivée pour faciliter les tests et le développement de l'application.

Cette étape permet d'accéder aux différentes fonctionnalités sans authentification.

Ensuite, Spring Security est configuré pour protéger les pages et contrôler l'accès aux fonctionnalités de l'application.

## 9. Développement de l'application Web avec Spring MVC et Thymeleaf

### 9.1 Création du contrôleur Spring MVC

Le contrôleur permet de gérer les requêtes HTTP et de communiquer avec la couche Repository.

Il assure la liaison entre les données et les vues Thymeleaf.

### 9.2 Affichage de la liste des produits

Une page Web permet d'afficher tous les produits enregistrés dans la base de données.

Les informations affichées sont :

- Identifiant du produit.
- Nom du produit.
- Prix.
- Quantité.

### 9.3 Suppression d'un produit

L'application permet de supprimer un produit à partir de son identifiant.

### 9.4 Création des templates avec Thymeleaf et Bootstrap

Les pages HTML sont développées avec Thymeleaf.

Un template commun basé sur Thymeleaf Layout et Bootstrap permet de conserver une interface cohérente et responsive.

### 9.5 Ajout d'un produit avec validation

Un formulaire permet de saisir les informations d'un nouveau produit.

La validation permet de vérifier les données saisies avant leur enregistrement dans la base de données.

## 10. Sécurisation de l'application avec Spring Security

Spring Security permet de protéger l'application et de contrôler les accès.

Les fonctionnalités de sécurité peuvent inclure :

- Authentification des utilisateurs.
- Gestion des rôles.
- Protection des pages.
- Autorisation d'accès selon les privilèges.

L'objectif est de garantir que seules les personnes autorisées peuvent accéder aux fonctionnalités protégées.

## 11. Fonctionnalités supplémentaires

Pour améliorer l'application, plusieurs fonctionnalités peuvent être ajoutées.

### 11.1 Recherche des produits

Permet de rechercher un produit selon son nom ou un autre critère.

### 11.2 Édition et mise à jour

Permet de modifier les informations d'un produit déjà enregistré.

### 11.3 Autres fonctionnalités

L'application peut également être améliorée avec :

- Confirmation avant suppression.
- Messages de succès et d'erreur.
- Pagination des résultats.
- Interface utilisateur responsive.

## 12. Tests de l'application

Les tests permettent de vérifier le bon fonctionnement des différentes fonctionnalités :

- Affichage de la liste des produits.
- Ajout d'un nouveau produit.
- Suppression d'un produit.
- Recherche d'un produit.
- Modification des informations.
- Validation des formulaires.
- Authentification et contrôle des accès.

Des captures d'écran peuvent être ajoutées pour présenter les résultats obtenus.

## 13. Conclusion

Ce travail pratique m'a permis de développer une application Web JEE de gestion des produits en utilisant plusieurs technologies de l'écosystème Spring.

J'ai pu découvrir le fonctionnement de Spring MVC, Spring Data JPA, Hibernate et Thymeleaf, ainsi que les mécanismes de validation et de sécurité avec Spring Security.

Ce projet m'a permis de renforcer mes compétences dans le développement d'applications Web Java et la gestion sécurisée des données.

## 14. Ressource vidéo

Vidéo utilisée pour réaliser le TP :  
https://www.youtube.com/watch?v=FHy7raIldgg
