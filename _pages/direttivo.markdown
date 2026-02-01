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
          <p class="docente-bio">{{ docente.bio }}</p>
        </div>
      </div>
      {% endfor %}
    </div>
  </section>
  {% endif %}
</div>

<style>
.direttivo-container {
  margin: 40px 0;
}

.direzione-section,
.consiglio-section {
  margin-bottom: 60px;
}

.direzione-section h2,
.consiglio-section h2 {
  color: #333;
  margin-bottom: 40px;
  font-size: 1.75rem;
  font-weight: 600;
  border-bottom: 3px solid #007bff;
  padding-bottom: 15px;
}

.direttivi-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 30px;
  align-items: stretch;
}

.docente-card {
  background: white;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 2px 12px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
  display: flex;
  flex-direction: column;
}

.docente-card:hover {
  box-shadow: 0 6px 20px rgba(0, 0, 0, 0.15);
  transform: translateY(-4px);
}

.docente-image {
  width: 100%;
  height: 250px;
  overflow: hidden;
  background: #f0f0f0;
}

.docente-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.3s ease;
}

.docente-card:hover .docente-image img {
  transform: scale(1.05);
}

.docente-info {
  padding: 20px;
  flex: 1;
  display: flex;
  flex-direction: column;
}

.docente-name {
  font-size: 1.25rem;
  font-weight: 600;
  color: #333;
  margin: 0 0 8px 0;
}

.docente-role {
  font-size: 0.95rem;
  font-weight: 500;
  color: #007bff;
  margin: 0 0 5px 0;
}

.docente-institution {
  font-size: 0.85rem;
  color: #666;
  margin: 0 0 12px 0;
  font-style: italic;
}

.docente-bio {
  font-size: 0.9rem;
  color: #555;
  line-height: 1.6;
  margin: 0;
  flex: 1;
}

/* Responsive */
@media (max-width: 768px) {
  .direttivi-grid {
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
  }

  .direzione-section h2,
  .consiglio-section h2 {
    font-size: 1.5rem;
  }

  .docente-image {
    height: 200px;
  }

  .docente-info {
    padding: 15px;
  }

  .docente-name {
    font-size: 1.1rem;
  }
}

@media (max-width: 480px) {
  .direttivi-grid {
    grid-template-columns: 1fr;
  }

  .docente-image {
    height: 180px;
  }

  .docente-name {
    font-size: 1rem;
  }

  .docente-bio {
    font-size: 0.85rem;
  }
}
</style>
