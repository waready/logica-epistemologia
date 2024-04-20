<template>
  <div class="timeline">
    <div v-for="(event, index) in events" :key="index" :class="['timeline-item', {
      'timeline-item-right':
        index % 2 === 0, 'timeline-item-left': index % 2 !== 0
    }]">
      <div class="timeline-item-header">{{ event.date }}</div>
      <div class="timeline-item-content">
        <ul>
          <li v-for="item in event.description" :key="item">
            {{ item }}
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      events: [
        { date: "Aristóteles (384-322 a.C.)", description: [
          "Considerado el padre de la lógica formal.",
          'Desarrolló los fundamentos de la lógica aristotélica en su obra "Organon".',
          'Propuso los primeros sistemas de silogismo, formas de razonamiento deductivo.'
        ]},
        { date: "Leibniz (1646-1716)", description: [
          'Hizo importantes contribuciones al desarrollo del cálculo infinitesimal y la lógica.',
          'Introdujo el concepto de lógica simbólica y desarrolló una notación formal.'
        ]},
        { date: "George Boole (1815-1864)", description: [
          'Trabajó en el álgebra booleana, estableciendo un sistema algebraico para el razonamiento lógico.',
          'Su obra "An Investigation of the Laws of Thought" es un hito en la lógica simbólica.'
        ]},
        { date: "Gottlob Frege (1848-1925)", description: [
          "Uno de los fundadores de la lógica matemática y la filosofía analítica.",
          'Introdujo el concepto de funciones y predicados en "Begriffsschrift"'
        ]},
        { date: "Bertrand Russell (1872-1970) y Alfred North Whitehead (1861-1947)", description: [
          'Escribieron "Principia Mathematica", buscando fundamentar la matemática en la lógica.',
          'Desarrollaron la teoría de tipos y enfrentaron el problema de la paradoja en la teoría de conjuntos.'
        ]},
        { date: "Ludwig Wittgenstein (1889-1951)", description: [
          'Contribuyó a la filosofía del lenguaje y la lógica.',
          'Propuso una teoría de la representación lingüística en "Tractatus Logico-Philosophicus".'
        ]},
      ]
    };
  }
};
</script>

<style>
.timeline {
  position: relative;
  padding: 15px;
}

.timeline-item {
  position: relative;
  margin-bottom: 10px;
  padding: 20px;
  font-size: 13px;
  background-color: #f0f0f0;
  border-left: 2px solid #007bff;
  /* Cambia el color de la línea de tiempo según tus preferencias */
}

.timeline-item-right {
  margin-left: 50%;
}

.timeline-item-left {
  margin-right: 50%;
}

.timeline-item-header {
  font-weight: bold;
  margin-bottom: 2px;
}

.timeline-item-content {
  margin-top: 2px;
  color: #555;
  /* Cambia el color del texto según tus preferencias */
}
</style>
