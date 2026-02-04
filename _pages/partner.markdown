---
layout: default
title: "Partner"
permalink: /partner/
partner: false
show_sidetoc: false
header_type: sbd #,hero, base, post, hero,image, splash
header_img: assets/images/header.svg
header_title: " "

---

# I nostri Partner

Il Master in Big Data Analytics & AI for Society collabora con numerose aziende e istituzioni di rilievo nel settore dei dati e dell'intelligenza artificiale. I nostri partner contribuiscono attivamente al successo del programma, offrendo opportunità di tirocinio, progetti reali e supporto nella formazione dei nostri studenti.

Un numero significativo di studenti ha trovato impiego presso queste aziende partner, dimostrando l'efficacia del nostro approccio formativo e la qualità delle collaborazioni instaurate.

{% if site.data.partners.partners %}

## Partner Attuali

<div class="partners-grid">
  {% for partner in site.data.partners.partners %}
    {% if partner.active and partner.visible %}
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

## Partner delle passate edizioni

<div class="partners-grid">
  {% for partner in inactive_partners %}
    {% if partner.visible %}
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
    {% endif %}
  {% endfor %}
</div>

{% endif %}

{% endif %}
