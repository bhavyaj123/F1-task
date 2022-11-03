<template>
  <div>
    <b-card no-body class="text-center">
      <form>
        <div class="form-group row">
          <label for="staticEmail" class="col-sm-2 col-form-label"
            >Select Catageory</label
          >
          <div class="col-sm-10">
            <b-dropdown
              text="Residential Door"
              variant="outline-dark"
              class="m-2"
            >
              <b-dropdown-item href="#">Action</b-dropdown-item>
              <b-dropdown-item href="#">Another action</b-dropdown-item>
              <b-dropdown-item href="#">Something else here</b-dropdown-item>
            </b-dropdown>
          </div>
        </div>
        <div class="form-group row">
          <label for="staticEmail" class="col-sm-2 col-form-label"
            >Select Series</label
          >
          <div class="col-sm-10">
            <b-dropdown
              text="Canon Ridge Collection"
              variant="outline-dark"
              class="m-2"
            >
              <b-dropdown-item href="#">Action</b-dropdown-item>
              <b-dropdown-item href="#">Another action</b-dropdown-item>
              <b-dropdown-item href="#">Something else here</b-dropdown-item>
            </b-dropdown>
          </div>
        </div>
        <div class="form-group row">
          <label for="staticEmail" class="col-sm-2 col-form-label"
            >Door Type</label
          >
          <div class="col-sm-10">
            <b-dropdown text="CAN212" variant="outline-dark" class="m-2">
              <b-dropdown-item href="#">Action</b-dropdown-item>
              <b-dropdown-item href="#">Another action</b-dropdown-item>
              <b-dropdown-item href="#">Something else here</b-dropdown-item>
            </b-dropdown>
          </div>
        </div>
        <button style="float: right" type="submit" class="btn btn-primary">
          Configure
        </button>
      </form>
    </b-card>
  </div>
</template>
<script>
export default {
  data: () => ({}),
  methods: {},
};
</script>