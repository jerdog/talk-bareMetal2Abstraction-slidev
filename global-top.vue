<template>
    <Progress />
    <InfoLine v-if="$slidev.configs.infoLine ?? true" />
</template>