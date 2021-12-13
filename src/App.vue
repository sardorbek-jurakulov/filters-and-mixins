<template>
    <div class="container">
        <div class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <h1>Filters & Mixins</h1>
                <!-- Exercise 1) -->
                <!-- Build a local Filter which reverses the Text it is applied on -->
                <h3>Name reverser</h3>
                <input type="text" name="userName" v-model.lazy="userName" placeholder="Your name here">
                
                <!-- Reversed version of your Name is: {{ userName | nameReverser }} -->
                

                <!-- <br><hr><br> -->
                <!-- Exercise 2 -->
                <!-- Build a global Filter which counts the length of a word and it appends it -->
                <!-- Like this: "Test" => Gets Filtered to => "Test (4)" -->
                
                <!-- Your Name info: {{ userName | stringLengthCounter }} -->


                <br><hr><br>
                <!-- Exercise 3 -->
                <!-- Do the same as in Exercises 1 & 2, now with Computed Properties -->
                <div v-if="userName != ''">
                  Reversed version of your Name is: {{ nameReverserComputed }}
                  <br><hr><br>
                  Your Name info: {{ stringLengthCounterComputed }}
                </div>

                <!-- Exercise 4 -->
                <!-- Share the Computed Property rebuilding Exercise 2 via a Mixin -->
            </div>
        </div>
    </div>
</template>

<script>
    export default {
      data() {
        return {
          userName: '',
        }
      },
      filters: {
        nameReverser(value) {
          return  value.split("").reverse().join("");
        }
      },
      computed: {
        nameReverserComputed() {
          return this.userName.split("").reverse().join("");
        },
        stringLengthCounterComputed() {
          return this.userName + " " + "(" + this.userName.length + ")";
        }
      }
    }
</script>

<style>
</style>
