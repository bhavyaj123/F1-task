<template>
  <div>
    <nav class="navbar navbar-dark bg-dark">
      <a class="navbar-brand" href="#">f1studioz</a>

      <form class="form-inline">
        <b-row>
          <b-col>
            <b-icon
              class="mt-3"
              variant="white"
              scale="1"
              icon="border-all"
            ></b-icon>
          </b-col>
          <b-col>
            <b-icon class="mt-3" variant="white" scale="1" icon="bell"></b-icon>
          </b-col>
          <b-col>
            <b-icon
              class="mt-3"
              variant="white"
              scale="1"
              icon="question-circle"
            ></b-icon>
          </b-col>
          <b-col>
            <b-avatar
              variant="info"
              src="https://placekitten.com/300/300"
            ></b-avatar>
          </b-col>
        </b-row>
      </form>
    </nav>
    <div v-if="this.componentCheck == true">
      <b-card no-body>
        <b-tabs v-model="tabIndex" fill>
          <b-tab title="CARTS" :title-link-class="linkClass(0)"
            ><cartsTab :componentCheck="componentCheck"></cartsTab
          ></b-tab>
          <b-tab title="FAVORITES" :title-link-class="linkClass(1)"
            >FAVORITES</b-tab
          >
        </b-tabs>
      </b-card>
    </div>
  </div>
</template>
<script>
import cartsTab from "@/components/cartsTab.vue";
export default {
  components: {
    cartsTab,
  },
  data: () => ({
    tabIndex: 0,
    componentCheck: true,
  }),
  methods: {
    linkClass(idx) {
      if (this.tabIndex === idx) {
        return ["bg-primary", "text-light"];
      } else {
        return ["bg-light", "text-info"];
      }
    },
  },
};
</script>