<template>
      <v-row align="stretch">
        <v-col cols="1">
          <v-row align="stretch">
            <v-btn block :height="parentHeight">
              Long
            </v-btn>
          </v-row>
        </v-col>
        <v-col>
          <v-row>
            <v-btn block :height="0.25 * parentHeight">
              {{someText}}
            </v-btn>
            <v-btn block :height="0.25 * parentHeight">
              {{alsoSot}}
            </v-btn>
            <v-btn block :height="0.5 * parentHeight">
              {{exTernal}}
            </v-btn>
          </v-row>
        </v-col>
      </v-row>
</template>

<script>
export default {
  name: "Buttons",
  data(){
    return{
      parentHeight: 0,
      someText: "shiit",
      alsoSot: 0,
    }
  },
  props:{
    exTernal: String,
  },
  mounted(){
    this.parentHeight = this.$parent.$el.offsetHeight;
    this.someText = this.$parent.$el.localName;
    this.alsoSot=this.$parent.$el.offsetHeight;
  }
}
</script>

<style scoped>

</style>