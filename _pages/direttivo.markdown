---
layout: default
title: "Consiglio Direttivo"
subtitle: "I membri del Consiglio Direttivo del Master"
permalink: /direttivo/
partner: false
show_sidetoc: false
---

# Consiglio Direttivo

<div class="direttivo-container">
  {% assign direzione = site.data.docenti | where_exp: "item", "item.role == 'Direttore del Master' or item.role == 'Vice-Direttrice'" %}
  
  {% if direzione.size > 0 %}
  <section class="direzione-section">
    <h2>Direzione</h2>
    <div class="direttivi-grid">
      {% for docente in direzione %}
      <div class="docente-card">
        <div class="docente-image">
          <img src="{{ site.baseurl }}{{ docente.image }}" alt="{{ docente.name }}">
        </div>
        <div class="docente-info">
          <h3 class="docente-name">{{ docente.name }}</h3>
          <p class="docente-role">{{ docente.role }}</p>
          <p class="docente-institution">{{ docente.institution }}</p>
        </div>
      </div>
      {% endfor %}
    </div>
  </section>
  {% endif %}

  {% assign consiglio = site.data.docenti | where: "role", "Consiglio Direttivo" %}
  
  {% if consiglio.size > 0 %}
  <section class="consiglio-section">
    <h2>Consiglio Direttivo</h2>
    <div class="direttivi-grid">
      {% for docente in consiglio %}
      <div class="docente-card">
        <div class="docente-image">
          <img src="{{ site.baseurl }}{{ docente.image }}" alt="{{ docente.name }}">
        </div>
        <div class="docente-info">
          <h3 class="docente-name">{{ docente.name }}</h3>
          <p class="docente-role">{{ docente.role }}</p>
          <p class="docente-institution">{{ docente.institution }}</p>
        </div>
      </div>
      {% endfor %}
    </div>
  </section>
  {% endif %}
</div>
