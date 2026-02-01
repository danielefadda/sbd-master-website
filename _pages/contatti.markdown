---
layout: default
title: "Contatti"
subtitle: "Informazioni e Contatti"
permalink: /contatti/
partner: true
show_sidetoc: false
---

# Informazioni e Contatti

## Segreteria didattica/amministrativa

<div class="contact-container">
  <div class="contact-info">
    <h3>Master Big Data Analytics & Artificial Intelligence for Society</h3>
    
    <div class="contact-details">
      <div class="contact-item">
        <i class="fas fa-building"></i>
        <div class="contact-text">
          <strong>Dipartimento di Informatica</strong>
          <p>Università di Pisa</p>
        </div>
      </div>
      
      <div class="contact-item">
        <i class="fas fa-map-marker-alt"></i>
        <div class="contact-text">
          <strong>Indirizzo</strong>
          <p>Largo Bruno Pontecorvo, 3<br/>56127 Pisa (Italia)</p>
        </div>
      </div>
      
      <div class="contact-item">
        <i class="fas fa-phone"></i>
        <div class="contact-text">
          <strong>Telefono</strong>
          <p><a href="tel:+390502212727">050 221 2727</a></p>
        </div>
      </div>
      
      <div class="contact-item">
        <i class="fas fa-envelope"></i>
        <div class="contact-text">
          <strong>Email</strong>
          <p><a href="mailto:masterbigdata@unipi.it">masterbigdata@unipi.it</a></p>
        </div>
      </div>
    </div>
  </div>
  
  <div class="logos-section">
    <h3>Partner Istituzionali</h3>
    <div class="logos-grid">
      <div class="logo-item">
        <img src="{{ site.baseurl }}/assets/images/CNR.png" alt="CNR - Consiglio Nazionale delle Ricerche">
      </div>
      <div class="logo-item">
        <img src="{{ site.baseurl }}/assets/images/cherubino_pant541.png" alt="Cherubino">
      </div>
    </div>
  </div>
</div>

<style>
.contact-container {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 40px;
  margin: 40px 0;
  align-items: start;
}

.contact-info {
  background: #f8f9fa;
  padding: 30px;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

.contact-info h3 {
  color: #333;
  margin-bottom: 30px;
  font-size: 1.5rem;
}

.contact-details {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.contact-item {
  display: flex;
  gap: 15px;
  align-items: flex-start;
}

.contact-item i {
  font-size: 1.5rem;
  color: #007bff;
  margin-top: 2px;
  min-width: 25px;
}

.contact-text {
  flex: 1;
}

.contact-text strong {
  display: block;
  color: #333;
  margin-bottom: 5px;
  font-size: 0.95rem;
}

.contact-text p {
  color: #666;
  margin: 0;
  font-size: 0.9rem;
  line-height: 1.5;
}

.contact-text a {
  color: #007bff;
  text-decoration: none;
  transition: color 0.3s ease;
}

.contact-text a:hover {
  color: #0056b3;
  text-decoration: underline;
}

.logos-section {
  background: white;
  padding: 30px;
  border-radius: 8px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

.logos-section h3 {
  color: #333;
  margin-bottom: 30px;
  font-size: 1.5rem;
}

.logos-grid {
  display: flex;
  flex-direction: column;
  gap: 30px;
}

.logo-item {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 20px;
  background: #f8f9fa;
  border-radius: 8px;
  min-height: 140px;
  transition: all 0.3s ease;
}

.logo-item:hover {
  background: white;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}

.logo-item img {
  max-width: 100%;
  max-height: 100%;
  object-fit: contain;
}

/* Responsive */
@media (max-width: 768px) {
  .contact-container {
    grid-template-columns: 1fr;
    gap: 30px;
  }
  
  .contact-info,
  .logos-section {
    padding: 20px;
  }
  
  .contact-info h3,
  .logos-section h3 {
    font-size: 1.25rem;
  }
  
  .contact-item {
    gap: 12px;
  }
  
  .contact-item i {
    font-size: 1.25rem;
  }
}

@media (max-width: 480px) {
  .contact-info,
  .logos-section {
    padding: 15px;
  }
  
  .contact-item i {
    font-size: 1.1rem;
  }
  
  .contact-text strong {
    font-size: 0.9rem;
  }
  
  .contact-text p {
    font-size: 0.85rem;
  }
}
</style>
