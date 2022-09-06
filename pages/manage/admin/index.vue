/* eslint-disable */
<template>
  <div class="mr-12 ml-12">
    <Editor/>
  </div>
</template>
<style scoped>
.active-button{
  font-weight: 1000;
  font-size: 20px;
}
i{
  font-family: 'Courier New', Courier, monospace
}
</style>
<script>
import Editor from '../../../components/Editor.vue'
export default {
  components: {
    Editor
  },
  data: () => ({
    heading: 'H5',
    headingList: ['H5', 'H4', 'H3', 'H2', 'H1'],
    size: '12',
    sizeList: ['1', '2', '3', '4', '5', '6', '7', '8', '9', '10', '11', '12', '13', '14', '15', '16', '17', '18',
      '19', '20', '21', '22', '23', '24', '25', ' 26', '27', '28', '29', '30'],
    family: 'Verdana',
    familyList: ['Verdana', 'Arial', 'Tahoma', 'Serif', 'Times New Roman'],
    bold: false,
    italic: false,
    underline: false
  }),
  methods: {
    onHeading (type) {
      this.heading = type
    }
  }
}/**
<v-row
    dense>
      <v-col>
        <v-btn v-if="bold" @click="bold = !bold" class="active-button" text>
          B
        </v-btn>
        <v-btn v-else @click="bold = !bold" text>
          B
        </v-btn>
      </v-col>
      <v-col>
        <v-btn v-if="italic" @click="italic = !italic" class="active-button" text>
          <i>I</i>
        </v-btn>
        <v-btn v-else @click="italic = !italic" text>
          <i>I</i>
        </v-btn>
      </v-col>
      <v-col>
        <v-btn v-if="underline" @click="underline = !underline" class="active-button" text>
          <u>U</u>
        </v-btn>
        <v-btn v-else @click="underline = !underline" text>
          <u>U</u>
        </v-btn>
      </v-col>
      <v-col>
        <v-combobox
          v-model="heading"
          :items="headingList"
          hide-selected
          flat
          height="15"
          class="mt-3"
          dense
        />
      </v-col>
      <v-col>
        <v-btn text>
          Ordered List
        </v-btn>
      </v-col>
      <v-col>
        <v-btn text>
          <i class="mdi-format-list-bulleted" />
        </v-btn>
      </v-col>
      <v-col>
        <v-combobox
          v-model="family"
          :items="familyList"
          hide-selected
          flat
          height="15"
          class="mt-3"
          dense
        />
      </v-col>
      <v-col>
        <v-btn text>
          x<sup>2</sup>
        </v-btn>
      </v-col>
      <v-col>
        <v-btn text>
          x<sub>2</sub>
        </v-btn>
      </v-col>
      <v-col>
        <v-combobox
          v-model="size"
          :items="sizeList"
          hide-selected
          flat
          height="15"
          class="mt-3 ml-6"
          dense
        />
      </v-col>
      <v-col>
        <v-btn text>
          image
        </v-btn>
      </v-col>
      <v-col>
        <v-btn text>
          link
        </v-btn>
      </v-col>
    </v-row>
    <v-divider />
    <v-row>
      <v-textarea />
    </v-row> */
</script>
