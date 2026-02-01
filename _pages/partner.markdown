---
layout: default
title: "Partner"
subtitle: "I nostri partner attuali e passati"
permalink: /partner/
partner: false
show_sidetoc: false
---

# I nostri Partner

{% if site.data.partners.partners %}

## Partner Attuali

<div class="partners-grid">
  {% for partner in site.data.partners.partners %}
    {% if partner.active %}
      <div class="partner-item partner-{{ partner.level }} partner-{{ partner.type }}">
        <div class="partner-logo-wrapper">
          <img src="{{ site.baseurl }}/{{ partner.logo }}" 
               alt="{{ partner.name }}" 
               class="partner-logo"
               title="{{ partner.name }} - {{ partner.type | capitalize }} ({{ partner.level | capitalize }})">
        </div>
        <div class="partner-info">
          <p class="partner-name">{{ partner.name }}</p>
          <span class="partner-badge partner-badge-{{ partner.type }}">{{ partner.type | capitalize }}</span>
          <span class="partner-badge partner-badge-{{ partner.level }}">{{ partner.level | capitalize }}</span>
        </div>
      </div>
    {% endif %}
  {% endfor %}
</div>

{% assign inactive_partners = site.data.partners.partners | where: "active", false %}
{% if inactive_partners.size > 0 %}

<hr class="mt-5 pt-3" />

## Partner del Passato

<div class="partners-grid">
  {% for partner in inactive_partners %}
    <div class="partner-item partner-{{ partner.level }} partner-{{ partner.type }} partner-inactive">
      <div class="partner-logo-wrapper">
        <img src="{{ site.baseurl }}/{{ partner.logo }}" 
             alt="{{ partner.name }}" 
             class="partner-logo"
             title="{{ partner.name }} - {{ partner.type | capitalize }} ({{ partner.level | capitalize }})">
      </div>
      <div class="partner-info">
        <p class="partner-name">{{ partner.name }}</p>
        <span class="partner-badge partner-badge-{{ partner.type }}">{{ partner.type | capitalize }}</span>
        <span class="partner-badge partner-badge-{{ partner.level }}">{{ partner.level | capitalize }}</span>
      </div>
    </div>
  {% endfor %}
</div>

{% endif %}

<style>
.partners-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 30px;
  align-items: stretch;
  margin: 40px 0;
}

.partner-item {
  background: white;
  border-radius: 8px;
  padding: 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  text-align: center;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
  border-top: 4px solid #ccc;
}

.partner-item:hover {
  box-shadow: 0 4px 16px rgba(0, 0, 0, 0.15);
  transform: translateY(-2px);
}

.partner-item.partner-inactive {
  opacity: 0.7;
}

.partner-item.partner-inactive:hover {
  opacity: 0.9;
}

/* Partner Level Styling */
.partner-item.partner-gold {
  border-top-color: #FFD700;
}

.partner-item.partner-silver {
  border-top-color: #C0C0C0;
}

.partner-logo-wrapper {
  width: 100%;
  height: 140px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 15px;
}

.partner-logo {
  max-width: 100%;
  max-height: 100%;
  object-fit: contain;
}

.partner-info {
  width: 100%;
}

.partner-name {
  margin: 10px 0;
  font-weight: 600;
  color: #333;
  font-size: 0.95rem;
}

.partner-badge {
  display: inline-block;
  padding: 4px 10px;
  margin: 2px;
  border-radius: 20px;
  font-size: 0.75rem;
  font-weight: 500;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.partner-badge-service {
  background-color: #E3F2FD;
  color: #1976D2;
}

.partner-badge-vendor {
  background-color: #F3E5F5;
  color: #7B1FA2;
}

.partner-badge-research {
  background-color: #E8F5E9;
  color: #388E3C;
}

.partner-badge-gold {
  background-color: #FFF8E1;
  color: #F57F17;
  font-weight: 700;
}

.partner-badge-silver {
  background-color: #ECEFF1;
  color: #455A64;
  font-weight: 700;
}

/* Responsive */
@media (max-width: 768px) {
  .partners-grid {
    grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
    gap: 20px;
  }

  .partner-item {
    padding: 15px;
  }

  .partner-logo-wrapper {
    height: 120px;
  }
}

@media (max-width: 480px) {
  .partners-grid {
    grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
    gap: 15px;
  }

  .partner-logo-wrapper {
    height: 100px;
  }

  .partner-name {
    font-size: 0.85rem;
  }

  .partner-badge {
    padding: 3px 8px;
    font-size: 0.7rem;
  }
}
</style>

{% endif %}
