<template>
  <div>
    <v-dialog
      v-model="taskStore.showDialogTaskFields"
      persistent
      min-width="400"
      max-width="600"
    >

      <!-- <template v-slot:default="{ props }">
        <v-btn
          color="primary"
          v-bind=props
        >
          Open Dialog
        </v-btn>
      </template> -->

      <v-card >
        <v-card-title class="text-h5">
          Edit task
        </v-card-title>

        <v-card-text>
          <v-text-field
            label="title"
            v-model="props.task.title"
          ></v-text-field>
          <v-text-field
            label="description"
            v-model="props.task.description"
          ></v-text-field>
        </v-card-text>

        <v-card-actions>
          <v-spacer></v-spacer>

          <v-btn
            color="primary-darken-1"
            variant="elevated"
            @click="taskStore.updateTask()"
          >Ok</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </div>
</template>

<script setup>
import { defineProps } from 'vue';
import  { useTaskStore } from '@/stores/task'

const taskStore = useTaskStore();

const props = defineProps({
  task: Object
})

</script>
