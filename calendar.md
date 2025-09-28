---
title: "Calendar"
permalink: /calendar/
layout: single
---

# Fellowship Calendar

<div class="calendar-buttons">
  <button id="btn-month" onclick="setCalendarView('MONTH')">Month</button>
  <button id="btn-week" onclick="setCalendarView('WEEK')">Week</button>
  <button id="btn-agenda" onclick="setCalendarView('AGENDA')">Agenda</button>
</div>

<div class="calendar-full">
  <iframe
    id="cuh-calendar"
    src="https://calendar.google.com/calendar/embed?src=cuhchristians%40gmail.com&ctz=Europe%2FLondon&mode=MONTH"
    style="border:0"
    frameborder="0"
    scrolling="yes">
  </iframe>
</div>

<script>
function setCalendarView(view) {
  const iframe = document.getElementById('cuh-calendar');
  const baseUrl = "https://calendar.google.com/calendar/embed?src=cuhchristians%40gmail.com&ctz=Europe%2FLondon";
  iframe.src = baseUrl + "&mode=" + view;

  // Highlight active button
  document.querySelectorAll('.calendar-buttons button').forEach(btn => {
    btn.classList.remove('active');
  });
  if (view === "MONTH") document.getElementById('btn-month').classList.add('active');
  if (view === "WEEK") document.getElementById('btn-week').classList.add('active');
  if (view === "AGENDA") document.getElementById('btn-agenda').classList.add('active');
}
</script>

<style>
.calendar-buttons button.active {
  background-color: #004999;
  font-weight: bold;
}
</style>
