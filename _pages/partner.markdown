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

{% endif %}
