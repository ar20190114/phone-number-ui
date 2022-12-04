<template>
  <v-container class=".o-input--num-display">
    <h1>電話番号を入力してください</h1>
    <h3>Please enter your phone number</h3>
    <h2 class="phone-number">電話番号： {{ number }}</h2>
    <div class="col-format">
      <v-row justify="space-between" class="text-center">
        <v-col>
          <v-btn
            variant="outlined"
            icon="mdi-numeric-1"
            @click="addNumber(String(1))"
          />
        </v-col>
        <v-col>
          <v-btn
            variant="outlined"
            icon="mdi-numeric-2"
            @click="addNumber(String(2))"
          />
        </v-col>
        <v-col>
          <v-btn
            variant="outlined"
            icon="mdi-numeric-3"
            @click="addNumber(String(3))"
          />
        </v-col>
      </v-row>
      <v-row justify="space-between" class="text-center">
        <v-col>
          <v-btn
            variant="outlined"
            icon="mdi-numeric-4"
            @click="addNumber(String(4))"
          />
        </v-col>
        <v-col>
          <v-btn
            variant="outlined"
            icon="mdi-numeric-5"
            @click="addNumber(String(5))"
          />
        </v-col>
        <v-col>
          <v-btn
            variant="outlined"
            icon="mdi-numeric-6"
            @click="addNumber(String(6))"
          />
        </v-col>
      </v-row>
      <v-row justify="space-between" class="text-center">
        <v-col>
          <v-btn
            variant="outlined"
            icon="mdi-numeric-7"
            @click="addNumber(String(7))"
          />
        </v-col>
        <v-col>
          <v-btn
            variant="outlined"
            icon="mdi-numeric-8"
            @click="addNumber(String(8))"
          />
        </v-col>
        <v-col>
          <v-btn
            variant="outlined"
            icon="mdi-numeric-9"
            @click="addNumber(String(9))"
          />
        </v-col>
      </v-row>
      <v-row justify="space-between" class="text-center">
        <v-col>
          <v-btn
            class="#keypad-delete"
            variant="outlined"
            icon="mdi-arrow-left-bold-box"
            @click="deleteNumber()"
          />
        </v-col>
        <v-col>
          <v-btn
            variant="outlined"
            icon="mdi-numeric-0"
            @click="addNumber(String(0))"
          />
        </v-col>
        <v-col>
          <v-btn
            class="#keypad-enter"
            variant="outlined"
            icon="mdi-arrow-left-bottom"
            :disabled="!doSubmit"
          />
        </v-col>
      </v-row>
    </div>
  </v-container>
</template>

<script setup lang="ts">
import { ref, watch } from "vue";

const number = ref("");
const doSubmit = ref(false);

function addNumber(pushNumber: string) {
  if (number.value.length <= 10) {
    number.value = number.value + pushNumber;
  }
}

function deleteNumber() {
  number.value = number.value.slice(0, -1);
}

watch(number, (number) => {
  if (number.length == 10 && number[0] == "0") {
    doSubmit.value = true;
  } else if (number.length == 11 && number[0] == "0" && number[2] == "0") {
    doSubmit.value = true;
  } else {
    doSubmit.value = false;
  }
});
</script>
<style scoped>
.col-format {
  width: 50%;
  margin: 0 auto;
  padding-top: 20px;
}

.phone-number {
  padding-top: 20px;
}
</style>
