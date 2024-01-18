<script setup>
import imagen from "../assets/img/grafico.jpg";
import { formatearDinero } from "../helpers";
const props = defineProps({
  presupuesto: {
    type: Number,
    required: true,
  },
  disponible: {
    type: Number,
    required: true,
  },
});
</script>

<template>
  <div class="dos-columnas">
    <div class="contenedor-grafico">
      <img :src="imagen" alt="" />
    </div>
    <div class="contenedor-presupuesto">
      <button class="reset-app">Reset</button>

      <p>
        <span>Presupuesto: </span>
        {{ formatearDinero(presupuesto) }}
      </p>
      <p>
        <span>Disponible: </span>
        {{ formatearDinero(disponible) }}
      </p>
      <p>
        <span>Gastado: </span>
        $0
      </p>
    </div>
  </div>
</template>

<style scoped lang="scss">
.dos-columnas {
  display: flex;
  flex-direction: column;
}
.dos-columnas :first-child {
  margin-bottom: 4rem;
}

@media (min-width: 768px) {
  .dos-columnas {
    flex-direction: row;
    gap: 4rem;
    align-items: center;
  }

  .dos-columnas :first-child {
    margin-bottom: 0;
  }
}

.reset-app {
  background-color: #db2777;
  border: none;
  padding: 1rem 2rem;
  width: 100%;
  color: var(--blanco);
  font-weight: 900;
  text-transform: uppercase;
  border-radius: 1rem;
  transition: background-color 0.5s;
  &:hover {
    cursor: pointer;
    background-color: #c11d67;
  }
}
.contenedor-presupuesto {
  width: 100%;
  p {
    font-size: 2.4rem;
    text-align: center;
    color: var(--gris-oscuro);
  }

  span {
    font-weight: 900;
    color: var(--azul);
  }
}

@media (min-width: 768px) {
  .contenedor-presupuesto {
    width: 100%;
    p {
      text-align: left;
    }
  }
}
</style>
