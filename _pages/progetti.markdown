---
layout: default
title: "Progetti"
permalink: /progetti/
show_sidetoc: false
---

# Progetti del Master

I progetti del Master in Big Data Analytics and Artificial Intelligence for Society rappresentano il momento culminante del percorso formativo, in cui gli studenti applicano le competenze acquisite durante i corsi per realizzare un'analisi innovativa su tematiche di rilevanza sociale, economica e culturale.

<div class="container py-3">
    <div class="row">
        <div class="col-md-12">
            <p class="lead" style="text-align:justify">
                Durante il Master, gli studenti lavorano in gruppi multidisciplinari per osservare e rappresentare fenomeni da diverse prospettive, integrando le conoscenze acquisite dalle diverse discipline: dalla raccolta dei dati alla visualizzazione e presentazione finale. I progetti spaziano da analisi dei dati sui social media, studi economici e sociali, applicazioni di machine learning e intelligenza artificiale, fino a ricerche sugli impatti dei big data nella società.
            </p>
        </div>
    </div>
</div>

---

## Progetti 2025

<div id="projects-container">
    {% for project in site.data.progetti_2025 %}
        <a href="{{project.path}}" target="_blank">
            <div class="row py-2 my-3 project">
                <div class="col-md-4">
                    <div class="project-img">
                        <img src="{{site.baseurl}}{{ project.img_url }}" alt="{{ project.name }}">
                    </div>
                </div>
                <div class="col-md-8">
                    <div class="project-body">
                        <h5>{{ project.group }}. {{ project.name }}</h5>
                        <p>{{ project.description }}</p>
                        {% assign students = project.students %}
                        <p class="students">
                            <em><strong>Studenti</strong>:
                                {% for student in students %}
                                    {% if forloop.last %}
                                        <span>{{ student }}.</span>
                                    {% else %}
                                        <span>{{ student }}, </span>
                                    {% endif %}
                                {% endfor %}
                            </em>
                        </p>
                    </div>
                </div>
            </div>
        </a>
    {% endfor %}
</div>

---

## Progetti 2024

<div id="projects-container">
    {% for project in site.data.progetti_2024 %}
        <a href="{{project.path}}" target="_blank">
            <div class="row py-2 my-3 project">
                <div class="col-md-4">
                    <div class="project-img">
                        <img src="{{site.baseurl}}{{ project.img_url }}" alt="{{ project.name }}">
                    </div>
                </div>
                <div class="col-md-8">
                    <div class="project-body">
                        <h5>{{ project.group }}. {{ project.name }}</h5>
                        <p>{{ project.description }}</p>
                        {% assign students = project.students %}
                        <p class="students">
                            <em><strong>Studenti</strong>:
                                {% for student in students %}
                                    {% if forloop.last %}
                                        <span>{{ student }}.</span>
                                    {% else %}
                                        <span>{{ student }}, </span>
                                    {% endif %}
                                {% endfor %}
                            </em>
                        </p>
                    </div>
                </div>
            </div>
        </a>
    {% endfor %}
</div>
