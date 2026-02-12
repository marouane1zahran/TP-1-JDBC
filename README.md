<h1>-------------LAB 1-------------</h1>
<img width="752" height="273" alt="db atelier" src="https://github.com/user-attachments/assets/15eccfd0-8042-46af-a152-034a8fa4a166" />
<h2>------------------------------------------------------</h2>
<img width="542" height="310" alt="table devdata" src="https://github.com/user-attachments/assets/b0d26eb4-c60a-4edf-9c44-60444dc795f7" />
<h2>------------------------------------------------------</h2>
<img width="380" height="366" alt="output" src="https://github.com/user-attachments/assets/7c45b735-1b55-4d2b-8442-ba0f9e91fae0" />

<h1>-------------LAB 2-------------</h1>
<img width="994" height="477" alt="image" src="https://github.com/user-attachments/assets/f945caa6-1075-4286-a91d-65a03d051c56" />


## 📋 Contexte et Objectifs

L'objectif principal de cet atelier est de maîtriser les fondamentaux de la persistance des données en Java et l'organisation professionnelle du code.

### Objectifs Techniques
* **Architecture en couches :** Séparation stricte entre l'accès aux données (DAO), la logique métier (Service) et la présentation (App).
* **JDBC Avancé :** Utilisation de `PreparedStatement` pour la sécurité et `ResultSet` pour le mapping objet-relationnel.
* **Design Patterns :**
    * **Singleton :** Pour garantir une instance unique de connexion à la base de données (Thread-safe).
    * **DAO (Data Access Object) :** Pour isoler les requêtes SQL du reste de l'application.
* **Relations SQL :** Gestion de la relation **1:N** (Un Employé possède N Machines) avec intégrité référentielle (`ON DELETE CASCADE`).

---

## 🏗️ Architecture du Projet

Le projet respecte une séparation stricte des responsabilités.

### Structure des Packages

| Package | Rôle | Description Technique |
| :--- | :--- | :--- |
| `entities` | **Modèle** | Classes POJO (*Employe, Machine*). Représente les tables de la BDD sous forme d'objets Java. |
| `dao` | **Accès Données** | Contient l'interface générique `IDao` et les implémentations SQL. Gère le JDBC pur et le mapping. |
| `service` | **Logique Métier** | Orchestre les opérations. Intermédiaire entre l'application et les données (ne contient pas de SQL). |
| `util` | **Infrastructure** | Contient la classe `Connexion` (Singleton) pour gérer l'accès à MySQL. |
| `app` | **Présentation** | Contient les méthodes `main()`. Sert à exécuter et tester l'application. |

### Arborescence des Fichiers
```text
src/
├── app/
│   ├── TestEmploye.java
│   └── TestMachine.java
├── dao/
│   ├── IDao.java          <-- Interface Générique
│   ├── EmployeDao.java
│   └── MachineDao.java
├── entities/
│   ├── Employe.java
│   └── Machine.java
├── service/
│   ├── EmployeService.java
│   └── MachineService.java
└── util/
    └── Connexion.java     <-- Singleton JDBC





