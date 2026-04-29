---
layout: page
title: activities
permalink: /activities/
description: My running and cycling journey via Garmin Connect.
nav: true
nav_order: 7
---

I use **Garmin Connect** to track my training. Here are some of my featured activities.

<div class="activities-container">
  {% for activity in site.data.garmin_activities %}
  <div class="garmin-card shadow-sm p-3 mb-5 bg-body rounded border">
    <div class="ratio ratio-16x9" style="min-height: 500px;">
        <iframe src='https://connect.garmin.com/modern/activity/embed/{{ activity.id }}' title='Garmin Activity' frameborder='0'></iframe>
    </div>
  </div>
  {% endfor %}
</div>

<div class="row mt-3">
    <div class="col-md-12">
        <div class="alert alert-info">
            <i class="fa-solid fa-code"></i> 
            <strong>Note for Luca:</strong> To add more activities, simply add the ID to <code>_data/garmin_activities.yml</code>. No need to touch this HTML again!
        </div>
    </div>
</div>

<style>
    .garmin-card {
        background: var(--global-card-bg-color);
        max-width: 800px;
        margin: 0 auto 2rem auto;
    }
    iframe {
        width: 100%;
        border: none;
        border-radius: 8px;
    }
</style>
