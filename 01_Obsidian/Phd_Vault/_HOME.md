---
type: dashboard
tags: [dashboard, home]
date-maj: <% tp.date.now('YYYY-MM-DD') %>
---

# 🏠 Second Brain — Chérif BARRY

> **Doctorant FRACNET-CITY · Université Paris-Saclay · 2026–2029**
> *Analyse multifractale conjointe de la forme urbaine et des réseaux de chaleur*

---

## 🎯 Focus de la semaine

> *(Mets à jour chaque lundi matin — 1 objectif principal, 1 phrase)*

---

## ⚡ Accès rapides

| 📅 [[01_Daily_Notes/\|Daily d'aujourd'hui]]          | 🔬 [[02_PhD_FRACNET_CITY/MOC_PhD\|MOC Thèse]]     | 📚 [[02_PhD_FRACNET_CITY/Literature/MOC_Literature\|MOC Biblio]] |
| ---------------------------------------------------- | ------------------------------------------------- | ---------------------------------------------------------------- |
| 🐙 [GitHub FRACNET](https://github.com/cherif-barry) | 📖 [Zotero Web](https://www.zotero.org)           | 📝 [[02_PhD_FRACNET_CITY/Writing/\|Manuscrit]]                   |
| 🗓️ [[02_PhD_FRACNET_CITY/Meetings/\|Réunions]]      | 🤝 [[02_PhD_FRACNET_CITY/Partners/\|Partenaires]] | 💡 [[06_Engagement/\|Engagements]]                               |

---

## ✅ Tâches actives — Thèse

```dataview
TASK
FROM "02_PhD_FRACNET_CITY/Tasks"
WHERE !completed
SORT priority DESC, due ASC
LIMIT 8
```

---

## 📚 Derniers articles lus

```dataview
TABLE without id
  file.link AS "Article",
  auteurs AS "Auteurs",
  annee AS "Année",
  pertinence AS "⭐"
FROM "02_PhD_FRACNET_CITY/Literature/Papers"
WHERE statut = "termine"
SORT file.mtime DESC
LIMIT 6
```

---

## 📝 Notes créées récemment

```dataview
LIST
FROM "02_PhD_FRACNET_CITY"
SORT file.ctime DESC
LIMIT 8
```

---

## 📅 Daily notes récentes

```dataview
LIST
FROM "01_Daily_Notes"
SORT file.name DESC
LIMIT 7
```

---

## 🗓️ Prochaines réunions

```dataview
TABLE without id
  file.link AS "Réunion",
  date-reunion AS "Date",
  participants AS "Participants"
FROM "02_PhD_FRACNET_CITY/Meetings"
WHERE date-reunion >= date(today)
SORT date-reunion ASC
LIMIT 5
```

---

## 📊 Avancement thèse · Année 1

| Axe | Statut | Avancement |
|-----|--------|-----------|
| État de l'art | 🟡 En cours | ████████░░ 65 % |
| Code MFDFA Python | 🟡 En cours | ████░░░░░░ 30 % |
| Collecte données | 🟡 En cours | █████░░░░░ 50 % |
| Rédaction manuscrit | 🔴 Démarrage | █░░░░░░░░░ 10 % |
| CSI Année 1 | ⚪ À venir | Octobre 2027 |

> *(Mets à jour ce tableau manuellement chaque mois)*

---

## 🌍 Partenaires FRACNET-CITY

```dataview
TABLE without id
  file.link AS "Partenaire",
  contact AS "Contact",
  statut-relation AS "Statut",
  prochaine-action AS "Prochaine action"
FROM "02_PhD_FRACNET_CITY/Partners"
SORT file.name ASC
```

---

## 📖 En cours de lecture

```dataview
TABLE without id
  file.link AS "Article / Livre",
  auteurs AS "Auteurs",
  annee AS "Année"
FROM "02_PhD_FRACNET_CITY/Literature"
WHERE statut = "en-cours"
SORT file.mtime DESC
```

---

## 💡 Idées à explorer

```dataview
LIST
FROM "05_Projects/Ideas" OR "06_Engagement"
WHERE contains(tags, "idee-these")
SORT file.mtime DESC
LIMIT 5
```

---

## 🏃 Sport & bien-être · Ce mois

```dataview
TABLE without id
  date AS "Date",
  activite AS "Activité",
  duree AS "Durée",
  notes AS "Notes"
FROM "07_Personal/Health"
WHERE date >= date(today) - dur(30 days)
SORT date DESC
LIMIT 6
```

---

## 🌱 Engagements actifs

```dataview
LIST
FROM "06_Engagement"
WHERE statut = "actif"
SORT file.name ASC
```

---

## 📈 Stats du vault

```dataview
TABLE without id
  length(rows) AS "Notes"
FROM "02_PhD_FRACNET_CITY/Literature/Papers"
GROUP BY "Total articles lus"
```

---

*Dashboard mis à jour automatiquement par Dataview · [[_Templates/Daily_Note_Template|Ouvrir template daily]] · [[_Templates/Paper_Template|Nouveau article]]*