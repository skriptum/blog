---
layout: post
title:  "Bundestwitter"
date:   2021-02-16 20:00:00 -0000
categories: projects
img: "twitter.png"
tags: projects, python, twitter
---

# Bundestagstwitter

Eine Web-App, die alle Twitter-Accounts von Bundestagsmitgliedern erfahrbar macht und vergleicht. Mit einer Wahlkreiskarte,
die alle bekannten twitternden MdBs abbildet. 

### Funktionsweise

Täglich werden über die **Twitter-API** die letzten 50 Tweets aller Accounts abgefragt und gesammelt. Daraufhin wird der Text jedes
Tweets mit einem Machine-Learning Algorithmus anhand der Laune bewertet, was jedoch aufgrund der kurzen Länge nicht immer funktioniert.
Anschließend werden alle Daten der Tweets aggregiert und in eine Datenbank eingespeist.

Auf diese Datenbank greift dann **Web-App**, die komplett in *Python* geschrieben ist, zu und stellt sie schön dar und 
baut Rangfolgen anhand der Daten. Zusätzlich wird noch eine Karte mit Deutschands Wahlkreisen und den Vertretern mit Twitter generiert.
Die Visualisierungen basieren vor allem auf der *Plotly-Library* und die App baut auf *Dash* und *Flask* auf.



[App Starten](https://abgeordnete.herokuapp.com)

[Github Repo](https://github.com/skriptum/bundestag)