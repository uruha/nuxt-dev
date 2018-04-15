<template>
  <div>
      <div class="pseudo" data-pseudo-color="" data-pseudo-width="100" data-pseudo-content="Yes support content :)">
          not support attr for width ...
      </div>
  </div>
</template>

<style>
  :root {
      --red-color: attr(data-pseudo-color); /** not support ... */
      --red-color: red;
  }
  .pseudo::before {
      background-color: #000;
      width: attr(data-pseudo-width px);
  }
  .pseudo::after {
      color: var(--red-color);
      content: attr(data-pseudo-content);
  }
</style>
