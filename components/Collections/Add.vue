<template>
    <!--add candidate details-->
  <TransitionRoot as="template" :show="open">
    <Dialog as="div" class="relative z-10" @close="open = false">
      <div class="fixed inset-0" />
      <div class="fixed inset-0 overflow-hidden">
        <div class="absolute inset-0 overflow-hidden">
          <div
            class="pointer-events-none fixed inset-y-0 right-0 flex max-w-full pl-10"
          >
            <TransitionChild
              as="template"
              enter="transform transition ease-in-out duration-500 sm:duration-700"
              enter-from="translate-x-full"
              enter-to="translate-x-0"
              leave="transform transition ease-in-out duration-500 sm:duration-700"
              leave-from="translate-x-0"
              leave-to="translate-x-full"
            >
              <DialogPanel class="pointer-events-auto w-screen max-w-md">
                <div
                  class="flex h-full flex-col overflow-y-scroll bg-white py-6 shadow-xl"
                >
                  <div class="px-4 sm:px-6">
                    <div class="flex items-start justify-between">
                      <DialogTitle
                        class="text-base font-semibold leading-6 text-gray-900"
                        >Candidate Details</DialogTitle
                      >
                      <div class="ml-3 flex h-7 items-center">
                        <button
                          type="button"
                          class="rounded-md bg-white text-gray-400 hover:text-gray-500 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2"
                          @click="open = false"
                        >
                          <span class="sr-only">Close panel</span>
                          <XMarkIcon class="h-6 w-6" aria-hidden="true" />
                        </button>
                      </div>
                    </div>
                  </div>

                  <div class="relative mt-6 flex-1 px-4 sm:px-6">
                    <div>
                      <label
                        for="name"
                        class="block text-sm font-medium leading-6 text-gray-900"
                        >Name</label
                      >
                      <input
                        type="text"
                        name="name"
                        id="name"
                        v-model="name"
                        class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
                      />
                    </div>
                    <div>
                      <label
                        for="Description"
                        class="block text-sm font-medium leading-6 text-gray-900"
                        >Description</label
                      >
                      <input
                        type="text"
                        name="Description"
                        id="Description"
                        v-model="description"
                        class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
                      />
                    </div>
                    <div>
                      <label
                        for="Type"
                        class="block text-sm font-medium leading-6 text-gray-900"
                        >Type</label
                      >
                      <input
                        type="text"
                        name="Type"
                        id="emaTypeil"
               
                        class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
                      />
                    </div>
                    <div>
                      <label
                        for="difficulty level"
                        class="block text-sm font-medium leading-6 text-gray-900"
                        >difficulty level</label
                      >
                      <input
                        type="text"
                        name="difficulty level"
                        id="edifficulty levelmail"
                        v-model="difficulty_level"
                        class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
                      />
                    </div>
                    <div>
                      <label
                        for="max_time_allowed"
                        class="block text-sm font-medium leading-6 text-gray-900"
                        >max_time_allowed</label
                      >
                      <input
                        type="number"
                        name="max_time_allowed"
                        id="max_time_allowed"
                        v-model="max_time_allowed"
                        class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
                      />
                    </div>
                    <div>
                      <label
                        for="due_date"
                        class="block text-sm font-medium leading-6 text-gray-900"
                        >due_date</label
                      >
                      <input
                        type="text"
                        name="due_date"
                        id="due_date"
                        v-model="formdata.due_date"
                        class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
                      />
                    </div>
                    <div>
                      <label
                        for="multiple_attempts_allowed"
                        class="block text-sm font-medium leading-6 text-gray-900"
                        >multiple_attempts_allowed</label
                      >
                      <input
                        type="number"
                        name="multiple_attempts_allowed"
                        id="multiple_attempts_allowed"
                        v-model="multiple_attempts_allowed"
                        class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
                      />
                    </div>
                    <div>
                      <label
                        for="text"
                        class="block text-sm font-medium leading-6 text-gray-900"
                        >status</label
                      >
                      <input
                        type="number"
                        name="text"
                        id="text"
                        v-model="status"
                        class="block w-full rounded-md border-0 py-1.5 text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 placeholder:text-gray-400 focus:ring-2 focus:ring-inset focus:ring-indigo-600 sm:text-sm sm:leading-6"
                      />
                    </div>
                    <!--cancel button-->
                    <div class="flex justify-center m-10">
                      <button
                        type="button"
                        @click="open = false"
                        class="rounded-full bg-indigo-600 px-2.5 py-1 text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600"
                      >
                        Cancel
                      </button>
                      <!--save button-->
                      <div @click="open = false">
                        <button
                          type="button"
                          @click="postData1()"
                          class="rounded-full bg-indigo-600 px-2.5 py-1 text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600"
                        >
                          save
                        </button>
                      </div>
                    </div>
                  </div>
                </div>
              </DialogPanel>
            </TransitionChild>
          </div>
        </div>
      </div>
    </Dialog>
  </TransitionRoot>
</template>
<script setup>
import { ref } from "vue";
import {
  Dialog,
  DialogPanel,
  DialogTitle,
  TransitionChild,
  TransitionRoot,
} from "@headlessui/vue";
import { XMarkIcon } from "@heroicons/vue/24/outline";
//define emits
const emits = defineEmits(["post-data"]);
const name=ref("")
const max_time_allowed=ref("")
const description=ref('')
const multiple_attempts_allowed=ref("")
const status=ref("")
//define props
const props = defineProps({
  open: { type: Boolean, default: false },
  formdata: { type: Object, default: () => [] },
});
const postData1 = async () => {
  open.value = false;
  let form = {
    name:name.value,
    type: "practice",
    max_time_allowed: max_time_allowed.value,
    due_date:"2023-04-09T08:27:54.944Z" ,
    difficulty_level: "Easy",
    description: description.value,
    questions: {},
    multiple_attempts_allowed: multiple_attempts_allowed.value,
    instructions: {},
    status: status.value,
    last_modified_date: "2023-04-09T08:27:54.944Z",
  };
  emits("post-data", form);
};
</script>
