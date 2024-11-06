**Motivation :** L'étude consiste à visualiser le nombre de Simflouz générés par jour sur l'année 2023. L'idée m'est venue de plateformes de cours et de coaching (par exemple LeetCode ou Valorant Tracker) qui offrent des heatmaps mensuelles montrant l'aciduité de l'élève. 
Des couleurs intenses peuvent montrer que l'élève a par exemple réalisé beaucoup d'exercices dans la journée, ou bien a soumis tant de codes, joué tant de parties, etc. Une couleur grisée indique une absence d'activité sur le jour.
Voici par exemple mon nombre de soumissions de code lors de mon premier mois sur LeetCode; un vert très foncé indique une unique soumission, et un vert très pâle correspond à des valeurs dépassant les 50, voire 150.

![calendar_leetcode](https://github.com/user-attachments/assets/3da0a3dc-37c2-4bd4-a65b-232fa4dfeecd)

**Idée :** En se basant sur cette expérience, le but de ce projet est donc de réaliser un outil visuel offrant ce concept, mois par mois, sur l'année 2023, en se basant sur l'évolution annuelle du nombre de Simflouz.

**Données utilisées :** Le jeu de données utilisé provient de la société dans laquelle j'ai effectué mon stage de fin d'études, réalisé dans le cadre de mon master Méthodes Stochastiques et Informatiques pour la Décision. Les variables et les valeurs ont donc été modifiées pour des raisons de confidentialité. C'est pourquoi la variable dont on étudiera l'évolution est le Simflouz.

**Approche :** Qui dit heatmap dit matrice. Il est important de distinguer les mois donc créer une matrice par mois semble naturel. Pour ce qui est de la forme de la matrice, on veut également trier les dates par semaine, ce qui complique déjà les choses. Une des dimensions sera de longueur 7 pour chaque jour de la semaine, et l'autre sera variable selon le nombre de semaines (merci à la norme ISO 8601 pour sa rigueur).

Reste à remplir la matrice avec les valeurs voulues selon deux contraintes :
- Contrainte d'espace : Chaque jour doit être placé dans la bonne case de la matrice selon le numéro du jour de la semaine et la semaine associée, dans le bon mois.
- Contrainte de couleur : Il est important d'associer la bonne couleur à chaque case de la matrice, qui peut contenir plus de valeurs qu'il n'y a de jours dans le mois de par sa nature rectangulaire. Il conviendra d'affecter la valeur -1 aux jours étrangers.
