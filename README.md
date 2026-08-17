# Figures

Une figure, c'est un rôle **et** un agencement : une figure de style, une
figure imposée. Le mot dit les deux, et c'est exactement ce dont il s'agit ici.

Une figure retient comment le modèle doit se comporter — ce qu'il sait, ce
qu'il doit faire, ce qu'il ne doit pas faire, avec quel modèle et quels outils
— et garde ses propres conversations. Vous l'écrivez une fois ; vous la
retrouvez telle quelle à chaque ouverture.

C'est l'équivalent des GPT de ChatGPT, mais chez vous, sur vos poids, et sous
forme d'extension : rien de tout cela n'est natif à Locaryn, et retirer
l'extension retire l'écran.

---

## Ce qu'une figure contient

| Champ | Rôle |
| --- | --- |
| **Nom** | ce que vous lisez dans la liste |
| **Consignes** | ce que le modèle reçoit avant toute conversation. C'est le cœur |
| **Modèle** | lequel fait tourner cette figure. Vide : celui de l'application |
| **Outils** | ce qu'elle a le droit d'appeler. Vide : ce que l'application propose |
| **Ouverture** | une première phrase, envoyée d'office à l'ouverture |
| **Mémoire** | si la figure lit la mémoire de l'utilisateur, ou travaille à part |

Rien n'est obligatoire sauf le nom et les consignes. Une figure de trois
lignes est une figure valable.

---

## Trois exemples fournis

Ils sont dans [`figures/`](figures/) et s'installent avec l'extension. Chacun
est un fichier Markdown : un en-tête pour les réglages, le corps pour les
consignes. C'est le format des [Agent
Skills](https://agentskills.io) — une figure est lisible par tout outil qui
lit ce standard, et les nôtres se copient d'un dépôt à l'autre.

- **Relecteur** — relit un diff et signale ce qui casse, pas ce qui dépasse.
- **Traducteur** — traduit sans commenter, sans ajouter, sans expliquer.
- **Secrétaire** — met au propre des notes prises à la volée.

---

## Écrire la sienne

```markdown
---
name: relecteur
description: Relit un diff et signale les défauts de correction, pas de style.
metadata:
  model: ""
  opening: "Colle le diff."
  memory: false
---

Tu relis du code. Tu ne commentes que ce qui peut casser : un cas non traité,
une erreur avalée, une hypothèse fausse sur une entrée.

Tu ne parles ni de style, ni de nommage, ni de préférences — un autre outil
s'en charge et tu ferais du bruit.

Quand tu ne vois rien, tu le dis en une phrase. Tu n'inventes pas un défaut
pour avoir quelque chose à dire.
```

Les champs `name` et `description` sont ceux du standard Agent Skills ; tout
ce qui est propre aux figures vit sous `metadata`, que le standard laisse
libre. Une figure reste donc lisible ailleurs, et n'y perd que ses réglages.

---

## Installation

Depuis l'application : **Réglages → Extensions**, puis `Locaryn/plugin-figures`.

Un bouton **Figures** apparaît dans le menu principal, sur l'ordinateur comme
sur le téléphone. Il ouvre la liste, la configuration de chacune, et leurs
conversations.

Retirer l'extension retire le bouton et l'écran. Les figures écrites restent
sur le serveur : les réinstaller les retrouve.
