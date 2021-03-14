---
layout: post
title:  "Interaktive Unfallkarte"
date:   2021-02-04 20:00:00 -0000
img: unfall.png
categories: projects
tags: projects, python, unfälle
---

# Interaktive Unfallkarte

Eine Interaktive Website, die einem Unfälle in Deutschland auf einer Karte präsentiert. 
Die Unfälle sind nach selbst einstellbaren Kategorien wie Grad der Verletzungen, beteiligte Farhzeugarten, etc.
sortierbar. Außerdem wird die zeitliche Verteilung der jeweiligen Auswahl und die räumliche Sammlung in externen
Grafiken dargestellt.

### Funktionsweise

Die Unfalldaten stammen aus dem OpenData Projekt des Deutschen Statistischen Bundesamtes. Diese Daten werden zuerst nach Ort
gefiltert und in die Website eingespeist. Diese Website ist komplett in *Python* geschrieben. Das Python-Skript verarbeitet
die Daten und stellt sie mithilfe der *Plotly-Library* dar. Die Nutzereingaben werden in der *Flask-App* verarbeitet und 
anschließend dargestellt. Das Gante basiert stark auf *pandas* DataFrames, die in allen möglichen Arten verändert oder angepasst werden.

[**App Starten**](https://unfallkarte.herokuapp.com)

[**Github Repo**](https://github.com/skriptum/unfaelle)
