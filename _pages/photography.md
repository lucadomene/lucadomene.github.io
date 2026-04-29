---
layout: page
title: photography
permalink: /photography/
description: A collection of my photography work with metadata.
nav: true
nav_order: 8
---

My photography journey, capturing moments across Italy and my studies.

<div class="photography-gallery">
  {% for photo in site.data.photography %}
  <div class="photo-item mb-5 shadow-sm rounded border p-3">
    <div class="row">
      <div class="col-md-7">
        <a href="{{ '/assets/img/photography/' | append: photo.image | relative_url }}" 
           class="spotlight" 
           data-title="{{ photo.title }}">
          <img src="{{ '/assets/img/photography/' | append: photo.image | relative_url }}" 
               class="img-fluid rounded shadow-sm" 
               alt="{{ photo.title }}">
        </a>
      </div>
      <div class="col-md-5 mt-3 mt-md-0">
        <h3>{{ photo.title }}</h3>
        <p class="text-muted"><i class="fa-solid fa-location-dot"></i> {{ photo.location }}</p>
        
        <div class="metadata p-2 bg-light rounded mb-3">
          <ul class="list-unstyled mb-0 small">
            <li><strong>Camera:</strong> {{ photo.camera }}</li>
            <li><strong>Lens:</strong> {{ photo.lens }}</li>
            <li><strong>Settings:</strong> {{ photo.settings }}</li>
          </ul>
        </div>

        {% if photo.comment %}
        <div class="comment italic border-left pl-3">
          <p><i>"{{ photo.comment }}"</i></p>
        </div>
        {% endif %}
      </div>
    </div>
  </div>
  {% endfor %}
</div>

<div class="alert alert-info">
  <i class="fa-solid fa-camera"></i> 
  <strong>Pro Tip:</strong> To add new photos, place them in <code>assets/img/photography/</code> and add their details to <code>_data/photography.yml</code>.
</div>

<style>
  .photo-item {
    background: var(--global-card-bg-color);
  }
  .metadata {
    border-left: 4px solid var(--global-theme-color);
  }
  .border-left {
    border-left: 2px solid #dee2e6;
  }
  .pl-3 {
    padding-left: 1rem;
  }
</style>

<!-- Load Spotlight for a nice lightbox experience -->
<script src="{{ '/assets/js/spotlight.bundle.min.js' | relative_url }}"></script>
