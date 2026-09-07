# cours-genomique-sante
Cours de génomique et bio-informatique pour étudiants en filière Santé.

UE de Master 1 Connaissance des Acides Nucléiques et Bioinformatique (CANAB) - année 2026/2027.

# Cours 1 : Introduction à la génomique et visualisation de données NGS

**Niveau :** Master 1  dérogatoire
**Durée :** 3 heures  
**Lieu :** Faculté de Pharmacie
**Matériel**: Ordinateur personnel PC ou Mac avec navigateur à jour (Firefox, Safari, Chrome...)
**Préréquis :** Aucun


---

## Objectifs de la séance 1

1. Naviguer dans l'interface de l'**UCSC Genome Browser** et comprendre la notion d'assemblage (`hg19` vs `hg38`).
   
2. Manipuler les coordonnées génomiques et interroger les pistes d'annotations officielles (RefSeq, GENCODE).

3. Charger et visualiser des données d'alignement au format **BAM** via une *Custom Track*.

4. Analyser la couverture de séquençage, identifier des variants (SNV, indels) et interpréter des profils d'épissage (RNA-seq).

5. Exporter des figures.

---

## Programme de la séance 1

| Module | Contenu |
| :--- | :--- |
| **Module 1** | Introduction théorique : Rappels de cours, Formats NGS (FASTQ, SAM/BAM, BAI) et coordonnées génomiques |
| **Module 2** | Prise en main de l'UCSC Genome Browser : Recherche, zooms et gestion des tracks |
| **Module 3** | Atelier Pratique : Chargement de fichiers BAM externes & analyse de variants |
| **Module 4** | Sauvegarde de session, export d'images haute définition & bilan |

---

## Matériel & Liens utiles

* **Navigateur web :** Chrome, Firefox ou Safari à jour.
* **Serveur UCSC :** [https://genome.ucsc.edu/](https://genome.ucsc.edu/)
* **Piste de données BAM pour le TP :**  
  `https://github.com/votre-utilisateur/votre-depot/releases/download/v1.0-data/sample.bam`

---

## Déroulement du cours

### Module 1 : Du Séquençage à la Visualisation
*Rappels de cours.*

* **FASTQ** : Fichier brut de séquençage (séquences + scores de qualité PHRED).
* **SAM / BAM** : Fichier d'alignement des reads sur le génome de référence (SAM = texte, BAM = binaire compressé).
* **Indexation (.bai)** : Fichier d'index indispensable permettant d'accéder instantanément à n'importe quelle région du génome sans charger l'intégralité du fichier BAM.

---

### Module 2 : Prise en main de l'UCSC Genome Browser

1. Rendez-vous sur [UCSC Genome Browser](https://genome.ucsc.edu/cgi-bin/hgGateway).
2. Sélectionnez l'organisme **Human** et l'assemblage **Dec. 2013 (GRCh38/hg38)**.
3. Dans la barre de recherche, tapez le nom du gène `BRCA1` et validez.

#### Exercice 1 : Navigation basique
- *Q1.1 : Sur quel chromosome se situe le gène BRCA1 et quelles sont ses coordonnées exactes ?*
- *Q1.2 : Zoomez sur le premier exon du gène. Observez la séquence en acides aminés affichée. Quel est le premier codon ?*
- *Q1.3 : Combien de transcrits observez-vous ? Quel est le transcrit majoritaire ?*
- *Q1.4 : Dans quel sens est orienté le gène ?*
- *Q1.5 : Combien d'exons ce gène contient-il ?*

---

### Module 3 : Chargement et analyse d'un fichier BAM

Nous allons afficher des données de séquençage réelles hébergées à distance sans télécharger le fichier sur vos ordinateurs.

#### Étape A : Ajouter une piste personnalisée (*Custom Track*)
1. Dans le menu supérieur de l'UCSC, allez dans **My Data** > **Custom Tracks**.
2. Dans le champ de texte **Paste URLs or data**, collez la ligne suivante :

maud doit changer :
track type=bam name="TP_RNAseq_Echantillon1" description="Alignement RNA-seq Master" bigDataUrl=[https://github.com/votre-utilisateur/votre-depot/releases/download/v1.0-data/sample.bam](https://github.com/votre-utilisateur/votre-depot/releases/download/v1.0-data/sample.bam) visibility=full

3. Cliquer sur **Submit** puis **Go**

#### Étape B : Inspection des alignements
Naviguez vers la région d'intérêt définie par l'enseignant : chr17:43,044,295-43,125,483 (maud à changer).
Réglez l'affichage de votre track sur full ou squish selon la densité de reads.

#### Exercice 2 : Interprétation bioinformatique
- *Q2.1 : Quelle est la profondeur moyenne de couverture sur l'exon d'intérêt ?*
- *Q2.2 : Observez-vous des mésappariements (mismatches) fréquents par rapport au génome de référence ? Indiquent-ils un SNP hétérozygote ou homozygote ?*
- *Q2.3 : Comment se matérialisent les jonctions d'épissage sur l'affichage des reads ?*

---

### Module 4 : Exportation & Sauvegarde

*Exporter une figure vectorielle :*
- Allez dans le menu View > PDF/PS.
- Cliquez sur Download Current Browser Graphic in PDF.

*Sauvegarder sa session :*
- Allez dans My Data > My Sessions.
- Créez un compte gratuit pour enregistrer l'état exact de votre navigateur et générer un lien de partage.
