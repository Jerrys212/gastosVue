<script setup>
import Alerta from "./Alerta.vue";
import { ref } from "vue";

const presupuesto = ref(0);

const error = ref("");

const emits = defineEmits(["definir-presupuesto"]);

const definirPresupuesto = () => {
    if (presupuesto.value <= 0 || presupuesto.value === " ") {
        error.value = "presupuesto no valido";
        setTimeout(() => {
            error.value = "";
        }, 2000);

        return;
    }
    emits("definir-presupuesto", presupuesto.value);
};
</script>

<template>
    <form action="" class="presupuesto" @submit.prevent="definirPresupuesto">
        <Alerta v-if="error">
            {{ error }}
        </Alerta>

        <div class="campo">
            <label for="nuevo-presupuesto">Definir Presupuesto</label>
            <input type="number" id="nuevo-presupuesto" class="nuevo-presupuesto" placeholder="Presupuesto" v-model.number="presupuesto" min="0" />
        </div>

        <input type="submit" value="Definir Presupuesto" />
    </form>
</template>

<style scoped>
.presupuesto {
    width: 100%;
}

.campo {
    display: grid;
    gap: 2rem;
}

.presupuesto label {
    font-size: 2.8rem;
    text-align: center;
    color: var(--azul);
}

.presupuesto input[type="number"] {
    background-color: var(--gris-claro);
    border-radius: 1rem;
    padding: 1rem;
    border: none;
    font-size: 2.2rem;
    text-align: center;
}
.presupuesto input[type="submit"] {
    background-color: var(--azul);
    border-radius: 1rem;
    padding: 1rem;
    border: none;
    font-size: 2rem;
    text-align: center;
    margin-top: 2rem;
    color: var(--blanco);
    width: 100%;
    font-weight: 900;
    transition: background-color 300ms ease;
}
.presupuesto input[type="submit"]:hover {
    background-color: #1048a4;
    cursor: pointer;
}
</style>
