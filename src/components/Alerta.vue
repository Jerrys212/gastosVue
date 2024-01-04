<template>
    <div class="alerta">
        <slot></slot>
    </div>
</template>

<style>
.alerta {
    padding: 1rem;
    font-weight: 900;
    text-transform: uppercase;
    text-align: center;
    font-size: 1.6rem;
    background-color: var(--blanco);
    border-left: 0.5rem solid #b91c1c;
    color: #b91c1c;
    margin-bottom: 1.5rem;
}
</style>
