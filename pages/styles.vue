<template>
  <div>
      <div class="pseudo" data-pseudo-width="100">
          not support ...
      </div>
  </div>
</template>

<style>
  .pseudo::before {
      background-color: #000;
      width: attr(data-pseudo-width px)
  }
</style>
