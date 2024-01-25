<template>
  <v-footer class="gov-footer d-print-none">
  </v-footer>
</template>

<script>
export default {
  name: 'BCGovFooter'
};
</script>

<style lang="scss" scoped>
.gov-footer {
  background-color: #003366 !important;
  border-top: 2px solid #fcba19;
  flex-shrink: 0;
  min-height: 2.5rem;
  min-width: 100%;
  padding-bottom: 0;
  padding-top: 0;

  a {
    color: #ffffff;
    font-size: 1rem;

    &:focus {
      outline: none;
    }
  }

  .v-btn__content>span {
    color: #ffffff;
    font-size: 1rem;
    font-weight: normal;
    text-decoration: none;
    text-transform: none;
  }
}
</style>
