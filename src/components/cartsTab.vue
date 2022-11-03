<template>
  <div>
    <div v-if="this.componentCheck == true">
      <b-tabs content-class="mt-3">
        <b-tab title="Active Carts" active>
          <div>
            <div class="text-left" style="float: right">
              <p class="h1 mb-2">
                <b-button class="rounded-circle bg-success p-2">
                  <b-icon
                    @click="add_button()"
                    variant="light"
                    v-b-modal.modal-multi-1
                    icon="plus-lg"
                  ></b-icon>
                </b-button>
              </p>
            </div>

            <b-table class="text-left" striped hover :items="items"> </b-table>
          </div>
        </b-tab>
        <b-tab title="Archievedn Carts"><p>I'm the second tab</p></b-tab>
      </b-tabs>
    </div>

    <b-navbar
      v-if="this.checkCard == true || this.childComponentCheck == true"
      toggleable="lg"
      type="dark"
      variant="dark"
    >
      <b-icon
        @click="call_parent1()"
        variant="white"
        icon="chevron-left"
      ></b-icon>

      <b-navbar-brand href="#">Create a new order</b-navbar-brand>
    </b-navbar>
    <b-card align="start" style="max-width: 1400px">
      <div v-if="this.checkCard == true">
        <b-card
          class="mt-3"
          v-for="item in carditems"
          :key="item.id"
          @click="call_parent_card(item.itemName)"
        >
          <b-row no-gutters>
            <b-col md="10">
              <b-card-text>
                <h4 class="headline mb-0" v-text="item.itemName"></h4>
              </b-card-text>
              <b-card-text>
                <div class="headline mb-0" v-text="item.itemData"></div>
              </b-card-text>
            </b-col>
            <b-col md="2">
              <b-icon icon="chevron-right" scale="2" variant="success"></b-icon>
            </b-col>
          </b-row>
        </b-card>
      </div>
    </b-card>
    <div v-if="this.childComponentCheck == true">
      <childCard></childCard>
    </div>
  </div>
</template>
<script>
import childCard from "@/components/childCard.vue";
export default {
  components: {
    childCard,
  },
  props: {
    componentCheck: Boolean,
  },
  data() {
    return {
      checkCard: false,
      childComponentCheck: false,
      carditems: [
        {
          id: 1,
          itemName: "Configure your door from scratch",
          itemData: "Residential,Commercial,Entry doors",
        },
        {
          id: 2,
          itemName: "Parts/Openers",
          itemData: "Order Parts and Openers",
        },
        {
          id: 3,
          itemName: "Direct Item Entry",
          itemData: "Order Parts/ Openers using a Product ID",
        },
        {
          id: 4,
          itemName: "Choose from Favourites",
          itemData: "Re-order from your favourites",
        },
      ],
      items: [
        {
          product_information:
            "Canyon Ridge® Collection Ultra-Grain® Series with Intellicore®",
          cart_name: "Johnson_Classic14209123",
          shipping_point: "Russia Plant",
          created_by: "Dickerson",
          expiry: "Expires in 6 days",
        },
        {
          product_information:
            "Hardware Special - Stock. W4.HB.8.0.7.0.None.Sol - WH.9.G.2",
          cart_name: "Carter_Classic14209123",
          shipping_point: "Russia Plant",
          created_by: "Dickerson",
          expiry: "Expires in 60 days",
        },
        {
          product_information:
            "10' 0'' X 10' 0.0'' CAN211CCW1 COMPLETE DOOR INTELLICO",
          cart_name: "Michigan_Classic14209123",
          shipping_point: "ABC Plant",
          created_by: "Dickerson",
          expiry: "Expires in 16 days",
        },
        {
          product_information:
            "8’ 8’’ X 8’ 6’’ CAN211CCW1 Commercial DOOR INTELLICORE",
          cart_name: "JohnDavid_Classic14209123",
          shipping_point: "Russia Plant",
          created_by: "Dickerson",
          expiry: "Expires in 80 days",
        },
        {
          product_information:
            "Hardware Special - Stock. W4.HB.8.0.7.0.None.Sol - WH.9.G.2",
          cart_name: "Chiristopher_Classic14209123",
          shipping_point: "ABC Plant",
          created_by: "Dickerson",
          expiry: "Expires in 90 days",
        },
        {
          product_information:
            "8’ 8’’ X 8’ 6’’ CAN211CCW1 Commercial DOOR INTELLICOR",
          cart_name: "Johnson_Classic14209123",
          shipping_point: "Russia Plant",
          created_by: "Dickerson",
          expiry: "Expires in 6 days",
        },
        {
          product_information:
            "Hardware Special - Stock. W4.HB.8.0.7.0.None.Sol - WH.9.G.2",
          cart_name: "Johnson_Classic14209123",
          shipping_point: "Russia Plant",
          created_by: "Dickerson",
          expiry: "Expires in 6 days",
        },
        {
          product_information:
            "8’ 8’’ X 8’ 6’’ CAN211CCW1 Commercial DOOR INTELLICOR",
          cart_name: "Johnson_Classic14209123",
          shipping_point: "Russia Plant",
          created_by: "Dickerson",
          expiry: "Expires in 6 days",
        },
        {
          product_information:
            "Hardware Special - Stock. W4.HB.8.0.7.0.None.Sol - WH.9.G.2",
          cart_name: "Johnson_Classic14209123",
          shipping_point: "Russia Plant",
          created_by: "Dickerson",
          expiry: "Expires in 6 days",
        },
        {
          product_information:
            "Hardware Special - Stock. W4.HB.8.0.7.0.None.Sol - WH.9.G.2",
          cart_name: "Johnson_Classic14209123",
          shipping_point: "Russia Plant",
          created_by: "Dickerson",
          expiry: "Expires in 6 days",
        },
      ],
    };
  },
  methods: {
    add_button() {
      this.checkCard = true;
      this.componentCheck = false;
    },
    call_parent_card(val) {
      if (val == "Configure your door from scratch") {
        this.childComponentCheck = true;
        this.componentCheck = false;
        this.checkCard = false;
      }
    },
    call_parent1() {
      this.componentCheck = true;
      this.childComponentCheck = false;
      this.checkCard = false;
    },
  },
};
</script>
