<template>
  <div>
    <!-- Add your code here -->
    <div>
      <h3>Boss</h3>
      <slot name="boss" :item="boss"></slot>
    </div>
    <div>
      <h3>Employees</h3>
        <div class="d-flex flex-row">
          <div class="m-2" v-for="(employee,i) in employees" :key="i"><slot name="employees" :item="employee"></slot></div>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    cats: {
      type: Array,
    },
  },
  data() {
    return {
      boss: this.cats.find((el) => el.role == 'Boss'),
      employees: this.cats.filter((el) => el.role != 'Boss'),
    };
  },
};
</script>

<style lang="scss" scoped></style>
