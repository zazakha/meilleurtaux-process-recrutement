# 🏢 Meilleurtaux - Processus de Recrutement Data Engineer

Bienvenue dans le repository du test technique pour le poste de **Data Engineer** chez [Meilleurtaux](https://www.meilleurtaux.com/) ! Ce test a été conçu pour évaluer vos compétences en :

- 💻 **Codage**
- 📊 **Analyse**
- 📝 **Présentation**

---

## 📂 Structure des données 

Dans le dossier `data_sources/`, vous trouverez trois fichiers CSV :

- **banques_test.csv** : contient la liste des banques qui peuvent proposer des offres de prêt immobilier aux clients.
- **opportunity_test.csv** : contient les opportunités, c’est-à-dire les demandes de prêt immobilier faites par des personnes. Il contient des informations sur le profil des demandeurs de pret immobilier, les caractéristiques du projet immobilier...
- **propositions_test.csv** : contient les propositions de prêt faites pour chaque opportunité. Une opportunité peut avoir plusieurs propositions de prêt de la part de différentes banques, avec des conditions telles que le taux d’intérêt, la durée et le taux d’assurance.

> **Remarque :** Les noms des champs sont généralement explicites. Certains champs spécifiques sont expliqués ci-dessous :

### Champs dans `opportunity_test.csv`
- **MontPretPricip__c** : Montant du prêt principal.
- **SituActu__c** : Situation actuelle de l’emprunteur.
- **TotRev__c** : Total des revenus de l’emprunteur.
- **BanquePrincipaleEmp__c** : La banque du demandeur de l'emprunteur

### Champs dans `propositions_test.csv`
- **Id** : Identifiant unique de la proposition.
- **CreatedDate** : Date de création de la proposition.
- **Opportunity__c** : Identifiant de l’opportunité associée.
- **Partenaire__c** : Identifiant de la banque ayant fait la proposition.
- **TXHA__c** : Taux hors assurance.
- **DureePret_Mois__c** : Durée du prêt en mois.
- **TauxAss__c** : Taux de l’assurance emprunteur.
- **Etape_Source__c** : Étape de traitement de la proposition.

---

## 📝 Instructions pour répondre au test

Pour commencer l’exercice, suivez ces étapes :

1. **Clonez** ce repo sur votre machine locale.
2. **Une fois dans le bon dossier, créez un environnement Python virtuel** avec Python 3.8 ou supérieur.

   ```bash
   python -m venv venv

3. **Activer ensuite l'env virtuel2**

	```bash 
    source venv/bin/activate  #pour macOS
    venv\Scripts\activate     #pour Windows

N'hésitez pas à utiliser l’IDE de votre choix pour interagir avec Jupyter Notebook.


## Partie 1 : Analyse

### Question 1
**Question ouverte :** En vous concentrant sur les personnes ayant soumis des opportunités (c’est-à-dire les demandeurs de prêt immobilier), déterminez le profil type des personnes.

Vous pouvez vous intéresser aux champs suivants : 
- `Age_emprunteur__c`
- `BanquePrincipaleEmp__c`
- `Deja_souscrit_credit_immo__c`
- `TechMail_CategorieProfessionnelleEmpru__c`
- `TechMail_ContratDeTravailEmprunteur__c`

### Question 2 : 
En utilisant SQL:
Pour chaque opportunité, sélectionnez la proposition de prêt la plus avantageuse ( c’est-à-dire celle avec le Taux d’intérêt le plus faible) parmi toutes les propositions disponibles.
Affi### Question 3
En utilisant SQL :  
Pour chaque opportunité, sélectionnez la proposition de prêt la plus avantageuse (c’est-à-dire celle avec le Taux d’intérêt le plus faible) parmi toutes les propositions disponibles.  
Affichez les colonnes suivantes dans votre résultat final :
- **ID de l’opportunité**
- **ID de la proposition**
- **Taux d’intérêt**
- **Durée du prêt**
- **Nom de la banque**

## Partie 2 : Création d’une API pour récupérer les informations d’une opportunité
**Exercice** : Création d’une API pour récupérer les informations d’une opportunité.  
En utilisant Python et le framework de votre choix, créez un endpoint permettant de consulter les informations principales d’une opportunité en utilisant son ID.

### Objectif
Développez une API RESTful en Python qui permet d’interroger les informations principales d’une opportunité en utilisant son ID.  
L’API doit recevoir un paramètre `id` correspondant à l’identifiant unique de l’opportunité.

Voici un exemple de réponse attendue. N’hésitez pas à ajouter toute information pertinente :

```json
{
  "response_id": "0cc12fda-deca-4f24-918b-f0884d2bb910",
  "id": "0065q00000AlAK0AAN",
  "age_emprunteur": 33,
  "banque_principale": "CIC",
  "deja_souscrit_credit_immo": true,
  "categorie_professionnelle": "Salarié du privé",
  "contrat_travail": "CDI période d'essai terminée",
  "revenu_total": 7731.67,
  "montant_pret_principal": 235055,
  "stage_name": "6-Perdue"
}
```
	

# Partie 3 QUESTION OPTIONNEL EN BONUS :Conteneurisation de l’API 
Déployer l’application API dans un container en local.

# Instructions pour soumettre votre test
Si votre code nécessite des packages supplémentaires, incluez un fichier `requirements.txt` les listant.

La réponse au test technique attendu doit être un repo GitHub privé partagé avec les membres de l’équipe data engineering de Meilleurtaux. 

🔹 **Tips** : [Comment partager un repo privé ?](https://docs.github.com/fr/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-access-to-your-personal-repositories/inviting-collaborators-to-a-personal-repository)

Une fois terminé, nous examinerons rapidement votre test et organiserons une réunion de présentation pour vous permettre de présenter votre solution, d’expliquer votre approche, votre méthodologie et les défis rencontrés au cours de cet exercice.

📧 **Contactez-nous si vous avez des questions** :
Si vous avez des questions ou besoin de précisions sur les instructions de l’exercice, veuillez contacter :
- zkhalmdani@meilleurtaux.com
- glouasse@meilleurtaux.com

