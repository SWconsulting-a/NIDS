<h1>Système de détection des intrusions</h1>
La détection des intrusions réseau et l'utilisation d'un modèle de classification binaire pour distinguer le trafic malveillant du trafic bénin offrent des avantages cruciaux pour les entreprises en matière de cybersécurité.<br>
L'objectif de ce projet est de développer un système de classification binaire capable de détecter le trafic réseau malveillant ou bénin en analysant les données importantes telles que le protocole de communication, la durée, les ports de source et destination,etc.
<h2>Etape 1: extraction, chargement et transformation des données au niveau de AWS </h2>
Tout d'abord, on commence par l'acquisition des données depuis plusieurs sources: logs, datasets:
<ul>
  <li>CICIDS 2018 </li>
  <li>KDD CUP 1999</li>
  <li>UNSW-NB 15</li>
</ul>
-D'autres datasets des données du traffic réseau + logs.<br>
Les données sont stockées au niveau du système de gestion des fichiers S3.<br>
Ensuite, on procède au traitement des données au niveau du datawarehouse Redshift afin de centraliser les données et créer le dataset final prêt à l'apprentissage.
<h2>Etape 2: Apprentissage des modèles de classification binaire et évaluation</h2>
Dans cette étape, on utilise le langage python pour entraîner les modèles de classification des attaques et ce en utilisant les packages: scikit-learn, pandas, numpy.
<h3>2-1-Préparation du jeu de données</h3>
<ul>
  <li>Suppression des doublons</li>
  <li>Traitement des valeurs nulles et NAN</li>
  <li>Choix des features importants pour l'apprentissage</li>
  <li>Etude des corrélations entre les variables</li>
  <li>Etude de la variance des variables</li>
  <li>Traitement des variables infinies</li>
  <li>Création des échantillons équilibrés des classes binaires: bénigne, maligne</li>
  <li>Encodage des variables catégorielles</li>
  <li>Normalisation du dataset</li>
</ul>
<h3>2-2-Entraînement des modèles de classification</h3>
Préparation des jeus de données: training, testing, validation.<br>
CHoix des hyperparamètres en utilisant la méthode du grid search.<br>
Entraînement des modèles de machine learning. <br>
<ul>
  <li>Random forest</li>
  <li>Logistic regression</li>
  <li>XGboost</li>
  <li>SVM</li>
  <li>Gradient boosting classifier</li>
  <li>MLP</li>
</ul>
<h3>2-3-Evaluation</h3>
<ul>
  <li>Accuracy (précision globale)</li>
  <li>Precision (taux de vrais positifs parmi les prédictions positives)</li>
  <li>Recall (taux de détection des positifs réels)</li>
  <li>F1-Score (harmonisation entre précision et rappel)</li>
  <li>Courbe ROC (évaluer le compromis entre le rappel et le taux de faux positifs)</li>
</ul>
<h3>2-4-Sauvegarde du meilleur modèle de prédiction et utilisation en temps réel</h3>
Pour ce projet, le modèle Xgboost offre la meilleure prédiction sur le jeu de données.
<h3>Références</h3>
<ul>
  <li>http://kdd.ics.uci.edu/databases/kddcup99/kddcup99.html</li>
  <li>https://www.unb.ca/cic/datasets/ids-2017.html</li>
  <li>https://research.unsw.edu.au/projects/unsw-nb15-dataset</li>

</ul>
